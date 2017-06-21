# **Finding Lane Lines on the Road Writeup** 

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

[//]: # (Image References)
[image1]: ./examples/grayscale.jpg "Grayscale"
[imageBefore]: ./test_images_output/solidYellowCurve2-beforeGaussianBlur.png "Before Gaussian Blur"
[imageAfter]: ./test_images_output/solidYellowCurve2-afterGaussianBlur.png "After Gaussian Blur"

---

## Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

Instead of modify draw_lines() function, I made a new function process_image().

My pipeline consisted of following steps.
  1. region_of_interest - Select the region that I should focus.
  2. color_region - Mark the white and yellow lines.
  3. grayscale
  4. canny - Edge detect
  5. gaussian_blur - 
  6. hough_lines - Find lines
  7. weighted_img - Draw lines over original image.
	
Here's the result before and after Gaussian Blur:

![imageBefore]  Before Gaussian Blur
![imageAfter] After Gaussian Blur
Because of resolution, it won't been consider it's a line in Hough transfer.
Using Gaussian Blur here will help it get more smooth.

### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when there are curved lines.
Another shortcoming could be created too many image objects it decrease performance.



### 3. Suggest possible improvements to your pipeline

A possible improvement would be to modify draw_lines() function:
Try not to draw a long line at once, but draw a several sort lines.
I think it will help to detect the curve lines.