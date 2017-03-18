**Finding Lane Lines on the Road** 

## Writeup

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

#### My pipeline consisted of 6 steps. 

- First, I converted the images to grayscale

- Then apply gaussian_blur

- Then apply canny transformation

- Then select region of interest

- Then draw hough_lines

- Then apply lines on original image

#### Changes in draw_lines() function

- First, I split lines by slop to left and right
    
- Then I calculate top and bottom Y coordinate in left lane lines

- Then I calculate top and bottom Y coordinate in right lane lines

- Then select the min top and max bottom Y from left and right lines
    
- Then I calcualte linear regression coefficients for both left and right using all the lines   

- Then I calculate top and bottom X coordinates by applying the cofficients to top and bottom Y coddinate for both left and right

- Then draw lines using top and bottom X Y coordinates

### 2. Identify potential shortcomings with your current pipeline

- region of interest is fixed and has to be manually tuned for different size of images

- lane lines are not stable

- to remove noise by more tuning can be done with blur and canny transformation

- linear regression does not deal with curves

### 3. Suggest possible improvements to your pipeline

- auto select region of interest from the first frame of video

- make line drawing more stable and smooth

- avoid lane lines intersect
