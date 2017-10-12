# **Finding Lane Lines on the Road** 

## George Vigelette
---

**Finding Lane Lines on the Road**

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

In this project I perform detection of lane lines in images and Video clips using Python and OpenCV.  OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images.  

The goals of this project was to create a pipeline to detect left and right lane lines and describe the pipeline.


[//]: # (Image References)

[image1]: ./test_images_output/grayscale.jpg "Grayscale"
[image2]: ./test_images_output/gaussian.jpg "Gaussian"
[image3]: ./test_images_output/canny_edge.jpg "CannyEdge"
[image4]: ./test_images_output/mask.jpg "Mask"
[image5]: ./test_images_output/roi.jpg "Region Of Interest"
[image6]: ./test_images_output/lanes.jpg "Lanes"
[image7]: ./test_images_output/final_output.jpg "End Result"

---

### Reflection

### 1. Pipeline Description

My pipeline consisted of 6 steps to achieve the desired results. 

STEP 1: I converted the image/frame to grayscale 

![alt text][image1]

STEP 2: Using the output of step one create a Gaussian Blurred image 

![alt text][image2]

STEP 3: Using the output of step three perform canny edge detection on image 

![alt text][image3]

STEP 4: Generate a mask area to create a region of interest and apply to canny edge result

![alt text][image4]

![alt text][image5]

STEP 5: Find the slopes of the lines within our region of interest and determine if they are 
	making up the left or right lane.  Using the averaged slope, generate lane lines for right
	and left lanes.
	
![alt text][image6]

STEP 6: Overlay Lane Lines onto original image/frame 

![alt text][image7]

### 2. Identifying potential shortcomings with my current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Possible future improvements to my pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
