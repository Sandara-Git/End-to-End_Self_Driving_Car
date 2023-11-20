# End-to-End_Self_Driving_Car
## Read the End to End Self driving Car Research Paper
This map raw pixels from a single front-facing camera directly to steering
commands.
Can drive on: traffic on local roads with or without lane markings 
and on highways.
operates in areas with unclear visual guidance such as in parking
lots and on unpaved roads.
better performance due to self optimize.
system operates at 30 frames per seconds from camera.
captures the 2D nature of images.
## This Research is to:
Avoid the need to recognize specific human 
designated features such as lane markings, guard rails, or other cars 
To avoid having to create a collection of "if,then,else" rules, based on observation of these features.
## Labels
Steering command as 1/r where r is the turning radius in meters. 
use 1/r instead of r to prevent a singularity, when driving straight (the turning radius for driving straight is infinity). 
1/r smoothly transitions through zero from left turns (negative values) to right turns (positive values).
## Features
Training data contains single images sampled from the video, paired with the corresponding steering command (1/r). 
Training with data from only the human driver is not sufficient.
The network must learn how to recover from mistakes. Otherwise the car will slowly drift off the road. 
The training data is therefore augmented with additional images that show the car in different shifts from the center of the lane and rotations from the direction of the road.

![image.png](attachment:image.png)

![image.png](attachment:image.png)
## Conclusion
Without manual decomposition into road or lane marking detection, semantic abstraction, path planning, and control.
A small amount of training data from less than a hundred hours of drivingwas sufficient to train the car to operate in diverse conditions, on highways, local and residential roads in sunny, cloudy, and rainy conditions.
The system learns for example to detect the outline of a road without the need of explicit labels during training.
