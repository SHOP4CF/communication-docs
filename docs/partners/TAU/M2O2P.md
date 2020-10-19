## Multi-Modal Offline and Online Programming solutions

Short name: M2O2P

By TAU


### Purpose


This component enables online robot programming using input methods based on human natural actions using a gesture tracking glove and a motion tracking controller.  


### Data interfaces





Input and output data (but not user interfaces):

INPUT

1. INPUT: CaptoGlove, leap motion (USB)
    - Format: JSON, socket 
    - Real-time constraints: TBD
    - Expected data volume? TBD
  

2. INPUT: HMI
    - Format: Socket 
    - Real-time constraints
    - Expected data volume: N/A 
    - Used to set up connection between the application contoller, the IKC and the robots.

3. INPUT: Inverse Kinematic Calculator (IKC)
    - Format: Socket .
    - Real-time constraints: TBD
    - Expected data volume? TBD
    
    
OUTPUT

1. OUTPUT: Vector of joint values from IKC to robots (ABB IRB120, eCobra 600) + end eddectors action
    - Format: CSV (on TCP/IP) 
    - Real-time constraints TBD
    - Expected data volume? TBD
    


The input data will be taken from captoglove and motion controller. 

The output data may be pushed to the application controller, which in turn send its output to the IKC. Interfaces to other components will be analyzed when necessary. 
