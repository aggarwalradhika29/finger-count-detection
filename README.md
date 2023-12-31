# finger-count-detection
### Efforts by: Radhika Aggarwal, Sanya Rao
## Introduction
This work represents our AI in robotics project whose problem statement using CV2 and Mediapipe library with an Arduino Nano connected to a 7-segment display is to develop a reliable and accurate system that can detect and interpret hand gestures in real-time and display the number of fingers being held up on the 7-segment display module. The system should be designed to work in different lighting conditions and be able to detect hand gestures from a reasonable distance.

# Requirements
## 1. Hardware Requirements
- High-end workstation containing GPU,
- WebCam
- Arduino NANO
- Breadboard
- 7-segment
- Jumper Wires

## 2. Software Requirements
- Python (opencv-python, mediapipe, pyserial)
- Code Editor
- Arduino IDE


## Robot building
Upload the ```arduinoNano.ino``` to your Arduino Nano, and make sure it's always ON as well as the Bluetooth connected to it.

The model displays the number of fingers present in the frame on the 7-segment display.

## Model Structure
```py
model = Sequential()
model.add(Conv2D(64, (3,3), strides=(1, 1), input_shape = (100, 100, 1), padding='same', activation = 'relu'))
model.add(MaxPool2D((8,8)))
model.add(Conv2D(128, (3,3), activation = 'relu'))
model.add(Flatten())
model.add(Dense(6, activation = 'softmax'))
```

### Circuit
![circuit](https://github.com/aggarwalradhika29/finger-count-detection/assets/91591831/eed9f32b-5146-45fa-87ed-c09ae70319da)


# Execution
Make sure your robot has a Bluetooth connection, connect to it using your laptop or any PC that has a webcam. Check which ports the robot is connected to and change its value in ```python-code.py``` here:
```py
serialcomm = Serial('COM6', 9600)
```
In our case, it's COM6.
Once it's done, execute the ```python-code.py```
### Windows:
```powershell
python .\python-code.py
```
### Linux/Mac:
```bash
python3 python-code.py
```

### Video Demonstration:


https://github.com/aggarwalradhika29/finger-count-detection/assets/91591831/4e86908c-81c5-49dd-8cc2-41d4b2149ff2


