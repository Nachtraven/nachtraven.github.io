---
title: "Twizy Braking"
excerpt: "Achieving automated braking"

sidebar:
  title: "Twizy Braking"
  nav: Twizy Braking

classes: wide
---


# Autonomous Twizy
## Letting the computer drive: Computer controlled braking for a Renault Twizy


Within otiv.ai advanced driver assistance and monitoring for trams is being developped. In order to demonstrate the technology to investors, a platform is required to run our tests on.
In this section we will explore the steps, items and tools necessary to perform this conversion.

Feel free to contact me via my [Github](https://github.com/Nachtraven) or [Linkedin](https://www.linkedin.com/in/sean-nachtrab-14175715a/) if you require help or want me to do these steps for you.

![An afternoon of fiddling](/assets/images/working_on_twizy.jpg)

The show (or in this case, twizy) stopping result

![The final result](/assets/images/braking.gif)


The main elements are an electronic braking system detailed under Twizy Braking and a series of 3d printed parts that hold the camera and radar to the vehicle, photo below. Additionally, an aluminium frame is built in the space occupied by the rear seats in order to hold a battery and computer used for testing.

![Twizy with accessories](/assets/images/niels_twizy_testing.jpg)


## The build


We aim to implement a system of computer controlled brakes.

In order to achieve this we utilised [OSCC's github](https://github.com/PolySync/oscc/wiki/Hardware-Brake-%28Petrol%29) as a starting point for our work.

![Prius Brake Module](/assets/images/brake_module_prius_small.jpg)

A 2004-2009 prius braking module is used. The diagram allows us to identify the main paths for brake fluid and necessary 

![Pinout diagram](/assets/images/brake_pinout.png)


Our goal is to have the front brakes lock up fully, ignoring the rear and leaving them mechanically connected to the main brake pedal and handbrake as from the factory.

We begin by dissasembling the front endread:

![Twizy front end fully](/assets/images/font_fully_dissasembled.jpg) 

![Twizy braking module positionning](/assets/images/module_positionning.jpg) 

Mounting the module and routing the brake lines was not easy but it ended up solidly in place, with fittings purchased at a toyota dealership
Bleeding the brakes was necessary.

Wiring a new loom and to control it, relays were used.

![Relays](/assets/images/relays.jpg) 

Not very pretty looking but we're prototyping here. For control, 10a relays are utilised. For SMC1/SMC2 safety, SLAFL/SLRFL fill ports and SLRFL/SLRFR empty ports the ground path is interrupted (Note: the positive for SMC1/2 solenoids comes from BSC1/BSC2). 3 ohms of resistors are added in order to lower the current consumption. 

Using arduino [standard firmata](https://www.arduino.cc/en/reference/firmata) allows us to write code in python to control the arduino outputs, thanks to the relays the computer and arduino are totally isolated from the 12v of the braking system.

After all this it is time to put the twizy back together and have a real world test! Some cutting of the twizy plastics on the front end were necessary, but once back together it is completely invisible from the outside.

The total time from beginning to end was about two weeks or 60ish hours, including the delays caused by difficulty finding the right brake lines, having to order a second pump in order to acquire a fill port, creating the wiring looms and experimenting with different ways of controlling the solenoids and pump.
