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

<div class="imgcap">
<img style="max-width: 450px; max-height: 650px" src="/assets/fanuc_retrofit/shipped.png">
</div>

The "compatible" AMT212B from ODrive is more expensive than when purchased from other suppliers, and adds a substantial amount of BOM cost. I may try a [magnetic encoders](https://docs.odriverobotics.com/v/latest/articles/magnetic-encoders.html) in the future like the AS5600, MA702 or 14 bit AS5048, which would be a double win if I can also use a driver with an encoder built in. I would need reassurance that there is enough precision though, as well as things like [harmonic compensation](https://docs.odriverobotics.com/v/latest/manual/hardware-config.html#harmonic-compensation) that ODrive has.


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
</div>

For control I considered something integrated like the [MJBots hat pi hat](https://mjbots.com/products/mjbots-pi3hat-r4-5) but wanted to be able to run ROS2 and a Foxglove like interface. I have had experience with NVidia products at work and due to them being discontinued, found a very cheap Jetson Xavier used. It turned out to be an absolute pain to work with, as I had remembered from work, and I ended up on a different option: a fully fledged PC with a CAN-FD card. A USB [CAN-FD](https://canable.io/) is also an option

<div class="imgcap">
<img style="max-width: 450px; max-height: 750px" src="/assets/fanuc_retrofit/final_setup.jpg">
</div>


A lidar and camera system is used for control and planning:

<div class="imgcap">
<img style="max-width: 650px; max-height: 550px" src="/assets/fanuc_retrofit/livox_temp.png">
</div>