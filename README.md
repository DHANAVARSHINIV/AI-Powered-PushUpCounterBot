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

### Installation Steps

1.  **Clone the Repository (or download the files):**
    ```bash
    git clone [https://github.com/YourGitHubUsername/Pushup-Counter-Project.git](https://github.com/YourGitHubUsername/Pushup-Counter-Project.git)
    cd Pushup-Counter-Project
    ```
    (Replace `YourGitHubUsername` and `Pushup-Counter-Project` with your actual details)

2.  **Create a Virtual Environment (Recommended):**
    ```bash
    python -m venv venv
    # On Windows
    .\venv\Scripts\activate
    # On macOS/Linux
    source venv/bin/activate
    ```

3.  **Install Dependencies:**
    Install all required Python packages using pip:
    ```bash
    pip install -r requirements.txt
    ```
    This will install `opencv-python`, `numpy`, `cvzone`, and `mediapipe`.

## Usage

### 1. Running Locally (with Webcam)

To run the push-up counter using your webcam, simply execute the main script:

```bash
python PushupCounter.py
