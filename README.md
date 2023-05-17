# Gesture_Recognition_using_Neural_Networks
Built a Neural Network Model to automatically identify the human gestures on 2D and 3D data by applying Time Series classification technique on Neural Network

# Problem Statement
A wide range of applications can be found under Computer Vision such as video surveillance, tracking, Human-Computer Interaction. Basic foundation of Computer Vision falls under image/video analysis and pattern recognition. However, accurate vision recognition system continues to be a challenging area of research in Artificial Intelligence. Various techniques have been explored to leverage the power of Neural Network and with coupling with digital sensors to improve the accuracy of the system. 

![Overview of ComputerVision](/resources/Overview_of_Computer_Vision.png)

# Task List
In this project, we will explore various techniques and related problems in the field of Computer Vision. We will focus on different Neural Network methods for Gesture Recognition. With this, we address the questions: 
* How accurate does Neural Network-based Computer Vision models predict identify Gesture Pattern?
* How Time Series Classification using Neural Network helps to recognize the Gestures? 
* which Neural Network models will help to enhance the Gesture Recognition? what are the limitations to for Neural Network to perform better in identifying Gesture?

# Dataset

* To experiment on implementing a Deep Learning model combining visual features and temporal features in the data.
* To train the model, we used a Gesture Commands for Robot Interaction Dataset (GRIT) Dataset. 
* This corpus contains nine Human-Robot Interaction (HRI) command gestures. The nine activities are as follows: Abort, Circle, Hello, No, Stop, Turn Right, Turn Left, and Warn. 
* Six different subjects participated to gesture. Each of them performed the same gesture at least 10 times. A total of 543 sequences were recorded.

![Gestures in GRIT Dataset](/resources/GRIT_dataset_gestures.png)

# Exploratory Data Analysis(EDA)

* The structure of the dataset is that there are 9 gestures, and each gesture has approximately 60 samples and each sample has approximately 24 timesteps [60X24X9]
* The dataset has array representation of each frame. From these, we were able to extract the coordinate points and draw the ellipse points on the image as shown below:

![Keypoints and labels for sample gesture image](/resources/Keypoints_and_labels_for_sample_gesture_image.png)

* Took origin as Nose point as it remained approximately constant for all gestures. By making this change, though the relative measure remains the same, calculating with respect to the object position can be easy to refer back while applying complex methods.
* Stored the coordinates of 17 joint positions of each image frame in an array representative form.

# Preprocessing on 2D gesture data:

* Approach used: Temporal difference is a frame differencing based method using any mathematical measures to identify motion between the sequence of frames.
* Each gesture contains keypoints(x, y) for their joint positions.
* Calculating polar coordinates and angular velocity to capture the movement data over time.
* To convert from Cartesian to Polar coordinate system:
        $$ Radical distance: r = √𝑥2+y2 $$
        Polar angle: 𝜃 = tan-1(y/x) 
        Angular velocity: 𝜔 = 𝛿𝜃 
        Acceleration: 𝑎 = 𝛿𝜔 𝛿𝑡
 
