# Image-Acquisition-from-Web-Camera
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
Use VideoCapture(0) to access web camera.

### Step 2:
Use imread to read the video or image.

### Step 3:
Use imwrite to save the image.

### Step 4:
Use imshow to save the image.


### Step 5:
End the program and close the output video windows by pressing 'q'.

## Program:

### Developed By: S.SAFA
### Register No: 212220230040

## i) Write the frame as JPG file
```
import cv2
videoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=videoCaptureObject.read()
    cv2.imwrite("New Picture.jpg",frame)
    result=False
videoCaptureObject.release()
cv2.destroyAllWindows()

```



## ii) Display the video

```
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('frame',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cap.destroyAllWindows()

```


## iii) Display the video by resizing the window

```
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```



## iv) Rotate and display the video


```
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```







## Output

### i) Write the frame as JPG image

![exp2- vid 4](https://user-images.githubusercontent.com/75234912/162226339-3635617c-4ac3-4b5e-94a9-3505784075d6.png)


### ii) Display the video

![exp2- vid 1](https://user-images.githubusercontent.com/75234912/162218523-d9fed349-9939-42a1-b2d6-b1f2a16748f5.png)


### iii) Display the video by resizing the window

![exp2-vid 2](https://user-images.githubusercontent.com/75234912/162218680-53f2e8ce-2107-46cd-96f1-59f5938ea353.png)




### iv) Rotate and display the video


![exp3-vid 3](https://user-images.githubusercontent.com/75234912/162218712-c1859244-04fe-4f38-96e1-17b3ae761749.png)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
