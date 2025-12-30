---
layout: post
comments: false
title: "Voron V0 volcano hotend"
excerpt: "3D printer engineering: voron V0.2 and custom toolchanger"
date:   2024-01-12 20:00:00
mathjax: false

featured: true
featured_rank: 2
featured_image: /assets/jubilee-3D-printer/voron.jpg
featured_alt: "Voron 0.2 with upgrades"
---

For my Voron V0, I chose to rebuild a secondhand kit and upgrade it with high CRI LEDs for the bed and hotend, a volcano hotend, bimetallic heatbreak, LGX lite and a full sized hat. Most interesting is the volcano hotend on a voron V0.2, so I focus on that:

<div class="imgcap">
<img style="max-width: 450px; max-height: 300px" src="/assets/jubilee-3D-printer/og_printer.jpg">
</div>

The original had a lot of problems, so many parts were swapped and upgraded.

<div class="imgcap">
<img style="max-width: 450px; max-height: 300px" src="/assets/jubilee-3D-printer/volcano.jpg">
</div>

Starting from a regular volcano, with an upgraded bi-metallic heatbreak, I sawed off the upper section closest to the mounting head. Two holes are then drilled and tapped, and one side needs to be sanded down (after tapping to ensure the orientation) 

<div style="display: flex; flex-wrap: wrap; gap: 10px; margin: 20px 0;">
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/jubilee-3D-printer/hotend_bimetal.jpg">
  </div>
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/jubilee-3D-printer/heatsink.jpg">
  </div>
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/jubilee-3D-printer/heatsink_sanded.jpg">
  </div>
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/jubilee-3D-printer/hotend_assembled.jpg">
  </div>
</div>

LEDs were added to the head, the electricals were upgraded and a full sized hat was added using 2020 extrusions, as well as a chamber thermostat. Both essential in my opinion as it allows to heatsoak before a print. 


<div style="display: flex; flex-wrap: wrap; gap: 10px; margin: 20px 0;">
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/jubilee-3D-printer/hoted_leds.jpg">
  </div>
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/jubilee-3D-printer/final_hotend_pos.jpg">
  </div>
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/jubilee-3D-printer/elec_panel.jpg">
  </div>
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/jubilee-3D-printer/voron.jpg">
  </div>
</div>

Has some VFA

<div class="imgcap">
<img style="max-width: 450px; max-height: 450px" src="/assets/jubilee-3D-printer/vfa.jpg">
</div>

---

Wanting something custom and enjoying the process of design and engineering, as many others have, I wanted to make my own 3D printer. I've owned quite a few, and wanted my own Toolchanger after seeing the E3D announcement. I knew nothing of CNCs or machine design, didn't know how to CAD, and blindly went forward.

I started independently in late 2020, and then found the (at the time) developping [Jubilee project](https://jubilee3d.com). The [E3D toolchanger](https://e3d-online.com/blogs/news/toolchanger-the-update-youve-all-been-waiting-for) was really the first "commercial" printer of the kind, but unfortunately was half baked and with little information online. The people buying them were not people making online content.

Initial specs for my machine were a print space of 40x40x40cm, with 4-6 tools. The design for manufacturing goal was to use 2020 and 2040 alu extrusions, possibility of enclosing, no 3D cnc parts and minimize 3d printed part use. I did not want to go the voron/usual 3D printer route of tons of extrusions, and really liked the idea of the E3D design of keeping everything on one thick flat plane thanks to the alu, but instead of pursuing this fully, I tried to do a halfway house using waterjet cut aluminium plates. In retrospect, this was not thought through enough, nor did I allocate the required budget to get it done properly.

<div class="imgcap">
<img style="max-width: 450px; max-height: 300px" src="/assets/jubilee-3D-printer/3D_diy/waterjet.jpg">
</div>

The machine design was driven by the goal of using waterjet cut aluminium plates, focusing on accurate CoreXY belt alignment, and regular hardware.

<div style="display: flex; flex-wrap: wrap; gap: 10px; margin: 20px 0;">
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/jubilee-3D-printer/3D_diy/plates.jpg">
  </div>
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/jubilee-3D-printer/3D_diy/align2.jpg">
  </div>
</div>

I unfortunately cheaped out, didn't use thick enough stock, nor did I cut the whole flat plane and instead tried to use the plates as connectors. Bad idea, everything should have been one plate, and the bed could have come out of that same piece! I also learned a lot about machine design by repeatedly buying cheap or the wrong parts. Did you know these should have a metal core if under constant tension? And that there are recommended ways of clamping to avoid relying on the metal to rubber link to maintain tension? They're also cut from a drum, so are naturally not perfectly aligned! You need particular spacing/tollerance, and tight idlers destroy belts.

Belts are also known to have different vibrations based on size, and sometimes smaller can be better! Example of a bad vs a good belt, note the core:

<div style="display: flex; flex-wrap: wrap; gap: 10px; margin: 20px 0;">
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/jubilee-3D-printer/3D_diy/bad_belt.jpg">
  </div>
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/jubilee-3D-printer/3D_diy/good_belt.jpg">
  </div>
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/jubilee-3D-printer/3D_diy/bent.jpg">
  </div>
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/jubilee-3D-printer/3D_diy/bent2.jpg">
  </div>
</div>

Bad parts like the above bent rod were also a pain and constantly caused difficult to diagnose issues.

The Jubilee [remote elastic twist lock (REL)](https://jubilee3d.com/index.php?title=The_Remote_Elastic_Lock) was an alternative to the motor-on-toolhead method of E3D, and it seemed a major improvement. I modified and re-used some aspects. In retrospect, it worked well, but wasn't worth the huge hassle and special parts to get it working.

<div style="display: flex; flex-wrap: wrap; gap: 10px; margin: 20px 0;">
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/jubilee-3D-printer/REL.jpg">
  </div>
  <div class="imgcap" style="flex: 1 1 45%; margin: 0;">
    <img style="width: 100%; height: auto;" src="/assets/jubilee-3D-printer/3D_diy/plastic_rel.jpg">
  </div>
</div>

The waterjet cut tool plates were a success though, and I ended up using these for other purposes with a manual REL.

<div class="imgcap">
<img style="max-width: 450px; max-height: 300px" src="/assets/jubilee-3D-printer/3D_diy/tool_plate.jpg">
</div>
During this time, the prusa design was also unveiled and released to the public.

Once working, I printed a few parts and took it apart. It was too big for its own good and, as was shown by Bambulab later, too focused on the machine aspect. I did not consider enough external factors like filament storage and especially drying (which I now do using spool dryboxes based on ikea cake tins, [a better design is available here](https://printables.com/model/829357-filament-dry-box-for-big-25kg-spools)) and slicing of models. 

I ended up after taking the DIY printer apart, owning a Jubilee, and an E3D toolchanger. I plan in the future to make my own enclosed printer with the learnings of this project, while learning more CAD.