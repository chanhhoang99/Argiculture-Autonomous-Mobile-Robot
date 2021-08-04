# Agriculture-autonomous-Robot
HCMUTE Final-year Project


![500px-Hcmute svg](https://user-images.githubusercontent.com/74817103/128142475-49e52521-994c-4fec-9706-0da05d8bb5d7.png)



This project is developed from Nox-Robot project ( see also :https://github.com/RBinsonB/Nox_robot). 

Robot Motor for wheels schematic :

Arduino communicates with Raspberry Pi 4 by UART method.

Motor Pin (Using XY-160D motor driver) : 

- Left motor : IN1 = 8 ; IN2 = 6 ; ENB = 10.
- 
- Right motor : IN1 = 11 : IN2 = 12 ; ENB = 9.
- 
- Encoder left motor: Chanel A = 2 ; Chanel B = 4.
- 
- Encoder right motor: Chanel A = 3 ; Chanel B = 5. 

Robotic arm schematic:

![image](https://user-images.githubusercontent.com/74817103/128136613-d7e44b0d-efd4-4ac7-9d84-4780cb8dea31.png)

Setting up the robot:

1. Clone the repository to your workspace.(Ubuntu 18.04.05 LTS)

2. You can install and build the package by typing on terminal :

    $ catkin_make
    
3. Source your work:

    $ source devel/setup.bash

To run the Robot:

1. Prepare a good Wifi connection

2. Connect to your RPi4 from your laptop workstation via ssh

3. Typing this on terminal of the RPi4:

    $ roslaunch nox nox_bringup.launch

4. Start the navigation by typing this on your laptop workstation's terminal

    $ roslaunch nox nox_slam.launch
    
To run the robotic arm:

  Controlling robotic arm with join-stat-publisher package
  
1. Typing this on RPi4 terminal:

  $ roslaunch arm_pkg check_motors.launch
  
2. Connect to hardware:

  $ rosrun rosserial_python serial_node.py _port:=/dev/ttyUSB0 _baud:=115200
  
  Controlling robotic arm with Moveit! and kinematics
  
1. $ roslaunch moveit_config_pkg demo.launch

2. $ rosrun rosserial_python serial_node.py _port:=/dev/ttyUSB0 _baud:=115200

( Note: You may need to use ttyACM)

For more detail please contact : chanhhoang999x@gmail.com


