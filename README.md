# Image-Acquisition-from-Web-Cameraa
## Aim

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
### Developed By: Mohamed Fareed F
### Register No:212222230082

## i) Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("captured_image.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()



## ii) Display the video
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('Live Video',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()




## iv) Rotate and display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![WhatsApp Image 2023-11-13 at 20 08 06_375beae4](https://github.com/MOHAMED-FAREED-22001617/Image-Acquisition-from-Web-Cameraa/assets/121412904/40ed1c63-9619-4b90-a45f-bcc44761c0b0)




### ii) Display the video
![WhatsApp Image 2023-11-13 at 20 07 57_19016522](https://github.com/MOHAMED-FAREED-22001617/Image-Acquisition-from-Web-Cameraa/assets/121412904/7d28269c-b750-4ba2-a792-22bb9f3323a8)


### iii) Display the video by resizing the window
![image](https://github.com/MOHAMED-FAREED-22001617/Image-Acquisition-from-Web-Cameraa/assets/121412904/0172c91c-dca6-4364-b2d8-061b920efa93)



### iv) Rotate and display the video
![image](https://github.com/MOHAMED-FAREED-22001617/Image-Acquisition-from-Web-Cameraa/assets/121412904/a73ac82f-87a5-4ca3-ab18-84d82916ab95)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
