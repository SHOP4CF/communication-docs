## AR_Teleassistance

Short name: AR_Teleassistance

By TECNALIA


### Purpose

This component provides a communication channel between operators/workers and experts. It uses video streaming to share the same visual information and enables to exchange Augmented Reality indications to support maintenance and collaboration in working processes.
 

### Data interfaces

Input and output data (but not user interfaces):


1. INPUT: Connection Client applications data
    - Format:  JSON file for REST service (using HTTP protocol) / data frame for Websocket Protocol
    - Real-time constraints: Internet connection
    - Expected data volume: no more than 1Mb per message

1. INPUT: Real-time stream (WebRTC) from the device camera (smartphone, MS Hololens) and the touch coordinates in the screen
    - Format: WebRTC message formats using SDP protocol
    - Real-time constraints: light and plain objects issues in context recognition, Internet connection
    - Expected data volume: depending on the resolution of the call, from 19 Mb/s in the lower to 498 Mb/s in the highest

1. OUTPUT: 3D and 2D objects in AR
    - Format: fbx, and runtime mesh for procedural objects in scene; png for number sprites
    - Real-time constraints: virtual memory used by the device
    - Expected data volume: no more than 1Mb per object

1. OUTPUT: Connection Client applications data
    - Format: JSON file for REST service (using HTTP protocol) / data frame for Websocket Protocol
    - Real-time constraints: Internet connection 
    - Expected data volume: no more than 1Mb per message


The input data will be provided by the operator and the expert through the mobile devices.

The output data will be pushed to the mobile devices and used in the Pilot provided by Arcelik.