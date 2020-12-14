## FIWARE data representation 

_This is work in progress!_

[The SHOP4CF project](https://shop4cf.eu/) defines data models on top of 
[FIWARE NGSI API](https://fiware-datamodels.readthedocs.io/en/latest/howto/index.html).  

The concept data models 
(i.e. the definitions of data entities, relationships, and attributes)
as well as further explanations of the data architecture
are described in the SHOP4CF architecture 
(link to be provided once it is public). 
Reviewing the data architecture may be necessary 
to understand this technical representation better.

### Conventions

Beyond the strict rules defined by FIWARE NGSI, 
SHOP4CF defines the following convention.

An entity identifier should be a [URN](https://en.wikipedia.org/wiki/Uniform_Resource_Name), 
built as `urn:ngsi-ld:<entity-type>:<factory-id>:<entity-id>`, 
for instance: `urn:ngsi-ld:Device:company-xyz:sensor-abc-12345`.
This rule applies to `id` and `ref`-like attributes (i.e. pointing at other entities).

### Examples

The FIWARE representation of the SHOP4CF concept data models
is presented as the examples below.

These examples are used for writing to the Context Broker. 
When reading these entities from the Context Broker, 
additional read-only attributes and metadata values may be present 
(refer to FIWARE documentation).

- Resources:
    - [Device](device.md)
    - [Material](material.md)
- [Task](task.md)
- [Alert](alert.md)
