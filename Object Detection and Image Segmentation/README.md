# Problem Statement
The problem that this project in this notebook solves are the two core computer vision tasks: object detection and image segmentation.

# Approach
I solved the problem by using Ultralytics library to perform object detection and image segmentation. Here's a breakdown of the methods and algorithms used:

For Object Detection, it uses YOLO11 (specifically yolo11n.pt), a real-time object detector. The key concepts explored here are the confidence threshold for filtering detections and Non-Maximum Suppression (NMS) for removing redundant bounding boxes.

For Image Segmentation, it first uses YOLO11-seg (yolo11n-seg.pt), which extends YOLO's capabilities to provide pixel-level masks alongside bounding boxes. It then introduces Segment Anything Model 2 (SAM 2, sam2.1_s.pt), a foundation model that can segment anything when prompted, often using bounding boxes from YOLO. This demonstrates a modern "detect then segment" pipeline.

The notebook also covers essential Evaluation Metrics like IoU (Intersection over Union) to measure localization accuracy, Precision (few false alarms), Recall (few missed detections), and mAP (mean Average Precision), which is a common benchmark for overall performance.

Here's a summary of the results and performance observed:

Object Detection (YOLO11): Successfully identified objects like buses and people with confidence scores (e.g., bus at 94%, persons at 62-88%). It showed how adjusting the confidence threshold impacts the number of detections, highlighting a trade-off between sensitivity and false positives. Inference times were fast (e.g., 463.0ms for bus.jpg).

Instance Segmentation (YOLO11-seg): Produced pixel-level masks for detected objects, offering more precise outlines than bounding boxes. For instance, it segmented 4 persons, 1 bus, and 1 stop sign from bus.jpg. Segmentation provides higher detail but is generally slightly slower than pure detection (e.g., 303.6ms for bus.jpg).

Foundation Model Segmentation (SAM 2): When prompted by YOLO11's bounding boxes, SAM 2 produced high-quality, precise masks. However, SAM 2 is significantly slower (e.g., 14715.2ms for bus.jpg) and does not provide object labels, contrasting with specialist models like YOLO11-seg.

Metrics (Conceptual): The lab explained key evaluation metrics: IoU (Intersection over Union) for localization accuracy, Precision (few false alarms), Recall (few missed events), and mAP (mean Average Precision) as a comprehensive benchmark score. While not calculated in the lab, their importance and trade-offs were discussed.

I learned about the three core CV tasks (Image Classification, Object Detection, and Image Segmentation).

# Technologies Used:
(Libraries) MatPlotlib, PIL.Image (Pillow), Numpy, Urllib.Request, Matplotlib.Patches.Rectangle, Ultralytics, YOLO11 (yolo11n.pt), YOLO11-seg (yolo11n-seg.pt), and Segment Anything Model 2 (SAM 2, sam2.1_s.pt)


(Framework) Ultralytics library

# How to Run
1. Open Google Colab
2. Go to and click on File (Open Notebook)
3. Click and look for L06_Nsofor_Troy_ITAI_1378.ipynb or L06_Nsofor_Troy_ITAI_1378.
