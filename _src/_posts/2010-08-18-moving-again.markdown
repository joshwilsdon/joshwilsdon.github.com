---
layout: post
title: Moving again!
summary: This site is (probably) moving again soon.
tags: [blog, work]
---

<div class="floatyimg"><a href="http://www.joyent.com/technology/"><img src="/images/joyent-smartos-stack.jpg" alt="" /></a></div>
Before I get around to the main topic of this post I wanted to post a small update to my story from last week about being [stuck in an elevator](http://josh.wilsdon.ca/2010/08/09/beware-of-the-middle-elevator).  The building manager did come by when I was next in the office and told me that he was sorry I had been stuck in the elevator so long.  He also told me that the reason it had failed was due to a relay that had "blown out" and needed to be replaced.  I'm not sure if that makes me feel better.  Maybe they should do maintenance on those elevators a little more often?

Anyway, the primary topic for this week is this blog itself.  I've been using [Heroku](http://heroku.com/) now for a while.  It actually has worked out pretty well.  There have been a few Heroku outages since I set this up, but I've not personally seen any issues with the blog.  There are several features of Heroku that I really like too, and they've really done well, such as the lack of administration and the theoretical scaling (I can't vouch for the scaling because this blog is not really all that popular.)  Ordinarily I think I would just leave well enough alone.  Since I do work for Joyent now though and Heroku is technically a competitor, I thought it would be a good idea to try out the old [dog food](http://en.wikipedia.org/wiki/Eating_your_own_dog_food) and see if I can get this moved over to a Joyent Smart Machine.

So far I have made some good progress.  I've got a Smart Machine set up and I already set it up for [Nginx](http://nginx.org/) and git-push based deploy so I can deploy my blog there just as easily as Heroku. [This page](http://toroid.org/ams/git-website-howto) was pretty helpful in setting up the git deploy, though I did a couple things differently.

There are a few things I still need to do in order to be comfortable switching the DNS to the new server.  The biggest of these is getting the nginx config just right.  I want to get the config setup as well so that I can start testing some other new technologies including [node.js](http://nodejs.org/) written by Joyent employee [Ryan Dahl](http://github.com/ry) without necessarily breaking my blog.  I want to try to set it up to be as maintenance-free as possible.

Anyway, this post is mostly just a heads-up to let you know what I'm up to.  Hopefully next week or the week after I'll be all done with the transition and you'll be impressed.

UPDATE: I got the nginx config fixed, and my deploy script is now deploying to both Heroku and Joyent.  I plan to switch the DNS over sometime in the next couple days!
