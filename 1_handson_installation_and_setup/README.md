# Hands-on: Installation and Set-up

Let's get started by installing and setting up the necessary python packages to run basic object detection exercises. 

## Step 1: Install Anaconda

### Context: 

Python can be installed on your system through various means. ArcGIS Pro comes with its own python installation, for example. 

For this exercise, we will leverage Anaconda, a free and open source distribution of Python that simplifies package management and deployment. One advantage of this approach is that it completely isolates any work from your important ArcGIS Pro python environment. 

### Procedure:

To install Anaconda, please use the version that supports Python 3.6, and can be found [at this location](https://repo.anaconda.com/archive/Anaconda3-5.2.0-Windows-x86_64.exe).

Once downloaded, run the installer and leave the following two options **unchecked**:

- Add Anavonda to my PATH environment variable
- Register Anaconda as my default Python 3.6

Once installation is complete, confirm that you can open the Anaconda Command Prompt. 

![Anaconda Command Prompt](https://github.com/Qberto/cv-objectdetection-workshop-2018/blob/master/media/Capture2.PNG) 

This is very similar to the regular Windows command prompt, with a few important differences:

- Python executables point to the Anaconda installation version of python.
- A conda environment is established. 

What is a [conda environment](https://conda.io/docs/user-guide/concepts.html#conda-environments)? Well it's a way to ensure that a python installation and all the stuff we're going to pile up on top of it does not interfere with other installations of python that run important stuff for us. 

## Step 2: Create and activate a new conda environment

To create a conda environment for this exercise, we will open the Anaconda Command Prompt and enter the following command: `conda create --name objectdetection python=3.6`

![Anaconda Command Prompt](https://github.com/Qberto/cv-objectdetection-workshop-2018/blob/master/media/Capture4.PNG) 

To activate this new environment, use the following command: `conda activate objectdetection`

You should now see the command prompt start with the name of the environment:

![Anaconda Command Prompt](https://github.com/Qberto/cv-objectdetection-workshop-2018/blob/master/media/Capture3.PNG) 

To see this and other conda environments, enter `conda env list`.

To keep things organized (and safe), all of the following python package installations will occur in this 'objectdetection' conda environment. 

## Step 3: Run PIP installs

Pip is a package management system used to install and manage software packages written in Python. It's similar but a bit lighter than Anaconda. We will use it to install a few useful python packages for our object detection projects. 

First, let's ensure that pip itself is up to date by executing: `python -m pip install --upgrade pip`. The current version of pip (as of October 23, 2018) is pip-18.1. 

Next, we're going to execute a series of pip installs:

- `pip install pillow`
- `pip install lxml`
- `pip install jupyter`
- `pip install matplotlib`
- `pip install opencv-python`
- `pip install requests`

 Let's now proceed to install the biggest python package yet...

## Step 4: Install TensorFlow

TensorFlow is Google's open source Machine Learning framework. This is the main engine for most of the object detection work we'll be doing in this exercise. 

TensorFlow comes in two variants: TensorFlow-CPU and TensorFlow-GPU. Can you guess what they're intended for? 

For this exercise, we'll leverage simple object detection exercises using pre-built models. We will stick with TensorFlow-CPU for now and you can progress to GPU once you are ready to kick off your new projects that require your beefy graphics card for additional horsepower. 

To install TensorFlow-CPU, execute the following: `pip install --upgrade tensorflow`. This step may take a few minutes. Let's take a brief break and refill our coffee. 

## Step 5: Install the ArcGIS API for Python

Finally, the crucial ingredient to integrate and make all of the object detection work nicely with ArcGIS: the ArcGIS API for Python!

Let's install this via a simple command: `conda install -c esri arcgis`. Conda is a little hesitant to install, so make note of the confirmation step and enter `y` when prompted. 

A conda install is very similar to pip. Let's continue. 


## Step 6: Validate Package Installations

I also like to verify all of the installations succeeded by opening up a python prompt and importing each package module in python. To do this, let's execute the following command: `ipython` and run the following command for each package:

- Pillow: `import PIL`
- lxml: `import lxml`
- jupyter: `import tornado`
- matplotlib: `import matplotlib`
- opencv-python: `import cv2`
- TensorFlow: `import tensorflow`
- ArcGIS API for Python: `import arcgis`

If all of these import statements went smoothly, exit the ipython prompt by running `exit()`. 

If everything went smoothly, congratulations! Installation of the python packages is complete!

## Step 7: Download the TensorFlow Object Detection API

We have installed TensorFlow, the python package, but we need models and data for our exercise. We will leverage the [TensorFlow research models GitHub repository](https://github.com/tensorflow/models). 

This repository comes with .proto files that need to be compiled before use, which can be a bit error-prone. To make this simple, I have already downloaded the research models into a Box folder and compiled all the .proto binaries into the needed files for our exercise. 

Go to https://esri.box.com/s/g0law24h8zb5t8dn2a4qwwcsjuz4b8t2 and download and unzip the "TensorFlowModels_GIS_ANieto_181011.zip" file (1.6 GBs). This might take a few minutes, so let's take another break and refill our coffee again. If there are any access issues, I can also provide you the zip file via sneakernet (i.e. USB drive)

### Optinal Step: 
If you want to go down the .proto compiler route, clone the TensorFlow models repo, head to the [protoc releases page](https://github.com/protocolbuffers/protobuf/releases) and download the protoc-3.6.1-win32.zip, extract it, and you will find protoc.exe in the bin directory. You can move this to something more appropriate if you like, or leave it here. I eventually put mine in program files, making a "protoc" directory and dropping it in there.

Now, from within the models directory in the cloned models repo, you can use the protoc command like so:

`"C:/Program Files/protoc/bin/protoc" object_detection/protos/*.proto --python_out=.`


## Installation and Set-up Complete

At this point, you should have the "TensorFlowModels_GIS_Anieto" directory unzipped in an easily-accessible location and all the python packages installed. 

Congratulations and thank you for coming along so far! The fun part now begins. 
