## Force-Based Assembly Strategies for difficult snap-fit parts using Machine Learning

Short name: FBAS-ML

By FZI

### Purpose

This component takes Force-Torque Sensor readings at the TCP (sensor mounted on the robot or already integrated, as in the URe series) and a deep neural network with trained data on the snap fitting task, calculates the best strategy to fit two or more parts together that require a snap connection, and returns joint positions for the hardware to fulfill this task

### Data interfaces


Input and output data (but not user interfaces):


1. INPUT: Force-torque sensor readings
    - Format:  ROS messages
    - Real-time constraints: yes, to update the fitting strategy depending on the action-reaction principle and compare if the expected behavior predicted by the learnt data agrees with the hardware behavior
    - Expected data volume: at least 125 Hz
    - Other details: force-torque readings can come from a sensor mounted on the robot, or robot arms with a sensor already integrated

1. INPUT: Real-time joint robot angles
    - Format:  ROS messages
    - Real-time constraints: yes. Precise knowledge from the joint states is needed to determine robot trajectories and position at all the times
    - Expected data volume: at least 30 Hz
    - Other details: Expected input from the (specific) robot driver: joint controller and cartesian controller

1. INPUT: Snap fitting demonstration by human worker to train deep NN
    - Format: trained neural network (datasets)
    - Real-time constraints: No
    - Other details: it provides possible robot joints configurations and force for the snap-fitting strategies

1. OUTPUT: Joint positions commands to the hardware drivers
    - Format:  ROS topics
    - Real-time constraints: yes. Precise knowledge from the joint states determines robot trajectories and positions at all the times
    - Expected data volume: at least 125 hz (to 1000 Hz, robot dependent)
    

The input and output data will be taken from robots and 
sensors available at Siemens and Bosch Pilots. 

The input and output data contribution with another components is to be decided.
