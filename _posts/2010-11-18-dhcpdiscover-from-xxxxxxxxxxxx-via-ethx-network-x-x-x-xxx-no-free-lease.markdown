--- 
layout: post
status: publish
published: true
title: "DHCPDISCOVER from XX:XX:XX:XX:XX:XX via ethX: network X.X.X.X/XX: no free lease"
author: ldubber
author_login: ldubber
author_email: luke.dubber@gmail.com
author_url: http://www.lukedubber.com
wordpress_id: 56
wordpress_url: http://www.lukedubber.com/?p=56
date: 2010-11-18 15:01:39 -09:00
categories: 
- Uncategorized
tags: []

comments: []

---
So I got that error while working on a Linux router. It runs on <a href="http://www.soekris.com/">Soekris</a> hardware, its running custom rolled Linux. I was not the one who set it up.

In order to even get that error you would have to run <em><strong>dhcpd -d ethX</strong></em> once you did that it would do that every time a DHCP request was sent.
Turns out in the end it was the clock. The box is set to sync time with the net well the router was not fully up so no internet. So when it started it got a time in the 1920s which causes a big big big issue with DHCP. So a few lines about syncing the clock after a NTP update was attempted fixed it from  happening again. I Googled the hell out of this and got nothing. Just thought it would not hurt to put it up so someone might find this.
