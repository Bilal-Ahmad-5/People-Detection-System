People Counter with DETR Object Detection
This project implements a real-time people counter using Facebook's DETR (DEtection TRansformer) object detection model. It tracks people across video frames, counts entries/exits across a defined line, and visualizes movement paths.

Features

- Real-time person detection using Hugging Face Transformers
- Object tracking with centroid-based matching
- Line crossing detection and counting

Visualization of tracking paths and counting statistics

FPS performance monitoring

- Requirements
- Python 3.8+
- PyTorch
- OpenCV
- Hugging Face Transformers
- Supervision
- Google Colab (for cv2_imshow if running in Colab)

Configuration

- video_source: Path to video file or camera index (default: 0 for webcam)
- model_name: DETR model variant (default: "facebook/detr-resnet-50")
- line_position: Vertical position of the counting line (default: mid-screen)
- confidence_threshold: Detection confidence threshold (default: 0.3)
- max_disappeared: Frames to keep tracking without detection (default: 30)

Implementation Details
Key Components

- Object Detection: Uses DETR model from Hugging Face Transformers
- Tracking: Centroid-based tracking with history buffer
- Counting: Supervision's LineZone for counting line crossings
- Visualization: OpenCV-based visualization of tracks and counts

Workflow

- Capture video frame
- Detect people using DETR model
- Update trackers with new detections
- Update line crossing counts
- Visualize results

Repeat

Performance Notes

- On GPU: ~5-10 FPS with DETR-ResNet50
- On CPU: ~1-2 FPS with DETR-ResNet50

For better performance, consider using smaller models like "facebook/detr-resnet-101"

Sample Output
The system displays:

- People tracks with movement paths
- Current people count in frame
- IN/OUT counts across the line
- Real-time FPS counter

Future Improvements

- Implement more efficient object detection models
- Add support for multiple counting lines
- Implement direction-sensitive counting
- Add database logging for counts
- Improve tracking robustness with Kalman filters
- Add support for RTSP streams

License
MIT License - Free for academic and commercial use

