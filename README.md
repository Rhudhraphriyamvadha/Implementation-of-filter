# IMPLEMENTATION OF FILTERS

## NAME: Rhudhra phriyamvadha K S
## REG NO: 212224040275

## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the required libraries.

### Step2
Convert the image from BGR to RGB.

### Step3
Apply the required filters for the image separately.

### Step4
Plot the original and filtered image by using matplotlib.pyplot.

### Step5
End the program.

## Program:
```python
Developed By   : Rhudhra phriyamvadha K S
Register Number: 212224040275
```

## 1. Smoothing Filters

### i) Using Averaging Filter
```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("Imgage2.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```
### OUTPUT:

<img width="813" height="480" alt="image" src="https://github.com/user-attachments/assets/60f79419-cf94-46b1-bf29-434d19da3248" />


### ii) Using Weighted Averaging Filter
```Python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```

### OUTPUT:

<img width="617" height="352" alt="image" src="https://github.com/user-attachments/assets/7b253e10-d7e5-4da5-9030-e43c7a6d146f" />

### iii) Using Gaussian Filter
```Python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

### OUTPUT:

<img width="609" height="369" alt="image" src="https://github.com/user-attachments/assets/4dc2a76e-512d-4d20-96b1-b13f4145fb3e" />


### iv)Using Median Filter
```Python
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

### OUTPUT:

<img width="813" height="488" alt="image" src="https://github.com/user-attachments/assets/c1042887-725c-4d83-9dbf-d39e7127fd14" />


## 2. Sharpening Filters:

### i) Using Laplacian Linear Kernal
```Python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```

### OUTPUT:

<img width="622" height="361" alt="image" src="https://github.com/user-attachments/assets/0981535c-dee7-418a-b31d-3ae89b240564" />


### ii) Using Laplacian Operator
```Python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

### OUTPUT:

<img width="603" height="352" alt="image" src="https://github.com/user-attachments/assets/ac7773cc-b624-48cb-8949-64acb5589ab7" />


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
