# Image_Acqusition-_using_Web_Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import necessary libraries (cv2).

### Step 2:
Open the camera using cv2.VideoCapture(0).

### Step 3:
Enter a loop to continuously capture frames from the camera.

### Step 4:
Resize each frame, create a blank image, divide it into quadrants, and assign resized frames accordingly. Rotate specific frames if needed.

### Step 5:
Display processed frames on the screen using cv2.imshow(), and continuously check for a termination signal (e.g., pressing 'q' key) to break out of the loop.

## Program:
``` Python
### Developed By: CHAITANYA P S
### Register No: 212222230024

## i) Write the frame as JPG file
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("image.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()

## ii) Display the video
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('Video Capture',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iii) Display the video by resizing the window
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Video Capture',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Video Capture',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![image](https://github.com/chaitanya18c/Image_Acqusition-_using_Web_Camera/assets/119392724/0dc4e6b3-755a-4262-9e53-8ae67de5d3f2)

### ii) Display the video
![image](https://github.com/chaitanya18c/Image_Acqusition-_using_Web_Camera/assets/119392724/b1c6805f-d8ce-432b-9c48-3de42172ba31)

### iii) Display the video by resizing the window
![image](https://github.com/chaitanya18c/Image_Acqusition-_using_Web_Camera/assets/119392724/e6e1fa95-657c-4017-91f8-92d974c4e5ba)

### iv) Rotate and display the video
![image](https://github.com/chaitanya18c/Image_Acqusition-_using_Web_Camera/assets/119392724/d64da822-3e0b-4fa9-83e8-20bc1a9a6e41)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
