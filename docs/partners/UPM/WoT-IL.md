## Interoperability Layer through Web of Things

Short name: WoT-IL

By UPM

### Purpose

This component takes an OpenAPI and returns a Web of Things Thing Description and vice versa.

Basically the component makes WoT compatible with OpenAPI to take advantage of the greater power that WoT has by allowing to describe semantic contexts.
 
### Data interfaces

Input and output data (but not user interfaces):


1. INPUT/OUTPUT: REST API description (OpenAPI format)
    - Format: JSON object
    - Real-time constraints: Not applicable
    - Expected data volume: Kb

1. INPUT/OUTPUT: Thing Description of the REST - API
    - Format: Thing Description object model with JSON-LD contexts
    - Real-time constraints: Not applicable
    - Expected data volume: Kb

The input data will be provided by the user of the component.

The output data will be generated in a file that can be downloaded to the user's computer
