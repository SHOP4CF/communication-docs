## Human Aware Mobile Robot Navigation in Large-Scale Dynamic Environments

Short name: HA-MRN

By JVERNE-FZI

_Text in italics are comments. Please remove them._

### Purpose

_Describe the purpose of this component in 1-2 sentences. Please focus especially on what the component takes as its input, what added value it produces, and what is its output._

This component takes ..., calculates ..., and returns ... 

### Data interfaces

_Describe what kind of input and output data is in use.
Be detailed about the interpretation of your data. 
Instead of writing 'input data from 20 sensors', please specify. 
Add reference to some examples or attachments, if reasonable._

_The provided information is to be the basis to identify opportunities for uniform data models across components._

_The preliminary information is taken from the cross-WP questionnaires from spring 2020. Feel free to modify._

Input and output data (but not user interfaces):


1. INPUT: Real-time connection to lidar
    - Format: ROS lidar stream ...
    - Real-time constraints?
    - Expected data volume? E.g. amount per unit of time, if makes sense
    - ... _other details_

1. INPUT: Real-time stream
    - Format: Camera stream ...
    - Real-time constraints?
    - Expected data volume? E.g. amount per unit of time, if makes sense
    - ... _other details_

1. INPUT: Robot destination definition
    - Format: GUI ...
    - Real-time constraints?
    - Expected data volume? E.g. amount per unit of time, if makes sense
    - ... _other details_

1. OUTPUT: Global/Local plan, local navigation waypoints
    - Format: None ...
    - Real-time constraints?
    - Expected data volume? E.g. amount per unit of time, if makes sense
    - ... _other details_

1. OUTPUT: Mobile platform commands
    - Format: ROS Twist ...
    - Real-time constraints?
    - Expected data volume? E.g. amount per unit of time, if makes sense
    - ... _other details_

1. OUTPUT: Virtual obstacles for ROS MoveBase stack
    - Format: None ...
    - Real-time constraints?
    - Expected data volume? E.g. amount per unit of time, if makes sense
    - ... _other details_


The input data will be taken from Component X of Partner Y 
and also from sensors available at Pilot Z. _Please update._

The output data will be pushed to Component X... 
or to system Y available at Pilot Z. _Please update._