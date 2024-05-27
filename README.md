# Emotion-Recognition

## 💫 About Developer:

### Banish J

🤖 AI & ML Developer | Data Science & Analytics Expert  
🌐 Web Apps & IoT Skilled | Awesome UI Creator  
💻 AI is my main focus! 👾

## 📞 Contact
##### **☎️**   [9444333914](tel:9444333914)
##### **📧**  [mail@banish.in](mailto:mail@banish.in)
##### **🌐**  [Banish](https://www.banish.in)

## Core Concept

***This code essentially captures video from the webcam, processes each frame to recognize facial emotions using the facial_emotion_recognition library, and displays the results in a window. The loop continues until the 'ESC' key is pressed, upon which it releases the webcam resource and closes all OpenCV windows.***

### Importing Necessary Libraries
```python
from facial_emotion_recognition import EmotionRecognition
import cv2
```
- **facial_emotion_recognition**: A library for recognizing facial emotions.
- **cv2**: The OpenCV library for computer vision tasks.

### Initializing Emotion Recognition
```python
er = EmotionRecognition(device='cpu')
```
- **EmotionRecognition(device='cpu')**: Initializes the emotion recognition model. The parameter `device` specifies the device to be used for processing (CPU in this case).

### Initializing Webcam
```python
cam = cv2.VideoCapture(0)
```
- **cv2.VideoCapture(0)**: Initializes the webcam for video capture. The argument `0` typically refers to the default webcam on the computer.

### Real-Time Emotion Recognition Loop
```python
while True:
    _, frame = cam.read()
    frame = er.recognise_emotion(frame, return_type='BGR')
    
    cv2.imshow("Frame", frame)
    key = cv2.waitKey(1)
    if key == 27:
        break
```
- **cam.read()**: Captures a frame from the webcam. `_` is used to ignore the first return value (a boolean indicating if the frame was read correctly), and `frame` stores the captured image.
- **er.recognise_emotion(frame, return_type='BGR')**: Recognizes emotions in the captured frame. The `return_type` parameter specifies the format of the returned image (BGR in this case).
- **cv2.imshow("Frame", frame)**: Displays the frame with recognized emotions.
- **cv2.waitKey(1)**: Waits for 1 millisecond for a key press. If the 'ESC' key (key code 27) is pressed, the loop breaks.
  
### Releasing Resources
```python
cam.release()
cv2.destroyAllWindows()
```
- **cam.release()**: Releases the webcam resource.
- **cv2.destroyAllWindows()**: Closes all OpenCV windows.
