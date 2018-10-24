# Hands-on: Installation and Set-up

Let's get started by installing and setting up the necessary python packages to run basic object detection exercises. 

## Step 1: Install Anaconda

### Context: 

Python can be installed on your system through various means. ArcGIS Pro comes with its own python installation, for example. 

For this exercise, we will leverage Anaconda, a free and open source distribution of Python that simplifies package management and deployment. One advantage of this approach is that it completely isolates any work from your important ArcGIS Pro python environment. 

### Procedure:

To install Anaconda, please visit the [Anaconda downloads site](https://www.anaconda.com/download/) and download the Python 2.7 Installer.

![Installer](https://github.com/Qberto/cv-objectdetection-workshop-2018/blob/master/media/Capture1.PNG) 

Once downloaded, run the installer and please ensure the following:

- When prompted, do not set PATH
- Do not set as default Python 3.7 (unless you know why you would want to)

Once installation is complete, confirm that you can open the Anaconda Command Prompt. 

![Anaconda Command Prompt](https://github.com/Qberto/cv-objectdetection-workshop-2018/blob/master/media/Capture2.PNG) 

This is very similar to the regular Windows command prompt, with a few important differences:

- Python executables point to the Anaconda installation version of python.
- A conda environment is established. 

What is a [conda environment](https://conda.io/docs/user-guide/concepts.html#conda-environments)? Well it's a way to ensure that a python installation and all the stuff we're going to pile up on top of it does not interfere with other installations of python that run important stuff for us. 

## Step 2: Create and activate a new conda environment

To create a conda environment for this exercise, we will open the Anaconda Command Prompt and enter the following command: `conda create --name objectdetection python=3.5`

![Anaconda Command Prompt](https://github.com/Qberto/cv-objectdetection-workshop-2018/blob/master/media/Capture4.PNG) 

To activate this new environment, use the following command: `conda activate objectdetection`

You should now see the command prompt start with the name of the environment:

![Anaconda Command Prompt](https://github.com/Qberto/cv-objectdetection-workshop-2018/blob/master/media/Capture3.PNG) 
