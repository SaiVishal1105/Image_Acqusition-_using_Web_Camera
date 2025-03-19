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
### Developed By: Sai Vishal D
### Register No: 212223230180

## i) Write the frame as JPG file
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
ret, frame = videoCaptureObject.read()
if ret:
    cv2.imwrite("web.jpg", frame)
    print("Image saved as web.jpg")
else:
    print("Failed to capture image")
videoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```
videoCaptureObject = cv2.VideoCapture(0)
while True:
    ret, frame = videoCaptureObject.read()
    cv2.imshow('myimage', frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()  
```



## iii) Display the video by resizing the window
```
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
```


## iv) Rotate and display the video
```
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
</br>
![Screenshot 2025-03-19 111458](https://github.com/user-attachments/assets/c484f89b-2532-4d62-bf63-f42a919afd46)

</br>


### ii) Display the video
</br>
![Screenshot 2025-03-19 112125](https://github.com/user-attachments/assets/3dbc643d-f9ee-402d-9b60-9187e7643ea1)

</br>


### iii) Display the video by resizing the window
</br>
![Screenshot 2025-03-19 112313](https://github.com/user-attachments/assets/179c47ef-36f5-4948-a091-8d68f5c18fd9)

</br>



### iv) Rotate and display the video
</br>
![Screenshot 2025-03-19 112557](https://github.com/user-attachments/assets/6dee7013-af10-42bd-97bb-6c2a5a4a1c18)

</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
