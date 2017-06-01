# **Finding Lane Lines on the Road** 

## Writeup

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

![image1](/test_images/grayscale.jpg)

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 8 steps. 

1) Converted the images to grayscale.
2) Apply blur filter.
3) Apply canny edge filter. 
4) Mask the region of interest, to avoid interferences,
5) Hough transformation used to detect lines.
6) Separation of the right and left lines.
7) Calculate the average line, to draw a single line in each side.
8) Exptend the lines to roi limits.

The draw_lines function was modified to separate left and right lines, get the average line,
extrapolate the lines to roi, and with a buffer that replace missing lines with ones of the 
previous frame, as a way to estabilizate the image.

I used the separate_lines function to eliminate low slopes lines, so I managed to run the challenge part 
of the project.

![image2](/test_images/grayscale.jpg) "Grayscale"

![image3](/test_images/image_canny.jpg) "Canny"

![image4](/test_images/mask.jpg) "Mask"

![image5](/test_images/draw_lines.jpg) "Lines Detected"


### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be the lost of lines due to some shadow over the road,
or fading lines.
Another shortcoming would be at night or under any weather condition that may dificult the visibility.


### 3. Suggest possible improvements to your pipeline

Trying to detect other colors instead of gray scale, would help to detect some fading lines.
