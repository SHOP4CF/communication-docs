## Multi-Modal Multi-Range Communication Platform

Short name: M3RCP

By IMEC

### Purpose

This component is a platform that groups adapters to connect different kinds of input to different kinds of output. For example, it could take input from a positioning engine ( location of an AGV, in x,y coordinates), convert the data into the correct format and post it to a PubSub server (e.g. a FIWARE context broker).

### Data interfaces

_Describe what kind of input and output data is in use.
Be detailed about the interpretation of your data. 
Instead of writing 'input data from 20 sensors', please specify. 
Add reference to some examples or attachments, if reasonable._

_The provided information is to be the basis to identify opportunities for uniform data models across components._

_The preliminary information is taken from the cross-WP questionnaires from spring 2020. Feel free to modify._

Input and output data (but not user interfaces):


1. INPUT: Input adapters
    - Format: LoRaWAN Adapter Vendor X, LoRaWAN Adapter Vendor Y, Sigfox Adapter ...
    - Real-time constraints: the component itself doesn't have any real time constraints as it pushed data to other components. So the end-component could have these restraints.
    - Expected data volume: Could be 1 message/hour or 1 message every second. We don't expect more frequent updates than that. E.g. counterweight measurements could be 1 message (e.g. X amount of kilogram) every 30 seconds, while the positioning updates from an AGV (e.g. location x,y in cm) could be done every second

1. OUTPUT: Data adapters
    - Format: LwM2M adapters REST-based adapters, MQTT adapters JSON ...
    - Real-time constraints: the component itself doesn't have any real time constraints as it pushed data to other components. So the end-component could have these restraints.
    - Expected data volume: every input could result in an output (e.g. push the data on the FIWARE context broker)


The input data will be taken from Component WiPOS of IMEC
and also from sensors available at Pilot Arcelik (counterweights measurements) and Pilot VW (skid health sensors).

The output data will be pushed to Component X (To be defined)
or to system Y available at Pilot ... (To be defined)
