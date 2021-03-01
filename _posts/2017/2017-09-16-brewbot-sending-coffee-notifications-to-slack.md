---
layout: post
title: BrewBot - Sending Coffee Notifications to Slack
categories: raspberry-pi
---
At work, we have a coffee machine that serves dozens of people in the building, and it's difficult to know when to come get fresh coffee. You might arrive when it's empty and be tasked with making more, but the ideal situation is to arrive just as a fresh pot is being brewed.

We also use Slack for team chat and various notifications, so integrating the coffee machine status was a no-brainer. Using a non-invasive/inductive current sensor and Raspberry Pi, the following setup monitors coffee machine energy consumption and waits for a significant rise in current draw, followed by several minutes of sustained usage. Once a time threshold has passed, it does an HTTP POST to a Slack webhook, sleeps for about 15 minutes, then starts monitoring again. This "brewbot" code is [available on GitHub](https://github.com/command-tab/brewbot), and a parts list can be found below.

![Completed kit](/assets/brewbot_full_kit.jpg)

![Packaged in box](/assets/brewbot_box.jpg)

![ADC board](/assets/brewbot_adc_board.jpg)

Full parts list:

* [MCP3008 8-Channel 10-Bit Analog to Digital Converter](http://www.adafruit.com/products/856)
* [Raspberry Pi model B](http://www.adafruit.com/products/998)
* [16-pin IC socket](http://www.adafruit.com/products/2203)
* [Assortment of heat shrink tubing](http://www.adafruit.com/products/344)
* [Panel mount to Micro USB adapter](http://www.adafruit.com/products/937)
* [10KΩ 1/4W LED resistor](https://www.sparkfun.com/products/11508)
* [Half-size Perma-Proto Raspberry Pi Breadboard PCB Kit](http://www.adafruit.com/products/1148)
* [5mm Yellow LED](https://www.sparkfun.com/products/9594)
* 1/8" panel mount audio jack
* 10uF electrolytic decoupling capacitor
* 33Ω 1/2W burden resistor
* 2x 470KΩ 1/2W voltage divider resistors
* [30A non-invasive current sensor](https://www.sparkfun.com/products/11005)
* [22 AWG Solid Core Hook Up Wire](https://www.sparkfun.com/products/11367)
* 5x7 photo box, from The Container Store
* [8 GB Class 10 SDHC card](http://www.amazon.com/gp/product/B00B588HY2)
* [Edimax EW-7811Un Wireless Nano USB Adapter](http://www.amazon.com/dp/B005CLMJLU)
* 6x Nylon screws washers and nuts
* [8" AC Cord Clips](http://www.monoprice.com/Product?p_id=8617)
* [HDMI to Mini HDMI adapter](http://www.monoprice.com/Product?c_id=102&amp;cp_id=10242&amp;cs_id=1024201&amp;p_id=3645&amp;seq=1&amp;format=2)
* [6' Mini HDMI to HDMI Cable](http://www.monoprice.com/Product?c_id=104&amp;cp_id=10419&amp;cs_id=1041909&amp;p_id=3654&amp;seq=1&amp;format=2)
* [10' USB A Male to B Male Cable](http://www.acehardware.com/product/index.jsp?productId=29313236)

Related reading: [Hyper Text Coffee Pot Control Protocol](https://en.wikipedia.org/wiki/Hyper_Text_Coffee_Pot_Control_Protocol)
