
# Image-Acquisition-from-Web-Camera
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
Import cv2 and capture the video using cv2.VideoCapture(0).
### Step 2:
Write the captured image using cv2.imwrite("pic.jpg",frame).

### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5).

### Step 4:
Display the image until the loop gets over.

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180).

## Program:
``` 
### Developed By: R.Vijay
### Register No: 212221230121
```
```
## i) Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("pic.jpg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()

## ii) Display the video
import cv2
vdocam=cv2.VideoCapture(0)
while(True):
    ret,frame=vdocam.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1)==ord('x'):
        break
vdocam.release()
cv2.destroyAllWindows()

## iii) Display the video by resizing the window
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=smaller_frame
    image[height//2:,:width//2]=smaller_frame
    image[:height//2,width//2:]=smaller_frame
    image[height//2:,width//2:]=smaller_frame
    cv2.imshow('myimage',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video
import numpy as np
import cv2
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:,: width//2] = smaller_frame
    image[:height//2, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:] = smaller_frame

    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image
![vj dip0](https://user-images.githubusercontent.com/94381788/226429415-0b1ad718-15fc-4ed8-b40e-d7d86caba069.png)
### ii) Display the video
![vj dip1](https://user-images.githubusercontent.com/94381788/226429433-11dd4bda-2b1d-4625-9e28-d333ec3719a1.png)

### iii) Display the video by resizing the window
![vj dip3](https://user-images.githubusercontent.com/94381788/226429443-441a9761-a014-4ea8-8f3f-efe3bc0ff930.png)

### iv) Rotate and display the video
![vj dip2](https://user-images.githubusercontent.com/94381788/226429438-69b4e6eb-772a-4e6e-8da1-d41ae7be1ced.png)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
