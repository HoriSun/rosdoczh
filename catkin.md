#Catkin入门

##1.[概念总览 Conceptual Overview](http://wiki.ros.org/catkin/conceptual_overview)
###1.1 Catkin概览
1. [x] ROS Hydro和ROS Indigo的官方编译系统, 在Hydro之前使用的是_rosbuild_.
2. [ ] 名称由来: `catkin` 意为`柳絮`,因其开发公司`Willow Garage`的名字意为`柳树车库`

###1.2 编译系统(Build System)
1. [x] `编译系统`从`源代码`生成`目标制品(target)`来给用户使用

2. [x] 生成目标可以是: `库文件`, `可执行程序`, 生成的`脚本文件(scripts)`, 导出的`接口`(如C++头文件) 或任何非静态源码的制品。

3. [ ] 其他编译系统：  
    - 基于控制台(console)的编译系统:
        + [GNU Make](http://www.gnu.org/software/make/)
        + [GNU Autotools](http://www.gnu.org/software/autoconf/)
        + [CMake](http://www.cmake.org/)
        + [Apache Ant](http://ant.apache.org/) (主要用于Java)    
    - 集成开发环境(Integrated development environment, IDE)，通常是基于上述使用控制台命令的编译系统，并为之提供图形界面(GUI)。:  
        + Qt Creator
        + Microsoft Visual Studio
        + Eclipse

4. [x] 编译系统均需要一些配置信息来进行编译。基本配置方法有两种：
    1. 使用文本文件配置，举例：
        + `CMake`, 文件名`CMakeLists.txt`
        + `GNU Make`, 文件名`Makefile`
        + `Apache Ant`
    2. 使用IDE时，则将其存入工程的元信息(meta-information)里,如VC++的工程文件
    需要提供给编译系统的信息如下:
        + 工具链各部分的位置(如C++编译器的位置)
        + 源码位置
        + 代码依赖(dependency，指开发者自己写的代码内部的依赖，如C/C++头文件，python库等)
        + 外部依赖(引用第三方库)
        + 依赖对象的位置(如头文件和链接库的位置)
        + 需要编译的目标(target)
        + 生成目标的位置
        + 安装目标的位置  

5. [x] ROS所使用的catkin是扩展了CMake的编译系统，在CMake的基础上，具有管理ROS包(package)之间依赖关系的能力，但同时可以应用于ROS以外的项目编译————在设计之初，catkin就被设计为[独立于ROS](http://wiki.ros.org/catkin/conceptual_overview#Decoupling_from_ROS)而又兼容ROS的编译系统。   

    catkin提供了`catkin_create_pkg`命令，可以用它很方便地创建 package, 不必手动建立 `CMakeLists.txt` 和 `package.xml` 等文件。  
    
    操作示例：  
    ```sh
    >>> catkin_create_pkg beginner_tutorials std_msgs rospy roscpp
    ```  
    ```
    Created file beginner_tutorials/package.xml
    Created file beginner_tutorials/CMakeLists.txt
    Created folder beginner_tutorials/include/beginner_tutorials
    Created folder beginner_tutorials/src
    Successfully created files in /tmp/beginner_tutorials. Please adjust the values in package.xml.
    ```  
    ```sh
    >>> tree beginner_tutorials/
    ```  
    ```
    beginner_tutorials/
    ├── CMakeLists.txt
    ├── include
    │   └── beginner_tutorials
    ├── package.xml
    └── src
        
    3 directories, 2 files
    ```   
    
    其中生成的[`CMakeLists.txt`](https://github.com/HoriSun/rosdoczh/blob/master/CMakeLists.txt)里包含了注释掉的    标准`CMakeLists.txt`文件结构，在给项目增加编译选项时，只需略加修改。同时也要注意同步修改[`packages.xml`](https:    //github.com/HoriSun/rosdoczh/blob/master/package.xml)文件。packages.xml描述了这个`package`的一些基本信息，包含    名字、版本、维护者(`maintainer`)、证书(`license`)、编译时依赖的packages、运行时依赖的packages。 
       
    想更深入地了解catkin的依赖关系管理，参见catkin文档里的[`Dependency Management`](http://wiki.ros.org/catkin/conceptual_overview#Dependency_Management)。
       
    延伸阅读(英文)：
    + [使用catkin命令行工具建立package](http://wiki.ros.org/ROS/Tutorials/CreatingPackage)
    + [如何手动建立一个package](http://wiki.ros.org/ROS/Tutorials/Creating%20a%20Package%20by%20Hand)
    + [CMakeLists.txt介绍](http://wiki.ros.org/catkin/CMakeLists.txt)
    + [package.xml文件介绍](http://wiki.ros.org/catkin/package.xml)
    + [REP-0127 -- package.xml文件定义](http://www.ros.org/reps/rep-0127.html)
    
        > REP全称ROS Enhancement Proposal（ROS改进方案）, 类似于互联网领域IETF发布的RFC系列文档，用于提出并审议修改方案，不断优化ROS。
    + [caktin教程](http://wiki.ros.org/catkin/Tutorials)

