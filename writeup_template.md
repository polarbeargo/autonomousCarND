# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of following steps. First, I converted the images to grayscale. Second, I applied 

Gaussian smoothing with three dimensional kernel. Third, Define our parameters with low threshold:high 

threshold=1:3 for Canny Edges detection and apply. Four, find region-of-interest vertices then applied 

to Hough transform.

  In order to draw a single line on the left and right lanes, I modified the draw_lines() function by 

separating line segments by their slope ((y2-y1)/(x2-x1)) to decide which segments are part of the left
    
line vs. the right line.  Then, you can average the position of each of the lines and extrapolate to the

top and bottom of the lane.

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


After testing my pipeline on challenge.mp4 and notice that a few frames have bad fits for the lane line. 




### 3. Suggest possible improvements to your pipeline

 I would think that a more robust lane finder would use previous frames to weight the choice of lane for

 the current frame and dropping all obviously incorrect dark colors.
