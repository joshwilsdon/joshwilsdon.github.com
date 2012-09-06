---
layout: post
title: Wheels or Tracks?
summary: Should my first robot use wheels or tracks?
tags: [robots, bob]
---

<div class="floatyimg"><img src="/images/mars-rover.jpg" title="NASA&#39;s Mars Rover" alt="NASA&#39;s Mars Rover" /></div>
I've still not ordered some of the parts I need to get started building the body for my robot.  The main reason I've not yet ordered the parts is that I still have a few design decisions to make first.  One of the bigger design decisions outstanding is what sort of propulsion system this robot will be using.

My first thought was to make it use tracks like a tank.  I thought this would give it the most mobility over the widest range of terrain and be simpler to build.  Plus, tanks are way cool!  After some reading though, it seems that may not be the best choice.  Tracks are not simpler to build (more parts!) and there are a number of other factors which I had not considered.

It turns out that tracks do in fact have better mobility over many types of terrain.  This is because they spread the weight of the vehicle over a larger contact area and small obstacles are no problem because while some parts of the track may be off the ground, the remaining portion still in contact with the ground continues to propel the vehicle forward.  This larger contact area however also has a number of drawbacks.

One big drawback of a track-based design is the fact that the additional contact with the ground also slows your vehicle down.  Another drawback, probably more critical for some applications, is that the track is a single point of failure.  If your vehicle has multiple wheels, it's possible for it to keep going if one fails.  If a track fails you can only go in circles.  This fault-tolerance is one of the reasons that both [NASA](http://marsrover.nasa.gov/home/index.html) and the [ESA](http://www.esa.int/esaMI/Aurora/SEM1NVZKQAD_0.html) are using wheel-based designs for their rovers.

When I first thought of a wheeled design, I was thinking 4 wheels.  I might even have chosen tracks over a 4-wheel design.  But it seems 6 or 8 wheel designs give you many of the advantages of tracks while mitigating the drawbacks.  A 6-wheeled vehicle can still go relatively fast since the contact area is lower than that of a pair of tracks, but it can also keep multiple wheels in contact with the ground when overcoming obstacles.  Especially when coupled with a decent suspension system.

At this point then, I've pretty much decided to build a 6 wheel robot.  This seems to be the best compromise between all of the factors mentioned above.  I think I'll order 2 motors for now in order to test the size, torque, and speed.  This will also let me build and test the control circuitry.  Once I have the motors in hand and have done some testing, I'll begin the next stage which is the design of the chassis and possibly the suspension system.  Then I can start building.
