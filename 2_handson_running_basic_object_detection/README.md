# Hands-on: Running Basic Object Detection

Now that we have everything installed, we're ready to start running some basic object detection exercises. We'll start with a pretrained model that uses the [COCO dataset](http://cocodataset.org/#home). This dataset contains a number of useful labels and can be used in combination with several pretrained models. It is also easy to use as a baseline to perform [transfer learning](https://machinelearningmastery.com/transfer-learning-for-deep-learning/). 

## Step 1: Run COCO Object Detection on Static Images

For this example, a jupyter notebook is available that performs the needed logic to execute object detection on a folder of images. To run the example, open the Anaconda Command Prompt, activate the 'objectdetection' environment (`conda activate objectdetection`), and change directory to the TensorFlowModels_GIS_ANieto\object_detection directory. Once there, run `jupyter notebook` to kick off a jupyter notebook file browser on your internet browser.

The jupyter notebook file browser will show the contents of the folder it was launched from. Let's open the Jupyter Notebook titled "TensorFlow_ObjectDetection_Demo01_StaticImages.ipynb" by clicking on it. This should load a new window.

![webcam detection](https://github.com/Qberto/cv-objectdetection-workshop-2018/blob/master/media/TeddyBear.PNG) 


## Step 2: Run COCO Object Detection on Webcam Feed

This example is quite similar, but we are now incorporating the cv2 module to connect to our laptop's webcam feed and pass this stream of imagery as an input to the model in the previous example. 

Let's open the notebook titled "TensorFlow_ObjectDetection_Demo02_Stream.ipynb" and follow along. 

![webcam detection](https://github.com/Qberto/cv-objectdetection-workshop-2018/blob/master/media/webcam_detection.PNG) 


## Step 3: Run COCO Object Detection on a section of your screen

One more interesting option is to use part of your screen to run inference (execution of the model). This method can be quite useful for demonstration and prototyping purposes. It allows you to designate bounding box coordinates for the section of your screen that you wish to pass to the model for observation. 

This jupyter notebook can be found at

![webcam detection](https://github.com/Qberto/cv-objectdetection-workshop-2018/blob/master/media/JacksonHoleDetection.gif) 