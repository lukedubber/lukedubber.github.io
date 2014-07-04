---
layout: post
title: Windows RDS Farm network printers disappearing....
---

So I ran into this really weird issue with our Windows 2012 R2 Remote Desktop Server (RDS) and '''Network Printers'''.

Here is a little background on our setup so this all makes sense.

Setup:

* 4 x Windows 2012 R2 Standard Hyper-V machines.
 * 1 x RD Connection Broker/Gateway
 * 1 x RD Web Access
 * 2 x Remote Desktop Server


In the medical clinic we have MAs (medical assistants) and doctors who go from their work area to exam rooms. 
They only have one session, which follows them around. Now over time they would start to slowly lose their network printers. 
It seemed very random no patter I could find. When I ran [Procmon](http://technet.microsoft.com/en-us/sysinternals/bb896645.aspx) I could see the Print Spooler going through the registry every time and looking at connections, but would just stop sometimes.

This happened only on reconnect; it seemed the printers were being removed for some reason. 

I had to open up a support ticket and it turns out they where! There was a reg key that had to be added that would tell the print spooler to not remove printers.
The key was "RemovePrintersAtLogoff", which in my mind would make me think on log off not disconnec. 

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Print\Providers\Client 
    Side Rendering Print Provider]
    "RemovePrintersAtLogoff"=dword:00000000

Once that key was applied their printers stuck; which was fantastic since it was quite an issue. 

I hope this post helps someone.

[My tech net post](http://social.technet.microsoft.com/Forums/windowsserver/en-US/9e8642e4-f83e-4902-9c28-39671bbf239a/network-printers-disappear-upon-reconnect-to-a-disconnected-session)
