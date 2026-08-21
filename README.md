# Record-Image-Acquisition-using-Web-Camera
## Aim
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

Write the frame as a JPG file
Display the video
Display the video by resizing the window
Rotate and display the video
## Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
## Algorithm
Step 1:
Import the required libraries and initialize the webcam using cv2.VideoCapture().

Step 2:
Capture frames continuously from the webcam.

Step 3:
Save a frame as a JPG image using cv2.imwrite().

Step 4:
Display the live video stream using cv2.imshow().

Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.
## PROGRAM
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite(r"C:\Users\acer\Pictures\Camera Roll\WIN_20260723_19_14_37_Pro.jpg", frame)
cap.release()
captured_image = cv2.imread(r"C:\Users\acer\Pictures\Camera Roll\WIN_20260723_19_14_37_Pro.jpg")
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```
ii) Display the video
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
```
iii) Display the video by resizing the window
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
iv) Rotate and display the video
```
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
## Output
i) Write the frame as JPG image
Captured image is saved as captured_image.jpg
<img width="666" height="530" alt="image" src="https://github.com/user-attachments/assets/896841d7-9322-4508-857a-9e2be5afbb68" />
ii) Display the video
Live webcam video is displayed
<img width="683" height="490" alt="image" src="https://github.com/user-attachments/assets/e84bccf9-e359-4124-8ff0-f43d5ad525c7" />

iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)
<img width="389" height="487" alt="image" src="https://github.com/user-attachments/assets/351d5f64-4e94-46a9-8dd7-6baa57a9f704" />

iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)
<img width="471" height="500" alt="image" src="https://github.com/user-attachments/assets/36915d87-c1d6-4704-9700-d248c06ff5db" />

## Result
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV



