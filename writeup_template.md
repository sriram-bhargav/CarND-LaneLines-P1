# **Finding Lane Lines on the Road** 

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

Steps involved in my pipeline (each step uses output from its previous step except first one):
1.  Copy and convert the image to grayscale.
2.  Applying Gaussian blur.
3.  Apply Canny's edge detection algorithm.
4.  Defining region of interest and running Hough's transformation algorithm.
5.  Merge original colored image with output from the step above to draw two lane lines (left and right).

In order to draw a single line on the left and right lanes, I modified the draw_lines() in following steps:
1.  Filtering: Remove lines if their slope is 
2.  Save slopes and mid-point of left and right lane hough lines to extract mean


![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
