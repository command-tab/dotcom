---
layout: post
title: How to Find the Right Windows Driver
---
When setting up a new Windows machine, whether it's Windows 2000 all the way up through Windows 7, you'll occasionally run into an issue where you need drivers for a system or PCI device that you just can't seem to find. To make matters worse, you don't know which company made the device, so you don't even know where to start looking for drivers. Should you go to Dell's site? The motherboard manufacturer? Persistent "Unknown device" entries in the Windows Device Manager are a plague upon even the most seasoned techs. Here's a tip to get your driver hunt moving in the right direction.

**Find Out Who Made the Device**

Figuring out which company made the device(s) in question is the first step towards getting it working. Start by opening the Windows Device Manager. My preferred quick way of doing this is clicking Start, Run, type `devmgmt.msc`, and pressing Enter. Once there, choose the device in question and right click it, and select Properties. Select the Details tab to see something like the view below:

![windows device manager](/static/windows_device_manager.jpg)

Note the PCI `VEN` and `DEV` 4-character identifiers. PCI, USB, and many other system devices have Vendor and Device IDs. The Vendor ID is specific to the manufacturer, like Broadcom or nVIDIA. The Device ID is specific to the particular make or model of device you have. These are expressed in hexadecimal (0 through 9 plus A through F), so don't be surprised to see letters there, as well. Some common Vendor IDs are `8080` and `8086` for Intel, `0A5C` for Broadcom, `10DE` for nVIDIA, `1002` for ATI, and [many more](http://www.pcidatabase.com/reports.php?type=tab-delimeted).

**Look Up Vendor and Device IDs**

A common way to express both the Vendor and Device IDs in a single string is 1022:2000, Vendor ID first. Combine your Vendor and Device IDs in this manner, and wrap it with quotes: "1022:2000". Google that, and you should quickly figure out who made your "Unknown device" and what model it is. With this knowledge, you can either find the appropriate driver on your computer manufacturer's website (Dell makes a good note of which manufacturer's devices they use for a particular system), or you can visit the device manufacturer's website directly.

I hope this information can help those looking to simply get their hardware working under Windows, whether it's running on a Mac or PC.
