# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:

### Step1: 
Generate a black image of size (300, 600) using np.zeros().

### Step2:
Add the text onto the image using cv2.putText()

### Step3:
Create a 5x5 rectangular kernel using cv2.getStructuringElement() for morphological operations.

### Step4:
Perform erosion and dilation on the image using cv2.erode() and cv2.dilate() with the defined kernel.

### Step5:
Use matplotlib to display the original, eroded, and dilated images side-by-side for comparison.

## Program:
```
Developed By : Iswarya P
Register no  : 212223230082
```

#### Import the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

#### Create the Text using cv2.putText
```
image = np.zeros((250, 380, 3), dtype="uint8")
text = "ISWARYA"
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, text, (50, 150), font, 2, (255, 255, 255), 3)
```
#### Original image
```
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")
```
#### Output
![image](https://github.com/user-attachments/assets/c618bb58-4af7-45ff-8333-304b02fe4464)

#### Create the structuring element

kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))

#### Erode the image
```
eroded_image = cv2.erode(image, kernel, iterations=1)
eroded_image_rgb = cv2.cvtColor(eroded_image, cv2.COLOR_BGR2RGB)
plt.imshow(eroded_image_rgb)
plt.title("Eroded Image")
plt.axis("off")
```
#### Output
![image](https://github.com/user-attachments/assets/c9d56865-635f-4ab6-a831-1a01d2bd2107)

#### Dilate the image
```
dilated_image = cv2.dilate(image, kernel, iterations=1)
dilated_image_rgb = cv2.cvtColor(dilated_image, cv2.COLOR_BGR2RGB)
plt.imshow(dilated_image_rgb)
plt.title("Dilated Image")
plt.axis("off")
```
#### Output
![image](https://github.com/user-attachments/assets/e3a9c9a4-abe8-4847-b11b-d9f2c7153dc7)

## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
