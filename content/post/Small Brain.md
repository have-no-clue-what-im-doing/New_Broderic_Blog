+++
title = "Small Brain Moment"
description = ""
tags = [
    "networking", "ONT", "small brain", "PDU"
]
date = "2024-07-24"

+++

So I recently had fiber installed for our house. I have symmetric speeds now of 400 down and 400 up! Everything is great, except for one little mistake I made. With this new fiber installation, the ISP needed to install an ONT, and originally I was hoping they could possibly give me some kind of rack mountable ONT, but yeah, they don't give that to residential customers. So the plan was to mount it to the wall behind the network rack. And when they asked me where exactly I wanted it mounted, I didn't really think much of it, and said to put it right next to the power outlet. 

![ONT not connected to the PDU](/small_brain/small_brain2.jpeg)

You see what the issue is though? It shouldn't be directly plugged into the power outlet, it should plugged into my PDU, which is connected to my UPS. This set up is straight up stupid. 

![Small Brain](/small_brain/small_brain1.jpeg)

And yeah I can't really just move the power cord over and plug it into the PDU. They literally gave me the smallest power cord in existence. So I'm going to have to remount this thing closer to where the PDU is. Really wish I could've just gotten a rack mounted ONT :(