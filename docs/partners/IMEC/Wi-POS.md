## Wi-POS Indoor Localization

Short name: Wi-POS

By IMEC

### Purpose

This component locates items/humans/robots/AGVs on the SHOPfloor in realtime and exposes the location data (e.g. x/y coordinate in cm). 

### Data interfaces

Input and output data (but not user interfaces):

1. OUTPUT: Location of equipment/AGVs/robots
    - Format: REST interface, or data could be pushed to M3RCP component so that it can be exposed on the FIWARE context broker in the correct format.
    - Real-time constraints: will depend on the end application (e.g. if the AGV depends on the accurate location information, or if it is just used for monitoring purposes).
    - Expected data volume: estimated to be around 1 position update per item/human/AGV every second (or less)


No real input is needed, however some parameters could be made configurable (e.g. increase the number of position updates for AGV 1).

The output data will be pushed to M3RCP (to be exposed on FIWARE context broker), other components to be defined...
or to system Y available at Pilot Z. (To be defined).
