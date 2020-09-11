_(This is only a draft proposal, nothing meaningful.)_

## Component 1

_(by Partner X)_

### Purpose

This component takes ... and manages ... Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus blandit finibus nunc, id laoreet dui dictum ac. Duis lobortis tincidunt velit, in tincidunt leo faucibus eget.

### Interfaces

_(currently available and currently planned)_

Input data:

1. Sensor data 
    - There are 40 types of sensors. For each sensor, time series is used (i.e. records with data points indexed by time).
    - Time series in CSV files 
    - Ca. 1000 data values per minute. 
    - See example TODO. 
2. High resolution pictures of XYZ.
    - Single picture between 5 and 10 MB
    - Ca. 2000 pictures per car, i.e. per 15 minutes

The input data will be taken from Component X of Partner Y 
and also from sensors available at Pilot Z.

Output data:

1. Location of AGVs, robots, etc.
    - For each object, XY position in the shop floor.
    - Positions are reported every 5 seconds.

### Mapping to FIWARE data model

The sensor data to be expressed as entity `SensorMeasurement`, 
for instance:

```json
{
  "id": "a73xiw73xnw3x",
  "type": "SensorMeasurement",
  "temperature": {
    "value": 23,
    "type": "Float"
  },
  "pressure": {
    "value": 720,
    "type": "Integer"
  }
}
``` 

Lorem ipsum ...
