# Image-Background-Generator
Assignment for Marble.ai DS internship
## Description
* IBG changes the background or style of the content image with background image. Three stages are used to realize the output image depending on the modes of usage.
* Firstly, the user provided background is taken, if not provided, then background image is generated using user provided prompt with Stable Diffusion model. 
* Secondly, mask is created for the content image's background using Mediapipe, Deeplabv3 or YOLOv8 model. 
* Thirdly, depending on user provided argument, the style of background image is applied to background of content image using VGG19 network by guiding the stylized pixels.
## General Requirements
- Place all the content images in the input directory.
- Place the background image in background directory.
- If Neural Style Transfer is not set, the background image will be set as background of the content image.
- If Neural Style Transfer is set, the background image's style will be applied to the background of the content image.
- If blur is set, then the background of the content image will be blurred.

## Code Requirements 🧙‍♀️
Use Python 3.8.13. Setup conda environment, git clone repo and run the below command,
``python setup.py``

## How to run 🏃‍♂️
``python run.py --input <dir path to input images> --output <dir path to store output images> --bg <dir path to background image> --mode <mode of segmentation>``

Arguments:

|Argument|	Description|	Value |
|--- | --- | ---
|--input|Path to input images directory|String|
|--output|Path to output images directory|String|
|--bg|Path to background image file|String|
|--mode| Mode of segmentation to be used to generate mask| Integer 0 : Mediapipe, 1 : Deeplabv3, 2 : Yolov8|
|--prompt|Text prompt to generate background. Used when --bg is not provide|	String|
|--nst|Perform Neural Style Transfer of background|store_true|
|--blur|Perform Gaussian Blur to Background|store_true|
