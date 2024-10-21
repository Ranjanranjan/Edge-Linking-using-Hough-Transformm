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

## Program:
### Developed by: Ranjan K
### Reg no: 212222230116


### Input image and grayscale image
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('/content/uiop.jpg')  
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')

```
<img width="233" alt="Screenshot 2024-10-21 at 10 52 37 AM" src="https://github.com/user-attachments/assets/21c0a1c0-d637-45d6-b444-cc374b58fd50">

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('/content/uiop.jpg')  
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.subplot(2, 2, 2)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

```
<img width="220" alt="Screenshot 2024-10-21 at 10 53 05 AM" src="https://github.com/user-attachments/assets/3a423b63-e76c-468c-aa56-5ebf55b9e007">





### Canny Edge detector 
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('/content/uiop.jpg')  
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)

plt.subplot(2, 2, 3)
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
```

<img width="239" alt="Screenshot 2024-10-21 at 10 53 23 AM" src="https://github.com/user-attachments/assets/ada29eff-0da2-42e2-b80b-f616c1fed18c">



### Detect lines using the probabilistic Hough transform
### Draw the lines on the original image
### Hough Transform Result
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('/content/uiop.jpg')  
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)
output_image = image.copy()
if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.subplot(2, 2, 4)
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
```
<img width="277" alt="Screenshot 2024-10-21 at 10 53 42 AM" src="https://github.com/user-attachments/assets/5ee2a5fa-6ab3-4e0b-9df4-e7fce67d4b8c">



## Result:
Thus, the program to detect the lines using Hough Transform implemented successfully.

