---
layout: post
title: VR cont'd - design considerations
---

Since VR has come so far in such a short time, there’s still a lot that we just don’t know about design “best practices”. For example, in my 
[last post](https://tommyhall.ca/experiences-in-virtual-reality/) I told a story of how one of our lab members accidentally walked
into a tree in the virtual environment, and spilled some coffee in the real world while bracing himself for the impact (that obviously
never came). 

So, what *should* have happened in the VR environment when he walked into that tree? In that case, he was sitting in a chair 
and moving himself around the virtual environment with an Xbox controller. But what if he was using the PlayStation VR, walking around his
living room, and he’d walked into a virtual object? Should we stop him in the VR environment, or let him keep walking through it? What if 
he was standing next to a virtual wall and leaned his head into it?

In our traffic safety training game, which was our first VR system to utilize the Oculus Rift, by far the biggest issue we ran into was 
motion sickness.

There are a number of reasons that motion sickness is a problem with VR headsets, and I’m not going to get into all of them here. The two 
that we ran into with our training game were having too low of a frame rate, and “moving without moving”.

### Refresh rate

Again, without getting into the details, it's considered a best practice for your VR application to run at a minimum of 90fps. The refresh 
rate on the Oculus Rift DK2 is 75Hz, and thus 75fps became our target. Before the Rift arrived at our lab, our game was running at 60fps. 
When we first started to run it on the Rift, we found we weren’t getting close to our target. The increased FOV of the Rift meant that our 
engine was now rendering more on the display than was visible before, so we were often struggling to even hit the 60fps that we were achieving
before.

This meant that we had cut back on our graphics output. We went back and optimized our 3D models again, removed details from our 
virtual environment entirely (our trees and shrubs were especially resource-intensive to draw), and stepped up our 
[level of detail](https://en.wikipedia.org/wiki/Level_of_detail) game.

In short, what this meant is that we had to step down our graphical fidelity to make sure that our system ran at the recommended refresh
rate. At least for the time being, VR applications may just have to live with having less impressive graphics. I had my doubts that the 
PlayStation 4 would have enough power to manage a high enough frame rate for PlayStation VR applications, but so far it seems to be doing
alright in that regard. In fact, Sony is [refusing to certify](http://www.polygon.com/2016/3/17/11256142/sony-framerate-60fps-vr-certification) games for the 
PlayStation VR if they drop below 60fps at all.

### Moving without moving

The other significant issue we ran into was “moving without moving”, or when your digital avatar moves around the environment while 
you’re sitting still in your chair (or on the couch). In our training game, whenever the user made a mistake in crossing the street 
(such as failing to look both ways before beginning to cross, stepping into the street too close to an oncoming car, etc.), they would 
be stopped, and shown a replay of what they’d just done wrong, and what they could do to fix the problem.

This system worked well when the users were sitting in front of a computer monitor, but with the Oculus Rift it became a motion 
sickness nightmare. When the replay started, their perspective was being shifted around between replay angles, and it became extremely 
disorienting. I often couldn’t sit through more than a couple of replays with the Oculus without having to take an extended break.

Our solution to this problem was actually fairly simple and very effective. When the user was wearing the Oculus Rift, instead of 
having their perspective shift along with the replay, a screen would appear in the middle of the street in front of them, with the 
replay projected onto it. It looked very much like a drive-in movie theatre (if anyone remembers those anymore).
<br/>
<br/>
<br/>
These are just two examples of design considerations in VR development that can significantly improve the experience of your VR application.
I may write more about VR development in the future, because this is such an exciting time to be (virtually) alive! It will be 
fascinating to see how designing for VR headsets evolves over the coming months and years.
