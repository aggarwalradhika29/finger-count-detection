# finger-count-detection

## Introduction
This work represents our AI in robotics project which is about controlling an Arduino Nano-connected 7-segment display using the Deep Learning algorithm: CNN. This project can be used for other similar cases.

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

# Circuit Diagram
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


