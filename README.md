# Robot-Obstacle-Avoider-YOLOv8
A small autonomous robot using YOLOv8, OpenCV, and Arduino for real-time object detection and obstacle avoidance.

# 🤖 YOLO Obstacle Avoider

A small autonomous robot that combines **YOLOv8, OpenCV, and Arduino**
for real-time object detection and obstacle avoidance.

---

## 📑 List of Contents

- [Introduction](#-introduction)
- [Background & Key Concepts](#-background--key-concepts)
- [Design](#-design)
- [Program](#-program)
- [Results](#-results)

---

## 📌 Introduction

Obstacle avoidance is one of the fundamental problems in mobile robotics.
A robot needs to be able to detect objects in its environment and determine
an appropriate movement based on the detected obstacles.

In this project, a small mobile robot was developed using a **webcam,
Python-based computer vision, YOLOv8, and Arduino**.

The webcam captures the environment and the image is processed using
OpenCV and YOLOv8 to detect objects. The detection results are then used
to determine the robot's movement, while Arduino controls the motors.

The main goal of this project is to build a simple robot that can detect
objects in real time and respond by changing its movement.

---

## 🧠 Background & Key Concepts

### YOLOv8

<p align="center"> <img src="images/yolov8.png" width="700"> </p>

YOLOv8 (You Only Look Once version 8) is a real-time object detection model developed by Ultralytics. It is designed to detect and locate objects in images or video by predicting their class, bounding box, and confidence score in a single inference process.

YOLOv8 is widely used in computer vision applications because of its balance between detection accuracy and computational efficiency. In this project, YOLOv8 is used to detect obstacles captured by a webcam, with the detection results serving as an input for the robot's obstacle avoidance system.

### Computer Vision

Computer vision is used to process the webcam image before the detection
result is sent to the robot control system.

The project uses **OpenCV** for image acquisition and processing.

### Obstacle Avoidance

The detected object's position and estimated distance are used to determine
the robot's movement.

The general decision process is:

```text
       Object Detection
              │
              ▼
       Check Position
              │
              ▼
       Estimate Distance
              │
              ▼
       Movement Decision
        ┌─────┼─────┐
        ▼     ▼     ▼
      LEFT  FORWARD RIGHTthe center of the camera frame.

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
