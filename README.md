# Mission Co-Pilot: An AI Driver Monitoring System 🚗💨
![Mission Copilot](C:\Users\t2208\OneDrive\Pictures\Screenshots)


## This repository contains the code for Mission Co-Pilot, a real-time driver monitoring system built to enhance automotive safety by detecting signs of drowsiness and distraction using computer vision.

*(This is where you will place the drowsiness_demo.gif you create!)*

**Motivation:**
Driver fatigue and distraction are leading causes of traffic accidents. This project aims to build a non-intrusive, camera-based system that can monitor a driver in real-time and provide alerts to prevent potential accidents. This serves as a practical application of computer vision and deep learning techniques to solve a critical real-world problem, inspired by the advanced driver-assistance systems (ADAS) in modern vehicles like those from Mercedes-Benz.

**Features**
Real-time Drowsiness Detection: Monitors the driver's eyes to detect signs of fatigue or microsleeps.
Eye Aspect Ratio (EAR) Monitoring: Utilizes the EAR algorithm to accurately track eye opening and closing. A sustained drop in EAR triggers a drowsiness alert.
Distraction Detection: Employs head pose estimation to determine if the driver's attention has shifted away from the road for an extended period.
On-Screen Visual Alerts: Provides immediate, clear visual feedback directly on the video feed when drowsiness or distraction is detected.

**Tech Stack**
Language: Python
Libraries:

OpenCV for real-time video capture and image processing.
Dlib for robust face detection and facial landmark prediction.
NumPy & SciPy for efficient numerical calculations.
Environment: Google Colab / Jupyter Notebook

**How It Works**
The system processes each frame from a webcam feed in a multi-step pipeline:
Face Detection: A frontal face detector from the Dlib library is used to locate the driver's face in the frame.
Facial Landmark Prediction: A pre-trained model predicts the location of 68 specific points (landmarks) on the face, such as the corners of the eyes, eyebrows, and mouth.

3.  Eye Aspect Ratio (EAR) Calculation: The landmarks for the eyes are used to compute the EAR. This ratio remains constant when the eye is open but drops close to zero during a blink. If the EAR stays low for a sustained period, the system flags it as a potential sign of drowsiness.
Head Pose Estimation: By analyzing the position of key landmarks (like the nose, chin, and eye corners), the system estimates the 3D orientation of the driver's head. A significant yaw (left/right) rotation triggers a distraction alert.
Visual Feedback: All calculated information and alerts are overlaid back onto the video feed, providing an intuitive display for the user.

**How to Run This Project**
This project is designed to be run easily in Google Colab.
Clone or Download: Clone this repository or download the Mission_Co_Pilot_AI.ipynb file.
Open in Colab: Upload and open the notebook in Google Colab.
Run the Setup Cells: Execute the first few cells to install the required libraries and download the dlib pre-trained model.
Run the Simulation: Execute the main simulation cell. Crucially, you must grant camera permission to your browser when prompted.
Stop the Program: To stop the real-time feed, click the "Stop" button next to the running cell in the notebook.

**Future Improvements**
Audio Alerts: Integrate sound-based alerts for a more effective warning system.
Model Optimization: Convert the dlib model to a more lightweight format like ONNX or TensorFlow Lite for better performance on embedded systems.
Yawn Detection: Add a module to detect yawns as an additional indicator of driver fatigue.

**Author**
Nandhini Ramesh
