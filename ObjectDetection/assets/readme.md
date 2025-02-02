# **Object Detection using YOLO & OpenCV**  

## **Overview**  
This project implements **object detection** using the **YOLO (You Only Look Once) model** on both **images** and **videos**. We use **cv2 (OpenCV)** for processing video input and performing frame-by-frame object detection.  

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

This project demonstrates how to apply **YOLO for object detection** in real-world applications using **OpenCV**. 🚀  
