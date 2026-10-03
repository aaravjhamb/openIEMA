---
title: "openIEMA"
author: "Aarav J"
description: "An Open Source, In Ear Monitor Amplifier built as an alternative to the Behringer P2 with dual headphone outputs driven from a mono balanced XLR input, with onboard LiPo power and USB-C charging!!"
created_at: "2026-10-03"
---

# 2026-10-03: Day 7 - (3/10/26) - Github files + JLC quote

**Total time spent: 1.5 hours**

# Day 7

Quick things today, I did this yesterday but I'm devlogging today


I spent a bit of time organising everything into the right folders and it looked like this

![image.png](https://cdn.aaravj.tech/files/31e1d222-b7db-418a-9260-c3628044ddad/image.png)

I then wrote my github readme and uploaded all the files to GH with some readme polish!

# Time spent : 1.5 hours


With that the entire project is done :DD total time spent was 



# 2026-10-03: Day 6 (2/10/26) - Blender Renders

**Total time spent: 7 hours**

# Day 6

pcb done!! now It was time to make blender renders :D

To do this I first installed the pcb2blender kicad plugin!
![image.png](https://cdn.aaravj.tech/files/eec2f13d-56ab-426d-a4d2-836d5d2a9e0a/image.png)


This allows me to take my PCB directly from KiCad and import it into blender using the companion extenion in blender. Once I imported it in blender it looked something like this

![image.png](https://cdn.aaravj.tech/files/bf11acb1-d422-4549-affe-d05af5b9bd3a/image.png)


I then whent to the shading settings and changed the solder mask colour to black and adjusted the strength aswell as changing the surface finish to enig!
![image.png](https://cdn.aaravj.tech/files/d5bb8dcf-bb25-4cfe-ae7f-43648832bdc4/image.png)


once this was done, I whent down to the world icon and set the environment to studio and downloaded this HDRI pack called "wooden_studio_08_4k" that basically handled the lighting and bg for me!

![image.png](https://cdn.aaravj.tech/files/b51f3d02-a7fd-45d0-b16e-bf18935d5dce/image.png)

After that I clicked N and opened the view panel to set my camera view
![image.png](https://cdn.aaravj.tech/files/26baebff-075b-4d01-b4e1-579cc62c4c67/image.png)
And then locked the object to camera view so I could recenter the PCB with the camera locked!

Once I recentered I whent into view > align > align camera to current view which allows me to set the current view as the camera's view!

![image.png](https://cdn.aaravj.tech/files/80b9797c-cb47-4079-acf9-2951417e6017/image.png)

Then I clicked Z and 8 to get a test render

![image.png](https://cdn.aaravj.tech/files/58561892-3a6c-401a-83d7-800c3f3b7003/image.png)

Finally once I was happy with this I clicked render and let it render with this being the final result!


![openIEMA.png](https://cdn.aaravj.tech/files/b9ec0a43-f817-47bf-8ae5-323921478136/openIEMA.png)


All of this took me quite a while with multiple tries as this is my second time using blender and its certainly a difficult software to understand

Time Spent : 7 hours

# 2026-10-03: Day 5 (2/10/26) - Started PCB

**Total time spent: 6 hours**

# Day 5

To make the PCB I first imported all the components from the schematic

![image.png](https://cdn.aaravj.tech/files/416b297d-7261-4d30-b286-6e525f37bb3c/image.png)


Then I did the PCB layout

![image.png](https://cdn.aaravj.tech/files/7091d00d-b54f-45b2-bbae-2c761adbbb3a/image.png)

I tried to place components as close as possible and ensure that routing wouldn't be too crazy so this took ~3 hours with me redoing the board 3 times. I then added the ground pour on both layers and decided to go with a 2 layer board as 4 layers is overkill imo

![image.png](https://cdn.aaravj.tech/files/c69e83e8-c8c1-45d0-822e-6b6bb01d2768/image.png)

Then I spent a bit doing routing

![image.png](https://cdn.aaravj.tech/files/1ed9af9e-c1c7-4652-b790-682dacebf8c7/image.png)
And while doing routing I tried to keep the trace widths and lengths as optimized as possible!

I don't have pictures of my rerouting verions however I do have a 3d model of my old PCB vs new layout!

v1 - 
![image.png](https://cdn.aaravj.tech/files/5de21702-a6a2-4a4b-9466-9ab978a55a39/image.png)

v2 - 
![image.png](https://cdn.aaravj.tech/files/393ab829-d7bb-4db0-a308-5a246ee20600/image.png)


# Time Spent : 6 hours

# 2026-10-03: Day 4 (1/10/26) - Assigning footprints

**Total time spent: 1.5 hours**

# Day 4

Spent a couple hours assigning footprints, there's not much to say lol

![image.png](https://cdn.aaravj.tech/files/55f89b16-02f8-46d4-bdf0-434b9a4432dc/image.png)

![image.png](https://cdn.aaravj.tech/files/3ff970c0-ea60-4944-8b5a-e3fd3fd0a8a0/image.png)

# Time spent : 1.5 hours

# 2026-10-03: Day 3 (30/09/26) - Schematic Continuation

**Total time spent: 9 hours**

# Day 3

more journal shennanigans!!! devlogging for two days

first thing I did today was get started on the voltage divider. this is required as the project has a stable +5v supply coming from +5vA however audio works in the negatives aswqell. Our target is to make the waveform clip at 0v however right now 5/2 is 2.5 so I need to create a voltage divider to allow it to swing betweeen -2.5v and +2.5v

This can be achieved simply by using 2 10k resistors like this

![image.png](https://cdn.aaravj.tech/files/7f392ffa-4b6f-46b1-ae8f-de1c8aa7d894/image.png)


After this I need to design the Unity Gain Buffer. This put simply takes 2.5v in from the  voltage divider and turns it from a weak signal to a stronger signal. This can be achieved using the OPA1678 chip which is a 3 part chip.

Part A (the main part) copies the dividers 2.5v to its output and holds it strong and stable so the rest of the circuit can use it and it looks something like this.

![image.png](https://cdn.aaravj.tech/files/4388793a-844a-44f3-8131-6eb5ba968055/image.png)


The next part (U3B) uses the same chip btu a different symbol and is called the difference amplifier. This basically takes the 2 XLR signals (hot and cold) and subtracts one from the other to remove cable noise and cleanms the audio to about 20db, this is important if I want to get clear sound and looks something like this


![image.png](https://cdn.aaravj.tech/files/f51e176d-639f-4230-851c-8a08d4471bf7/image.png)

The last and final part of the chip is pretty simple, the chip needs some way to power it and to do that I can use U3C which is the power input of the chip!


![image.png](https://cdn.aaravj.tech/files/f360a2a9-29f4-4801-81be-737c64a866d8/image.png)

It's pretty simple and just takes our cleaned 5va, with a decoupling cap to GND and v- going to ground!

That's the hard part done!! Now I can move onto the fun part's - volume control and sound output but before I move on I actually need to design the XLR input circuit! 

![image.png](https://cdn.aaravj.tech/files/0194f6cb-bc1b-40cb-8f1f-b6874c19be0e/image.png)

This basically takes the XLR input and shoves it through a diode to prevent backflow and gives the two outputs that then input into the difference amplifier!


Now it's time for the audio volume control! I can achieve this using a potentiometer and 2 LED's that clip the signal such as the high peaks that kill your ears

![image.png](https://cdn.aaravj.tech/files/173f9547-d159-4b99-ae93-82875e5b2632/image.png)

This also provides accurate volume control going out to the HAC (headphone amplifier circuit) chip
 


![image.png](https://cdn.aaravj.tech/files/b1f32c5d-58ef-458a-93d5-7141cb4ed442/image.png)


Finally to finish off I added the two headphone jacks,
![image.png](https://cdn.aaravj.tech/files/508c8f61-ba59-4651-af0a-1adf2015b54c/image.png)
 and some tespoints and power LED's



once all done, it looked something like this!

![image.png](https://cdn.aaravj.tech/files/2ad4cc7f-ff0e-4ca5-8515-65ebfd751b3d/image.png)


Now I can move onto the PCB once I assign footprints

# Time spent : 9 hours

# 2026-10-03: Day 1 - Started Schematic

**Total time spent: 5 hours**

# Day 1

guess who forgot to journal!!! anyway I'm setting out to build an open source IEMA or In Ear Monitor Amplifier for short
I want to build this as an alternative to the Bereginer C2 as that is a bit costly and doesn't have some features I want

To get started I'm going to be making this project as a fully analog circuit!! since this is my first time I'm going to have to understand how sound engineering works(fun)

my first step was to add USB C with the usual setup like so

![image.png](https://cdn.aaravj.tech/files/bec71ece-c1fc-4c09-911e-ed1c63337f2c/image.png)

This is just a simple USB C PCB implementation that has 2 5.1k resistors to invoke the USB C power protocol + a power flag so kicad stops yelling at me and a simple decoupling cap placed on vbus for stability!


The next step was to add a battery charging circuit and do some research for the chip + the battery capacity and time I wanted the device to operate. My first thoughts was to use the TP4056 charging module but I wanted to go with something new and easier and more efficient to operate so after consulting my [boss] claude I decided to go with the MCP73831-2-MC chip. 

I then whent throughout the [datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/MCP73831-Family-Data-Sheet-DS20001984H.pdf) and tried to find an example circuit that looked somethinig like this


![image.png](https://cdn.aaravj.tech/files/6ddaf353-0e14-45aa-b28d-e2ce7569709c/image.png)

I imported it into kicad and made a circuit that looked something similar to this


![image.png](https://cdn.aaravj.tech/files/31abd0cb-3fe1-4c75-aff8-d384cb3919f9/image.png)

This circuit is pretty simple and in essence here's what the pins do

#### Pin 8
 - Programming pin for charging speed, putting a 2k resistor charges the battery at 500mah for a 1k cell
#### Pin 6
  - ground :D
#### Pin 2
- +5v Power
#### Pin 3
- Battery input/output basically where the chip will charge and send power to the battery
#### Pin 5
 - Status LED for when the battery is charging!

Overall pretty simple so time to move on.

The next step was to implement a battery boost converter considering our battery will only be sending ~3.7v on a full charge and ~3v when it's empty however our circuit needs a steady 5v with no fluctuatioins and noise

To do this I'm going to use the TPS61023DRLR chip as a step up voltage circuit implemented like so


![image.png](https://cdn.aaravj.tech/files/90fe90a6-01ef-444a-b5c3-d16de3cb1f7a/image.png)

This circuit is a combination of capacitors for decoupling and a ferrite bead to get a clean and desnoised +5vA input that will be used for the soujnd circuitry later on.


with that I'm going to finish today's devlog as I'll work on the rest tommorow!

# Time spent : 5h

