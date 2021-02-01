---
title: "Home"
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
  - excerpt: 'Graduate from Kings College London and passionate about real world problem solving, with experience in fields as diverse as machine learning, engineering and electronics'
feature_row:
  - image_path: assets/images/radar_in_hand.jpg
    alt: "ars 408 radar"
    title: "ARS408 Radar"
    excerpt: "Experiments with canbus radar"
    url: "/ars-408-radar/"
    btn_label: "More"
    btn_class: "btn--primary"
  - image_path: /assets/images/working_on_twizy.jpg
    alt: "twizy"
    title: "Automatic Braking"
    excerpt: "Giving a twizy computer controlled braking"
    url: "/twizy-braking"
    btn_label: "More"
    btn_class: "btn--primary"
  - image_path: /assets/images/BEV.png
    alt: "ars408 bev"
    title: "Birds Eye Radar"
    url: "/birds-eye-view/"
    btn_label: "More"
    btn_class: "btn--primary"
---

{% include feature_row id="intro" type="center" %}

{% include feature_row %}
