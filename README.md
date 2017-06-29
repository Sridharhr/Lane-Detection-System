# lane-detection-opencv

### About
Advanced OpenCV for lane detection and curvature.

### Data

* Camera calibration chessboard images are in `camera-cal`. Use to compute camera calibration matrix and distortion coefficients.


### Code / Pipeline

`code.ipynb` (Jupyter notebook) implements the following pipeline:

* Camera calibration
* Distortion correction
* Transforms and Theresholding: Line detection through gradient threshodling along x and y axes, Color thresholding (S channel in HLS space to detect 'saturated' lane lines, V channel in HSV space to eliminate shadows.) 
* Perspective Transform using a trapezoidal region of interest
* Finding centers
	* Discrete horizontal slices
	* Convolution along x in each slice, to find points of highest pixel concentration (=lane centers)
	* Fit lines to centers found at each slice
* Find curvature and offset from center
* Inverse perspective transform to draw on road


### Testing

* Use `test.mp4` to test. Sample output in `out.mp4`
