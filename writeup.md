# **Finding Lane Lines on the Road**

### Reflection

### 1. Pipeline Description.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

1. Convert the images to grayscale
2. Use Gaussian smoothing to 
3. Use canny edge detector
4. Use an image mask to only keeps the region of interest
5. Use hough transform to find lane Lines

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by average the slopes and centers of lines detected.First, I separating line segments by their slope to decide which segments are part of the left line vs. the right line.Then average the position of each of the lines by slopes and centers and extrapolate to the top and bottom of the masked area.

![](http://p37mg8cnp.bkt.clouddn.com/201805100952_526.png)

![](http://p37mg8cnp.bkt.clouddn.com/201805100953_624.png)

![](http://p37mg8cnp.bkt.clouddn.com/201805100954_146.png)

![](http://p37mg8cnp.bkt.clouddn.com/201805101010_880.png)

![](http://p37mg8cnp.bkt.clouddn.com/201805100956_704.png)

### 2. Identify potential shortcomings with current pipeline

One potential shortcoming would be the road is not always straight the lines detected would not fit well when the car drive in the curve.

Another shortcoming could be region of interest is fixed,but when a car drive Uphills or Downhills the ROI may not work well.

For video, only single frame images are processed, and the lane line detected in video will flicker due to the influence of some abnormal points. 

### 3. Possible improvements

A possible improvement would be to use curve-fitting rather than average the position of lines by slopes and centers.

Another potential improvement could be to use kalman filter to make the detection more robust.
