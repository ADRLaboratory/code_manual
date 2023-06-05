---
title: rc_visard
layout: default
parent: ROS 2
nav_order: 2
---

# rc_visard

The [rc_visard] is an RGBD camera family created and sold by [Roboception]. We will be using their drivers to interface with ROS and retrieve perception data.

## Setup

Make sure you have [ROS 2] installed and set up.

Create a new workspace directory in your user home folder. In this guide we will use `rc_visard`.

Clone the following repositories (`git clone <URL>`) to this workspace:

```
https://github.com/roboception/rc_genicam_api
https://github.com/roboception/rc_common_msgs_ros2
https://github.com/roboception/rc_genicam_driver_ros2
```

Run `colcon build`.


[rc_visard]: https://roboception.com/en/rc_visard-en/
[Roboception]: https://roboception.com/en/
[ROS 2]: ros2.html
