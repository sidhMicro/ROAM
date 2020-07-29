Robotic Assistance Machine (ROAM)
=================================

Project ROAM enables voice control of the Stretch RE1 from Hello Robot. With voice control, Stretch's abilities are made accessible to a larger audience. One can say low level commands like "move forward 10 centimeters" or high level commands like "pick up the cup".

The main technologies used in this project are the Stretch SDK and Azure Speech SDK and LUIS. The project is built on top of ROS.

Setup
-----

Stretch RE1 comes with a ROS workspace and stretch_ros installed.

 1. `cd ~/catkin_ws/src`
 2. `git clone https://github.com/sidhMicro/ROAM.git`
 3. Create an Azure account, then follow the [Create an resource](https://docs.microsoft.com/en-us/azure/cognitive-services/speech-service/get-started#new-resource) documentation on Azure to create an Speech resource.
 4. Follow the instruction in the ros_msft_luis [README](https://github.com/ms-iot/ros_msft_luis) to setup the Speech SDK
 5. `cd ~/catkin_ws`
 6. `catkin_make`

File an issue if anything fails.

Running
-------

```
roslaunch ROAM voice_teleop.launch
```
