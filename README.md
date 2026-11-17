# Experiment 2: Image Acquisition Using Web Camera
### Developed By : HARISH KUMAR S
### Register Number : 212224230091

### Aim :
To acquire an image using a web camera, save the captured frame as a JPG file, display the video stream, and display the video by resizing the frames using Python and OpenCV.

### Requirements :
- Computer or laptop
- Web camera (built-in or external)
Software requirements
- Python
- Jupyter Notebook / Anaconda

### Procedure :
1. Import the required libraries: OpenCV, Matplotlib, IPython display, and time.
2. Open the web camera using cv2.VideoCapture(0).
3. Capture and save an image: Read a frame from the camera and save it as ex.jpg using cv2.imwrite().
4. Display the captured image: Read the saved JPG file and display it using Matplotlib.
5. Display the video: Capture and display 50 consecutive frames from the web camera. Convert each frame from BGR to RGB format before displaying it.
6. Resize the video: Resize each captured frame to 100 × 150 pixels using cv2.resize() and display it.
7. Rotate the video: Rotate each captured frame by 90 degrees clockwise using cv2.rotate() and display the rotated frame.
8. Release the web camera after completing the image and video acquisition operations.

### Program :

### Step1 : Write the frame as JPG file

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("ex.jpg", frame)
cap.release()

captured_image = cv2.imread('ex.jpg')

plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('on')
plt.show()
```

### Step2 : Display the video

```python
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

### Step3 : Display the video by resizing the window

```python
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

### Step4 : Rotate and display the video

```python
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

### Output : 

### Step1 : Write the frame as JPG file
<img width="628" height="497" alt="Screenshot 2026-11-17 233029" src="https://github.com/user-attachments/assets/e52986d2-c75d-41c6-bad3-69b0c368d325" />


### Step2 : Display the video

<img width="628" height="475" alt="Screenshot 2026-11-17 233049" src="https://github.com/user-attachments/assets/7f98ae6f-991c-49e0-9288-f84d65ab1eb5" />



### Step3 : Display the video by resizing the window

<img width="318" height="477" alt="Screenshot 2026-11-17 233100" src="https://github.com/user-attachments/assets/a9160022-1f11-470d-8e94-2582d132803e" />


### Step4 : Rotate and display the video

<img width="357" height="470" alt="Screenshot 2026-11-17 233111" src="https://github.com/user-attachments/assets/41942030-d263-4c56-8e14-5564c47e7387" />


### Result: 

Thus, the image was successfully captured, saved, displayed, resized, and rotated using Python and OpenCV.
