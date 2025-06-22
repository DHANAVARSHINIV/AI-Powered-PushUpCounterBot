# AI-Powered Push-up Counter

This project implements an AI-powered push-up counter using computer vision. It leverages the `cvzone` library, which internally uses Google's MediaPipe Pose, to detect human pose landmarks and calculate angles to accurately count push-ups.

## Features

* **Real-time Push-up Counting:** Detects and counts push-ups from a live webcam feed (for local execution) or a video file.
* **Angle-based Detection:** Utilizes elbow and shoulder angles to determine the 'up' and 'down' stages of a push-up.
* **Visual Feedback:** Displays a progress bar and percentage for arm extension, along with the current push-up count directly on the video feed.
* **Frame Rate (FPS) Display:** Shows the frames per second for performance monitoring.

## How It Works

The core of the project relies on:
1.  **Pose Detection:** `cvzone.PoseDetector` is used to identify 17 key points on the human body (e.g., shoulders, elbows, wrists).
2.  **Angle Calculation:** The `findAngle` method (from `cvzone.PoseDetector`) calculates the angle between three specified key points (e.g., shoulder-elbow-wrist for the arm bend).
3.  **Counting Logic:** By monitoring the elbow angles of both arms, the script determines when a user completes a push-up cycle (moving from an "up" position to a "down" position and back to "up").

## Setup and Installation

### Prerequisites

* Python 3.x
* A webcam (for local real-time execution) or a video file.

## Demo Video

Watch the demo video here: [AI-Powered Push-Up Counter Demo](https://drive.google.com/file/d/1KmEe3fMgXK9wJHf4zUQSW88MoJActzm1/view?usp=sharing)



## Usage

### 1. Running Locally (with Webcam)

To run the push-up counter using your webcam, simply execute the main script:

```bash
python PushupCounter.py
