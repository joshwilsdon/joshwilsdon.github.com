---
layout: post
title: Bob's In Control
summary: Bob can now move his motors
tags: [robots, bob]
---

<div class="floatyimg"><img src="/images/bob_asof_20100609.jpg" title="Bob as of 2010-06-09" alt="Bob as of 2010-06-09" /></div>
I made lots of progress on Bob finally in the past week!

The power supply that I wrote briefly about in [my last post](/2010/06/02/micro-bob-update) has been working pretty well so far.  I've been testing both with a 9v wall-wart power supply and with 6 NiMH  1.2v batteries.  In both cases it has done what I needed.

I did a lot more testing and prototyping and then I built a working motor controller.  It's pretty ghetto looking, but it is now working!  It is able to control all 4 motors independently.  There are a number of things I would do differently next time, so I guess it was good experience.  I especially think it will be worth my time to get setup to make custom PCBs instead of green-wiring the whole thing on a prototype board.  Anyway, this is what the board looks like now:

<div class="blockimg"><img src="/images/bobs_motor_controller_v2_back.jpg" title="Motor controller view from back" alt="Motor controller view from back" /><img src="/images/bobs_motor_controller_v2_side.jpg" title="Motor controller side view" alt="Motor controller side view" /></div>

So put together with the frame, the power supply, the battery pack and the Ardweeny, Bob now looks like this:

![Bob from the top](/images/bob_topview_20100609.jpg)

and more importantly, it's possible to actually program him now!

The first program I wrote simply flashes the LEDs on his motor controller and then sets all 4 motors to go at about 50% speed.  When I first got all the motors spinning using my controller (this was when I just had the parts sitting on my desk -- I hadn't mounted them to the frame yet), I was pretty excited!  Unfortunately, once I got everything all mounted together though I had a problem.  Only 3 of Bob's motors were moving!

On further inspection, it turned out that one of the connectors on the back of the motor had broken off.  These are extremely tiny and fragile.  In trying to fix this I got the wires reconnected, but ended up making a bit of a mess of it.  The long and short of it is that the motor sort of works now, but it spins the opposite way that I tell it to and I'm not entirely sure that it's going to have as much power as the others.  One tiny washer seems to have fallen out and I couldn't get it back in place.  I might end up replacing it eventually but for now I'll compensate for it in software.  I've also got to see if I can think up some sort of protection for the other motors so their connectors don't also get broken.

Anyway, for the next while I'll probably be focusing on getting the software working how I want it to.  Once I get the software written to let me do things like forward, reverse, turn left and turn right, then I'll hook up the wheels and start running some more tests with him actually going somewhere.  I hope to take a video of Bob's "first steps" when that happens.  Stay tuned!

After moving is taken care of, I'm still planning to:

 * mount the boards a little more solidly to the frame
 * connect and write code for the servo
 * connect and write code for the [PING)))](http://www.parallax.com/tabid/768/ProductID/92/Default.aspx) sensor
 * possibly add some bottom and top protection to the frame
 * have Bob detect and avoid obstacles

Other things I'm still considering adding Xbee wireless for remote commands, but I'm not sure I'll even have enough pins left for that without some serious juggling.  I think pretty quickly I'm going to run up to some limits with Bob that are going to require more and more work to get around.  I could use more shift registers and one or more [TLC5940 chips](http://www.arduino.cc/playground/Learning/TLC5940) to work around the pin shortage for example, but that would require rebuilding a lot of the components I have already built and it seems I'd be better off just working on the next robot at that point.  So I plan to push the existing hardware as far as I can, and try to get him to do some interesting things in software, but I don't think I'll add too much more hardware to him at this point.  I'm even debating whether it's even worth it to replace his gimped motor.

That's it for this week!  Lots of other exciting (non-Bob) stuff going on that I hope to be able to write about eventually.
