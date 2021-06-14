---
title: "BEV planning"
excerpt: "Path planning from above"

sidebar:
  title: "BEV planning"
  nav: BEV planning
toc: true
toc_label: "BEV"
---


# BEV planning
## The world from above: utilising a lidar and camera to extract object point clouds for path planning


Employing a similar approach to our RADAR solution, a lidar top down view was created by colleagues.
We create bounding boxes/rail mask on a 2d camera image, project lidar points to this image and filter them based on the bb's and some secret sauce.
These points are then transfered to a top down view alongside an estimated path for the rails based on regressing a function through the points associated with these rails.

![BEV](/assets/images/BEV_12-05-2021-09-42-39_safe-zone.jpg)

Compared to 3DOD based purely on LiDAR, results are good but do present some framerate issues.
Our approach allows for a more explainable pipeline that is more easily troubleshooted and definitely needs improvement down the line once we have our own data collection pipeline.

![3DOD](/assets/images/3DOD_baumer_ouster0.jpg)

This model was originally trained for a different, less dense lidar and was repurposed for our ouster model.