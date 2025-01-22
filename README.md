This project uses the YOLOv8 model for real-time object detection. The script captures video frames from either a webcam or a video file, applies object detection using a pretrained YOLOv8 model, and displays the detected objects with bounding boxes and class names.

Features
Real-time object detection using YOLOv8 model.
Detection on live webcam feed or video file input.
Bounding boxes are drawn around detected objects.
Class names and confidence scores are displayed on the screen.
Random colors for each class to differentiate between objects.
Requirements
Python 3.8+
OpenCV (cv2)
NumPy
ultralytics (for YOLOv8 model)
Pretrained YOLOv8 weights (yolov8n.pt)
Installation
Clone the repository:

bash
Copy
git clone https://github.com/Yogesh22102001/yolov8-object-detection.git
cd yolov8-object-detection
Install required packages:

bash
Copy
pip install -r requirements.txt
Download the YOLOv8 pretrained weights from the official repository or from your desired source and place it in the weights/ directory.

Example of YOLOv8 weights download:
YOLOv8 weights
Ensure you have the coco.txt file containing the class labels (usually provided by the YOLOv8 repository or dataset) in the utils/ folder.

File Structure
php
Copy
yolov8-object-detection/
├── utils/
│   └── coco.txt  # Contains class labels for detection
├── weights/
│   └── yolov8n.pt  # YOLOv8 Pretrained weights
├── main.py  # Main object detection script
├── requirements.txt  # Required Python packages
└── README.md  # This file
Running the Script
To run the object detection script:

Open a terminal and navigate to the project directory.

Run the following command:

bash
Copy
python main.py
This will open the webcam or the video file (if specified) and start detecting objects in real-time.

Customization
Video Input:
By default, the webcam is used as the video input. To use a video file, modify the cap variable in the script:

python
Copy
cap = cv2.VideoCapture("path/to/video/file.mp4")
Confidence Threshold:
The detection confidence threshold is set to 0.45 by default. You can adjust this by modifying the conf parameter in the model.predict function:

python
Copy
detect_params = model.predict(source=[frame], conf=0.45, save=False)
Frame Size:
You can resize the frames to optimize performance by changing the frame_wid and frame_hyt values:

python
Copy
frame_wid = 640
frame_hyt = 480
Dependencies
OpenCV (for video capture and image processing)
NumPy (for data manipulation)
ultralytics (for loading and using the YOLOv8 model)
Install dependencies using:

bash
Copy
pip install opencv-python numpy ultralytics
