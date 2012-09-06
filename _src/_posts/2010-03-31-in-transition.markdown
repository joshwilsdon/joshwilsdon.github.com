---
layout: post
title: In Transition
summary: Blog in Transition
---

<div class="floatyimg"><img src="/images/file-transfer.jpg" title="Transfering Files" alt="Transfering Files" /></div>
I work at [Layerboom](http://www.layerboom.com/) building awesome stuff.  Layerboom started and ran [GeoVPS](http://www.geovps.com/) for a while using our awesome virtualization platform.  It has however taken resources away from working on the platform itself and is therefore being shut down.

This site has been hosted so far on GeoVPS, but today is the last day for GeoVPS, so the whole thing has to be moved immediately.

I'm using [Jekyll](http://jekyllrb.com/) to basically generate this as a static site and thus I don't really need a full VPS instance to host it.  I was originally just going to move my files to either Rackspace's [Cloudfiles](http://www.rackspacecloud.com/cloud_hosting_products/files) or Amazon's [S3](http://aws.amazon.com/s3/), since I would just be able to upload the new files when I make them and forget about it.  When I looked into this I found there's a problem that prevents people from hosting their website entirely in either of these.

The problem is that it's not possible to have a default handler for /index.html.  This means that I can't have people go to [http://josh.wilsdon.ca](http://josh.wilsdon.ca), they'd need to include a trailing "index.html".  I really don't want that since people who went to the front page without the index.html would just get an error.

So I kept looking around.  It seems that there's now a tool that makes a [Jekyll site into a Rack app](http://github.com/bry4n/rack-jekyll).  So I think I might give that a try.  If that works well, I'm going to try deploying to [Heroku](http://www.heroku.com/).  Heroku looks pretty cool and I've been meaning to try it out anyway.  If it works out I'll get free hosting for my blog and perhaps I can start using some of the other nifty features of Heroku to eventually make some dynamic content.

We'll see.

In the mean time I've moved all my files to a temporary location so there should be no disruption in your ability to view [the scoreboard](/scoreboard) and see how badly Kevin's failing.

**UPDATE**: If you're seeing this, the site's been moved to Heroku!  It was actually really easy.
