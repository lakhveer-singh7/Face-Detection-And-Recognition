# Face Detection and Recognition with OpenCV

## Overview
This project provides a complete pipeline for face detection and recognition using OpenCV in Python. It enables you to:
- Train a face recognizer on your own dataset of images.
- Detect and recognize faces in real-time using your webcam.
- Detect faces in static images.

## Project Structure
```
face_detection_And_recognizer/
├── faces/                    # Training images organized by person
│   ├── bhoodev/
│   ├── bipin/
│   ├── lakhveer/
│   └── scarlate/
├── src/
│   ├── image_face_detection.py    # Detects faces in a static image
│   ├── face_detect.xml           # Haar cascade for face detection
│   ├── face_recog_train.py       # Trains the face recognizer
│   ├── faces_trained.yml         # Trained recognizer model
│   ├── features.npy              # Saved features from training
│   ├── labels.npy                # Saved labels from training
│   ├── video_face detection.py   # Real-time face recognition from webcam
│   └── photos/                   # Sample images for testing
└── README.md
```

## Dependencies
- Python 3.7+
- OpenCV (opencv-python, opencv-contrib-python)
- numpy

Install dependencies with:
```bash
pip install opencv-python opencv-contrib-python numpy
```

## Setup & Usage

### 1. Prepare the Dataset
- Place your training images in the `faces/` directory.
- Each person should have their own subfolder (e.g., `faces/bhoodev/`, `faces/bipin/`, etc.).
- Add multiple images per person for best results.

### 2. Train the Recognizer
Run the following command to extract features and train the model:
```bash
python src/face_recog_train.py
```
This will generate `faces_trained.yml`, `features.npy`, and `labels.npy` in the `src/` directory.

### 3. Face Detection on Static Images
To detect faces in a sample image:
```bash
python src/image_face_detection.py
```
You can modify the script to use your own images in `src/photos/`.

### 4. Real-Time Face Recognition (Webcam)
To recognize faces in real-time using your webcam:
```bash
python src/video_face\ detection.py
```
*(Note: If you have issues with the space in the filename, consider renaming the file to `video_face_detection.py` for easier command-line usage.)*

## Notes
- The Haar cascade file (`face_detect.xml`) is used for face detection.
- The recognizer uses the LBPH (Local Binary Patterns Histograms) algorithm from OpenCV.
- Make sure your OpenCV installation includes the `face` module (provided by `opencv-contrib-python`).
- You can add more people by creating new folders in `faces/` and retraining the model.
- Sample images for testing are available in `src/photos/`.

## License
This project uses the OpenCV Haar cascade under the Intel Open Source Computer Vision Library License (see `src/face_detect.xml`). 