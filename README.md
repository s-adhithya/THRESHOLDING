# THRESHOLDING
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
Use Otsu's method to segment the image.

### Step6:
Display the results.

## Program

```
Developed by: Adhithya.S
Register No: 212222240003
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2




# Read the Image and convert to grayscale
image = cv2.imread("cheetah.jpeg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("cheetah.jpeg",0)



# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)



# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)



# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)



# Display the results
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
![Screenshot 2023-10-18 111447](https://github.com/s-adhithya/THRESHOLDING/assets/113497423/fba6d463-c795-4ba2-b152-86b9e757d35b)


### Global Thresholding
![Screenshot 2023-10-18 111505](https://github.com/s-adhithya/THRESHOLDING/assets/113497423/60bafa3c-8040-4839-8828-83de659144a5)
![Screenshot 2023-10-18 111544](https://github.com/s-adhithya/THRESHOLDING/assets/113497423/df639aab-9a67-4ef1-93f1-8e32f31378c0)
![Screenshot 2023-10-18 111602](https://github.com/s-adhithya/THRESHOLDING/assets/113497423/64ca3869-5749-4fa7-9059-41e1f9d632d2)
![Screenshot 2023-10-18 111618](https://github.com/s-adhithya/THRESHOLDING/assets/113497423/4cd7848f-7f21-4e88-bfe6-965aba627134)


### Adaptive Thresholding
![Screenshot 2023-10-18 111633](https://github.com/s-adhithya/THRESHOLDING/assets/113497423/0b503a5f-23e4-4317-835e-4131ed83a62e)
![Screenshot 2023-10-18 111648](https://github.com/s-adhithya/THRESHOLDING/assets/113497423/ed31020d-87ab-4dc2-ba8b-952cd4bb0dbf)


### Optimum Global Thesholding using Otsu's Method
![Screenshot 2023-10-18 111715](https://github.com/s-adhithya/THRESHOLDING/assets/113497423/10d05350-cae1-420a-bf17-b1f738053b72)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

