---
title: "LiDAR and a sensor suite"
excerpt: "LiDAR learnings and building a sensor suite"

sidebar:
  title: "LiDAR and a Sensor suite"
  nav: LiDAR and a Sensor suite
  title: "Lidar images"
  nav: Lidar images
  title: "Mounting"
  nav: Mounting
  title: "Final iteration"
  nav: Final iteration
toc: true
toc_label: "LiDAR"

classes: wide
---


# LiDAR and a Sensor suite
## Adding a sensor suite to our self braking twizy and testing LiDAR

A livox horizon was used with our own API.

![A lidar](/assets/images/lidar_hardware.jpg)

Speaking of LiDAR, this MID-70 model from Livox was very poor

![A Bad lidar](/assets/images/bad_lidar.jpg)

## Lidar images

The images the horizon produces

![Indoor LiDAR](/assets/images/lidar_indoors.jpg)

![Railway LiDAR](/assets/images/lidar_otiv_railway.jpeg)

Compared to stereo vision with a disparity map, it is a world of difference

![Disparity](/assets/images/disparity_traffic_image.png)

## Mounting

Now to mount it on our self braking twizy (Check out the other post about braking)

Dual cameras for testing different lenses as well as the aformentioned stereo vision algorithms

![Sensor suite](/assets/images/sensor_suite.jpg)

![Sensor suite on twizy](/assets/images/sensor_suite_twizy.jpg)

![Mounted on twizy](/assets/images/twizy_mounted.jpg)

# Final iteration

This lidar turned out to be quite average, a change was made to a superior ouster model and surround cameras worked well enough on our RSS prototype that we chose to implement these in too.

![Proto of sensor suite](/assets/images/sensor_suite_proto.jpg)

This gave us a solid 180° fov with high density lidar point cloud at 10+ fps

![Proto of sensor suite](/assets/images/lidar_example.png)

Quick example of the raw LiDAR results. For more, see BEV planning