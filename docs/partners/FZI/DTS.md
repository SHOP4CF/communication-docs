## Dynamic Task Scheduling for Efficient Human-Robot-Collaboration

Short name: DTS

By FZI

### Purpose

This component takes the robot tasks; it classifies these tasks as achievable or not, to be done or completed; and it returns sub-tasks for the robot to work in a collaborative environemnt.

### Data interfaces

Input and output data (but not user interfaces):

1. INPUT: Real-time joint robot angles
    - Format:  ROS Topics
    - Real-time constraints: yes. Precise knowledge from the joint states is needed to determine robot trajectories and position at all the times
    - Expected data volume: 30 Hz
    - Other details: Expected input from the (specific) robot driver. Joint controller and cartesian controller subcribe to this topic

2. INPUT: Real-time sensors data (depth cameras, RGB images)
    - Format: ROS Topics
    - Real-time constraints: yes. Precise knowledge from the environment for decision making in the robot trajectory planning
    - Expected data volume: Sensor information requires to check the environments at least 10 times per one second
    - Other details: TF information from objects in the workspace, as well as depth information and RGB information from cameras is also used

3. INPUT: GPU-Voxels
    - Format: ROS Topics
    - Real-time constraints: yes. Precise knowledge from the environment for decision making in the robot trajectory planning
    - Expected data volume: GPU-Voxels subscribes to Real-time sensors data, thus at least 10 checks per one second
    - Other details: GPU-Voxels outputs volumen occupancy in the workspace available for the robot to follow the planned trajectory

1. OUTPUT: Volumen Ocuppancy as GPU Voxels
    - Format:  ROS Topics
    - Real-time constraints: yes. Precise knowledge from the environment for decision making is required for accurate trajectory and goal planning
    - Expected data volume: Equivalent to the subscription time for GPU Voxels. Real time is necessary.
    - Other details:

1. OUTPUT: Robot Trajectory Points
    - Format:  ROS Topics
    - Real-time constraints: yes. Reactive path planning to shown obstacles on the workspace
    - Expected data volume: Update on the points in the trajectory needs to be as close to real time as possible
    - Other details:

1. OUTPUT: Task Schedule (Reachable sub-tasks, completed sub-tasks)
    - Format: ROS Topics
    - Real-time constraints: yes. Constant supervision of tasks (reachable, unreachable, finished) is necessary for the task manager
    - Other details:


The input data and output data are at the current moment of this document not provided nor given to any of the available partners,
this information will be updated in the future.
