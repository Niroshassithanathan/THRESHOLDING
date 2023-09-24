# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.


## Program
# DEVELOPED BY :NIROSHA S
# REG NO : 212222230097

# Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
# Read the Image and convert to grayscale
```
image=cv2.imread("white.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("white.jpg",0)
```
# Use Global thresholding to segment the image
```
ret,thresh_white1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_white2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_white3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_white4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_white5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
# Use Adaptive thresholding to segment the image
```
ret,thresh_white6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
# Use Otsu's method to segment the image 
```
thresh_white7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_white8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
# Display the results
```
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_white1,thresh_white2,thresh_white3,thresh_white4,thresh_white5,thresh_white6,thresh_white7,thresh_white8]
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
![image](https://github.com/Niroshassithanathan/THRESHOLDING/assets/121418437/6fe356e4-7360-49c4-93d9-68374651da5f)

### Global Thresholding
![image](https://github.com/Niroshassithanathan/THRESHOLDING/assets/121418437/d35f38c3-61f6-47e8-bd60-36f1a0bab36c)
![image](https://github.com/Niroshassithanathan/THRESHOLDING/assets/121418437/2a77cf40-bf5b-4147-be9d-1c00e74ad2a7)

### Adaptive Thresholding
![image](https://github.com/Niroshassithanathan/THRESHOLDING/assets/121418437/48fc8fc8-ce62-4c1a-bd57-26f4e09aa1e0)

### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/Niroshassithanathan/THRESHOLDING/assets/121418437/22643c5b-32cb-4ef2-b47f-2fd3d60f9d8d)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

