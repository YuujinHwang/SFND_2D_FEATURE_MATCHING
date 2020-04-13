<<<<<<< HEAD
# SFND 2D Feature Tracking

<img src="images/keypoints.png" width="820" height="248" />

The idea of the camera course is to build a collision detection system - that's the overall goal for the Final Project. As a preparation for this, you will now build the feature tracking part and test various detector / descriptor combinations to see which ones perform best. This mid-term project consists of four parts:

* First, you will focus on loading images, setting up data structures and putting everything into a ring buffer to optimize memory load. 
* Then, you will integrate several keypoint detectors such as HARRIS, FAST, BRISK and SIFT and compare them with regard to number of keypoints and speed. 
* In the next part, you will then focus on descriptor extraction and matching using brute force and also the FLANN approach we discussed in the previous lesson. 
* In the last part, once the code framework is complete, you will test the various algorithms in different combinations and compare them with regard to some performance measures. 

See the classroom instruction and code comments for more details on each of these parts. Once you are finished with this project, the keypoint matching part will be set up and you can proceed to the next lesson, where the focus is on integrating Lidar points and on object detection using deep-learning. 

## Dependencies for Running Locally
* cmake >= 2.8
  * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1 (Linux, Mac), 3.81 (Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* OpenCV >= 4.1
  * This must be compiled from source using the `-D OPENCV_ENABLE_NONFREE=ON` cmake flag for testing the SIFT and SURF detectors.
  * The OpenCV 4.1.0 source code can be found [here](https://github.com/opencv/opencv/tree/4.1.0)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools](https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory in the top level directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./2D_feature_tracking`.
=======

## MP.7 Total detected keypoints (knn)

### SHITOMASI
7008 kpts
### HARRIS
950 kpts
### FAST
26342 kpts
### BRISK
14571 kpts
### ORB
2847 kpts
### AKAZE
7240 kpts
### SIFT
7435 kpts

## MP.8 Matched keypoints (knn)

### SIFT Descriptor uses MAT_FLANN, while others use MAT_BF
(matched kpts , time, efficiency)
### SHITOMASI
- BRISK : 2225 / 182 / 12
- BRIEF : 3234 / 169 / 19
- ORB : 2856 / 169 / 17
- FREAK : 2229 / 134 / 17
- AKAZE : fail(compute_descriptor)
- SIFT : 3281 / 137 / 24

### HARRIS
- BRISK : 295 / 225 / 1.3
- BRIEF : 396 / 205 / 1.9
- ORB : 360 / 203 / 1.8
- FREAK : 290 / 165 / 1.8
- AKAZE : fail
- SIFT : 385 / 188 / 2

### FAST
- BRISK : 7343 / 23 / 320
- BRIEF : 12184 / 21 / 568
- ORB : 10388 / 22 / 475
- FREAK : 7721 / 22 / 344
- SIFT : 14991 / 21 / 698

### BRISK
- BRISK : 5073 / 3861 / 1.3
- BRIEF : 7474 / 3819 / 2.0
- ORB : 5095 / 3843 / 1.3
- FREAK : 5008 / 3917 / 1.3
- SIFT : 7225  3812 / 1.9

### ORB
- BRISK : 1378 / 88 / 16
- BRIEF : 1403 / 81 / 17
- ORB : 1466 / 85 / 17
- FREAK : 627 / 114 / 6
- SIFT : 1605 / 79 / 20

### AKAZE
- BRISK : 3235 / 904 / 3.6
- BRIEF : 4041 / 971 / 4.2
- ORB : 3340 / 910 / 3.7
- FREAK : 3228 / 813 / 4.0
- AKAZE : 3463 / 853 / 4.1
- SIFT : 3683 / 831 / 4.4

### SIFT
- BRISK : 3235 / 906 / 3.6
- BRIEF : 4041 / 885 / 4.6
- ORB : 3340 / 885 / 3.8
- FREAK : 3228 / 799 / 4
- SIFT : 3683 / 840 / 4.4

## MP.9 BEST SET

FAST-SIFT
FAST-BRIEF
FAST-ORB
