---
layout: post
title: Mini Bob Update
summary: Quick Bob Update
tags: [robots, bob]
---

<div class="floatyimg"><img src="/images/bob_powersupply_rev_2.jpg" title="New Power Supply" alt="New Power Supply" /></div>
If [Howie](http://howiewu.com) can blog [2 sentences and a video](http://howiewu.com/iped) and [Kevin](http://yinkei.com) can blog [2 pictures of something](http://yinkei.com/v-lock) that solves a problem I don't understand, without any text (I'm not sure I can even give full points for that on the [scoreboard](/scoreboard)), then certainly I can make a short blog post about Bob even though I've not done very much.

So, since my last Bob post there are really 2 things I made progress on.  One is Bob's new power supply.  I [wrote before](/2010/05/11/bob-is-screwed) that I had built a prototype but since then I actually soldered the thing together.  You can see a picture of it at the top of this post.  I've tested with both 9v and ~7.2v input and it can output 5v and 6v.  The 6v can actually be adjusted, so that I can reuse this board on other projects in the future too.  It's not very pretty, but hopefully it works.

The other thing I've done some work with is the shift registers and motor controllers.  I put together the shift registers on a couple breadboards and managed to control 13 LEDs with 3 I/O pins from the Arduino.  This is perfect for what I need.  It will allow me to control all 4 motors using just 1 PWM pin per motor and 3 digital out pins total. This leaves me lots of pins (though only 2 PWM) on my Ardweeny to control other stuff.  I've even started work on a more permanent board for this.  If I'm lucky, by keeping this post short this week I'll save myself some time tonight to be able to work on finishing up this board.  This is what the setup I built to test the shift registers looks like:

![Shift Registers Mess](/images/shift_registers_initial_testing.jpg)

Once I'm finished the motor controller board, I'm going to attach the three boards I've built so far (Ardweeny, power supply and motor controller) to Bob's frame and I should be able to start testing some control software!  My goal is to get the control working correctly for the motors first and then attach the servo and [PING)))](http://www.parallax.com/tabid/768/ProductID/92/Default.aspx) sensor once I've got that figured out.  Hopefully there'll be more updates (and pictures) next week.
