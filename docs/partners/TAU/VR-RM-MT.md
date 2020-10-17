## Virtual Reality Set for Robot and Machine Monitoring and Training

Short name: VR-RM-MT

By TAU



### Purpose


This component enables training and supporting human workers in collaborative tasks by offering 3D simulation of the task at hand.    


### Data interfaces





Input and output data (but not user interfaces):


1. INPUT: Position movement and actions of worker
    - Format:  ...
    - Real-time constraints?
    - Expected data volume? N/A
    - ... _other details_

1. INPUT: Sensors (USB) HMD (HDMI/USB) controller joysticks
    - Format: Oculus Rift 
    - Real-time constraints?
    - Expected data volume? E.g. amount per unit of time, if makes sense
    - The data is passsed through an external GPU to make 3D rendering smooth.  

1. INPUT: Simulation model
    - Format: .glb file 
    - Real-time constraints : Upload speed
    - Expected data volume? TBD
    - Different format transformations maybe required (based on 3D model imports) to obtain final .glb format. 

1. OUTPUT: Guided VR simulation of automated collaborative task
    - Format:  ...
    - Real-time constraints?
    - Expected data volume? E.g. amount per unit of time, if makes sense
    - ... _other details_


The input data will be taken from the movement and actions of the user through the sensor, HMD, and joysticks. 

The output data will be the guided VR simulation projected on the HMD or shown through the browser window. 
