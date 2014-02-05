--- 
layout: post
status: publish
published: true
title: VirtualBox, Dual Monitors and Linux
author: ldubber
author_login: ldubber
author_email: luke.dubber@gmail.com
author_url: http://www.lukedubber.com
wordpress_id: 13
wordpress_url: http://www.lukedubber.com/?p=13
date: 2012-05-09 15:14:26 -08:00
categories: 
- System Administration
- Visualization
tags: 
- Linux
- Visualization
- VirtualBox
- Ubuntu 12.04
- Ubuntu
comments: []

---
So I just tried out Ubuntu 12.04 and I am not sold on the interface, overall I still am kind of fond of Windows type desktops (<a href="http://linuxmint.com/" target="_blank">Linux Mint </a>is favorite so far). But this post is not about that, its about multi monitor setups.

Now a little background on my host machine, its Windows 7 64bit with VirtualBox and dual monitors. It seems to have no issue powering through virtual machines 32bit or 64bit. I have <a href="http://www.virtualbox.org" target="_blank">VirtualBox </a>(get a copy!) 4.1.14; it supports more then one monitor, now I have read that previous version did as well but I have not tried this in over a year since my last attempts were unsuccessful.

Steps:
<ol>
	<li>Install <a href="https://www.virtualbox.org/wiki/Downloads">VirtualBox</a> (its free, Windows, Linux and Mac)</li>
	<li>Once you have created your virtual machine (VM) edit your settings.</li>
	<li>Go to Display section and increase the Monitor Count.</li>
	<li><strong>Make sure to increase your Video Memory</strong>. If you don't it won't work (I should know, took me a bit to figure out that was my issue). I would go with the maximum 128MB if possible.</li>
	<li>Install your OS (you can do this before step 3&amp;4).</li>
	<li>Make sure to install the VirtualBox guest additions.</li>
	<li>Then reboot and once you are back in you should be able to use more than one.</li>
</ol>
My best results where in full screen mode (right crtl+f) or seamless mode (right ctrl+l). It was great to have use of my two monitors while in Linux virtual machine. Now you can do this for Windows as well.

Have fun!
