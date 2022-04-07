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
<br>

### Step 2:
<br>

### Step 3:
<br>

### Step 4:
<br>

### Step 5:
<br>

## Program:
``` Python
### Developed By: P.SUGANYA
### Register No: 212220230049

## i) Write the frame as JPG file
import cv2

videocaptureobject = cv2.VideoCapture(0)

while(True):
    ret,frame = videocaptureobject.read()
    cv2.imwrite("Pic1.jpg",frame)
    result = False 
videocaptureobject.release()
cv2.destroyAllWindows()



## ii) Display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    cv2.imshow('frame', frame)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllwindows()



## iii) Display the video by resizing the window
import cv2
import numpy as np
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[height//2:, width//2:] = smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows(



## iv) Rotate and display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2:, width//2:] = smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllwindows()
```
## Output

### i) Write the frame as JPG image
</br>
</br>![2022-04-07 (3)](https://user-images.githubusercontent.com/77089743/162167463-c9c31f6a-a503-4146-bc6e-b23417c21897.png)



### ii) Display the video
</br>
</br>


### iii) Display the video by resizing the window
</br>
</br>



### iv) Rotate and display the video
</br>
</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
