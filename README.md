# ✋ Virtual Hand Gesture Keyboard

**Real-Time Virtual Typing Using MediaPipe + OpenCV**

This project implements a Real-time virtual keyboard controlled entirely through hand gestures, using a standard webcam. It eliminates the need for a physical keyboard and lets users type characters with simple finger gestures in front of the camera.

The system uses MediaPipe for hand-tracking, OpenCV for image processing, and custom distance-based logic to detect key presses and deletion gestures.


# 🧠 How It Works

**1. Hand Detection**

    The webcam feed is processed frame-by-frame. MediaPipe identifies and tracks 21 key hand landmarks.

**2. Coordinate Extraction**

    Landmark positions (x, y) are captured for:

    Index Tip (8)

    Middle Tip (12)

    Thumb Tip (4)

    Base points used for area estimation

**3. Key Hover Detection**

    If the index fingertip lies within the bounding box of a key, it is visually highlighted.

**4. Gesture-Based Key Press**

    A key press is registered when:

    The distance between the index tip and the middle tip is within a small threshold

    The hand area is small enough

    The fingertip hovers over a key

**5. Backspace Gesture**

If the distance between the **index tip (8) and the thumb tip (4)** is very small (< 25 px),
The last character in the text box is removed.

# 🛠️ Technologies Used

    Python 

    OpenCV

    MediaPipe Hands

    NumPy

    Math (distance calculations)

# 🚀 Usage Instructions

**1. Install dependencies:**

    pip install opencv-python mediapipe numpy

**2. Run the program:**

    python Virtual_Keyboard.py


# Controls:

    Move your index finger over a key to highlight it.

    Bring index + middle fingertip close → press key.

    Bring index + thumb fingertip close → delete last character.

    Press Q on your keyboard to exit the program.




