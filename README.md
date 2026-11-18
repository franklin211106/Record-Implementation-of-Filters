# Exp-5--Record-Implementation-of-Filters

## Aim:
To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

## Software Used:

Anaconda – Python 3.7  
Jupyter Notebook / VS Code  
OpenCV (cv2)  
NumPy  
Matplotlib  

## Algorithm:

Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Read the input image (e.g., image.jpg).

Step 3:
Convert the image from BGR to RGB format for display.

Step 4:
Apply Averaging Filter using cv2.blur().

Step 5:
Apply Weighted Averaging Filter using a custom kernel with cv2.filter2D().

Step 6:
Apply Gaussian Filter using cv2.GaussianBlur().

Step 7:
Apply Median Filter using cv2.medianBlur().

Step 8:
Apply Laplacian Sharpening using Kernel with cv2.filter2D().

Step 9:
Convert image to grayscale and apply Laplacian Operator using cv2.Laplacian().

Step 10:
Display all filtered images using a grid layout for comparison.

## Program:

### Developed By
### Name: FRANKLIN F
### Reg.No: 212224240041

```python

import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("WhatsApp Image 2026-10-24 at 3.32.56 PM.jpeg")
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

## Output:

### Smoothing Filters

#### Averaging filter produces blurred image

<img width="910" height="568" alt="image" src="https://github.com/user-attachments/assets/3308d48a-d904-489f-a62b-851a89550ca3" />


#### Weighted averaging provides smoother result with less distortion

<img width="667" height="428" alt="image" src="https://github.com/user-attachments/assets/d4301faa-a4e0-4892-97fd-6c219171204f" />


#### Gaussian filter preserves edges better while reducing noise

<img width="648" height="412" alt="image" src="https://github.com/user-attachments/assets/ac5bca08-a6cd-4777-8bcd-504805259b6c" />


#### Median filter removes salt-and-pepper noise effectively

<img width="918" height="573" alt="image" src="https://github.com/user-attachments/assets/a9a6dbc2-80d6-47f1-a435-61e9665ee8be" />



### Sharpening Filters

#### Laplacian kernel enhances edges and fine details

<img width="648" height="413" alt="image" src="https://github.com/user-attachments/assets/8f1b9a53-f9b9-4c0b-b051-3463aaeb4092" />

#### Laplacian operator detects edges clearly in grayscale

<img width="672" height="417" alt="image" src="https://github.com/user-attachments/assets/7bff6b8f-148a-4a2a-9dba-27967bdea0d0" />


## Result:

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.

