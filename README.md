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
## Developed by: PRAKASH M
## Register No: 212222100035
```

### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

### Read the Image and convert to grayscale
```python
image = cv2.imread("cat.jpeg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("cat.jpeg",0)
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

<img width="533" alt="image" src="https://github.com/Prakashmathi2004/THRESHOLDING/assets/118350045/caa851dc-8c8d-4166-95b0-4a915b372d34">



### Global Thresholding

<img width="537" alt="image" src="https://github.com/Prakashmathi2004/THRESHOLDING/assets/118350045/c11c2207-5214-4128-8f02-88c3194b5273">

<img width="524" alt="image" src="https://github.com/Prakashmathi2004/THRESHOLDING/assets/118350045/54b92451-3b27-4a05-97f0-a0092bfbf4a4">


<img width="535" alt="image" src="https://github.com/Prakashmathi2004/THRESHOLDING/assets/118350045/da1cb7a8-4b86-46de-94ae-02003986146b">


<img width="543" alt="image" src="https://github.com/Prakashmathi2004/THRESHOLDING/assets/118350045/52ba94fe-06ab-46a0-bc0a-ac1ae4b1084a">



<img width="527" alt="image" src="https://github.com/Prakashmathi2004/THRESHOLDING/assets/118350045/9ac6e15a-8995-4b13-8dfd-2554cad21129">





### Adaptive Thresholding

<img width="530" alt="image" src="https://github.com/Prakashmathi2004/THRESHOLDING/assets/118350045/6651a33a-5e5d-4910-ab82-3cc004d68a55">



<img width="539" alt="image" src="https://github.com/Prakashmathi2004/THRESHOLDING/assets/118350045/c8091b37-4406-4855-a7fb-2cb051670f93">




### Optimum Global Thesholding using Otsu's Method
<img width="530" alt="image" src="https://github.com/Prakashmathi2004/THRESHOLDING/assets/118350045/390913c1-f15e-4d0b-83c1-70b9bfa06145">


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
