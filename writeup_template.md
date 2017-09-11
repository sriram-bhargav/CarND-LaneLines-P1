# **Finding Lane Lines on the Road** 

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

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
1.  Filtering: Remove lines which have unusual slope (ex: slope < 0.45).
2.  Averaging: Slope and mid point of line are used for averaging.
3.  Extrapolating: Once mean slopes and mid points for left and right lanes are found, we then use them to extrapolate to top and bottom of the lane.


### 2. Identify potential shortcomings with your current pipeline

1.  This doesn't work if lane is curvy.
2.  This doesn't work if lane is merging with other lane.
3.  This doesn't work if something is written on the road and algorithm detects non-existent lane line (ex: for driving instructions).
4.  If the lane width is different then the polygon for area of interest needs to changed.
5.  If the camera is not mounted at the center then again the polygon for area of interest needs to changed.
6.  If there are shadows or different lighting conditions (night), then this pipeline won't work.

### 3. Suggest possible improvements to your pipeline

1.  Arrange hough lines into more than two buckets, see which ones are actual left and right lanes (might solve 3).
2.  Adaptive area of interest selection based of distance from bottom of the hough's line (left of right) to bottom of the image (in an ideal case, like in our examples, hough lines touch bottom of the image).
3 . HSV conversion: It allows us to filter colors easily by focusing on hue and saturation/intensity of pixels, and not so much on how dark it is, thus handling shadows and bad lighting conditions easily.
