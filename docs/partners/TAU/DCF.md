## C2NET Data Collection Framework

Short name: DCF

By TAU



### Purpose



This component enables data collection from the factory shop floor and Enterprise Resources.

### Data interfaces


Input and output data (but not user interfaces):

INPUT

1. INPUT: IoT Devices data (HTTP1.1 / MQTT on TCP/IP) > IoT Hub
    - Format: Apache Active MQ messages 
    - Real-time constraints TBD
    - Expected data volume? TBD
  

2. INPUT: MS Excel, SQL, RESTful > Legacy Systems Hub (LHS), adapters
    - Format: Apache Active MQ messages 
    - Real-time constraints: TBD
    - Expected data volume? TBD
    Data adapters functionality have to be analyzed in respect to the legacy system of interest. 
    
OUTPUT

1. OUTPUT: Stream data 
    - Format: XML data (internal)
    - Real-time constraints:N/A
    - Expected data volume? TBD
    The intended end use of data (transfer, storage, etc) has to be further defined.

2. OUTPUT: Events 
    - Format:  TBD
    - Real-time constraints TBD
    - Expected data volume? TBD
   The event types, dispatching and processing have to be defined based on system requirements. 



The input data will be taken from IoT devices and legacy systems in the shopfoor. 

The output data and its intended end use have to be further defined. 
