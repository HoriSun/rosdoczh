##ROS的运行架构
1. 使用publish-subscribe的消息分发方式，topic为消息池，发出和获取消息的程序单元称为node。
   使用rostopic命令查看和手动发送消息。
2. 使用xml格式的.launch文件描述模块加载的参数，并利用launch文件的相互包含，实现按顺序
   加载依赖模块，但加载时是异步的，有时会出现模块在其依赖加载完成之前已经就绪的情况，导致出错。
   使用roslaunch命令载入package里的launch文件。
3. 使用rosrun运行package里的程序，   
