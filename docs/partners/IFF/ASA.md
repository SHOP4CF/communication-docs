## Automated Safety Approval

Short name: ASA

By IFF

### Purpose

This component ensures safety of robot cells that use speed and separation monitoring. The software can evaluate computer-generated motions and trajectories prior to their execution determine whether a given action is safe. This is achieved by calculating the required separation distance and comparing it with the predefined area covered by the sensor configuration.

### Data interfaces

The component outputs a boolean value, indicating whether a specific robot state is safe.
All static information required for this judgement (robot/sensor properties and layout of the robot cell) is modelled using the „Safety Planning Tool“ provided by Fraunhofer within the SHOP4CF project. This data is installed during deployment of the component.
Dynamic input consists of position and speed of the robot’s axes (joint state) at a given point in time. Additionally, geometry and mass of the current tool (including workpiece) can be taken into account.

**Input and output data (but not user interfaces):**
- A _joint state_ is defined as the position of an axis controller (in radian by default) and its speed (normally radian per second). Currently only rotary joints are supported.
A single joint state can be expressed as entity `JointState`, e.g.:
```jsonc
{
    "name": {
        "value": "A1",
        "type": "string"
    },
    "position": {
        "value": 3.141592,
        "type": "float",
        "metadata": {
            "unitCode": {
                "value": "rad"
            }
        }
    },
    "speed": {
        "value": 0.1,
        "type": "float",
        "metadata": {
            "unitCode": {
                "value": "rad/s"
            }
        }
    }
}
```
or simplified as:
```jsonc
{
    "name": "A1",			// optional 
    "position": 3.141592,
    "speed": 0.1
}
```
- The _geometry_ of the tool/workpiece is given by a list of 3D points specifying the relevant convex hull relative to the robot’s tool center point (TCP). 3D points can be written in json as: `{"x": 1.0, "y": 2.0, "z": 3.0}` or `[1.0, 2.0, 3.0]`
- Its _mass_ is either defined in kilogram or percentage of the robot’s maximum payload.

1. INPUT: RobotState
- The _robot’s_ state at time _t_ comprises an array of all its joint states, geometry of the current tool/workpiece and the actual payload.
- A _UUID_ is used to identify the relevant static data in the backend, in case several robots are observed. Additionally, a _timestamp_ in microsecond resolution is provided to indicate the relevant point in time.
- The _robot state_ is to be expressed as entity `RobotState`, for instance:
```jsonc
{
    "id": "XYZ",
    "type": "RobotState",
    "uuid": "edf2eb4f-02ed-4e4e-8275-ee6cbcdd8048",
    "timestamp": 1582024510340400,
    "jointStates": [
        {"name": "A1", "position": 0.1, "speed": 0.1},
        {"name": "A2", "position": 0.2, "speed": 0.2},
        {"name": "A3", "position": 0.3, "speed": 0.3},
        {"name": "A4", "position": 0.5, "speed": 0.5},
        {"name": "A5", "position": 0.4, "speed": 0.4},
        {"name": "A6", "position": 0.6, "speed": 0.6}
    ]
    "tool": [
        {"x": 0.1, "y": 0.1, "z": 0},
        {"x": 0.1, "y": -0.1, "z": 0},
        {"x": -0.1, "y": -0.1, "z": 0},
        {"x": -0.1, "y": 0.1, "z": 0},
        {"x": 0, "y": 0, "z": 0.1}
    ],
    "mass": {
        "value": 12.8,
        "type": "float"
        "metadata": {
            "unitCode": {
                "value": "kg"
            }
        }
    },
    "payload": {
        "value": 80,
        "type": "float"
        "metadata": {
            "unitCode": {
                "value": "pct"
            }
        }
    },
}
```
or simplified as:
```jsonc
{
    "id": "XYZ",
    "type": "RobotState",
    "uuid": "edf2eb4f-02ed-4e4e-8275-ee6cbcdd8048",
    "timestamp": 1582024510340400,
    "jointStates": [
        {"position": 0.1, "speed": 0.1},
        {"position": 0.2, "speed": 0.2},
        {"position": 0.3, "speed": 0.3},
        {"position": 0.4, "speed": 0.4},
        {"position": 0.5, "speed": 0.5},
        {"position": 0.6, "speed": 0.6}
    ],
    "tool": [		// optional (if missing, tool will stay unchanged)
        [0.1, 0.1, 0],
        [0.1, -0.1, 0],
        [-0.1, -0.1, 0],
        [-0.1, 0.1, 0],
        [0, 0, 0.1]
    ],
    "mass": 12.8,	// optional (only mass or payload should be given)
    "payload": 80	// optional (only mass or payload should be given)
			// if neither mass nor payload are given,
			// payload will stay unchanged
}
```
- Real-time constraints are not necessary as the software will currently not run in real-time. In the future it might be possible to check the safety in hard real-time to stop the robot system in case of dangerous situations.
- The data volume depends on the amount of requests and the length of trajectories tested.
- The source of the input data is still unclear.

2. OUTPUT: SafetyStatus
- As described above, the component outputs a boolean value, indicating if the input violates the safety areas around the robot. The output might include a polygon (array of 2D points) describing the minimal safety area with respect to the input. UUID and timestamp reflect the respective input. Its expressed as entity `SafetyStatus`, for instance: 
```jsonc
{
    "id": "XYZ",
    "type": "SafetyStatus",
    "uuid": "edf2eb4f-02ed-4e4e-8275-ee6cbcdd8048",
    "timestamp": 1582024510340400,
    "isSafe": true,
    "safetyContour": [
        [1.0, 1.0],
        [1.0, -1.0],
        [-1.0, -1.0],
        [-1.0, 1.0]
    ],
}
```
- The output data can be used as a clearance signal to start the robot’s motion.
