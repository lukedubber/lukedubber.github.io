--- 
layout: post
title: "DHCPDISCOVER from XX:XX:XX:XX:XX:XX via ethX: network X.X.X.X/XX: no free lease"
---
So I got that error while working on a Linux router. It runs on [Soekris](http://www.soekris.com/) hardware, its running custom rolled Linux. I was not the one who set it up.

In order to even get that error you would have to run __dhcpd -d ethX__ once you did that it would do that every time a DHCP request was sent.
Turns out in the end it was the clock. The box is set to sync time with the net well the router was not fully up so no internet. So when it started it got a time in the 1920s which causes a big big big issue with DHCP. So a few lines about syncing the clock after a NTP update was attempted fixed it from  happening again. I Googled the hell out of this and got nothing. Just thought it would not hurt to put it up so someone might find this.
