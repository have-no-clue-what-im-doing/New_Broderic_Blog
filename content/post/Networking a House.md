+++
title = "Networking My Parents' House"
description = ""
tags = [
    "networking", "unifi", "ubiquiti",
]
date = "2022-06-01"

+++

So before I began this project, it was clear that the network closet was a mess:

![Network closet is a huge mess.](/networking/one.jpg)

Wires and cables everywhere. The patch panel is unorganized. There's so much crap everywhere you can't even tell what's going on. I do want to say that most of this was not me. This was the previous owner. When we moved into the house the previous owner had already wired every inch of it with cat5e and coaxial. When installing Unifi AP's around the house I traced them down to here and connected them all to a switch. The reason you don't see a router or modem is because those are in a totally different room. For whatever reason the demarc doesn't lead to the network closet. I'm sure there's a way I can trace it to the network closet, but then I'd have to invest in a multimeter, which I don't want to do just to trace coaxial. 

The house was originally wired in around the year 2000 and I am so thankful they actually wired it with cat5e. Would cost a fortune to have someone come in and rewire everything. Like there's no crawl space or attic that you can lead the wires through. It's all hard wired in. Half the crap on the wall is completely useless. That white mounted container thing is like some ancient security system.

There was even a 66 block in use at one point:

![66 block](/networking/two.jpg)

Just a bunch of early 2000s crap that no one had any use for anymore. At this point the house had 3 AP's and 1 AP in the pool house / AirBNB. The tiny 8 port switch was getting full. My parents had recently switched to YoutubeTV which requires large amounts of bandwidth to stream reliably. I knew the best thing to do would be to have all the TV's hardwired instead of relying on Wifi. Wifi is honestly kind of annoying, especially with multiple AP's. You have to make sure all the AP's are on different channels and that their gain isn't too low or high. Also placement and direction are important too. It's really hard to optimize everything. 

Originally we were using ancient Unifi AP's from like 2012 that only used the 2.4 GHz frequency. As far as channels go we were at our limit. With 5 GHz you have 24 non-overlapping channels. And when we upgraded to the Unifi 6 AP's they made a huge difference, but the original spots I had chosen to place the AP's wasn't the most optimal. If I could connect every single Ethernet port to a switch I could easily go through a trial and error and find the most optimal placement for the AP's. 

To begin I had to convert a bunch of RJ-11's to RJ-45. Most rooms only had RJ-11 keystones put in place. Had to change the keystone out for an RJ-45. Once that was complete I then had to trace the cable all the way down to the network closet and then labeled them using sticky notes. 

![Labeling Ethernet with sticky notes.](/networking/three.jpg)

Once that was complete I then was able to start punching down the wires onto the patch panel. One I mistake I made here was not getting a patch panel with a hinge on it. This made it a little more awkward and harder to access the patch panel. I had to attach it upside down on the wall mount while it was resting on a shelf. If I had just gotten a patch panel with a hinge I could've attached the patch panel to the wall mount and then opened it at an angle that would've made it easy to punch down the wires. 

![Attaching Ethernet to patch panel.](/networking/four.jpg)

![Attaching Ethernet to patch panel.](/networking/five.jpg)

Once that was complete I then attached both the patch panel and switch to the wall mount:

![Attaching Ethernet to patch panel.](/networking/six.jpg)

All that was left after that was the Unifi PoE injectors and a Raspberry Pi for the AP controller:

![Attaching Ethernet to patch panel.](/networking/seven.jpg)

So, obviously, there is a lot wrong with this picture. First, I'm not even using a surge protector, just a power strip. One lightning strike could take out everything in that picture. Another problem is that the Ethernet connecting from the patch panel to the switch is way too long. I chose 4 feet because I was worried it could be too short. Much better for it to be too long than too short. PoE injectors need to be hung up along with the Pi as well. Cable management also needs some work too. Overall though, everything is working fine. Top priority is to definitely switch out that power strip for a surge protector. 

Here's a before and after:

{{< rawhtml >}} 

<video width=100% controls >
    <source src="/networking/videoone.mp4" type="video/mp4">
    Your browser does not support the video tag.  
</video>

{{< /rawhtml >}}


{{< rawhtml >}} 

<video width=100% controls >
    <source src="/networking/videotwo.mp4" type="video/mp4">
    Your browser does not support the video tag.  
</video>

{{< /rawhtml >}}

Lots of work still be to done. I have yet to take advantage of all the connected etherenet ports. Still haven't tried optimizing the position of the AP's. The reality is that after messing with the settings more, the current WiFi situation is good enough. The biggest issue is with the roaming. Which is when a device is moved around the house but still communicates with its original AP instead an AP that is now closer. I'll definitely make a post detailing WiFi optimization with diagrams and specific settings. For now, I am content with this set up. 
