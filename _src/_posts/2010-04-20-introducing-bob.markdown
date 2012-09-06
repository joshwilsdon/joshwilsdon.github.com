---
layout: post
title: Introducing Bob!
summary: Update on robot #1
tags: [robots, bob]
---

Last week I finally managed to get some wheels for my robot.  They're a lot smaller than the wheels I originally planned, so I had to scale back my other plans accordingly.  My original plan was to build something similar to [Oddot's Wild Thumper](http://letsmakerobots.com/node/14156).  Plans change.  Instead of 6 giant wheels with a custom suspension system, this robot will have 4 smaller (42mm) wheels attached directly to the frame.  Since this is my first robot, simpler is probably better anyway.  Over the past weekend I had some time to work on it, so this post is an update of my progress so far.

I've decided to call my robot Bob.  This is what he looks like right now:

![Picture of Bob](/images/first_pic_of_bob.jpg)

Notice that the wheels aren't even attached yet.  When they are the wheelbase will be slightly wider and he'll have a bit more ground clearance.  He'll also be able to move!  At least theoretically.

His whole frame is made out of aluminum held together by [JB Kwik](http://jbweld.net/products/jbkwik.php) (this stuff's awesome).  This means he's really light and pretty sturdy.  I had all the aluminum pieces left over from previous (non-robot) projects.  All the pieces were cut with a hacksaw and filed by hand.  The couple places where I needed to use screws, I used a drill and a 6-32 tap to make the screw holes.  The frame's approximately 6.5 x 4 inches.

The only somewhat complicated part so far was designing a mount for the motors.  As mentioned previously, [these motors are tiny](/2010/03/10/very-tiny-motors) and the screws I'd need to use if I was going to just use the built in screw holes are even smaller.  I wanted to mount them directly to the frame to make it more sturdy, but I want to be able to remove the motors later if I want to borrow them for another project.  Just JB Kwiking them on is out of the question then.

The solution I came up with was to attach a small piece of square aluminum tubing to the frame and add set screws and some small aluminum shims to hold the motors in place.  This is what the motor mounts look like:

![Bob's motor mounts](/images/bobs_first_motor_mounts.jpg)

In the picture you can see one of the shims in place.  There will be one on the other side as well, then the set screws on the side can be tightened to clamp the motor in place.  Only time and testing will tell if it works well enough or not.

Bob's "eyes" are actually a [PING))) Ultrasonic Sensor](http://www.parallax.com/tabid/768/ProductID/92/Default.aspx).  It is mounted on a servo which will allow him a 180 degree field of "vision".  I may add some additional sensors later.  Possibly infrared.

Power will come from 6 NiMH 1.2v "AA" batteries.

To drive the motors I decided that I'll try a [TB6612FNG-based driver board](http://www.hvwtech.com/products_view.asp?ProductID=1266) mostly because it's cheap and seems like it will be good enough.  The wheels aren't going to turn side-to-side so I need to be able to control the motors independently to enable skid steering.

To control the motors, servo and sensor(s) I'm going to be using an [Ardweeny](http://www.hvwtech.com/products_view.asp?ProductID=1257).

The next steps are:

 * finish the rear motor mounts
 * build and test the Ardweeny
 * hookup the TB6612FNG board
 * test the motor control

If the motor controller works well, I'm going to order another one (one can control 2 wheels) and 2 more motors.  Then I'll need to wire the whole thing up and start working on the PING))) and servo controls.

I'll post more updates as the Bob progresses!
