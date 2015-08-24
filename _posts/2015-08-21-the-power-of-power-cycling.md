---
layout:     post
title:      The Power of Power Cycling
date:       2015-08-21
summary:    One of three easy steps in becoming a troubleshooting guru.
categories: troubleshooting programming
---


<p>
An electrical engineer, a mechanical engineer, and a software engineer are riding in a car on their way to a conference. The car’s brakes fail on a hill; but luckily the engineers are able to pull the car to the side without anyone getting hurt. </p>

<p>
The electrical engineer says: “The problem might be in the electrical system. I will start by checking the fuse box.”
</p>

<p>
The mechanical engineer says: “The problem might be in the hydraulics. l will start by checking the fluid levels”
</p>

<p>
The software engineer says: “Why don’t we all get out of the car and get back in and see if that fixes the problem”
</p>

![Happy emoticon](/images/2015-08-21-the-power-of-power-cycling/awesome.png){: style="height: 50px"}
![Happy emoticon](/images/2015-08-21-the-power-of-power-cycling/awesome.png){: style="height: 50px"}
![Happy emoticon](/images/2015-08-21-the-power-of-power-cycling/awesome.png){: style="height: 50px"}


---------------

The official terminology to describe turning stuff off and then back on is “power cycling”. As an engineer, systems will freeze on you in a non-reproducible manner all the time. If googling stack-overflow has not helped you, the only recourse is to power cycle. 17th century mathematician Blaise Pascal explains it best with his binary cost benefit analysis diagram on whether or not to believe in power cycling:

{:.center}
![4 quadrant diagram on expected value of power cycling](/images/2015-08-21-the-power-of-power-cycling/pascals_wager.png) <small>Pascal’s Power Cycling Wager</small>

<br>
Even though I learned to restart a frozen computer at a young age, it took me a long time to apply this philosophy to other areas of engineering.  Have you ever wondered what made engineers so good at fixing problems like bad wifi? Hundreds upon thousands of hours of fixing other unfathomably obscure problems have given them widely applicable tools for troubleshooting problems. Their first line of defense is Google, and the second is power cycling. This blog will get you, the reader, to a point where power cycling becomes a handy tool for dispatching intractable hardware and software problems. Luckily for you power cycling will work 99% of the time. Praise Jesus.

---------------

### Case Study 1

When a computer program freezes, I quit it and restart it. When my computer freezes, I turn it off and turn it back on. When my internet stops working, I turn my wifi router off and back on. I turn my network adapter off and back on. I set my DNS servers to Google. If they are already Google, I set them to OpenDNS. This fixes all problems except Comcast. Sometimes Comcast is the problem.

__Conjecture 1__: Power cycle your computer. Power cycle your computer programs. Power cycle your internets.


---------------


### Case Study 2
The first smartphone I owned was an iPhone 4S. One day the internet on it randomly stopped working, but I could still take and receive calls and text. I managed to make it a whole week before going into the AT&T store. By then I was positively FURIOUS. As I stormed into the store, an attendant standing with a tablet and an earpiece greeted me. His job was to triage people and guide them to the relevant areas of the store. While I meticulously described my problem to him he had already power cycled my phone and fixed my problem.

__Conjecture 2__: Power cycle your electronics.



---------------


### Case Study 3
The second smartphone I owned was an iPhone 5S. One day it hopped out of my pocket and the screen cracked. Instead of paying someone else to fix it, I went ahead and bought a repair kit from iCracked. It saved me 30 bucks and was a lot of fun. Everything worked after my 1 hour repair except my accelerometer. I tried power cycling my phone, as well as recalibrating my accelerometer through the compass app. After contacting iCracked support  they tell me:

>Hey,
>
>
>This is not a common issue since the accelerometer is protected behind multiple components. If you perform a hard reset which is done by holding down the power button and home button for about 45-60 seconds, not while connected to the computer since that will delete all of your data. The next tip is, if you are using iOS 7, to swipe up on the locked screen and ensure that the lock icon all the way to the right is black, as that is it in its off position. Thanks and let me know if these tips help!
>
>iCracked Support

The hard reset helped.

__Conjecture 3__: Power cycle your electronics. Harder.


---------------


### Case Study 4
One day I was debugging an error on Kestrel (a twitter open sourced message queue library). Workers were having trouble pulling jobs from a queue, which is a pretty annoying because what is the point of a messaging queue if it won’t message things. At a certain point I had enough and restarted the service and that fixed my problem.

__Conjecture 4__: Power cycle your services, your containers, and your servers


---------------


### Case Study 5
One day my python unit tests were breaking and I could not figure out why it was happening. About an hour in, I asked someone for help. They suggested I reinstall nose and that fixed my problem.

__Conjecture 5__: Power cycle your code (as well as other people's code)


---------------


### Case Study 6:
My Prius’ fan vent is operated by an electronic MODE button. This one time the fan vents got into a bad state. The forward blowing mode blew air at my feet, the feet vent mode blew air at my windscreen, my feet and the far left and far right front facing vents, the windscreen vent mode would only blow the windscreen and no mode would get the center front facing vents to work. I figured that there might be a combination of fans and/or flaps that were broken.  Actually all this probably will make more sense with a diagram.
<br>

{:.center}
![How my fan vents are broken](/images/2015-08-21-the-power-of-power-cycling/prius_vent_diagram.png){: style="border:1px solid gray"}<small>You can blow air at anything as long as it’s your feet.</small>


When I parked that night I made mental plans to go to a mechanic, but the next day when I started my car there was no longer a problem.

__Conjecture 6__: Power cycle your car.


---------------


There it is. I have told you six stories in order to persuade you to turn stuff off and turn it back on. You have leveled up your abilities to debug program, gadget, code, car, and dev-ops problems.

{:.center}
![Power cycle yo kids, power cycle yo wife](/images/2015-08-21-the-power-of-power-cycling/hide_yo_kids.png)

