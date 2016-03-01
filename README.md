Project Description
===================

The objective of this project is to detect and track lanes in a series of frames taken from an automobile. The method used for this purpose is Hough transform to detect lines which are then compared using a score of weighted intercepts and angles. Kalman filter is used to narrow the area in which Hough transform needs to be applied, improving performance.


Image processing
================

The images processed before using the Hough transform to enhance the probability of detection and reduce the computational effort. The source image is initially devided into two regions of interest where left and right lanes can be found, then these images are denoised before applying adaptive thresholding to improve contrast. The image obtained after adaptive thresholding is again denoised before applying Canny tranform to obtain the edges. The image obtained is againdenoised to remove noise amplified by the high pass filter.


Lane Detection
==============

Hough line transform is then applied on the image obtained after processing and lines whose angles are steep enough to be possible lanemarkings are gathered, These lines are then scored based on weighted sum of their angles and their intercepts with the bottom of the image. The lines with the highest score are selected as the most probable lanes. 


Kalman Filter
=============

After the detection of first lane markings, a Kalman filter is used to predict an estimate of lanes in the next frame. The estimate is used to narrow down the application of  subsequent hough transforms to a narrow strip surrounding the estimate.
In the even that suitablelanes are not found in this narrow strip, Hough transform is applied on the entire region of interest to find the lanes. If the lanes are still not found, the Kalman estimate of lanes are assumed to be best possible estimate of lane markings.


Results
=======

The program is failry accurate in detecting and tracking lanes, however results did tend to diverge when the curvature of lanes exceeded a certain value. However, after a momentory degression, the predictionagain started to converge with the actual measurements





