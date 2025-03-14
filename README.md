# Real Time Driver Fatigue Detection to Enhance Road-Safety
Description
This project is a Real-Time Driver Fatigue Detection System aimed at enhancing road safety by detecting driver drowsiness. The system monitors eye movements and facial expressions using Dlib's facial landmark detection, processing real-time video frames from a webcam. It classifies the driver's state into:

Active (Awake)
Drowsy (Tired but awake)
Sleeping (Eyes closed for an extended time)
Features
Real-time face detection using Dlib
Eye blink detection based on facial landmarks
Classification of driver alertness levels
Works under low-light conditions
Visual alerts when drowsiness is detected
Installation & Setup
Prerequisites
Ensure you have the following dependencies installed:

nginx
Copy
Edit
pip install opencv-python numpy dlib imutils
Additionally, download the Dlib facial landmark predictor model:
shape_predictor_68_face_landmarks.dat
Extract the .dat file and place it in the project folder.

Usage
Run the script
nginx
Copy
Edit
python fatigue_detection.py
The webcam starts capturing frames, detecting faces and eye movements.
The system classifies the driver’s state and displays it on-screen:
Active (Green) → Alert
Drowsy (Red) → Warning
Sleeping (Blue) → Critical Alert
Press Esc to exit the application.

How It Works
Face Detection

Uses Dlib’s get_frontal_face_detector()
Identifies the driver’s face and marks 68 facial landmarks
Eye Aspect Ratio (EAR) Calculation

Computes eye openness using the Euclidean distance formula
Classifies blinking patterns to determine drowsiness
Alertness State Classification

Active (EAR > 0.25)
Drowsy (0.21 < EAR ≤ 0.25)
Sleeping (EAR ≤ 0.21)
Alerts & Warnings

If the driver is drowsy or asleep for consecutive frames, alerts are displayed.
