#Catkin入门

##1.[概念总览](http://wiki.ros.org/catkin/conceptual_overview)
###1.1 Catkin概览
1. [x] ROS的官方编译系统, 之前使用的是_rosbuild_.
2. [ ] 名称由来: `catkin` 意为`柳絮`,因其开发公司`Willow Garage`的名字意为`柳树车库`

###1.2 编译系统(Build System)
1. [x] 编译系统从源代码生成目标制品(target)来给用户使用
2. [x] 生成目标可以是: 库文件, 可执行程序, 生成的脚本文件(scripts), 导出的接口(如C++头文件) 或任何非静态源码的制品。
3. [ ] 其他编译系统：
    - 基于控制台(console)的编译系统: 
        - [GNU Make](http://www.gnu.org/software/make/)
        - [GNU Autotools](http://www.gnu.org/software/autoconf/)
        - [CMake](http://www.cmake.org/)
        - [Apache Ant](http://ant.apache.org/) (主要用于Java)
    - 集成开发环境(Integrated development environment, IDE), 通常是基于上述使用控制台命令的编译系统，并为之提供图形界面(GUI)。:
        - Qt Creator
        - Microsoft Visual Studio
        - Eclipse
4. [ ] 需要提供给编译系统的信息:
    - 工具链各部分的位置(如C++编译器的位置)
    - 源码位置
    - 代码依赖(dependency，指开发者自己写的代码内部的依赖，如C/C++头文件，python库等)
    - 外部依赖(引用第三方库)
    - 依赖对象的位置(如头文件和链接库的位置)
    - 需要编译的目标(target)
    - 生成目标的位置
    - 安装目标的位置
