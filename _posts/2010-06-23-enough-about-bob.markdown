---
layout: post
title: Enough About Bob.
summary: Going to take a break from Bob now?
tags: [robots, bob]
---

<div class="floatyimg"><img src="/images/bob_asof_20100623_sm.jpg" title="Bob as of 2010-06-23" alt="Bob as of 2010-06-23" /></div>
I found [Bob's Bug](/2010/06/16/bobs-got-bugs).  It turned out that the issue was not with either the hardware or the software directly but with the Servo library.  For some reason the Arduino Servo library needs to use two clocks from the Arduino.  That means that when you start using any servos, immediately PWM output stops working on pins 9 and 10.  This is not what I expected.  It's even [documented](http://www.arduino.cc/en/Reference/Servo).  Unfortunately I didn't read that documentation and instead relied on copying an example I found somewhere and modifying it in a way that I thought reasonable.

With that bug fixed (I moved everything except the servo off pins 9+10), Bob can now use both his servo and motors without a problem.  Unfortunately this means I'm now using all of the PWM pins on Bob's Ardweeny.  I'm also using a lot of the other pins.  Because of this I think I'm about done adding stuff to Bob.  If I wanted more pins I'd have to mess around with some more shift registers and some other PWM chips.  This seems like just too much work for Bob, so I'm going to take a break from Bob for now and start thinking about my next project.  If I do anything more with him it'll likely just be software tweaks.

At this point I think Bob is pretty much a success.  He can successfully drive forward, stop before running into something (see the video below) and then back up and go a different direction.  This works at least as well as I hoped.  I've learned a lot building Bob.  Some of these lessons at random include:

 * building a robot frame is a lot of work if you do it with a hacksaw and hand file
 * making PCBs on protoboard using the green-wire technique takes a long time
 * shift registers are useful
 * parts with weak connectors need extra protection
 * [Ardweeny](http://www.hvwtech.com/products_view.asp?ProductID=1257) is cool (and cheap!)
 * isolating the power from the programming is a good idea
 * connect all the grounds

overall I think I have a lot more appreciation for what it takes to make a robot.  Now for my next one I hope to use these lessons to make something a little more advanced.  I'll write about some of my ideas in a future post.

In the meantime, here's a quick video of Bob not running into stuff:

<object width="640" height="385"><param name="movie" value="http://www.youtube.com/v/FCDH-IJ25mU&hl=en_US&fs=1&"></param><param name="allowFullScreen" value="true"></param><param name="allowscriptaccess" value="always"></param><embed src="http://www.youtube.com/v/FCDH-IJ25mU&hl=en_US&fs=1&" type="application/x-shockwave-flash" allowscriptaccess="always" allowfullscreen="true" width="640" height="385"></embed></object>
