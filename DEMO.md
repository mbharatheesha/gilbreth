# How to launch demo
## Getting Started
- fetch gilbreth source code
- fetch moveit source code (https://github.com/ros-planning/moveit)
- copy and paste the 'moveit_commander' package in the same /src folder with gilbreth

## Demo Setup
- Bring up the application components
  ```
  roslaunch gilbreth_application application_setup.launch
  ```
  - Both Gazebo and Rviz will be launched at the same time. 
  - Several windows containing various nodes (object_recognition, tool_planning, trajectory_planning and robot_execution) will start as well.

*Use Rviz to test the robot controller by dragging the end-effector to another pose and click 'plan and execute' in moveit panel.
If the robot failed to move to the target pose, then the robot controller is now working. 
Close Gazebo and Rviz and then relaunch the environment.

### Demo Run

- Start the application
  ```
  roslaunch gilbreth_application application_run.launch
  ```

### Launch node seperately (Outdated):

The script will run object_recognition, tool_planning, trajectory_planning and robot_execution nodes seperately.

- object segmentation and object recognition:
```
roslaunch gilbreth_perception gilbreth_perception.launch
```
- robot tool planner:
```
rosrun gilbreth_grasp_planning tool_planner.py
```
- robot trajectory planner:
```
rosrun gilbreth_grasp_planning trajectory_planner.py
```
- robot execution:
```
rosrun gilbreth_grasp_planning robot_execution.py
```
