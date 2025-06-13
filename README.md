# Single and Multi-Person Tracking with YOLOv11

## Overview
This project provides a Python-based solution for tracking single or multiple people in a video using the YOLOv11 model with pose estimation. Utilizing the Ultralytics YOLO library, it detects and tracks individuals, visualizing their movement paths in real-time. The project supports two modes: single-person tracking, which locks onto the first detected individual, and multi-person tracking, which monitors all detected individuals with unique IDs.

## Key Features
- **Flexible Tracking Modes**: Track a single person or multiple people simultaneously using YOLOv11 (`yolo11n-pose.pt`) for robust detection and tracking.
- **Keypoint Extraction**: Extracts key body points (nose, shoulders, hips) to compute central tracking points for precise movement tracking.
- **Visualization**: Annotates video frames with bounding boxes and movement trajectories, using unique IDs and colored paths (e.g., green for single-person tracking).
- **Customizable Pipeline**: Processes input videos (`people.mp4`) and outputs annotated videos (`output_video.mp4`)(`multiple.mp4`) with tracking data.

## Technologies Used
- **Python Libraries**: OpenCV (`cv2`), PyTorch, NumPy, Ultralytics YOLO
- **Model**: YOLOv11 for pose estimation and object tracking
- **Environment**: Developed and tested in Google Colab with Python 3

## How It Works
1. **Initialization**: Sets up video capture and output using OpenCV, initializing tracking data to store routes and IDs.
2. **Keypoint Processing**: Extracts and validates keypoints (nose, mid-shoulder, mid-hip) to determine tracking points for each person.
3. **Tracking Logic**:
   - **Single-Person Mode**: Locks onto the first detected person, maintaining their ID across frames and ignoring others.
   - **Multi-Person Mode**: Tracks all detected individuals, assigning unique IDs and maintaining separate movement paths.
4. **Visualization**: Draws bounding boxes and trajectories on video frames, saving the output as a new video file.

## Usage
1. Open Google Colab and create a new notebook.
2. Upload the project files, including the script (`Object tracking.ipynb`) and your input video (e.g., `people.mp4`), to your Colab environment:
   - Click the folder icon in the left sidebar.
   - Drag and drop people.mp4 and track.py into the file explorer.
3. Install required dependencies in a Colab cell:
   ```bash
   pip install ultralytics
   ```
4. Run the whole script in Colab
5. Download the output video (output_video.mp4),(multiple.mp4) from the Colab file explorer by right-clicking and selecting "Download".
