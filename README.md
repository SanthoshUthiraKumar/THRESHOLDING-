# EX-08 THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:
Use Otsu's method to segment the image and display the results.
## Program
```
DEVELOPED BY: Santhosh U
REGISTER NO: 212222240092
```
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("dark.jpeg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("dark.jpeg",0)
```
### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
## Output
### Original Image
![Output1](https://github.com/SanthoshUthiraKumar/THRESHOLDING-/assets/119477975/f280ed2a-0599-45cd-85da-c4a651d5b73d)

### Global Thresholding
![Output2](https://github.com/SanthoshUthiraKumar/THRESHOLDING-/assets/119477975/36e0532c-c71d-44e1-a476-923db828a55c)
![Output3](https://github.com/SanthoshUthiraKumar/THRESHOLDING-/assets/119477975/b75cb1aa-f047-4192-84b5-dcfcf1ca0c08)
![Output4](https://github.com/SanthoshUthiraKumar/THRESHOLDING-/assets/119477975/6df4ff54-e42b-4f42-9242-8b1b6ef8f796)
![Output5](https://github.com/SanthoshUthiraKumar/THRESHOLDING-/assets/119477975/5176d048-22a9-4cae-a953-da7b7ae67039)
![Output6](https://github.com/SanthoshUthiraKumar/THRESHOLDING-/assets/119477975/e807514b-1193-4472-94f0-4bd36d8878a8)

### Adaptive Thresholding
![Output7](https://github.com/SanthoshUthiraKumar/THRESHOLDING-/assets/119477975/302e2649-3824-4d82-a7ff-85239af474b1)
![Output8](https://github.com/SanthoshUthiraKumar/THRESHOLDING-/assets/119477975/e2da14b0-ea05-47d7-afa0-6e7193fb0c6a)

### Optimum Global Thesholding using Otsu's Method
![Output9](https://github.com/SanthoshUthiraKumar/THRESHOLDING-/assets/119477975/6f0b8cdf-8feb-478e-b26e-9cddb5c39099)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
