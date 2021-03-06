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
  caption: " "
excerpt: "Computer Scientist working on advanced safety and autonomy solutions for rail vehicles at OTIV.ai"
intro: 
  - excerpt: 'Graduate from Kings College London passionate about prototyping, real world problem solving with hardware and software.'
feature_row:
  - image_path: assets/images/thumbnails/v1_complete.jpg
    alt: "Sensor suite"
    title: "Prototyping"
    excerpt: "Automated braking and innovative shunting solution"
    url: "/prototyping_home/"
    btn_label: "Explore prototyping"
    btn_class: "btn--primary"
  - image_path: /assets/images/thumbnails/working_on_twizy.jpg
    alt: "twizy"
    title: "Hardware & Electronics"
    excerpt: "Radar, LiDAR, Cameras, wireless video transmission"
    url: "/hardware_home"
    btn_label: "Explore hardware"
    btn_class: "btn--primary"
  - image_path: /assets/images/thumbnails/disparity_traffic_image.png
    alt: "software"
    title: "Software & ML"
    excerpt: "Software development, data visualisation and image recognition"
    url: "/software_home/"
    btn_label: "Explore software"
    btn_class: "btn--primary"
---

{% include feature_row id="intro" type="center" %}

{% include feature_row %}