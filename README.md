# ros2-triggered-recorder
该程序用于L4自动驾驶车辆研发过程中的数据录制，基于ros2+fastdds消息中间件，可对传感器数据及模块间ros2消息的进行缓存和触发式录制 ，模块进程间默认使用udp作为ros消息的传输方式，保证收发效率，针对大消息和跨机传输，程序作了如下优化以降低丢帧率：
- 使用共享内存的方式，在同设备的进程间传输传感器（图片、点云）等大消息，保证大消息的收发效率，降低链路延迟；
- 使用tcp作为跨设备的、大消息的传输方式，保证跨机传输不掉帧；
- 录包主模块（负责消息缓存、压缩、写入等）部署在外接设备中；
- 录包子模块（负责消息打包转发）部署在ADU上，并保证30%以下的CPU占用和极低的内存占用；


![alt text](https://github.com/XH-Yang-archive/ros2-triggered-recorder/blob/main/figures/demo_figure.png?raw=true)


程序的软件架构如下图所示：
![alt text](https://github.com/XH-Yang-archive/ros2-triggered-recorder/blob/main/figures/demo_figure2.png?raw=true)

