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
### PROGRAM :
```
Developed by: S.ANUSHARON
Reg.no: 212222240010
```
### Read image and convert it to grayscale image
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("/content/doggg.jpg",0)
img_c=cv2.imread("/content/doggg.jpg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```
### Find the edges in the image using canny detector and display
```
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
### Detect points that form a line using HoughLinesP
```
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
### Draw lines on the image
```
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```
### Display the result
```
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```

## Output

### Input image and grayscale image
![Screenshot 2024-04-03 085709](https://github.com/Anusharonselva/Edge-Linking-using-Hough-Transformm/assets/119405600/840dc2e3-3994-45ff-94a6-42acb1d517c1)


### Canny Edge detector output
![Screenshot 2024-04-03 085722](https://github.com/Anusharonselva/Edge-Linking-using-Hough-Transformm/assets/119405600/511c735c-ba76-4bd6-a2e9-ec97cd322de8)


### Display the result of Hough transform

![Screenshot 2024-04-03 085734](https://github.com/Anusharonselva/Edge-Linking-using-Hough-Transformm/assets/119405600/e6c91cd9-4ba4-4275-a87e-f4ca8c41b576)
### Result :
Thus the program is written with python and OpenCV to detect lines using Hough transform.
