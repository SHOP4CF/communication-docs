## FIWARE data representation 

_This is work in progress!_

[The SHOP4CF project](https://shop4cf.eu/) defines data models on top of 
[FIWARE NGSI API](https://fiware-datamodels.readthedocs.io/en/latest/howto/index.html).  

The concept data models 
(i.e. the definitions of data entities, relationships, and attributes)
as well as further explanations of the data architecture
are described in the [SHOP4CF architecture](https://workbench.ub.tum.de/#/files/238ac0ad-d8b6-4271-8c02-d5a953bd00cb) 
(a public link to be provided once available). 
Reviewing the data architecture may be necessary 
to understand this technical representation better.

### Conventions

Beyond the [FIWARE Smart Data Models guidelines](https://github.com/smart-data-models/data-models/blob/master/guidelines.md), 
SHOP4CF defines the following convention.

An entity identifier should be a [URN](https://en.wikipedia.org/wiki/Uniform_Resource_Name), 
built as `urn:ngsi-ld:<entity-type>:<factory-id>:<entity-id>`, 
for instance: `urn:ngsi-ld:Device:company-xyz:sensor-abc-12345`.

### Examples

The examples given below provide an overview 
of the FIWARE representation for the SHOP4CF concept data models.

The examples are in the NGSI v2 normalised format. 

Examples of the data models:

- Resources:
    - [Device](device.md)
    - [Material](material.md)
- [Task](task.md)
- [Alert](alert.md)