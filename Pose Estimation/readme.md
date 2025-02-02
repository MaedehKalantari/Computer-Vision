# **Pose Landmark Detection using MediaPipe**  

## **Overview**  
This project implements **pose landmark detection** using **MediaPipe**, a machine-learning solution by **Google** for real-time human pose estimation. **MediaPipe Pose** detects **33 keypoints** on the human body, allowing accurate movement analysis.  

### **Key Features of MediaPipe**  
MediaPipe is widely used for various tasks, including:  
- **Object detection**  
- **Image classification**  
- **Gesture recognition**  
- **Face detection & landmark detection**  

In this project, we use **MediaPipe Pose** to detect and track **body keypoints** in real-time and apply it to a specific task: **counting dumbbell curls (bicep curls).**  

## **Landmark Keypoints**  
MediaPipe provides **33 keypoints** corresponding to body joints. Some key ones include:  
- **Head & Face**: Nose (0), Eyes (1-6), Ears (7-8), Mouth (9-10)  
- **Upper Body**: Shoulders (11-12), Elbows (13-14), Wrists (15-16), Fingers (17-22)  
- **Lower Body**: Hips (23-24), Knees (25-26), Ankles (27-28), Feet (29-32)  

## **Objective**  
Our goal is to:  
1. **Detect and track pose landmarks** using **MediaPipe Pose**.  
2. **Identify key joints** involved in bicep curls.  
3. **Compute the arm angle** in real-time (between **wrist, elbow, and shoulder**).  
4. **Count the number of completed curls** based on movement patterns.  

## **Approach**  
1. **Perform Pose Detection**  
   - Capture real-time frames using **OpenCV (cv2)**.  
   - Convert frames from **BGR to RGB** (as MediaPipe works with RGB).  
2. **Identify Key Joints**  
   - Extract **shoulder, elbow, and wrist** positions.  
3. **Compute Angles**  
   - Calculate the **angle** between **wrist-elbow-shoulder** to track movement.  
4. **Count Curls**  
   - Detect upward and downward arm motion.  
   - Count reps when a full curl is completed.  
 

## **Implementation Details**  
- **Capture frames using OpenCV** → `cv2.VideoCapture()`  
- **Convert BGR to RGB** → `cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)`  
- **Detect landmarks using MediaPipe Pose**  
- **Compute angles dynamically**  
- **Display real-time video with annotations** using `cv2.imshow()`  

## **Important Terminology**  
| Term | Description |  
|------|------------|  
| **Keypoints** | Detected points like joints, landmarks. |  
| **Heatmaps** | Grids indicating keypoint likelihood. |  
| **Skeleton** | Arrangement of keypoints into a body structure. |  
| **Part Affinity Field (PAF)** | Maps relationships between keypoints. |  
| **Multi-Person Detection** | Technique to detect multiple people. |  
| **3D Pose Estimation** | Adds depth dimension (X, Y, Z). |  

## **Expected Output**  
- Real-time pose detection with **landmarks overlaid** on the body.  
- **Live angle display** between **wrist-elbow-shoulder**.  
- **Automated curl counter** updating with each completed rep.  

This project demonstrates **how MediaPipe Pose can be used for real-time movement analysis and fitness tracking**.  
