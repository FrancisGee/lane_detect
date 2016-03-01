Project Description
===================

The objective of this project is to detect and track lanes in a series of frames taken from an automobile. The method used for this purpose is Hough transform to detect lines which are then compared using a score of weighted intercepts and angles. Kalman filter is used to narrow the area in which Hough transform needs to be applied, improving performance.

Image processing
================

The images processed before using the Hough transform to enhance the probability of detection and reduce the computational effort. The source image is initially devided into two regions of interest where left and right lanes can be found, then these images are denoised before applying adaptive thresholding to improve contrast. The image obtained after adaptive thresholding is again denoised before applying Canny tranform to obtain the edges. The image obtained is againdenoised to remove noiseamplified by the high pass filter.


