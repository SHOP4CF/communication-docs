## Visual Quality Check

Short name: VQC

By PSNC

### Purpose

This component serves to detect car paint defects based on high resolution pictures of the car body on the production line.

It helps in human workers' accuracy, comfort and efficiency.


### Data interfaces

Input and output data (but not user interfaces):

1. INPUT: High-resolution pictures of the car
    - Format: Image format with metadata to know which part of the car is pictured
    - No real-time constraints, but the data should be collected and analysed 'online'.
    - Thousands (or more) high-resolution pictures taken for a single car. For instance, 10k pictures x 5 MB each = 50 GB (per car).

1. OUTPUT: Pictures of defects
    - Format: Images with marked defects
    - No real-time constraints
    - A few images for each defect. It might be hundreds in total, per car.


The input data will be taken from a camera. 
The output will be presented directly to a worker at the production line.
