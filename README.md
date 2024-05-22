# ros2-triggered-recorder
This program is developed for buffering and storage of ros2 data in autonoumous vehicles. It supports:
- udp as default interhost/interprocess communication protocol for small topics with the consideration of efficiency,
- shared memory for interprocess communication to transfer large data,
- tcp for interhost communication of large data due to the request of the reliable delivery.

![alt text](https://github.com/XH-Yang-archive/ros2-triggered-recorder/blob/main/demo_figure.png?raw=true)
