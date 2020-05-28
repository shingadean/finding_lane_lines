# finding_lane_lines

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

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I
  1. Applied gaussian blur with kernel size of 5
  2.Used canny edge detection
  3.Masked the image with four sided polygon
  4.Get lines using the hough transform
  5.Convert the masked image with lines drawn on it into weighted image

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by by detecting the slope of the lines.
First I initialize the slope, top and bottom value for both the left and right lane. Then according to the slope I calculated the points for both the lanes. Then I calculated the average slope for both lanes and got the b(offset value) using that slope. After that I got the bottom values of both lanes and used cv2.line for drawing the lines


If you'd like to include images to show how the pipeline works, here is how to include an image: 

![output1]: ./test_image_output/solidWhiteRight.jpg


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be multiple lanes can be detected which can also help for lane change of the car 

Another shortcoming could be the curve lane line in challenge video is intersecting which can be improved by sepreating them 


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to detect accurate curve lane lines


