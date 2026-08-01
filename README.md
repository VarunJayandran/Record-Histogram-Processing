# Record-Histogram-Processing.

### DEVELOPED BY : VARUN JC
### REG NO : 212224240179

## AIM : 
To perform histogram processing and histogram equalization on grayscale and color images using OpenCV.
To enhance image contrast and compare the original and equalized histograms.

## SOFTWARE REQUIRED :
```
--> Anaconda - Python 3.7
--> Jupyter Notebook (for interactive development and execution)
```

## ALGORITHM :
### Step 1:
Read the input image in grayscale and display the original image with its histogram.

### Step 2:
Apply histogram equalization to the grayscale image using cv2.equalizeHist().

### Step 3:
Display the equalized grayscale image and its histogram for comparison.

### Step 4:
Read the original image in color and convert it from BGR to HSV color space.

### Step 5:
Apply histogram equalization to the V (Value) channel of the HSV image.

### Step 6:
Convert the modified HSV image back to BGR color space and display the enhanced color image.

### Step 7:
Compare the original and equalized images along with their histograms to observe the improvement in contrast.

## PROGRAM :

### Read and Display the Original Grayscale Image :
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('Bird.jpg', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Histogram')
plt.show()

```

### Perform Histogram Equalization on Grayscale Image
```py
img_eq = cv2.equalizeHist(img)

plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.show()

plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')
plt.show()

```

### Perform Histogram Equalization on Color Image
```py
img = cv2.imread('Bird.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Color Image')
plt.show()

plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.show()

```
###  Compare Original and Equalized Images with Histograms
```py
plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')
plt.show()

```

1. 

<img width="718" height="382" alt="image" src="https://github.com/user-attachments/assets/987d5366-2172-4251-ad3a-caa4e6bc47c2" />


2.


<img width="717" height="523" alt="image" src="https://github.com/user-attachments/assets/b48bdd30-ffc9-47f8-88bf-4de7456bbab5" />


3.
<img width="735" height="537" alt="image" src="https://github.com/user-attachments/assets/66747df8-c390-495a-9e73-78ed462fc146" />


3.
<img width="742" height="371" alt="image" src="https://github.com/user-attachments/assets/6f50fe84-d0c0-498c-8f2c-cfc92d40324d" />

4.
<img width="723" height="391" alt="image" src="https://github.com/user-attachments/assets/df05b01f-098d-4cab-86f2-5e93015659ed" />

5.
<img width="712" height="522" alt="image" src="https://github.com/user-attachments/assets/2edfbf7a-8552-4e02-b949-ab10978dae30" />

6.
<img width="742" height="503" alt="image" src="https://github.com/user-attachments/assets/d69fc75b-a4e9-4d11-92d4-fb8d8307e202" />

7.
<img width="1390" height="408" alt="image" src="https://github.com/user-attachments/assets/034f20b6-d8f3-4d02-878f-83628a0b1d14" />


 ## RESULT :

Histogram equalization successfully improved the image contrast by redistributing pixel intensity values.
The equalized images showed enhanced visual quality with a more uniform intensity distribution compared to the original images.
