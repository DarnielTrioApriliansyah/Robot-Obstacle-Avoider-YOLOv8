# Robot-Obstacle-Avoider-YOLOv8
A small autonomous robot using YOLOv8, OpenCV, and Arduino for real-time object detection and obstacle avoidance.

# 🤖 YOLO Obstacle Avoider

> A small robot that uses **YOLOv8 + OpenCV + Arduino** to detect objects and avoid obstacles in real time.

<p align="center">
  <img src="images/robot.jpg" width="500">
</p>

## ⚡ About

This project is a small **Obstacle Avoider Robot** controlled by Arduino and a Python-based computer vision system.

A webcam captures the environment, while **YOLOv8** detects objects in real time. The detected object's position and estimated distance are then used to decide whether the robot should move forward, turn left, or turn right.

The system was tested with objects such as **bottles, cups, books, and hands**.

## 🧠 How It Works

```text
             Webcam
                │
                ▼
        ┌───────────────┐
        │    OpenCV     │
        │   + YOLOv8    │
        └───────┬───────┘
                │
         Object Detection
                │
                ▼
       Position + Distance
                │
                ▼
        Decision Making
                │
        ┌───────┼───────┐
        ▼       ▼       ▼
      Left   Forward   Right
        │       │       │
        └───────┼───────┘
                ▼
            Arduino
                │
                ▼
          Motor Driver
                │
                ▼
             Motors
```

## 🔧 Hardware

* Arduino Uno R3
* L293D motor driver
* Webcam
* DC gear motors + wheels
* Caster wheel
* Breadboard
* Jumper wires
* 9V battery
* Powerbank

The Arduino is connected to the laptop through serial communication at **9600 baud**.

## 💻 Software

* Python
* OpenCV
* YOLOv8
* PyTorch
* CVZone
* Arduino IDE

## 🚀 Features

* Real-time object detection
* YOLOv8 object recognition
* Webcam-based computer vision
* Automatic obstacle avoidance
* Arduino motor control
* Serial communication
* Hand tracking
* Object position-based navigation

## 🎯 Detected Objects

The current implementation focuses on:

```text
Bottle
Cup
Book
Hand
```

The YOLO detection code filters the target classes using a confidence threshold of **0.5**.

## 🧭 Navigation Logic

The robot determines its movement based on the detected object's position and estimated distance.

```text
Object detected?
       │
   ┌───┴───┐
   │       │
  YES      NO
   │       │
   ▼       ▼
Check     Move
distance  forward
   │
   ▼
Distance < 30 cm?
   │
 ┌─┴─┐
YES  NO
 │    │
 ▼    ▼
Turn  Move
 │    forward
 └──────┘
```

When an object is detected as close, the robot chooses a turning direction based on the object's position relative to the center of the camera frame.

## 📦 Installation

Clone this repository:

```bash
git clone https://github.com/YOUR-USERNAME/YOLO-Obstacle-Avoider.git

cd YOLO-Obstacle-Avoider
```

Install the required Python libraries:

```bash
pip install opencv-python
pip install torch
pip install ultralytics
pip install cvzone
pyserial
```

Or install everything using:

```bash
pip install -r requirements.txt
```

## ▶️ Run

1. Connect the Arduino to the computer.
2. Connect the webcam.
3. Make sure `yolov8n.pt` is available.
4. Check the Arduino serial port in the Python code.
5. Upload the Arduino program.
6. Run the Python program.

Example:

```bash
python Python/obstacle_avoider.py
```

The camera will display the detection results in real time while sending movement commands to the Arduino.

## 📸 Results

### Object Detection

<p align="center">
  <img src="images/detection-result.jpg" width="700">
</p>

The robot successfully detected objects such as bottles, hands, and cups during testing and responded by changing its movement.

## 🛠️ Project Status

**Completed / Experimental**

This project was developed as an experimental robotics and computer vision project.

## 👨‍💻 Author

**Darniel**

Physics Instrumentation & Robotics

---

⚡ *Build it. Break it. Fix it. Learn from it.*
