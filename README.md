# **BOSCH's Age and Gender Detection**

The goal of the project is to detect age and gender of peoples from given low quality CCTV surveillance video. For the same purpose, we have broken the problem statement into three parts:


1.   Detecting Persons from the surveillance video and extracting the faces from it.
2.   Enhancing the photo thus obtained through GAN models.
3.   Predicting the gender and age from the super-resoluted image obtained.


The above components have been named as M1, M2 and M3 respectively.

The codes have been written in Google Colabotary notebook.

## **Pre-requisites for running the code:**



*   The colab must be connected to GPU runtime.
*   The version of the libraries should be the following:
    *  numpy : 1.21.5
    *  openCV : 4.1.2
    *  torch : 1.10.0+cu111
    *  matplotlib : 3.2.2
    *  Pillow : 7.1.2
    *  pytube : 12.0.0
    *  gdown : 4.2.2
    * basicsr>=1.3.3.11
    * facexlib>=0.2.0.3
    * gfpgan>=0.2.1



## **How to run the code?**


* First two cells of the ipynb installs the necessary libraries needed for stage 1.
```
!pip install --upgrade --no-cache-dir gdown
```
```
!pip install pytube
```
* The next three cells downloads the required data such as pretrained wights of the models and other necessary data. 
```
!gdown --id '10NaxFCpitXjtLX0rZ4M02FV0rOGRpLKI' #weights_dummy.pt 
```
```
!gdown --id '1rJI17Y2u0MDmqv2qkcM6ScOYZpGE_9dd' #weights.caffemodel
```
```
!gdown --id '1M38YE0S9ZztaKK9JJ1GeBbUqIunAimRV' #deploy.prototext file for caffemodel
```

* **Kindly run these cells individually as it might take few seconds to load the large files into the workspace.**

After doing so, you can run the rest of the code. The training has been skipped and the model is loaded with pretrained weights. In case, you want to train thestage 1 of the model, then you need to uncomment the cell just below 


> **Note:** It might take some time to clone some repositories in the notebook.



* After running some of the initial functions, the program will pause and ask the user for the input. ![input.jpg](https://user-images.githubusercontent.com/75763525/159293859-37e20f18-ac56-4321-93bc-2fd2f12707de.jpg)

  * The user have the flexibility to provide the input either as images or videos. 
  * The user can provide the video input in two formats, i.e., either as a youtube video link or upload the video from the local system. 
  * For providing video inputs, first you need to give 0 as input and again you will be asked for input. Enter 0 if you want to enter youtube video link otherwise it will ask to upload files from the system.
  ![yt.jpg](https://user-images.githubusercontent.com/75763525/159293988-d1210c02-d96a-4918-a3f5-9a9a2406bfb1.jpg)

  * For providing image inputs, the user need to enter 1 and choose the images **only from the local system**. 
  

> **Note:** It might take some time to upload the images/videos into the google colab workspace depending upon the speed of the network being used.

> **Note:** Kindly refrain from using YouTube video link whose content length is more than 5 minutes, as it might not be processed by pytube library. 


