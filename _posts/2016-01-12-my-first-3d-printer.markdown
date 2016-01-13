---
layout: post
title: "My first 3d printer: A journey of not burning my house down and having fun."
uploads: 2016-01-12-my-first-3d-printer
---

#A journey of not burning my house down and having fun.

3d printing has been in the news the past few years. I have been wanting one for
quite a while (my first post was about [3d printers]({% post_url 2010-09-03-repstrap-part-1 %}))

I ran across a great sale on [3dprintersonlinestore.com](https://www.3dprintersonlinestore.com/electron-3d-prusa-i3-kit),
where you can get a Sixth Gen Prusa i3 kit, it starts at $255 USD and has some nice
upgrades that don't cost to much. I purchased the larger build area and the auto level
sensor.

It uses a Marlin compatible board that can easily be flashed with the Arduino IDE.
In order to get better prints, I was able to find on a forum the right settings
and a guide to upgrade my firmware. Also enable some of my feature and make some
tweaks. I like the openness of even this kit, I have made some upgrades (you will)
read about them bellow. And this unit is quite flexible. I spent sub $500 and
I have feature that some of the $2,000 models don't have yet.

#And so it begins!

Some parts were damaged in shipping, but I was able to glue them together/tape. The
nice thing about a 3d printer is you can always print new parts! If you happen
to have the same printer as I and need the STL files [here they are]({{site.image}}/{{page.uploads}}/MigBot_printer_parts.zip).

![So it begins!]({{site.image}}/{{page.uploads}}/20150828_214803_13.jpg)
![So it begins2!]({{site.image}}/{{page.uploads}}/20150828_214904_13.jpg)

![Coming together]({{site.image}}/{{page.uploads}}/20150829_004000_15.jpg)

My initial setup, I used a old Lenvo tablet to be my main printer. I used
[Printrun (Pronter)](http://www.pronterface.com/) as my first 3d printing host
software. That has since changed. You can read more bellow.

![My Setup]({{site.image}}/{{page.uploads}}/20150907_211606_15.jpg)

#Inital upgrades
Before and after I started my first print I did some minor upgrades. First thing
I did was go buy a good solid 3 pin AC power cable. The one they sent was very
cheap, and had no netrual/ground. So before I did anything with the power supply
I went to Homedepot and picked up a good one. I also changed out the gage wire
to a thicker one.

#First print!
It took a while to get my first print done, the tool chain was a pain to wrap my
head around. I use Cura 15.02.1 as my slicing software. Then I had to find a good
print host software. Its not as simple as open STL and click print. Even though
commercial ones I hear it is.

This was a calibration cube printed in ABS. Not very good bed adhesion. I have
since gone to almost 100% printing PLA, just easier to work with. I want to
enclose the printer, but due to the frame being acrylic; I worry about warping.

![First Print!]({{site.image}}/{{page.uploads}}/20150831_112637_15.jpg)

#Smoke?!
So this is my first big project where I put something together that has a power
supply. I did some upgrades as I went along, putting in thicker gaged wire then
what came with my printer, since I could feel the wires outside plastic coating
start to get soft on the original cables.

So after I put in thicker gage, it was hard to get a good connection. But it was
good enough, or so I thought. I learned a valuable lesions that night about current
AMPs and resistance; and about listening to my wife when she smells burning plastic.

What seemed to be the issue was I did not have enough of the cooper touching the
connector. So the contact surface was poor, which caused resistance, and heating
of the connector and the melting, smoke and almost fire.

But I was quick enough to turn it off and there was no damage to the components or the
PCB. But that connector was fried, so I removed it and attached a new one/better one.
Have not had a heating issue or connection issue since then. Did many, many hours
of printing with no issues.

![Fire damage...]({{site.image}}/{{page.uploads}}/20150923_212652_13.jpg)
![Repairs start...]({{site.image}}/{{page.uploads}}/20150923_215306_13.jpg)

#Last Upgrades (for now...)
I did some upgrades and put a Raspberry Pi as the new print host, I am using
[OctoPrint](http://octoprint.org/). I cannot say enough good things about this
software, its simple to use. I just drop my GCODE files into the browser window.
Then I click print! Fantastic, also I have a Wi-Fi dongle so now my printer is
wireless. On top of that I bought 24v to 5v USB adapter and wired it up to my
printer so I only have one power cable.

I have as much fun and enjoyment upgrading and learning as I do printing. My kids
love what can be done. They had a mustache day at school and I forgot. But luckly
for me on [Thingiverse](http://thingiverse.com) there was this neat [mustache](http://www.thingiverse.com/thing:533418)
made by Microsoft (I know right?). I printed a few out for my boys to use and share
and I heard it was pretty cool.

#Current Status
So this is the current status of my printer, I made a mod to get closer to the
set screw to tighten it up and well it kind of ended up doing the opposite. As
of this post, that's the status of my printer. I have yet to work on getting it
running, even thought its only 15 minutes of work. But my day job has gotten me
pretty busy as of late. I hope to get back to it soon.

![Repairs start...]({{site.image}}/{{page.uploads}}/20151118_092723_15.jpg)

#I love 3d printing!
See above!

Also, this kit was pretty cheap and is not a out of box experience. But if you
want to have a cheaper decent quality 3d printer and learn and upgrade things at
the same time. It maybe the printer for you.

#Other prints
![A Cat]({{site.image}}/{{page.uploads}}/20150901_210133_13.jpg)
![A neat little basket for tools]({{site.image}}/{{page.uploads}}/20150916_225452_13.jpg)
![Solder spool holder]({{site.image}}/{{page.uploads}}/20150908_113128_15.jpg)
![Space wrench!]({{site.image}}/{{page.uploads}}/20150909_211002_15.jpg)
![Parts for a Pip-Boy 3000 Mark IV]({{site.image}}/{{page.uploads}}/20150917_191642_15.jpg)
![Painted Pip-Boy 3000 Mark IV]({{site.image}}/{{page.uploads}}/20151031_195756_15.jpg)
![AEP7 Laser Pistol]({{site.image}}/{{page.uploads}}/20150918_225546_15.jpg)
![The force is strong]({{site.image}}/{{page.uploads}}/20151013_185237_15.jpg)
![Phone stand]({{site.image}}/{{page.uploads}}/20151118_082536_15.jpg)
