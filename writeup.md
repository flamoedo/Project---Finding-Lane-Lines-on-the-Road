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

My pipeline consisted of 8 steps. 

1) Converted the images to grayscale.
2) Apply blur filter.
3) Apply canny edge filter. 
4) Mask the region of interest, to avoid interferences,
5) Hough transformation used to detect lines.
6) Separation of the reight and left lines.
7) Calculate the average line, to draw a single line in each side.
8) Exptend the lines to roi limits.


[image2]: ./test_images/grayscale.jpg "Grayscale"

[image3]: ./test_images/image_canny.jpg "Grayscale"

[image4]: ./test_images/mask.jpg "Grayscale"

[image5]: ./test_images/draw_lines.jpg "Grayscale"


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be the lost of straignt lines, that are necessary to Hough transformation, on curved road.
At night or under any weather condition that may harm the vivibility.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to take the average of lines among frames, this would estabilizate the lines.

Use another tipe of transformation to detect curves, and not only straight lines.