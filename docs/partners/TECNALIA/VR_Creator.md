## VR_Creator

Short name: VR_Creator

By TECNALIA


### Purpose

This component allows operators/workers to be trained in the operation/usage of a machine, or manufacturing line through the use of Virtual Reality. It creates and consumes immersive VR experiences (with glasses) oriented to training.
 

### Data interfaces

Input and output data (but not user interfaces):


1. INPUT: 360 photos/videos of the warehouse, machine, line
    - Format: jpg, png, mp4, pdf 
    - Real-time constraints: upload speed (important high speed, minimum 100Mb for a smooth experience)
    - Expected data volume: 50-500MB if it is 360 photos, 1-5GB if it is 360 videos

1. INPUT: 3D objects, sequence of training steps
    - Format: Plain text, glb, jpg, png, mp4, pdf, etc ...
    - Real-time constraints: upload speed (important high speed, minimum 100Mb for a smooth experience)
    - Expected data volume: 50-500MB without videos, 1-3GB with videos

1. OUTPUT: VR project data
    - Format:  JSON, Images (jpg, png), audios (wav, mp3), 3d objects (glb), videos (mp4, avi, flv, mov, mpg), documents (pdf)
    - Real-time constraints: download speed (important high speed, minimum 200Mb for a smooth experience), working/play area of 9 square meters
    - Expected data volume: 50-500MB without videos, 1-5GB with videos


The input data will be provided by the user of the design tool. 

The output data will be pushed to the VR glasses. At this moment, we are identifying a pilot to use it.