---
layout: post
title: Adding an SD card to a WRT54GL 1.1 router
summary: adding an SD card to a WRT54GL 1.1 router
tags: [hardware, electronics, wrt54gl, foosalytics]
---

<div class="floatyimg"><a href="http://github.com"><img src="/images/wrt54gl.jpg" title="WRT54GL!" alt="WRT54GL" /></a></div>
There's a project that I've been thinking about for a while (more on this in the coming weeks hopefully) which I think will be pretty interesting.  I've finally started spending some actual time on it and it's going to need a whack of GPIO pins and Internet connectivity.  Since I found one of the famous [Linksys WRT54GL](http://en.wikipedia.org/wiki/Linksys_WRT54G_series#WRT54GL) routers lying around and I still have an extra [Ardweeny](http://www.solarbotics.com/product/kardw/), I figured: why not connect them and make a frankenbox?  I'm documenting it here mostly so I can refer back and remember what I did.

I've used [DD-WRT](http://www.dd-wrt.com/site/index) and [Tomato](http://www.polarcloud.com/tomato) in the past, but not [OpenWRT](https://openwrt.org/).  DD-WRT seems to be falling behind though and OpenWRT seems more easily customized.  I don't need a web UI or anything fancy for this project so I gave OpenWRT a try.

Installing OpenWRT when you've already loaded Tomato (I think the same would be true if you had DD-WRT) is trivial.  It was a simple matter of downloading the firmware image and installing using the built-in firmware update tools.  In Tomato this is through their web interface.  So I went to [openwrt.org](http://openwrt.org) and downloaded the latest firmware (Attitude Adjustment \(12.09\)), flashed it to the device and it booted right up.  I changed the networking config to put the wireless into 'sta' mode and changed the encryption type to 'psk2+tkip+ccmp' since that's what I needed for my network.  Filling in that and the wireless SSID and key allowed me to connect to the network with little effort.

What I realized soon though is that this firmware image is pretty porky and there was a ton of crap installed by default that I didn't need.  A firewall, a web interface, PPP and a bunch of other stuff.  I spent some time removing all this extra stuff but then realized that even deleting all the non-essential stuff I wasn't going to have much room left.  And more importantly I wasn't going to have enough room left to install the other packages I'm likely to need.  So I needed more space.

Searching around I found that many people have used the available GPIO on these routers and attached SD cards.  For example (in no particular order):

 * [http://www.jbprojects.net/articles/wrt54gl_mods/](http://www.jbprojects.net/articles/wrt54gl_mods/)
 * [http://duff.dk/sd/](http://duff.dk/sd/)
 * [http://wiki.the-mesh.org/wiki/LinksysSDCard](http://wiki.the-mesh.org/wiki/LinksysSDCard)
 * [http://www.isnull.com.ar/2009/12/wrt54gl-v11-sd-card-mod-with-openwrt.html](http://www.isnull.com.ar/2009/12/wrt54gl-v11-sd-card-mod-with-openwrt.html)

Since I was going to be hacking a serial port into this thing anyway (to talk to the Ardweeny) it seemed adding an SD card wasn't too bad an idea.  This way I'd have more space for data storage if I need it.

I read through a few different posts (including the ones above) on how to go about this then got to work.  I opened the case, soldered the leads, confirmed it still worked and then loaded the mmc-gpio driver.  It didn't work.  The kernel couldn't detect the card.  So I spent some more time digging and wondered if I'd melted something inside the micro-SD adapter I was using.  So I broke that open (I've got a few of these lying around so no big loss) and everything looked ok.  Somewhat unsurprisingly these things have nothing inside that's going to melt other than the plastic:

![An opened SD - microSD adapter](/images/opened-sd-microsd-adapter.jpg)

After soldering in another one I started looking at the software.

It seems that the "latest" version that I chose is actually a very new kernel and many people have been [having problems with SD cards on newer kernels](https://forum.openwrt.org/viewtopic.php?pid=91200).  I decided that since most of the examples I could find of people getting this working were from a while ago and I probably don't need any of the features of the newer firmware for my use-case, I should just downgrade to a known-working version instead of working through what might or might not be broken in the latest version.

I chose to download the "Kamikaze" (8.09.2) version and used the command:

    mtd -r write /tmp/openwrt-brcm-2.4-squashfs.trx linux

to update the firmware.  This worked without hitches and soon I was logged back into the router reapplying the same wireless/networking config I had before.

When I went to load the driver this time, I found that the driver was not available through opkg, but I was able to use the [mmc-v1.3.4-gpio2.tgz](http://wiki.openwrt.org/_media/oldwiki/openwrtdocs/customizing/hardware/mmc-v1.3.4-gpio2.tgz) one at wiki.openwrt.org \([local copy](/blobs/mmc-v1.3.4-gpio2.tgz)\) which I found through the www.isnull.com.ar link above.  That driver loaded right away and saw the SD card.

I added the /etc/init.d/mmc with the following contents:

    #!/bin/sh
    
    echo 0xb8 > /proc/diag/gpiomask
    insmod mmc
    mkdir -p /opt
    mount /dev/mmc/disc0/part1 /opt

note: I originally had 0x9c in the /proc/diag/gpiomask as is used on many sites.  When I did that I kept seeing:

    /usr/sbin/hotplug-call button

show up multiple times in the process list whenever I accessed the SD card and the "Cisco button" LEDs weren't working when accessing the SD card.  It seems based on my limited understanding that this means I'm using GPIO 5 instead of GPIO 2 even though the WRT54GL is supposed to be the other way around.  When I made the change to 0xb8 the hotplug-call processes went away and the LEDs worked when accessing the SD card.

I've setup the sd card as an alternate dest in /etc/opkg.conf and installed python and a few other packages there.  Much more than would have fit on this thing otherwise.  Since I'm using FAT32 on the microSD card, I need to manually create the symlinks in /usr/* but this isn't so hard and means that if I need to I can take the card out and copy files to it from any other machine.

Anyway, now that I've got everything I need for now installed on the router I'm going to move on to some other parts of the project which I hope to also document eventually.
