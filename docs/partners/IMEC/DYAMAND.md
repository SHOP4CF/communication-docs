## DYAMAND

Short name: DYAMAND

By IMEC

### Purpose

This component is a platform that groups adapters to connect different kinds of input to different kinds of output. For example, it could take input from a positioning engine ( location of an AGV, in x,y coordinates), convert the data into the correct format and post it to a PubSub server (e.g. a FIWARE context broker). While the M3RCP component focuses more on adapters for wireless technologies, this component is more mature regarding FIWARE integration and provides already lots of adapters for home automation appliances (e.g. Philips Hue).

### Data interfaces

Input and output data (but not user interfaces):

1. INPUT: Legacy and future input data
    - Format: None ...
    - Real-time constraints: depends highly on the requirements from the component that provides the input data.
    - Expected data volume: depends highly on the requirements from the component that provides the input data. However, this component is able to handle quite large volumes of data.

1. OUTPUT: Aggregated factory floor data
    - Format: Dashboard, push data to database
    - Real-time constraints: depends highly on the INPUT data.
    - Expected data volume: depends highly on the INPUT data.


The input data will be taken from possibly all components that generate data and want to expose this on the FIWARE context broker (not clear for now)
and also from sensors available at : No usage in Pilots currently planned.

The output data will be pushed to (To be defined)
or to system Y available at Pilot Z: No usage in Pilots currently planned, but this could change in the future. (FSTP pilots?)
