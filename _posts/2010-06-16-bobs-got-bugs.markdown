---
layout: post
title: Bob's Got Bugs!
summary: Bob is mostly together but has some wierd issues.
tags: [robots, bob]
---

<div class="floatyimg"><img src="/images/bob_asof_20100616.jpg" title="Bob as of 2010-06-16" alt="Bob as of 2010-06-16" /></div>
Bob's parts have all been mounted together now.  Some are more solidly mounted than others, but he's staying together so far.  Since I got everything together I was able to finally run a test where he moved!  He can actually move faster than I expected.  You can see his first "steps" in the video at the bottom of this post.  Note that this is at 20% power.  At full speed he zips along pretty well.  Oh, and you can see part of my new floor in this video too.

I've not actually done anything about the motor that I wrecked the connector on.  For now I've just adjusted the software to handle the different rotation on this motor and it seems to be working well enough.

Individually, Bob can control all of his parts.  He can move his servo left and right 90 degrees either direction.  He can measure distance with his [PING)))](http://www.parallax.com/tabid/768/ProductID/92/Default.aspx) sensor (Bob only wants to think in metric, so he measures distance in centimeters).  He can move any combination of his motors forward or backward (with individual speed control) or set them to coast or brake.  All of this works just fine when it's run once (eg. start all motors going forward).

Bob's not perfect yet though.  There is a bug hiding somewhere and I'm still trying to track it down.  After sending a few commands to the motors it seems something is eventually getting corrupted.  If I keep sending commands eventually motors are going when I don't want them to be and not going when I want them to be.  This is obviously a problem.  I'm not sure yet whether this is a hardware or software problem.  If it's a hardware problem my best guess is that I wired something wrong when connecting the two shift registers.  If it's a software problem I'm also suspecting my code that's working with the shift registers.  In either case I hope to track it down soon, fix it, and be able to explain it next week.

Here's the video of Bob's first trip:

<object width="640" height="385"><param name="movie" value="http://www.youtube.com/v/mJioT1xdKrE&hl=en_US&fs=1&"></param><param name="allowFullScreen" value="true"></param><param name="allowscriptaccess" value="always"></param><embed src="http://www.youtube.com/v/mJioT1xdKrE&hl=en_US&fs=1&" type="application/x-shockwave-flash" allowscriptaccess="always" allowfullscreen="true" width="640" height="385"></embed></object>

Hopefully my next video will be of him going toward a wall/object and stopping before running into it.  If I can get his bugs worked out.
