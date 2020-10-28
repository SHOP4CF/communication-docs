## Human Aware Mobile Robot Navigation in Large-Scale Dynamic Environments

Short name: HA-MRN

By JVERNE-FZI

_FZI Component_

### Purpose

This component takes sensor information and robot localization, calculates the best trajectory avoiding obstacles on the way, and returns trajectory points for the most efficient path

### Data interfaces


Input and output data (but not user interfaces):


1. INPUT: Real-time connection to lidar
    - Format: ROS Topics
    - Real-time constraints: Real time for trajectory avoidance is requested 
    - Expected data volume: at least 30 Hz
    - Other details: the expected data volume depends on the LIDAR

1. INPUT: Real-time Camera stream
    - Format: ROS Topics
    - Real-time constraints: Real time for trajectory avoidance is requested
    - Expected data volume: at least 30 Hz
    - Other details: the expected data volume depends on the camera to be used and the trained Neural Network for image post-processing

1. INPUT: Robot positioning
    - Format: ROS Topics
    - Real-time constraints: During the goal achievement update on current position of the robot in a real time is requested to avoid collision and estimate if the goal (delivery) was achieved or not
    - Expected data volumen: at least 30 Hz

1. INPUT: Robot destination definition
    - Format: Coordinate point in a bitmap (Global map) with respect to the origin
    - Real-time constraints: No
  
1. INPUT: Global map
    - Format: Bitmap and YAML File (specifying meta information about the map, like origin, resolution and size)
    - Real-time constraints: No, once the map is stored no updates on the workspace are done    

1. OUTPUT: Global/Local plan, local navigation waypoints
    - Format: Coordinates in the bitmap (Global map) with respect to the origin
    - Real-time constraints: yes. Obstacles might change the pre-established path 
    - Expected data volume: at least 30 Hz

1. OUTPUT: Mobile platform commands
    - Format: ROS topics
    - Real-time constraints: yes. The platform might be requested to stop, change direction or return the path, if an obstacle appears in the path
    - Expected data volume: at least 10 Hz

1. OUTPUT: ROS MoveBase Stack
    - Format: ROS Topic
    - Real-time constraints: yes. The platform will be constantly informed about the trajectory to follow, and any changes in its path if there is an obstacle.
    - Expected data volume: at least 10 Hz

The interaction with another components to obtain or use the 
input and output data is still to be decided.
