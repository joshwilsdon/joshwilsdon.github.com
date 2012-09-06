---
layout: post
title: Bob's Brain
summary: Bob is getting smarter!
tags: [robots, bob]
---

I've made more progress on Bob.  It's taken a lot more work to get to this point than I expected, but I've learned a lot.  Here's a really blurry picture of what he looks like right now:

![Bob earlier today](/images/bob_as_of_20100426.jpg)

In that picture you can see 3 new components that weren't there in the last update.  The one on the lower right is the Ardweeny.  This is what it looks like close up:

![Bob's Brain](/images/bobs_brain.jpg)

That's basically Bob's Brain.  It came as a package of parts that I had to solder together.  It was pretty straightforward, though I would have liked to make a neater job of it and get the microcontroller closer to the PCB.  Next time...

After I put the Ardweeny together, I needed to power it.  When I have it connected to my computer via USB it gets power from the computer, but I don't want to leave it connected to the computer all the time.  The 6 AA batteries I plan to use can't be connected directly to the Ardweeny though since their voltage adds up to significantly more than the 5.0 volts that the Ardweeny wants.  In order to resolve this issue I needed to build a voltage regulator circuit.  I built mine based on the second last schematic in [this Sparkfun tutorial](http://www.sparkfun.com/commerce/tutorial_info.php?tutorials_id=57).  It seems to work pretty well so far, though I do want to modify it to have a 6v output as well.  This is approximately what it looks like:

![Bob's Power Supply](/images/bob_powersupply_rev_1.jpg)

except brighter.  You can also see it in the first picture in this post, on the center-right.

After building the controller and power boards I was able to power up Bob's Ardweeny and make it blink some LEDs, so I knew it worked.  Blinking LEDs is great, but I think Bob wants to be able to do more than that so my next step was to hook up some pins and test out the motor controller.  The controller board as I mentioned in [my last post](/2010/04/20/introducing-bob) is a TB6612FNG based board.  Here's a close up with all the headers soldered on and wires connected:

![Bob's Motor Controller](/images/bobs_motor_controller.jpg)

I've now got that board connected to the Ardweeny and done some initial testing.  At this point Bob can:

 * Spin his front wheels clockwise or counterclockwise (independently)
 * Vary the speed of his front wheels
 * Blink his LED
 * Be powered via battery, wall-wart adaptor or USB

But he doesn't actually go anywhere by himself yet.  Nor can he stand up, or speak Japanese (sorry kids).

Building the control mechanisms and other related pieces took longer than I expected so far but I think I've made pretty good progress.  I did however run across a couple more issues though that I'll need to resolve:

 * The TB6612FNG requires 7 pins to control and the Ardweeny's only got 14 total.  I plan to solve this using some 74HC595 shift registers (already ordered) to get some extra I/O pins.
 * The motors seem to work best with 6v but I'm currently using the 5v regulator circuit I built.  I plan to build a new improved power supply which will have both 5v and 6v outputs and hopefully current protection as well.
 * The motor mounts don't seem as stable vertically as I had hoped.  I'm still thinking about this one.  Hopefully I can find a solution.

Otherwise, my plan was to get the first 2 motors controlled first so I could tell if this motor controller, Ardweeny and motor combination would work for me and it seems it will.  So I've ordered the other 2 motors and a second motor controller.  Once I get these and deal with the other issues listed above, Hopefully Bob will be mobile!

Once he's able to actually move, I need to setup the servo and PING))) sensor.  At that point I think the hardware portion of the project will be complete (for now) and I'm going to have to move on to writing and debugging his software.

After that?  Who knows!
