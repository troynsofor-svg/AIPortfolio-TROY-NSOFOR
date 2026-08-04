# Problem Statement
The problem that this project in this notebook solves are the two main computer vision tasks: object detection and image segmentation.

# Approach
I solved the problem by using Ultralytics library to perform object detection and image segmentation. Here's a breakdown of the methods and algorithms I used:

With Object Detection, I applied it with YOLO11 (particularly yolo11n.pt), a real-time object detector. The main ideas investigated here are the score threshold for filtering detections and Non-Maximum Suppression (NMS) for eliminating unnecessary bounding boxes.

With Image Segmentation, it first applies YOLO11-seg (yolo11n-seg.pt), which offers YOLO's capabilities to produce pixel-level masks along with bounding boxes. Next, it offers Segment Anything Model 2 (SAM 2, sam2.1_s.pt), a basis model that could segment something when prompted, frequently applying bounding boxes from YOLO. This describes a modern "detect then segment" pipeline.

The notebook even goes over important evaluation metrics such as IoU (Intersection over Union) to calculate localization accuracy, Precision (small number of false alarms), Recall (small number of missed detections), and mAP (mean Average Precision), which is a significant benchmark for general performance.

# Results
Here's the summary of the results and performance examined:

Object Detection (YOLO11): Successfully spotted objects such as buses and people with probability scores (e.g., bus at 94%, persons at 62-88%). It displayed how changing the confidence threshold affects the number of detections, emphasizing a trade-off between responsiveness and false positives. Inference times were quick (e.g., 463.0ms for bus.jpg).

Instance Segmentation (YOLO11-seg): Provided pixel-level masks for detected objects, introducing more correct outlines than bounding boxes. For example, it segmented 4 people, 1 bus, and 1 stop sign from bus.jpg. Segmentation produces a higher detail but is usually a little slower than pure detection (e.g., 303.6ms for bus.jpg).

Foundation Model Segmentation (SAM 2): When prompted by YOLO11's bounding boxes, SAM 2 provided high-quality, precise masks. But, SAM 2 is essentially slower (e.g., 14715.2ms for bus.jpg) and does not produce object labels, differentiating with specialist models such as YOLO11-seg.

Metrics (Conceptual): This lab explained key evaluation metrics: IoU (Intersection over Union) for localization accuracy, Precision (small number of false alarms), Recall (few missed episodes), and mAP (mean Average Precision) as a holistic evaluation metric. While they weren't estimated in this lab, their significance and trade-offs were discussed.

# Key Findings
I learned about the three core CV tasks (Image Classification, Object Detection, and Image Segmentation).

# Technologies Used
(Libraries): MatPlotlib, PIL.Image (Pillow), Numpy, Urllib.Request, Matplotlib.Patches.Rectangle, Ultralytics, YOLO11 (yolo11n.pt), YOLO11-seg (yolo11n-seg.pt), and Segment Anything Model 2 (SAM 2, sam2.1_s.pt)


(Framework): Ultralytics

# How to Run
1. Open Google Colab
2. Go to and click on File (Open Notebook)
3. Click and look for the L06_Nsofor_Troy_ITAI_1378.ipynb file
4. Run all the cells from top to bottom
