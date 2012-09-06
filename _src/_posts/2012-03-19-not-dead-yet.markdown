---
layout: post
title: Not Dead Yet
summary: still making progress on the RepRap
tags: [reprap]
---

Wow.  I had been thinking that my last post was in January and I really should make a new one soon...  Then when I finally got around to looking, it was even longer ago than that.  In between we had Christmas and started a whole new year.  We had Valentines Day and now it's already more than halfway through March!

My [reprap](/reprap) is now at least partially functional.  I've built and rebuilt many of its parts multiple times now.  It seems like I'm constantly taking 2 steps forward and 1.9 steps back, but I have definitely learned a lot about what I'm doing that will help me improve things in the future.

The todo list I included at the end of [my last post](/2011/11/28/slow-but-steady) that I needed to do before I could print, I have actually had done for a while.  In fact I've done and redone several of them multiple times.

The good news is that I have actually been able to print a few things.  Mostly I've tried to print the same part repeatedly after making some tweaks.  It's supposed to be a [20mm x 20mm x 10mm solid block](http://www.thingiverse.com/thing:5573), but in my case the first print kinda turned out like abstract art:

![blob that was my first print](/images/reprap_first_print.jpg)

I adjusted the print settings and broke the y-axis platform and fixed it and broke the x-axis platform and meanwhile printed these further iterations:

![a little closer to a shape](/images/reprap_20mm_cube_1.jpg)

![starting to look like a cube](/images/reprap_20mm_cube_3.jpg)

![best yet](/images/reprap_20mm_cube_5.jpg)

by the last one you can see that it's actually starting to look like what you'd expect.  I realized that the reason it's rectangular and not square is that the x-axis was not working quite right.  I had calibrated it, but the travel distance was not actually stable.  My theory was that the problem was related to the printed pulleys I had not been accurate enough.  Doing some reading around it seemed a lot of people are recommending GT2 pulleys and belts, so I decided I should get a set of those so I can see how much that helps.  I'll talk about that in another post.  Sneak preview: It helped!

I've had a number of problems and unforeseen changes I decided to make throughout which I might write about in more detail in the future.  These include:

 * y-axis coming unglued
 * y-axis becoming crooked
 * fixing crooked y-axis the wrong way
 * finally fixing crooked y-axis the right way
 * y-axis belt tension problems
 * z-axis crashing into the build plate causing x-axis breakage
 * z-axis crashing into the top of the machine
 * mounting heated bed
 * warped bed #1 attempt to fix with silicone sheet
 * warped bed #2 attempt to fix with more silicone sheet and different bulldog clips
 * warped bed #3 attempt to fix by drilling glass
 * warped bed #4 attempt to fix with screws on corners (of now-broken glass)
 * warped bed #5 raising the bed to finally make things a bit better
 * plastic leaking between the PTFE tube and brass barrel of the extruder
 * y-axis bushings binding on steel rods
 * adding diode to RAMPS for powering Arduino from PSU
 * adding a fan to the extruder
 * updating + configuring the firmware
 * upgrading to GT2 belt / pulleys
 * building a spool holder/mount for the filament
 * building a platform for the machine to deal with wildly non-level desk

And all my work recently on this has been to try to get everything calibrated better so I can make nice prints.  I plan to try to go back and write about some of these while also posting new progress as well.  Hopefully the combination will get things here back up-to-date and keep it that way.
