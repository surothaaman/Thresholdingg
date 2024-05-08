# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
<br>
Load the necessary packages.

### Step2:
<br>
Read the Image and convert to grayscale.

### Step3:
<br>
Use Global thresholding to segment the image.

### Step4:
<br>
Use Adaptive thresholding to segment the image.

### Step5:
<br>
Use Otsu's method to segment the image and display the results.

### Program
```
Developed By : SUROTHAAMAN R
Register Number : 212222103003
```

### Load the necessary packages:
```PY
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

# Read the Image and convert to grayscale
```PY
image = cv2.imread('SF23.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('SF23.jpg',0)
```
# Use Global thresholding to segment the image
```PY
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
# Use Adaptive thresholding to segment the image
```PY
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
# Use Otsu's method to segment the image 
```PY
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
# Display the results
```PY
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
### Output

### Original Image
![Screenshot 2024-04-23 111843](https://github.com/rakesh9339/Thresholdingg/assets/121115650/d9b0d2f9-db3a-4218-8909-72d6e4de4c08)


### Global Thresholding
![Screenshot 2024-04-23 111920](https://github.com/rakesh9339/Thresholdingg/assets/121115650/d8f3a8a0-3109-4861-abbd-1cf8815bda93)

![Screenshot 2024-04-23 111931](https://github.com/rakesh9339/Thresholdingg/assets/121115650/76882227-4b8d-43d5-84dd-1076b60b3334)

![Screenshot 2024-04-23 111944](https://github.com/rakesh9339/Thresholdingg/assets/121115650/e0d734f4-2c4f-4d4c-bd53-4c34a4f5af87)

![Screenshot 2024-04-23 111958](https://github.com/rakesh9339/Thresholdingg/assets/121115650/6ba8f669-bd5c-4a84-ac2f-cbbdcf191d1a)

![Screenshot 2024-04-23 112008](https://github.com/rakesh9339/Thresholdingg/assets/121115650/4c769f86-b1c6-40bb-a957-d26aa2a1658e)






### Adaptive Thresholding
![Screenshot 2024-04-23 112026](https://github.com/rakesh9339/Thresholdingg/assets/121115650/492be6c3-0c4a-4e05-bed3-59fc25c225f3)


![Screenshot 2024-04-23 112038](https://github.com/rakesh9339/Thresholdingg/assets/121115650/3059c9e8-fb79-49bb-ad5e-9783f69b5687)


### Optimum Global Thesholding using Otsu's Method

![Screenshot 2024-04-23 112105](https://github.com/rakesh9339/Thresholdingg/assets/121115650/30bd87de-9dce-4e63-a6d3-c4d682d35b1a)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
