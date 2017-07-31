# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:

* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consists of following steps:

1. Copy the image from the test images
2. Change the image into grayscale image
3. Smoothen the image using Gaussian smoothing process with a kernel size = 5
4. Perform Canny edge detection to find edges
5. Apply region masking to mask the image only through the region of interest
6. Apply Hough transform to the edge image found from Canny algorithm
7. Combine the initial image and blank image with hough lines
8. Finally modified draw_lines() function to extrapolate left and right lines


Steps for modification of the draw_line() function

1. Calculate slopes for all the line generated cv2.HoughLinesP() function
2. Segregate the coordinates (x1,y1,x2,y2) of the lines with positive (right lines) and negative (left line) slopes
3. Take the mean / average of the individual coordinates for both left and right lines
4. Calculate slope and y-intercept of the average coordinates for both left and right lines
5. Define y1 and y2 for both lines and calculate x1 and x2 from average slope and intercept calculated in the previous step
6. Draw line with x1,y1 and x2,y2 both in the left and right side


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... In the optional challenge, the pipeline is unable to detect lane lines if it is a curve rather than straight line

Another shortcoming could be ... The pipeline is not properly detecting yellow line


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ... Instead of grayscaling, the color space can be changed to HSL or HSV for better identification of yellow line 

Another potential improvement could be to ... Curve fitting mechanism can be implemented to detect the lane lines in optional challenge
