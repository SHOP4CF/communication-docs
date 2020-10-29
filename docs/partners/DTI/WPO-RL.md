## Workcell Process Optimization based on Reinforcement Learning

Short name: WPO-RL

By DTI

### Purpose

This component implements a reinforcement learning pipeline for a single workcell process optimization. 
In its current state, it takes and image as input and output a shaking pattern for a vibration feeder. Thus, it tried to decrease the amount of time parsing before a pickable object is ready.

### Data interfaces

1. INPUT: action configuration
    - File type: `.json`
    - Format:
      ```
      {
        "actions": [
            {
              "name": "FlipAction",
              "shake_service": "feeder/flip",
              "repetitions": 4,
              "speed": 10
            },
            {
              "name": "ForwardAction",
              "shake_service": "feeder/forward",
              "repetitions": 4,
              "speed": 10
            },
            {
              "name": "BackwardAction",
              "shake_service": "feeder/backward",
              "repetitions": 4,
              "speed": 10
            }
        ]
      }
      ```
1. INPUT: General configuration
    - This includes which model to use. The following are currently implemented: `a2c`, `d3qn`, `dqn`, `hardcoded`, `random`.
    - Learning parameters
    - Run training/execution in simulation or on real hardware
    
1. INPUT: image
    - Format: ROS2 message
    - Expected data volume: 2 images per action taken
    - Expected data source: smart-camera

1. INPUT: number of pickable objects
    - Format: ROS2 message
    - Expected data volume: 2 images per action taken
    - Expected data source: smart-camera

1. OUTPUT: action (shaking pattern to vibration feeder)
    - Format: ROS2 message:
        - type: `{forward, backward, flip, flip_forward, flip_backward}`
        - speed: `[1, 10]`
        - repetitions: `[1, 10]`
    - Expected data volume: heavily depends on the time it takes to perform an action.

1. OUTPUT: pick-position to robot
    - Format: ROS2 message, (position, orientation)
    - Expected data volume: [1, 100] seconds depending on the stage of the training.
    - This is only intended to be used during training to speed up the process.


The `image` and `number of pickable objects` is current optained from a smart-camera. 
This setup have the advantage that the camera also can be used directly by the robot/workcell-controller.
