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

The image pipeline consisted of 6 steps to process the image/frame RGB data and 
annotate lane lines that are found onto the original image/frame. 

STEP 1: We must convert the image to grayscale to normalize the image pixels between 0-255 

![alt text][image1]

STEP 2: Using the output of step one create a Gaussian Blurred image to reduce noise 
	and unwanted details and textures. 

![alt text][image2]

STEP 3: Using the output of step three perform canny edge detection which determines edges
	in the image from transition gradients.

![alt text][image3]

STEP 4: Generate a mask area to create a region of interest and apply this region to the 
	canny edge result removing areas of the image we are not interested in.

![alt text][image4]

![alt text][image5]

STEP 5: Find the slopes of the lines detected by the canny edge algorithm that fall within 
	our region of interest. Calculating their slope we determine if the lines make up the 
	left or right lane.  Using the averaged slopes, we generate lane lines for right and 
	left lanes.
	
![alt text][image6]

STEP 6: Overlay Lane Lines onto original image/frame for annotation of the image

![alt text][image7]

### 2. Identifying potential shortcomings with my current pipeline

This is a rather simplistic algorithm and will perform poorly with winding roads.
	This algorithm will also have issues with various weather conditions and different lighting.


### 3. Possible future improvements to my pipeline

A possible improvement is to change the colorspace to HSV instead of grayscale which will allow 
	for selecting yellow or white lines a little better.  Currently my pipeline does not try to 
	isolate the yellow, but picks it up rather well.

Another potential improvement would be to write a better algorithm for finding the lanes so when 
	lanes curve they will be picked up and annotated correctly.  I think another improvement would
	be to track the polygon of the detected lane.
