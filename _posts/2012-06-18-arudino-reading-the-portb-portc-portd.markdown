--- 
layout: post
status: publish
published: true
title: Arudino & reading the PORTB, PORTC, PORTD
author: ldubber
author_login: ldubber
author_email: luke.dubber@gmail.com
author_url: http://www.lukedubber.com
wordpress_id: 23
wordpress_url: http://www.lukedubber.com/?p=23
date: 2012-06-18 22:23:33 -08:00
categories: 
- Arduino
- Electronics
tags: 
- Arudino
- Diecimila
- ATmega168
- DDRD
- DDRB
- PROTD
- PORTB
comments: []

---
The Arduino has a way to access the port registers (<a href="http://www.arduino.cc/en/Reference/PortManipulation" target="_blank">official documentation here</a>), it allows lower-level and fast manipulation of the i/o pins on the micro-controller. This pertains to the ATmega8 and ATmega168. I did my testing with a Diecimila (ATmega168).

Now you may be wondering why I am making a post about this, well I ran into a interesting scenario while trying to use the registers to read if a pin was high or low. Now it is covered in the official documentation but I thought it would be nice to create a chart and elaborate on it some more.

When I was reading the output on digital pins 0-7 I had no issues, since I could define the ping with a variable and pass that variable to the <a href="http://arduino.cc/en/Reference/BitRead" target="_blank">bitRead()</a> function and get what I needed. What happened is if I had a variables for say pin 8 and then passed that variable to the bitRead() and I would get nothing back.

Turns out what I did not know is this pings 0-7 map directly with the bits used to access the lower level of the chip.
<table>
<tbody>
<tr>
<td>Pin</td>
<td>7</td>
<td>6</td>
<td>5</td>
<td>4</td>
<td>3</td>
<td>2</td>
<td>1</td>
<td>0</td>
</tr>
<tr>
<td>DDRD</td>
<td>7</td>
<td>6</td>
<td>5</td>
<td>4</td>
<td>3</td>
<td>2</td>
<td>1</td>
<td>0</td>
</tr>
</tbody>
</table>
As you can see its gos in descending order from right to left. So if you want to set pins 3&amp;4 for output on DDRD it would be DDRD = B00011000, since you either have on (1) or off (0).
<table>
<tbody>
<tr>
<td>Value</td>
<td>0</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>1</td>
<td>0</td>
<td>0</td>
<td>0</td>
</tr>
<tr>
<td>Pin</td>
<td>7</td>
<td>6</td>
<td>5</td>
<td>4</td>
<td>3</td>
<td>2</td>
<td>1</td>
<td>0</td>
</tr>
<tr>
<td>DDRD</td>
<td>7</td>
<td>6</td>
<td>5</td>
<td>4</td>
<td>3</td>
<td>2</td>
<td>1</td>
<td>0</td>
</tr>
</tbody>
</table>
Now back to my issue, I was passing the variable for pin 8 which as you can see there is no 8 on the DDRB, so I had to set it to 0 without using the variable. Now not knowing this did cause me about an hour of troubleshooting. But now that I learned this its much easier.
<h1><strong>WARNING I am not 100% sure if DDRB can go past 4 bits or if it has to be 4, so be CAREFUL!</strong></h1>
<table>
<tbody>
<tr>
<td>Pin</td>
<td>11</td>
<td>10</td>
<td>9</td>
<td>8</td>
</tr>
<tr>
<td>DDRB</td>
<td>3</td>
<td>2</td>
<td>1</td>
<td>0</td>
</tr>
</tbody>
</table>
Example say you wanted to set ping 8 &amp; 9 to output. DDRB = B0011. Now on the official documents it only has DDRB with four bits. So you might only be able to set pin 8-11. So read up on it first, before you try to go higher, I only used bitRead() on mine.
<table>
<tbody>
<tr>
<td>Value</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>1</td>
</tr>
<tr>
<td>Pin</td>
<td>11</td>
<td>10</td>
<td>9</td>
<td>8</td>
</tr>
<tr>
<td>DDRB</td>
<td>3</td>
<td>2</td>
<td>1</td>
<td>0</td>
</tr>
</tbody>
</table>
If you want to read if the output on pin 9 is high or low just use "bitRead(PORTD,1)".

I hope this information is useful to someone. This information is in the Arduino official documentation, the issue I had is it was not painfully obvious to me.
