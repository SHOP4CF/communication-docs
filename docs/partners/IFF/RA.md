## Review of Risk Analysis

Short name: RA

By IFF

### Purpose

The Risk Analysis Support Tool is designed for use when designing/implementing a collaborative robotics application and later when adapting an existing application. The tool supports an applications designer and/or robotic systems integrator during the phases of hazard identification, risk evaluation, and hazard elimination and risk reduction. 

This component takes the list of currently used objects (including robots, tools, parts, etc.) for a specific application (from the digital twin?), compares these components with the ones listed in the risk analysis, and returns a new version of the risk analysis whereby objects of the application that have been changed/ replaced are highlighted in the risk analysis. The probabilities that follow the concatenation of objects, actions, and other objects (including environmental objects), which together represent hazards are also highlighted and the user is asked to review them. These can either be accepted, or updated manually.

### Data interfaces

From the digital twin, all the objects involved in the application including the robot, tool(s), environmental parts (e.g. tables, conveyors, machines, etc.) are listed. 
An object or environmental part has the following format:
```jsonc
{
    "id": "XYZ",
    "type": "object"
    "name": {
        "value": "KUKA KR60",
        "type": "string"
    }
}
```
The components subscribes to updates and deletions of objects that are part of the digital twin.

Input and output data (but not user interfaces):

1. INPUT: Objects fromdDigital twin
    - Format: JSON
    - Real-time constraints: No
    - Expected data volume: < 1 MB

1. OUTPUT: Digitally signed certificate
    - Format: Certificate (JSON?)
    - Real-time constraints: No
    - Expected data volume: < 1MB

1. OUTPUT: Risk Analysis report
    - Format: RA report (JSON?)
    - Real-time constraints?
    - Expected data volume: < 1 MB


The input data will be taken from a Digital Twin (Component X of Partner Y?)
