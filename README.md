# Eye aspect ratio to detect eye blinks

## Description
This repository is made to implement this [paper](http://vision.fe.uni-lj.si/cvww2016/proceedings/papers/05.pdf) by Soukupová and Čech in 2016. The aim of the paper is to do Real-time eye blink detection using facial landmarks. The ear involves a very simple calculation based on the ratio of distances between facial landmarks of the eyes. This method for eye blink detection is fast, efficient, and easy to implement.

Each eye is represented by 6 (x, y)-coordinates, starting at the left-corner of the eye (as if you were looking at the person), and then working clockwise around the remainder of the region:

![alt text](https://github.com/sakethbachu/ear-python/blob/master/img/blink_detection_6_landmarks.jpg "Logo Title Text 1")

## Methods
* To count a blink we infer a simple and elegant equation.
* There is a relation between the width and the height of the coordinates as mentioned in the above image.
* Based on the work by Soukupová and Čech in their 2016 paper, Real-Time Eye Blink Detection using Facial Landmarks, we can then derive an equation that reflects this relation       called the eye aspect ratio (EAR):

![alt text](https://github.com/sakethbachu/ear-python/blob/master/img/ear-equation.png "Logo Title Text 1")

* Where p1, …, p6 are 2D facial landmark locations.
* The numerator of this equation computes the distance between the vertical eye landmarks while the denominator computes the distance between horizontal eye landmarks, weighting     the denominator appropriately since there is only one set of horizontal points but two sets of vertical points.
* Using this simple equation, we can avoid image processing techniques and simply rely on the ratio of eye landmark distances to determine if a person is blinking.
* This can be visualized by the following image,

![alt text](https://github.com/sakethbachu/ear-python/blob/master/img/ear%20comparison.jpg "Logo Title Text 1")

## Features
* We use the dlib library for accessing the facial landmarks, which will intern be used in the calculations of ear. 
* The following image demonstrates the standard facial landmarks available in the dlib library, 

![alt text](https://github.com/sakethbachu/ear-python/blob/master/img/dlib%20landmarks.jpg "Logo Title Text 1")

## Demo

## Usage
Use this in command line where python is installed `python detectblinks1.py --shape-predictor shapepredictor`


## Requirements
 1. Python
 2. OpenCV
 3. Dlib
 4. Shape predictor by dlib
