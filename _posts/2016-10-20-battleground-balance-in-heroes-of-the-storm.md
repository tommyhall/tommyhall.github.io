---
layout: post
title: Battleground balance in Heroes of the Storm
---

Over the last year I’ve been playing a lot of Blizzard’s *Heroes of the Storm*. Like other [MOBA](https://en.wikipedia.org/wiki/Multiplayer_online_battle_arena)-style games (such as *League of Legends* and *Dota 2*), *Heroes* is a game with a relatively simple concept (two teams of five players, controlling single characters, attempt to destroy the opposing team’s base) disguising a surprising depth of strategy.

One of the obvious sources of strategic depth (as in other MOBA titles) is in which heroes each player selects to make up their team, each with different strengths, weaknesses, and synergies. More unique to *Heroes*, however, is how each battleground has a fundamentally different, and powerful, objective of its own (such as recruiting a pirate to bombard the enemy’s structures, or allowing an allied hero to transform into a gigantic plant-monster).

In my next series of posts, I’ll be diving into some of the differences in these battlegrounds, and particularly different ways of assessing how balanced they are. This is an especially interesting time to look into the game’s balance, as Blizzard has been adding new content at a *rapid* pace. In just over a month, they’ve added two new battlegrounds, a new game mode, and new heroes added to the roster every couple of weeks.

Just as an appetizer before my longer posts in the coming weeks (pending my completion of some data mining of *Heroes* replay files), I wanted to look into a complaint that a friend had about one of the new battlegrounds: Braxis Holdout. He felt that in the Quick Match game mode (where every player selects their hero before knowing who the opponent heroes are, what battleground will be played, or even which heroes their teammates selected), it was possible to be much more outmatched based on teammate/enemy hero selections than on other battlegrounds. If true, this imbalance would be especially frustrating since the factors creating it cannot be foreseen and countered.

To analyze this complaint, I obtained hero win rate statistics for each battleground from [HOTS Logs](http://www.hotslogs.com) with the following features:

* Games were played in the Quick Match game mode
* Games were played in the previous 7 days of *Heroes of the Storm* build 20.6.47133

I looked at games involving players of all skill levels, as well as only players at the Gold skill level (approximately the skill level of my friend, so games similar to what he'd experienced). For more information on how skill levels are calculated on HOTS Logs, click [here](http://www.hotslogs.com/Info/MMRInformation). These data sets represented thousands of games.

I wanted to look at the distribution of hero win rates across each of the battlegrounds. In perfectly ideal circumstances (a perfectly balanced game), all heroes would have a win rate of right around 50%. So, when we look at how the hero win rates are actually distributed, what does it look like? First, I looked at the data from players of all skill levels, and created box plots for each battleground, with strip plots layered on top (with a bit of jitter added along the x-axis for easier visualization).

![Box and strip plot, All skills levels, Quickmatch]({{ site.baseurl }}/images/all_box_and_strip.png)

At first glance, these box plots do seem to have a fairly high level of agreement with one another. The inter-quartile ranges are all quite similar, stretching from win rates of a little over 45% to a little under 55%. There are some differences in the variability of these battlegrounds, but they don’t appear to be too drastic.

What happens if we only look at players at the Gold skill level?

![Box and strip plot, Gold skill level, Quickmatch]({{ site.baseurl }}/images/gold_box_and_strip.png)

Now we can see a bit more of a difference in the battlegrounds! Braxis Holdout and Towers of Doom have nearly an identical mean win rate, but the Braxis Holdout box itself is quite a bit larger, indicating that the win rates have less agreement with one another. Overall, Towers of Doom and Cursed Hollow appear to have a little bit less variability than the others, with the other four having a little more variability.

(Interestingly, the mean win rate for BoE is lower than the other battlegrounds. Presumably, this is due to Gold players on BoE performing differently against players of other skill levels, compared to the other battlegrounds. While Blizzard tries to match players of a similar skill level, players of differing skill levels do still get matched together at times.)

If we look at a density plot of this same data, we get another look at what's happening.

![Density plot, Gold skill level, Quickmatch]({{ site.baseurl }}/images/gold_density.png)

Again, Towers of Doom and Cursed Hollow appear to be quite nicely distributed, with most win rates around 50% and dropping off fairly quickly on either side of that mark. We can see that Braxis Holdout has relatively less agreement around the 50% win rate, with a wider distribution of win rates overall.

So, does Braxis Holdout appear to be more unbalanced than the other battlegrounds? Looking at the Gold skill level, there does seem to be a higher number of heroes performing poorly, especially compared to Towers of Doom and Cursed Hollow. However, part of this could be an artifact of Braxis Holdout being a new battleground, and the metagame not having quite settled yet.

I’ll be adding more posts on battleground and game balancing in *Heroes of the Storm* over the coming weeks.
