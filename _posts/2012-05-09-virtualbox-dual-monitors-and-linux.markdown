--- 
layout: post
title: VirtualBox, Dual Monitors and Linux
---

So I just tried out Ubuntu 12.04 and I am not sold on the interface, overall I still am kind of fond of Windows type desktops ([Linux Mint](http://linuxmint.com/) is favorite so far). But this post is not about that, its about multi monitor setups.

Now a little background on my host machine, its Windows 7 64bit with VirtualBox and dual monitors. It seems to have no issue powering through virtual machines 32bit or 64bit. I have [VirtualBox](virtualbox.org) (get a copy!) 4.1.14; it supports more then one monitor, now I have read that previous version did as well but I have not tried this in over a year since my last attempts were unsuccessful.

Steps:

1. Install [VirtualBox](https://www.virtualbox.org) (its free, Windows, Linux and Mac)
2. Once you have created your virtual machine (VM) edit your settings.
3. Go to Display section and increase the Monitor Count.
4. __Make sure to increase your Video Memory__. If you don't it won't work (I should know, took me a bit to figure out that was my issue). I would go with the maximum 128MB if possible.
5. Install your OS (you can do this before step 3).
6. Make sure to install the VirtualBox guest additions.
7. Then reboot and once you are back in you should be able to use more than one.

My best results where in full screen mode (right crtl+f) or seamless mode (right ctrl+l). It was great to have use of my two monitors while in Linux virtual machine. Now you can do this for Windows as well.

Have fun!
