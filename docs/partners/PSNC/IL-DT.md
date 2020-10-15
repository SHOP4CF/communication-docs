## Digital Twin For Intralogistics

Short name: IL-DT

By PSNC

### Purpose

This component takes, as an input, the information about factory topography and  movements of operators (humans, AGVs, robots).
Based on that, it creates an intralogistic model of the factory together with its visualisation, that lead to new recommendations for intralogistics.

### Data interfaces

Input and output data (but not user interfaces):

1. INPUT: Topographic data, operators data (humans, robots, AGVs), operations data
    - Some information in natural language, and some data in machine format (to be specified)
    - No real-time constraints

1. OUTPUT: Recommendations for charges in setting positions, timing, routes, AGLT compositions
    - Format: report in natural language
    - No real-time constraints


Under discussion how the input data will be collected.
Possibly, it could be read from FIWARE Context Broker.
