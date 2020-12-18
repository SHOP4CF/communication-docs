## Device

(in progress)

This model is based on [FIWARE Device](https://github.com/smart-data-models/dataModel.Device/blob/master/Device/doc/spec.md).

An example sensor of electrical current 
measured from a busbar no. 789 
with the current value of 11.54 A:

```
{
    "id": "urn:ngsi-ld:Device:company-xyz:sensor-12345",
    "type": "Device",
    "source": {
        "value": "urn:ngsi-ld:Device:busbar-789"
    }
    "category": {
        "value": ["sensor"]
    },
    "serialNumber": {
        "value": "9845A"
    },
    "value": {
        "value": 11.54,
        "metadata": {
            "unitCode": {
                "value": "AMP"
            },
            "timestamp": {
                "value": "2020-12-01T11:23:19Z"
            }
        }
    },
    "controlledProperty": {
        "value": ["electricCurrent"]
    },
    "deviceState": {
        "value": "ok"
    }
}
```
