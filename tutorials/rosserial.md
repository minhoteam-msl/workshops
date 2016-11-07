##Usage tutorial of ROSSERIAL for Arduino (IDE)

After installing everything, one has to generate the library to use in the IDE.   
For that, run the following script:    

$ rosrun rosserial_arduino make_libraries.py DIRECTORY

Where DIRECTORY should be <sketchbook>/libraries (Arduino IDE library directory) or another directory of choice
to use outside the IDE.

After generating the library, one can see the directory ros_lib, containing all the messages and services of 
the user's packages. If a new package is created/messages changes, this step has to be ran again to regenerate
the library.

Now, program the arduino like a normal ros node. To make connection between serial and network, a "brigde" node
will be running in the host computer. To run it type:   

$ rosrun rosserial_python serial_node.py PORT

Where PORT is usually /dev/ttyACM0 or /dev/ttyACM1

From this point onwards, the Arduino behaves as a full functional ROS Node. See [IMPLEMENTATION](https://github.com/minhoteam-msl/minho_team_ros/blob/master/low_level/MinhoTeamHardware/MinhoTeamHardware/MinhoTeamHardware.ino), 
which is the hardware_node implementation in Arduino, containing a lot of useful code.

* Other Tutorials
[ARDUINO](http://wiki.ros.org/rosserial_arduino/Tutorials)
