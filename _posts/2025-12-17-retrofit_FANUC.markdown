---
layout: post
comments: false
title: "Retrofit - FANUC Robot arm"
excerpt: "Retrofit of FANUC Lr Mate 200 iL with ODrive"
date:   2025-12-17 19:00:00
mathjax: false

featured: true
featured_rank: 1
featured_image: /assets/fanuc_retrofit/final_setup.jpg
featured_alt: "Fanuc motor ODrive control WIP"
---

[Previously mentioned in this blog post, my LR Mate 200 il Fanuc arm](https://nachtraven.github.io/2024/11/12/FANUC/) is now in the process of being retrofitted to be ran with modern electronics and controls, in parallel with a LiDAR and camera system.

As a reminder, here is the datasheet:

<div style="display: flex; flex-wrap: wrap; gap: 10px; margin: 20px 0;">
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/fanuc/fanuc_lr_mate_200i_datasheet-1.png">
  </div>
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/fanuc/fanuc_lr_mate_200i_datasheet-2.png">
  </div>
</div>

After getting very familiar with open loop steppers, and building [Arctos](https://arctosrobotics.com/) a plastic 3D printed stepper driven arm, I wanted to try servos with a closed loop and FOC.

### Motor controller

I selected the ODrive S1 to prototype the arm, and to keep things simple I'm experimenting with their "upgraded" 16384 CPR AMT212B shaft encoder instead of going the cheaper magnetic route. I was happy to see separate mosfets, and a braking resistor, as I did not know if my motors would be thermally limited. I remember when the project used to be open source, but if it works with less hassle than the failed previous times I wanted to control a three phase motor I'll be happy.

I compared the ODrive with some alternatives like:
- MJBots Moteus C1/R4/N1/X1 - probably the closest to what I wanted
- SimpleFOC - not "commercialized" and but these were more difficult to stack axes, less robust, lower voltage
- VESC but out of budget and overkill
- Tinymovr M5.2 - but limited to 38v
- MIT Mini Cheetah - eaten by others in this list, and I don't know if I trust aliexpress sellers
- Some Makerbase aliexpress drivers, but I wanted to help fund further development since my use case is a bit outside of the usual drone motors

There are also some open source projects on hackaday/github, but where the driver felt like the project:
- [Dagor](https://www.dagor.dev/)
- [VESCular6](https://dongilc.gitbook.io/openrobot-inc)

And some interesting similar projects for integrated modules:
- [Robot actuator module](https://kreier.github.io/actuator/)

---

Once the decision was made, I emailed ODrive asking for confirmation if it would likely work.

<div class="imgcap">
<img style="max-width: 450px; max-height: 450px" src="/assets/fanuc_retrofit/shipped.png">
</div>

**Disclaimer:** When I reached out to ODrive, I asked if they would be interested in offering a discount code in exchange for the publicity of this post/linkedin/tutorials, which they accepted. No money exchanged hands and I still paid multiple hundreds of euros for all the parts. My opinions here and elsewhere were not reviewed by ODrive before posting.

<div style="display: flex; flex-wrap: wrap; gap: 10px; margin: 20px 0;">
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/fanuc_retrofit/shaft.jpg">
  </div>
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/fanuc_retrofit/shaft_roller.jpg">
  </div>
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/fanuc_retrofit/shaft_encoder.jpg">
  </div>
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/fanuc_retrofit/final_setup.jpg">
  </div>
</div>

The first motor was wired up for bench testing; for the encoder I used the "compatible" AMT212B directly from ODrive, unfortunately it is more expensive than when purchased from other suppliers and adds a substantial amount of BOM cost. I may try the built in encoder or an external [magnetic encoder](https://docs.odriverobotics.com/v/latest/articles/magnetic-encoders.html) like the AS5600, MA702 or 14 bit AS5048. I would need reassurance that there is enough precision though, as well as things like [harmonic compensation](https://docs.odriverobotics.com/v/latest/manual/hardware-config.html#harmonic-compensation) that ODrive has.

Assembly of all the parts is greatly simplified by having the right tools. Over the years, I've acquired a lot of crimping "sets" as well as some tools of varying quality, but that did not prevent the absolute headache that is JST crimp connectors. [This is a useful explanation of JST connectors from IOT Expert](https://iotexpert.com/jst-connector-crimping-insanity/).

Once all assembled and wired for a single ODrive using a USB isolator and following the [Getting Started guide](https://docs.odriverobotics.com/v/latest/guides/getting-started.html), the motor spins!

<div class="imgcap">
<img style="max-width: 850px; max-height: 650px" src="/assets/fanuc_retrofit/compressed_motor_gif_odrive">
</div>

---

### Software control

For software control there are multiple avenues. The one I am most familiar with, before doing any research, is ROS2, and I wanted good 3D visualizations in something like Foxglove. Commands are sent for the moment over CAN to the motors

Foxglove is an excellent method for visualizing from ROS, although they moved away from being opensource/free. ROS also has some tutorials for 6 axis robotcs:
- [6 Axis robot in ROS](https://control.ros.org/rolling/doc/ros2_control_demos/example_7/doc/userdoc.html)
- [ROS in Foxglove Studio](https://docs.ros.org/en/foxy/How-To-Guides/Visualizing-ROS-2-Data-With-Foxglove-Studio.html)
- [There also exists a ROS2 controller for ODrive](https://github.com/Factor-Robotics/odrive_ros2_control)
- [And a Python robotics controller](https://github.com/petercorke/robotics-toolbox-python)

Before starting I had also learned that Reprapfirmware has inverse kinematics for 6 axis arms, although this seemed like a less well supported direction to head in:
- [Robot industrial 6 axis](https://docs.duet3d.com/User_manual/Machine_configuration/robot_industrial_6_axis)

### Moving the arm

Once I had tested the ODrive S1 with the on axis encoder, as well as the built-in magnetic encoder of the two drivers I bought, I placed them into the arm for some tests, as I do not have the budget at the time of writing to purchase all the controllers required for all the axis.