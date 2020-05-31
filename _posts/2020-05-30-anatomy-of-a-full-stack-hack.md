---
layout:     post
title:      A Full Stack Hack
date:       2020-05-30
summary:    My favorite hackathon project, and how to solve diversity issues in a single sitting.
categories: startups programming
---

>This is a 2015 blog post I wrote while I worked for Shopkick, but never really published because Shopkick didn’t have a blog.[^brand]

I’m going to present one of my favorite company hackathon projects. One where:

1. Nobody lost any sleep over it (product complet in 10 hours)
1. Was tangentially (but not too) related to the company hosting the hackathon
1. Really really really fun to build
1. Pulled participation from non-engineers

-----
In attractions, festivals, and tourist spots the lines typically snake out of the women’s bathroom; however, this was the headline coming out of Apple’s 2015 WWDC developer conference.
_“WWDC Bathroom Lines Summarizes Tech's Gender Problem”_

![WWDC 2015 Bathroom Line](/images/2020-05-30-anatomy-of-a-full-stack-hack/WWDC_2015.jpg)
<small>(Photo Credit Ben Bajarin, Twitter, @BenBajarin)</small>

Tech's gender inequality problem: **men need to wait in a line for the bathroom.**[^sarcasm]

-----

At Shopkick, the women’s bathroom had 3 stalls, and the men’s 2 stalls and 1 urinal. As an under-privileged (over-represented) male, I frequently found myself checking on the stalls only to find them all occupied. This is the story of how I solved a major gender diversity pain point plaguing the tech world in a single hackathon. [^webcam]

{:.center}
![ShopBeacon](/images/2020-05-30-anatomy-of-a-full-stack-hack/shopbeacon.jpg)

These are Shopkick’s bluetooth low energy beacons/ibeacons. You peel a 3M sticker off the back of them and stick them onto a wall. They will broadcast a unique ID as well as a battery level for 5 years, which can be useful to trigger location-based events on your phone when you detect them. Since 2013, Android Phones and iPhones have all adopted this technology. Shopkick’s deployment of beacons in partner physical retail stores let their customers see location specific information in the app, trigger loyalty rewards and other interactions.

We opened up some beacons and wired 2 spare pins on the beacon’s chip with mechanical push switch. A minor code edit was made to the beacon firmware so that when the pins were shorted, the beacon would start broadcasting a battery level of 0.


{:.center}
![Push Switch](/images/2020-05-30-anatomy-of-a-full-stack-hack/switch.jpg){: style="height: 150px"}

We then jerry rigged all 5 of the stalls with beacons and switches. When the stall bolt is in the locked position, it closes the switch.

{:.center}
![Bathroom Stall Lock](/images/2020-05-30-anatomy-of-a-full-stack-hack/lock_mechanism.jpg){: style="height: 400px"} ![Shopbeacon Mounted](/images/2020-05-30-anatomy-of-a-full-stack-hack/shopbeacon_mounted.jpg){: style="height: 400px"}

An old macbook in our supply closet, which we inexplicably decided to put arch linux on [^arch], picked up the Bluetooth Packets and interpreted whether or not a stall was empty based on broadcast battery levels. The result was fed via USB serial to an Arduino to drive addressable Adafruit LEDs which indicated occupancy outside of the bathroom.

{:.center}
![Bathroom Stall Lock](/images/2020-05-30-anatomy-of-a-full-stack-hack/led_indicators.jpg){: style="height: 400px"}

Status updates are also passed via HTTP to a website <a>bathroom.shopkick.com</a> (no longer availible). [^shitkick]

{:.center}
![Bathroom Stall Lock](/images/2020-05-30-anatomy-of-a-full-stack-hack/website.jpg){: style="height: 300px"}


We logged stall occupancy rates in a Postgres database and presented the most interesting stats at some point during a company all-hands.

Some people had reservations about the whole hack but a wise man once said “with great technology comes great privacy violations” and the matter was settled once and for all.[^zuck]

I was also suprised at how many complaints we got when the networking stack on our frankenstein-arch-linux-macbook server occasionally failed. People actually liked the occupancy sensors...

-----

Thanks to the engineering efforts of Asher, Jeremy, Nandan, and graphics design from Sunni and Taylor.

-----

[^brand]: And because this post sacrifices all professionalism for entertainment value.
[^sarcasm]: All politically incorrect statements in this blog are sarcastic and purely for entertainment value.
[^arch]: Ubuntu would have been fine for this project. Our engineers wanted to configure Arch Linux from the ground-up and ended up playing a lite version of [linux speed run](https://rachelbythebay.com/w/2020/04/11/pengrun/).
[^shitkick]: Shopkick also owned a questionable collection of anti-troll urls like myshitkick.com which we also gleefully redirected.
[^zuck]: Mark Zuckerberg, probably

[^webcam]: The web-cam was invented in 1991 when a couple of engineers were too lazy to check if there was coffee left in their coffee pot.
