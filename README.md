Robotic Assistance Machine (ROAM)
=================================

Project ROAM enables voice control of the Stretch RE1 from Hello Robot. With voice control, Stretch's abilities are made accessible to a larger audience. One can say low level commands like "move forward 10 centimeters" or high level commands like "pick up the cup".

The main technologies used in this project are the Stretch SDK and Azure Speech SDK and LUIS. The project is built on top of ROS.

Setup
-----

Stretch RE1 comes with a ROS workspace and stretch_ros installed.

 1. `cd ~/catkin_ws/src`
 2. `git clone https://github.com/sidhMicro/ROAM.git`
 3. `git clone --recurse-submodules https://github.com/ms-iot/ros_msft_luis.git`
 4. Create an Azure account, then follow the [Create an resource](https://docs.microsoft.com/en-us/azure/cognitive-services/speech-service/get-started#new-resource) documentation on Azure to create an Speech resource.
 5. Visit [luis.ai](luis.ai), connect your Azure account, and create a LUIS model by importing an `.lu` file. The file is in the `luis/` folder of this repo.
 6. Follow the instructions in the [Build the Sample](https://github.com/Azure-Samples/cognitive-services-speech-sdk/tree/master/quickstart/cpp/linux/from-microphone#build-the-sample) section of this README to install the Speech SDK. Ignore downloading the sample code and all steps related to it.
 7. Collect the `appid`, `key`, `region`, and `intent` from the Azure portal and the Luis portals.
 8. Add the following exports to your `.bashrc`

 ```
 export SPEECHSDK_ROOT="<path/to/speech/sdk>"
 export azure_cs_luis_appid=<insert luis appid>
 export azure_cs_luis_key=<insert azure key>
 export azure_cs_luis_region=<insert azure region>
 export azure_cs_luis_intent=<insert luis intent>
 ```
 9. `cd ~/catkin_ws`
 10. `catkin_make`

File an issue if anything fails.

Running
-------

```
roslaunch ROAM voice_teleop.launch
```
