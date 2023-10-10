# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
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

```python
## Developed by: PERARASU M
## Register No: 212222100033
```

### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

### Read the Image and convert to grayscale
```python
image = cv2.imread("ntr.jpeg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("ntr.jpeg",0)
```

### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

### Display the results
```python
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

![image](https://github.com/PERARASU10/THRESHOLDING/assets/118348589/5dac3b65-9b28-463a-87aa-43ce6e33d5bd)



### Global Thresholding

![image](https://github.com/PERARASU10/THRESHOLDING/assets/118348589/fa0b60c8-52f0-4206-8698-ab2a79f6b12f)

![image](https://github.com/PERARASU10/THRESHOLDING/assets/118348589/d34d9b45-264a-4910-a991-24c189df5b10)

![image](https://github.com/PERARASU10/THRESHOLDING/assets/118348589/5599bb21-702d-4a82-8100-78600847fc37)

![image](https://github.com/PERARASU10/THRESHOLDING/assets/118348589/18e53214-ebae-4e91-b841-a81f0dc5f335)


![image](https://github.com/PERARASU10/THRESHOLDING/assets/118348589/0e550366-d646-44e0-850f-ab7641bb6e5b)




### Adaptive Thresholding
![image](https://github.com/PERARASU10/THRESHOLDING/assets/118348589/3c2d4588-d715-4950-a023-ae4541a6bb62)


![image](https://github.com/PERARASU10/THRESHOLDING/assets/118348589/11338a0a-ac9c-4833-b6cb-1fdf2c4609e6)



### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/PERARASU10/THRESHOLDING/assets/118348589/dd875aea-3047-4174-abba-59e5749184ba)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
