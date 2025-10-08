# EXP:07 Edge-Linking-using-Hough-Transformm
# NAME: ESHWAR T
# REF NO: 212223230054
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
## program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('me.jpg') 
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
    x1, y1, x2, y2 = line[0]
cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')
```
## Output

### Input image and grayscale image
<img width="364" height="450" alt="Screenshot 2025-09-30 153926" src="https://github.com/user-attachments/assets/7588780c-fce5-421a-996a-9808a503e820" />
<img width="349" height="474" alt="Screenshot 2025-09-30 153931" src="https://github.com/user-attachments/assets/abb59b7b-2c3c-42fb-b6ba-8e0c967a606c" />


### Canny Edge detector output
<img width="375" height="468" alt="Screenshot 2025-09-30 153936" src="https://github.com/user-attachments/assets/4ab98ab8-a7eb-4884-90a6-b12411350aaa" />


### Display the result of Hough transform
<img width="341" height="459" alt="Screenshot 2025-09-30 153943" src="https://github.com/user-attachments/assets/8221313f-2e50-4232-b4c8-1e08891eb13e" />

