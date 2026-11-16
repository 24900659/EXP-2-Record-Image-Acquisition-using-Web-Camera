# EXP-2-Record-Image-Acquisition-using-Web-Camera
EX 02: Image_Acqusition-_using_Web_Camera
Aim:
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG

ii) Display the video

iii) Display the video by resizing the window

iv) Rotate and display the video

Software Used:
Anaconda - Python 3.7

Algorithm:
Step 1:
Use cv2.VideoCapture(0) to access web camera.

Step 2:
Use cv2.imread to read the video or image.

Step 3:
Use cv2.imwrite to save the image.

Step 4:
Use cv2.imshow to show the video.

Step 5:
End the program and close the output video window by pressing 'q'.

Program:
Developed By: MOHANA K.V.S.L


Register No: 212224240093
```
## i) Write the frame as JPG file
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
captured_image = cv2.imread('captured_frame.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
<img width="712" height="542" alt="image" src="https://github.com/user-attachments/assets/e5959e45-9ce3-456e-8d1d-8bc700c562bb" />

```



## ii) Display the video
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break

    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()

    time.sleep(0.05)

cap.release()
<img width="726" height="541" alt="image" src="https://github.com/user-attachments/assets/d65d85fc-65b2-4b95-835a-ccbb72ce905d" />
```

## iii) Display the video by resizing the window
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break

    resized_frame = cv2.resize(frame, (100, 150))

    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()

    time.sleep(0.05)

cap.release()
<img width="370" height="523" alt="image" src="https://github.com/user-attachments/assets/adf01183-9067-4525-a6da-3390cbecbbb7" />
```

## iv) Rotate and display the video
```
## iv) Rotate and display the video
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
<img width="375" height="490" alt="image" src="https://github.com/user-attachments/assets/f5a22f3e-f936-479e-b21d-e503e7548e56" />


Result:
Thus the image is accessed from webcamera and displayed using openCV.
