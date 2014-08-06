---
layout: post
title: Cypress PSoC 4 CY8CKIT-049-42xx prototyping kit
---

    Warning, I am juts a novice, so there might (and will be) mistakes.
    First time using a IDE like this or using a ARM based chip.
    Also I have defined the initialisms, I figure if my past self finds this post,  
    it might help him. 

#Intro

So I first learned about the Cypress PSoC 4 CY8CKIT-049-4xxx protyping kits from 
[Hackaday](http://hackaday.com/2014/06/16/cypress-launches-5-arm-dev-board/) a month ago.
It really caught my attention as a cheap board to play with. I am always looking for cheap 
boards to play with. Also I have not worked with any Cypress or ARM chips before. 

#Hardware

About the board, it has two ICs[^IC] the first is the target (the main chip) 
an ARM Cortex M0+ based PSoc 4 MCU[^MCU]. The second chip is the USB bridge 
[CY7C65211](http://www.cypress.com/?mpn=CY7C65211-24LTXI). The USB bridge allows you to 
communicate with the devices built in bootloader for flashing code. 

What really neat about this whole package is that the bridge can be configured to talk UART[^URT], 
GPIO[^GPIO], I2C[^I2C] or SPI[^SPI]; so if you need a USB to serial converter, jackpot! Also 
its easily removed from the rest of the board (as you will see bellow) 

After a little bit of research I decided to go with 42xx, it has double the frequency and has 4 
universal digital blocks where the 41xx does not (Thanks "Tim G" from Hackaday comments![^Tim G]). 
When I deiced to pick mine up I went to [Mouser](http://www.mouser.com/), they where only $4 there 
(Also picked up a Nucleo Board STM32F4, but that's another post). At the $4 price, I picked up 
four total. I figured if I break one not a big deal, also I already gave one away.

If you need the software, code, guide, design files etc. [Go here](http://www.cypress.com/?rID=92146) 
(Cypress product page for the 4xxx Prototyping kits)

So I got them pretty quick and this is what they come in.
 
![Package front]({{site.image}}/2014-07-25-cypress-psoc-cy8ckit-049/20140725_112338_15.jpg)

![Package back]({{site.image}}/2014-07-25-cypress-psoc-cy8ckit-049/20140725_112307_15.jpg) 

Now I already opened it up, but they just used thick cardboard and put the board inside, 
honestly liked the way they did it, they store great.

![Out of package]({{site.image}}/2014-07-25-cypress-psoc-cy8ckit-049/20140718_111822_18.jpg)

It has the blinking LED example already on it. Plug it in and watch it go!

![Plugged in]({{site.image}}/2014-07-25-cypress-psoc-cy8ckit-049/20140718_111854_18.jpg)

So after having it for only a short while, I decided to add some header pins and make it work with 
a breadboard. I cut off the USB connection and then put some pins on it so I can connect 
the two. That way I can program it easier. 

![Breadboard mode go!]({{site.image}}/2014-07-25-cypress-psoc-cy8ckit-049/20140721_225900_18.jpg)



#Development tools (IDE)

I should state this again.

    I am a novice, so a lot of this is all new to me!

You will need to download the [PSoC Creator](http://www.cypress.com/psoccreator), this is a download 
you need to register for. Also you need the [USB-Serial Software Development Kit](http://www.cypress.com/?rID=83110) 
this has the CDC and Vendor class driver, I installed both and I think you need both (don't quote me on that).

Once all the software and drivers are installed you are ready to program. I just downloaded and 
loaded [CY8CKIT-049-42xx Example Projects.zip](http://www.cypress.com/?rID=92146) from the 
***Related Files*** section.

A lot of this system is drag and drop which is great, but threw me for a loop since I was use to 
using the Arduino IDE where its all C like syntax and no neat graphics. But I love the design 
files and layout tools.

There is neat slide show PDF from MIT about this [here](http://web.mit.edu/6.115/www/miscfiles/Creator_for_MIT.pdf), 
its a nice introduction to the PSoC Creator. Not sure if its the most up-to-date version of 
creator but it gets you started.

#Issues!

Once you are ready to upload the file you may run into this error while using the ***Bootlader Host*** program.

    Communication port reported error 'Unable to read data from the target device'.

What that error could mean is that you don't have the proper communication port selected (should not be COM1),
or the board was not in bootloader mode, if its not in that mode then it won't accept the binary
image file.

To put in that mode you have to do the following.

What you need to do is before you plug it in, is push and hold down the little black switch at
the end of the stick, insert into the USB port, once the LED on the board start to flash rapidly you let go.

Now its ready to program, this has to be done also again if you want to verify the image in memory.
So pull it out give Windows a few seconds to think and the repeat the hold down process. 

**That is one thing I really love about the Arudino over this.**


#Conculsion 

I hope this was helpful to someone. Writing this down helps me remember and also a great reference for myself if
I forget things. 

---
**Update - 2014/08/06**

Cypress has some great videos. [Cypress Training On-Demand](http://www.cypress.com/?id=1162)

---
Footnotes

 [^URT]: [Universal asynchronous receiver/transmitter](http://en.wikipedia.org/wiki/Universal_asynchronous_receiver/transmitter)
 [^GPIO]: [General-purpose input/output](http://en.wikipedia.org/wiki/GPIO)
 [^I2C]: [Inter-Integrated Circuit](http://en.wikipedia.org/wiki/I2c)
 [^SPI]: [Serial Peripheral Interface](http://en.wikipedia.org/wiki/Serial_Peripheral_Interface_Bus)
 [^IC]: [Integrated circuit](http://en.wikipedia.org/wiki/Integrated_circuit)
 [^MCU]: Microcontroller unit
 [^Tim G]: [Hackaday Comment](http://hackaday.com/2014/06/16/cypress-launches-5-arm-dev-board/comment-page-1/#comment-1575361)