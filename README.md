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
Developed By: SRINITHI V

Register No: 212222110046
### i) Write the frame as JPG image
```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
ret,frame=viedoCaptureObject.read()
cv2.imshow("webcam_img.jpg",frame)
cv2.waitKey(10000)
viedoCaptureObject.release()
cv2.destroyAllWindows()
```

### ii) Display the video
```
import numpy as np
import cv2
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
cv2.imshow('captured_frame', frame)
cv2.waitKey(10000)
cap.release()
cv2.destroyAllWindows()
```

### iii) Display the video by resizing the window
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=smaller_frame
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=smaller_frame
image[height//2:, width//2:]=smaller_frame
cv2.imshow('SRINITHI V_212222110046',image)
cv2.waitKey(5000)  
image_dict = {'captured_image1': image}
cv2.imwrite('captured_image1.jpg', image)
cap.release()
cv2.destroyAllWindows()
```

### iv) Rotate and display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, width//2:]=smaller_frame
cv2.imshow('SRINITHI V_212222110046',image)
cv2.waitKey(5000) 
image_dict = {'captured_image2': image}
cv2.imwrite('captured_image2.jpg', image)
cap.release()
cv2.destroyAllWindows()
```

## Output
### i) Write the frame as JPG image
![Screenshot (173)](https://github.com/user-attachments/assets/0515d55e-0452-4332-a56f-cebe0b13c6aa)

### ii) Display the video
![Screenshot (174)](https://github.com/user-attachments/assets/47390069-9869-4e5f-9536-3936cbedf107)

### iii) Display the video by resizing the window
![Screenshot (177)](https://github.com/user-attachments/assets/2cc20f1d-acfa-46d6-b971-0ec2da291235)

### iv) Rotate and display the video
![Screenshot (176)](https://github.com/user-attachments/assets/53677c8f-418f-4863-8ae7-3d9b39c07b20)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
