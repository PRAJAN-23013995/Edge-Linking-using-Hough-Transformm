# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program :

### Name: PRAJAN P
### Reg No: 212223240121
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('thor.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')

```
## Output:

### Input image 

![download](https://github.com/user-attachments/assets/161b27d9-c69e-4368-93e7-b4f16f9bac9c)

### Grayscale image

![download](https://github.com/user-attachments/assets/33b6d998-4c13-4153-997a-bb628a509d4c)

### Canny Edge detector output

![download](https://github.com/user-attachments/assets/5f8244fc-099a-4a06-893b-3cbf28e6d50b)

### Display the result of Hough transform

![download](https://github.com/user-attachments/assets/cc684ec5-1304-4e0f-8f16-21489803ad12)

## Result:

Thus the grayscale image , canny edge detector and hence we had displayed the result of hough transform
