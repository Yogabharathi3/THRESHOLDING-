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
# DEVELOPED BY :Yogabharathi
# REG NO : 212222230179

# Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
# Read the Image and convert to grayscale
```
image=cv2.imread("kitty.jpg",1)
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
![image](https://github.com/Yogabharathi3/THRESHOLDING-/assets/118899387/bc0181fd-545e-406b-a99b-ec306adf2a9a)

### Global Thresholding

![image](https://github.com/Yogabharathi3/THRESHOLDING-/assets/118899387/d0fa648c-a9dd-4124-9ec7-1c4e04f572fb)
![image](https://github.com/Yogabharathi3/THRESHOLDING-/assets/118899387/d438cbc6-d5a7-4829-aac0-a9963c00837d)
![image](https://github.com/Yogabharathi3/THRESHOLDING-/assets/118899387/83d5797d-e39a-4714-b1b7-c85fecd0694d)
![image](https://github.com/Yogabharathi3/THRESHOLDING-/assets/118899387/1d967365-e890-4d6a-9284-d28140e7f8d5)
![image](https://github.com/Yogabharathi3/THRESHOLDING-/assets/118899387/70df0f3b-5639-452a-9ef9-01a3184234fd)

### Adaptive Thresholding
![image](https://github.com/Yogabharathi3/THRESHOLDING-/assets/118899387/0291563f-7000-4bc7-954b-f1b0619e0959)

![image](https://github.com/Yogabharathi3/THRESHOLDING-/assets/118899387/b1357c01-384f-4b81-aa54-7cdd48ede1f4)

### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/Yogabharathi3/THRESHOLDING-/assets/118899387/d225fe58-7a72-4b29-93f1-46158cc670fd)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
