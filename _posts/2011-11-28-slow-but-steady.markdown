---
layout: post
title: Slow but Steady
summary: making progress on the RepRap
tags: [reprap]
---

It's been a long time since my last post already. It seems like I'm always making the same excuse that I've been busy at work, but you never run out of things that need to be done with complex software. Despite the fact that I've spent most of my time working, I have found some time to make forward progress on my [RepRap](/reprap).  As you can see from the menu, I've also added a [RepRap page](/reprap) for people who only want to look at RepRap posts and not the rest of my ramblings.

At this point I've completed the mounting of the steppers for all axes. You can see what it looked like after I completed that here:

  ![My RepRap with the axes complete](/images/axes-complete.jpg)

an astute observer will see that there are 2 steppers that control the z-axis, these will be run in parallel. Then there is one stepper for each of the x and y axis.  These are belt driven and move the extruder and build platform respectively.

Here's a close-up of the stepper that drives the x-axis:

  ![x-axis stepper](/images/x-stepper-mounted.jpg)

once I got all the axis put together, I moved on to the extruder + hot-end.

It is really overwhelming to look at the available information on hot-ends and extruders.  There are so many variations and combinations that I really didn't know what to do.  So I ended up just basically picking some parts, reading through a few things and putting them together.  Hopefully this works!  The hot end is basically going to be a block of aluminum screwed onto a brass insert which itself is screwed into a PTFE (teflon) barrel.  I drilled the PTFE by hand holding the drill bit in my hand and turning the part and the bit opposite directions.  I was able to get much more control this way as I have no drill press nor even an accurate drill.  I then drilled two holes in the sides so that it can be attached to the extruder, it looks like this:

  ![PTFE barrel with brass insert](/images/ptfe-barrel.jpg)

This piece goes into the extruder which was quite a complicated bit to put together. This is what it looked like part-way through construction:

  ![extruder frame](/images/extruder-frame.jpg)

And this is what it looks like now with the PFTE barrel also attached:

  ![extruder view1](/images/extruder-view1.jpg)

and:

  ![extruder view2](/images/extruder-view2.jpg)

I've manually pushed some filament into the extruder and rotated the gears and it pulled through.  Hopefully it works well when powered up.

Speaking of power, the next step after getting most of the extruder put together and mounted is wiring everything up.  I decided I wanted to do something special with the power switch as I had a red missile-launch style switch cover that I'd bought previously.  I hooked it up like this:

  ![Missile switch](/images/missile-switch.jpg)

with a dual-color red-green LED. When the machine is connected to the power supply but the power supply is in standby (switch is off) the LED is red.  When you flip the switch the power supply turns on and the LED turns green.  This seemed like it should be very simple but turned out to be one of the more complicated things I've done on this build so far.  I did learn some things along the way though about using transistors and NOR gates, so this was worth while.  And now it works.

The final bit I'll include in this update is a bit about the endstops I'm building.  I chose optical endstops because again it wasn't clear to me yet why I'd choose one over the other and the optical ones seemed cooler. The purpose of these is to signal the controller when the build plate has travelled the maximum distance in one direction. Eventually I might want 6 of these but it seems like most people use 3, so that's what I'm going to start with too.  These came in kit form so I've got to solder them.  Here's one complete and one not yet started:

  ![Opto endstop](/images/opto-endstop.jpg)

And that's all the pictures I've got for this update.

Things that I've still got to do before I can get printing include:

 * finishing the other 2 end-stops
 * finishing wiring everything up
 * finish the build platform
 * mount the endstops
 * mount the resistor and thermistor in the aluminum block and test that out
 * calibrate the axes
 * figure out how I'm going to spool the filament into the extruder
 * figure out how to use the software

That sounds like a lot of work.  Hopefully I'll have time for an update again before Christmas.
