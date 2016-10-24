---
layout: post
title: Data mining Heroes of the Storm replays
---

As I mentioned in a [previous post]({{ site.baseurl }}/battleground-balance-in-heroes-of-the-storm), I’ve recently been working on data mining and analyzing *Heroes of the Storm* replay files. I’ve got some posts coming in the next week or two covering some of my initial analysis, but I thought I’d take a few minutes and write about the process of data mining the files themselves, in case anyone else is interested.

First, you’ll need to go and get a hold of Blizzard’s [heroprotocol](https://github.com/Blizzard/heroprotocol) library, which is written in Python. They update this library every time they release a new build of *Heroes of the Storm*. It has some basic information about what kind of information is contained in the replay files, but one thing you’ll notice, once you start digging into some replay files, is that the documentation is quite sparse. 

That’s unfortunate, because there’s a *ton* of information in these replay files. They contain information such as the interface settings for every player, which hero they chose, what battleground the game was played on, in which game mode, and so on. They also have event information such as when minions or heroes are killed, when heroes selected a new talent, and coordinate information of just about anything that happened in the game. Since the documentation didn’t give many details at all about what was in the files, what I ended up doing was opening up some replays and just digging around for a while. I was trying to see what kinds of things were in there, and how they fit together.

So, let's walk through an example. To get started, what you need to do is open a replay file and turn it into a usable Python object. Replays in *Heroes* are in the mpq format, so we need to use the mpq library (included with heroprotocol).

```python
from mpq import MPQArchive
mpq = MPQArchive('your_replay.StormReplay')
```

You're still going to need the heroprotocol library itself to get something meaningful from the replay. You'll want to use the protocol with the same build number as the replay you're examining (e.g. protocol47133 if your replay is from build 47133). If these don't match, sometimes the protocol won't be able to read the replay properly. It appears that in most cases you can use just about any protocol to read the replay's header information (which contains the replay's build number), so we'll use that to help us load the correct protocol without having to know what build our replay was from beforehand.  At the time of this writing, the latest *Heroes* build is 47133, so we're just going to use that.

```python
from heroprotocol import protocol47133 as protocol
```

Let's get the replay's header information and the build number.

```python
header = protocol.decode_replay_header(mpq.header['user_data_header']['content'])
build_number = header['m_version']['m_baseBuild']
```

Now make sure that you're loading in the correct protocol to read the rest of the replay data.

```python
from importlib import import_module
module_name = 'heroprotocol.protocol{}'.format(build_number)
protocol = import_module(module_name)
```

If we wanted to know who the players were and which hero they selected, we can now do that as follows:

```python
details = protocol.decode_replay_details(mpq.read_file('replay.details'))
player_list = details['m_playerList']

for player in player_list:
  name = player['m_name']
  hero = player['m_hero']
  result = player['m_result']  # this is 1 (victory) or 0 (defeat)
  ...
```

What if we wanted to get a look at information on units and statistics? A lot of that is stored away in what heroprotocol calls *tracker events*. They can be acquired in a similar way to the *detail* we grabbed above:

```python
tracker_events = protocol.decode_replay_tracker_events(
  mpq.read_file('replay.tracker.events')
)
```

This returns a generator object, so you can loop through it and take a look at the different kinds of data found in there. One of the things I was interested in researching was the influence that hero talent choices have on the game. We can get that information from the 'EndOfGameTalentChoices' event, which is a type of 'NNet.Replay.Tracker.SStatGameEvent' event.

```python
for tracker_event in tracker_events:
  if tracker_event['_event'] == 'NNet.Replay.Tracker.SStatGameEvent':
    if tracker_event['m_eventName'] == 'EndOfGameTalentChoices':
      talents = tracker_event['m_stringData']
```

Of course, you'll likely still have to process the result in some way, depending on what your end goal is. One issue that I ran into with a different type of event dealing with talent selection is that you had to cross-reference ID numbers with the player IDs (obtained in one of the earlier steps above), but in some replays these IDs didn't always match up. I'm still not sure why this is the case, but I suspect it has something to do with the presence of Observers in the replays I was parsing.

Anyway, this should give you a good idea of where to start with *Heroes* replay files! My [first pass](https://github.com/tommyhall/hotsparser) at a replay parser is up on Github now if you’d like to check it out.
