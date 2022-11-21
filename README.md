# Setup instructions:
- Clone this repository from github to your local Linux machine (Tested with Ubuntu 20.02 and ROS Noetic)
- Run `catkin build` (or your normal catkin build procedure). You can also run `build_ros.sh`
- Source your catkin files with `source devel/setup.bash`
- Everything should build correctly or it will post a message about a missing package.
- If you are missing a package, please apt install as normal with `sudo apt install ros-noetic-PAKCAGE-NAME-HERE`


# Run instructions:
- To launch the simulation environment of Gazebo and the drone, please run: `start_world.sh`
- Once the Gazebo simulation window opens up, launch ORB-SLAM2
 - Remember to source your catkin files again (`source devel/setup.bash`)
 - Run ORB-SLAM2 using `launch_orbslam2.sh`


# Instructions for inputs and outputs:
- The drone can be controlled using ROS messages to the topic of `/firefly/command/pose`
 - For example: `rostopic pub /firefly/command/pose geometry_msgs/PoseStamped "header: ... your message here (you can tab to complete the message)"`
 - The message format is a standard PoseStamped message with xyz position and quaternion xyzw orientation
- Camera feed from the drone is accessible at the topic `/firefly/vi_sensor/left/image_raw`
- The Pose output from ORB-SLAM2 is available at the topic of `/orb_slam2_rgbd/pose`


# Resources:
- The simulation environment is independently available at: `https://github.com/ethz-asl/rotors_simulator`
- ORB-SLAM2 ROS package is available at: `https://github.com/appliedAI-Initiative/orb_slam_2_ros`
