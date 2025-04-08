# Hand-Gesture-Media-Control-System

## Overview
The **Hand Gesture Media Control System** is a Python-based application that uses hand gestures to control media playback and system volume. The system leverages Mediapipe for hand tracking, OpenCV for video input, and PyAutoGUI for automating media control actions.

---

## Features
- **Volume Control**: Adjust system volume by pinching your thumb and index finger.
- **Play/Pause**: Play or pause media by pinching your thumb and middle finger.
- **Forward/Backward**: Navigate media forward or backward by pinching your thumb with the ring or pinky finger, respectively.
- **Cross-Platform Support**: 
  - **Windows**: Volume control implemented via Pycaw.
  - **MacOS**: Volume control implemented using `osascript`.

---

## Prerequisites
Ensure the following libraries and dependencies are installed:
- Python 3.7 or higher
- Required Python libraries:
  ```bash
  pip install opencv-python mediapipe numpy pyautogui
  ```
- For Windows users:
  ```bash
  pip install pycaw comtypes
  ```

---

## Usage Instructions

### 1. **Setup**
Run the script on the system with the camera. The application initializes hand gesture detection and displays a GUI window for volume updates.

### 2. **Controls**
- **Gesture Calibration**: The system calibrates gesture thresholds at startup. Follow the instructions on the console.
- **Key Gestures**:
  - **Thumb + Index Finger Pinch**: Adjusts volume.
  - **Thumb + Middle Finger Pinch**: Toggles play/pause.
  - **Thumb + Ring Finger Pinch**: Skips to the next media.
  - **Thumb + Pinky Finger Pinch**: Goes back to the previous media.

### 3. **Exit**
- Press `Q` in the camera window to exit the application.

---

## GUI
A Tkinter-based GUI shows the current system volume in real-time.

---

## Code Structure

### 1. **Libraries**
- **OpenCV**: Captures video input.
- **MediaPipe**: Detects hand landmarks for gesture recognition.
- **PyAutoGUI**: Automates media control keystrokes.
- **Pycaw (Windows)**: Controls system volume.
- **Tkinter**: Displays the volume percentage.

### 2. **Key Functions**
- `get_hand_landmarks(image)`: Extracts hand landmarks from the video feed.
- `calculate_distance(landmarks, idx1, idx2)`: Computes the distance between two hand landmarks.
- `detect_gestures(landmarks)`: Maps hand gestures to actions like play/pause or volume adjustment.
- `set_system_volume(vol)`: Adjusts the system volume based on the gesture distance.

### 3. **Main Loop**
The application processes video frames, detects gestures, updates the GUI, and performs the corresponding actions.

---

## System Requirements
- **Operating System**: Windows or MacOS
- **Camera**: Built-in or external webcam

---

## Known Issues
- The application might require a stable and well-lit environment for accurate hand tracking.
- Volume control for MacOS is limited by the system's AppleScript interface.

---

## Future Improvements
- Add support for Linux systems.
- Enhance gesture recognition accuracy in low-light conditions.
- Include more gestures for additional media control features.

---

## License
This project is licensed under the MIT License. You are free to use, modify, and distribute the code.

---

Feel free to reach out with suggestions or improvements!
