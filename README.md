# Exp 2 - Image_Acqusition-_using_Web_Camera
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG 

ii) Display the video 

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera

### Step 2:
Use cv2.imread to read the video or image

### Step 3:
Use cv2.imwrite to save the image

### Step 4:
Use cv2.imshow to show the video

### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
``` 
Developed By: SRINITHI V
Register No: 212222110046

i) Write the frame as JPG file
import cv2
videoCaptureObject=cv2.VideoCapture(0)
while (True) :
    cap,frame=videoCaptureObject.read()
    cv2.imwrite("NewPicture.jpg",frame)
    
    result=False
videoCaptureObject.release()
cv2.destroyAllWindows()

ii) Display the video
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('video capture',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

iii) Display the video by resizing the window
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

iv) Rotate and display the video

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

### i) Write the frame as JPG image:

![Screenshot 2024-09-26 153154](https://github.com/user-attachments/assets/1e7b2ed6-49be-4144-b636-fab10aa3cc16)


### ii) Display the video:

![Screenshot 2024-09-26 153314](https://github.com/user-attachments/assets/79ec4680-8ebb-4183-8417-19e5c42f3bae)


### iii) Display the video by resizing the window
![Screenshot 2024-09-26 153517](https://github.com/user-attachments/assets/76fc8cc3-e5bb-49bb-895a-e47cf4570683)


### iv) Rotate and display the video
![Screenshot 2024-09-26 152908](https://github.com/user-attachments/assets/265902da-e0d2-412b-baf4-d5329dd77425)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
