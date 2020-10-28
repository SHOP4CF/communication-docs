## Flexible Task Programming Tool

Short name: F-TPT

By FZI

### Purpose

_Describe the purpose of this component in 1-2 sentences. Please focus especially on what the component takes as its input, what added value it produces, and what is its output._

Graphical Front End Interface (GUI) to program robotic applications using Behavior Trees (comparable to FlexBe and Smach ROS packages). This component takes messages from external sensors and robots, models the different tasks and interactions between the ROS components, and returns status feedback 

### Data interfaces

Input and output data (but not user interfaces):


1. INPUT: From robots and sensors
    - Format: ROS bridge, ROS topics and services 
    - Real-time constraints: it depends on the tasks and processes to be used, it could be real time for some application (for instance, Task Manager component)
    - Expected data volume: it depends on the task and process
    - Other details: graphical visualization from robots and sensors' ROS topics and services available

1. OUTPUT: Process status feedback
    - Format: ROS topics, services and actions 
    - Real-time constraints: it depends on the tasks and processes used, it could be real time for some application (for instance, Task Manager component)
    - Expected data volume: it depends on the task and process
    - Other details: graphical visualization from robots and sensors' ROS services, topics and actions available


The input and output data will be taken from/ pushed to all the components developed by FZI 

It is to be decided with other partners about the usability for another use cases and components.
