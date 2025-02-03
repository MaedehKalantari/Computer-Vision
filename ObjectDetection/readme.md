### **Using Ultralytics YOLO for Object Detection**  
In this project, we implemented object detection using **YOLO (You Only Look Once)**, specifically leveraging **Ultralytics' YOLO framework**. **Ultralytics YOLO** is a powerful, easy-to-use implementation of YOLO that provides pre-trained models and a user-friendly API for object detection. We use **cv2 (OpenCV)** for processing video input and performing frame-by-frame object detection.  

#### **Why Ultralytics YOLO?**  
1. **Ease of Use** – The Ultralytics library simplifies training, inference, and deployment with a high-level API.  
2. **Pre-trained Models** – Comes with multiple pre-trained versions (YOLOv5, YOLOv8) for different accuracy vs. speed trade-offs.  
3. **Fast Inference** – Optimized for real-time object detection, making it ideal for both image and video processing.  
4. **Supports Multiple Input Types** – Can process images, videos, and even webcam feeds with just a few lines of code.  

#### **How YOLO is Used in This Project**  
- **Model Loading**: We use Ultralytics’ `YOLO` class to load a pre-trained YOLO model.  
- **Object Detection**: The model runs inference on images and video frames, detecting objects with high speed and accuracy.  
- **Bounding Boxes & Labels**: Detected objects are highlighted using bounding boxes, and their labels are displayed on the screen.  

#### **Code Example (Using Ultralytics YOLO for Detection)**  
```python
from ultralytics import YOLO
import cv2  

# Load the YOLO model (YOLOv8 pre-trained)
model = YOLO("yolov8n.pt")  

# Read an image
image = cv2.imread("image.jpg")

# Run inference on the image
results = model(image)  

# Show results
results.show()
``


## **Key Features**  
- **Real-time object detection** using **YOLO**.  
- **Supports both images and videos** as input.  
- **Processes video frame-by-frame** to detect objects dynamically.  
- **Utilizes OpenCV (cv2) for video handling and frame extraction**.  

## **Implementation Steps**  

### **1. Load YOLO Model**  
- Load **pre-trained YOLO weights and configuration files**.  
- Define **object classes** for detection.  

### **2. Process Images & Videos**  
- For **images**: Read the image and pass it through YOLO.  
- For **videos**:  
  - Capture the video using `cv2.VideoCapture()`.  
  - Read the video **frame-by-frame**.  
  - Obtain **video properties**:  
    - **Width & Height**: `cv2.get(cv2.CAP_PROP_FRAME_WIDTH)`, `cv2.get(cv2.CAP_PROP_FRAME_HEIGHT)`.  
    - **Frames per second (FPS)**: `cv2.get(cv2.CAP_PROP_FPS)`.  

### **3. Object Detection with YOLO**  
- Convert frames to a format suitable for YOLO processing.  
- Run YOLO model and detect objects.  
- Draw bounding boxes around detected objects.  

### **4. Save Processed Video**  
- Define a video writer using **FourCC**.  
- Write the processed frames to create an output video.  

## **What is FourCC?**  
**FourCC (Four Character Code)** is a 4-byte code used to specify the **video codec** for encoding video files. It determines how video frames are compressed and stored.  

### **Common FourCC Codes**  
| FourCC Code | Description |  
|------------|------------|  
| `XVID` | Widely used codec for AVI files. |  
| `MJPG` | Motion JPEG codec. |  
| `MP4V` | MPEG-4 codec. |  
| `H264` | Advanced video coding format. |  

We use:  
```python
fourcc = cv2.VideoWriter_fourcc(*'XVID')
```
to define the codec for saving the processed video.  

## **Libraries Used**  
- **OpenCV (cv2)** – For video handling, frame processing, and visualization.  
- **YOLO** – Deep learning model for object detection.  
- **NumPy** – For numerical operations.  

## **Expected Output**  
- For **images**: Objects detected with bounding boxes.  
- For **videos**:  
  - Objects detected in **real-time**.  
  - Output video with **bounding boxes** drawn on detected objects.
  - 
This project effectively integrates **Ultralytics YOLO with OpenCV** to achieve real-time object detection in both images and videos. 🚀
