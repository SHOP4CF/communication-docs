## ROS Monitoring
Short name: ROS-Mon

By DTI

### Purpose
This component (ROS2 node) monitors other ROS2 nodes, e.g: are they running, publishers, subscribers, service, actions, and parameters. 
The component uses the standard ROS2-client library as data-source, so no additional functionality have to be implemented by monitored nodes.

### Data interfaces
This component has a GUI as its _output_ interface.   

There are currently no plans to have other types of output. However, that might change if requested by users. 

1. Input: configuration file
   - File type: `.json`
   - Format: 
     ```json
     {
       "node_names": [
         {
           "name":  "node",
           "namespace": "/",
           "full_name": "/node"
         },
         {
           "name":  "other_node",
           "namespace": "namespace/",
           "full_name": "/namespace/other_node"
         }
       ],
       "organization": "dti.dk",
       "app_name": "Moni2",
       "version": "0.1.0"
     }
     ```
   - Note: the configuration file can be created within the application.

1. Input: Status data
   - Format: primarily ROS2 messages
   - ROS2 service calls: 
      - `list_parameters`: list a nodes parameters
      - `get_parameters`: retrieve specific information about a parameter
      - Note: all of the above is standard implemented for all ROS2 nodes.
   - ROS2 subscribers:
      - `rosout`: to get log-messages
   - `rclpy` methods to retrieve data:
      - `get_node_names_and_namespaces()`: retrieve a list of _online_ nodes
      - `get_publisher_names_and_types_by_node()`: get a list of a nodes publishers
      - `get_subscriber_names_and_types_by_node()`: get a list of a nodes subscribers 
      - `get_service_names_and_types_by_node()`: get a list of a nodes services
      - `get_client_names_and_types_by_node()`: get a list of a nodes clients
      - `get_action_server_names_and_types_by_node()` get a list of a nodes action-servers
      - `get_action_client_names_and_types_by_node()`: get a list of a nodes action-clients
   - Update-rate: every x seconds (default: x = 3)

1. Output: Dashboard/GUI
