---
title: "Sean Nachtrab"
layout: splash
permalink: /home/
date: 2020-03-23T11:48:41-04:00
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/collage.jpg
  actions:
    - label: "Projects"
      url: "/projects/"
  caption: "Collage"
excerpt: "Computer Scientist working on advanced safety and autonomy solutions for rail vehicles at OTIV.ai"
intro: 
  - excerpt: 'Graduate from Kings College London and passionate about real world problem solving, with experience in prototyping, hardware and software.'
feature_row:
  - image_path: assets/images/thumbnails/niels_twizy_testing.jpg
    alt: "ars 408 radar"
    title: "Prototyping"
    excerpt: "Automated braking, turning, driver assistance"
    url: "/prototyping_home/"
    btn_label: "Explore prototyping"
    btn_class: "btn--primary"
  - image_path: /assets/images/thumbnails/working_on_twizy.jpg
    alt: "twizy"
    title: "Hardware & Electronics"
    excerpt: "Radar, lidar, wireless video transmission"
    url: "/hardware_home"
    btn_label: "Explore hardware"
    btn_class: "btn--primary"
  - image_path: /assets/images/thumbnails/disparity_traffic_image.png
    alt: "software"
    title: "Software & ML"
    excerpt: "Data visualisation, python development and image recognition"
    url: "/software_home/"
    btn_label: "Explore software"
    btn_class: "btn--primary"
---

{% include feature_row id="intro" type="center" %}

{% include feature_row %}
