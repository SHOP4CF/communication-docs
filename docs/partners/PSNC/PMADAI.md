## Predictive Maintenance and Anomaly Detection in Automotive Industry

Short name: PMADAI

By PSNC

### Purpose

This component helps in predicting or preventing potential failures and incidents. It may also support human workers in planning services and repairs.
It is done by taking certain measurements and information on events from the shop floor as the input, and by applying a machine-learning model on such data to make predictions.

The concrete use case is prediction of repair and maintenance interventions for parts of the paintshop.

### Data interfaces

Input and output data (but not user interfaces):

1. INPUT: Events about SKIDs entering and leaving the poll of paint
    - Format to be decided. Required attributes: timestamp, SKID ID, pendle ID.
    - Such events ocurr multiple times per hour. No real-time constraints.

1. INPUT: Current measurements
    - Format to be decided. Required attributes: timestamp, current measurements from a few busbars.
    - Sampling every 1 second. No real-time constraints.

1. OUTPUT: (not yet decided, to be considered) Notifications about predicted problems
    - Details to be decided.
    - No real-time constraints.

These input and output data could be possibly taken from FIWARE Context Broker.
