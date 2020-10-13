## AR_Manual Editor

Short name: AR_Manual_Editor

By TECNALIA



### Purpose

This component provides a Mixed Reality (MR) simulator for operator/worker asistance in customised product assembly process. Based on recognition of objects, it calculates a sequence of operations and returns a MR guidance to operators.
 

### Data interfaces

Input and output data (but not user interfaces):


1. INPUT for EDITOR part: 3D objects, sequence of operations for the product assembly
    - Format: JSON, Images (jpg, png), audios (wav, mp3), 3d objects (glb), videos (mp4, avi, flv, mov, mpg), documents (pdf)
    - Real-time constraints: Not applicable
    - Expected data volume: less than 1MB

1. INPUT for visualizator part: 3D/context/image/BIDI/recognition
    - Format: JSON, Images (jpg, png), audios (wav, mp3), 3d objects (glb), videos (mp4, avi, flv, mov, mpg), documents (pdf)
    - Real-time constraints: Light and patterns used for object recognition.
    - Expected data volume: less than 1MB

1. OUTPUT: Mixed Reality manual for a specific product assembly process
    - Format: JSON, Images (jpg, png), audios (wav, mp3), 3d objects (glb), videos (mp4, avi, flv, mov, mpg), documents (pdf)
    - Real-time constraints: Not applicable
    - Expected data volume: less than 1MB


The input data for EDITOR part will be provided by the user of the design tool. The input data for VISUALIZATOR part will be provided through object recognition using the camera in mobile or in the HUD.

The output data will be pushed to a mobile device or a HUD used in the Pilot provided by SAG.