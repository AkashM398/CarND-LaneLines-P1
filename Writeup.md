# **Finding Lane Lines on the Road** 


**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


---

### Reflection

### 1. Description of Pipeline.

 - The image will be taken as input for which lines have to be detected. For video, it will be turned into frames which will be read at a time. 
 - The input image will be converted into grayscale.
 - HSL space works better than RGB, since RGB can be affected when there is a variation to the lighting. White and Yellow color filter is created for the image in the HSL space and the RGB image is masked with these filters.
 - Edges are detected using the Canny edge detector
 - The grayscale image is blurred using gaussian filter
 - Assuming that camera is mounted at the center top of the image, we get the triangular region as our region of interest to detect the lane line.
 - Hough transform is used to get the lines on the image in the form of (x1,y1,x2,y2).
 - Quadratic curve is fitted in the set of points obtained from hough lines using numpy polyfit function, since the road will not always be straight and curves on turn.


### 2. Potential shortcomings with this pipeline.
 - The current pipeline will fail intersection and can only work on straight and curve roads, since all parameter are hard coded.
 - Finding optimal parameters and some calibration process should be performed to automate finding and tuning the parameters.


### 3. Suggest possible improvements to your pipeline

 - A calibration process to optimise and tune the parameters automatically.
 - A CNN model to detect lane lines accurately