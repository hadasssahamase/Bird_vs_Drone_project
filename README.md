# Bird_vs_Drone_project

---

## 📌 Project Overview
This project aims to build a robust real-time object detection system that can differentiate between birds and drones using YOLOv8 — a cutting-edge deep learning model optimized for speed and accuracy.
Such systems have real-world applications in:
- 🔒 Security & Surveillance (detecting unauthorized drones)
- ✈️ Airports & Flight Zones (avoiding collisions with birds)
- 🐦 Wildlife Monitoring (tracking birds without confusing them for drones)

---

## Business Understanding	
The need to distinguish between birds and drones arises in areas like airport safety, wildlife conservation, and national security. Misidentification can lead to false alarms or even catastrophic incidents (e.g., bird strikes or drone trespassing). The goal is to develop a real-time detection system that accurately classifies aerial objects.

---
## Data Understanding	
The dataset contains images of birds and drones sourced from open datasets (e.g., Roboflow, Kaggle, Google Images). Images vary in resolution, angle, lighting, and background. A preliminary EDA revealed class imbalance and noise (blurred or irrelevant images).

---
## Data Preparation	
- Cleaned mislabeled or low-quality images
- Resized and normalized input images
- Split into training/validation/test sets
- Applied data augmentation: flipping, brightness adjustment, rotation
- Annotated using Roboflow for YOLO format

---
## Modeling 
Choose YOLOv8n for fast and lightweight object detection. 
Trained using:
- 50 epochs
- Image size: 640
- Batch size: 16
- Optimizer: SGD
- Evaluated with mAP, Precision, and Recall

---
 ## Evaluation 
The trained model achieved:
- mAP@0.5: 89%
- Precision: 92%
- Recall: 87%
- Misclassifications mostly occurred in distant or overlapping objects.
- The model performs well in most daylight and mid-range scenarios.

---
## 📚 Lessons Learned
- Quality of annotations significantly affects detection performance
- Smaller YOLOv8 models (YOLOv8n) are ideal for edge deployment
- Augmentations like flip, rotation, brightness boost generalizability
- Post-processing (NMS thresholds) can reduce false positives

---
## 💬 Future Work
- Deploy on Raspberry Pi or Jetson Nano for edge-based detection
- Integrate with alarm system or live dashboard
- Add more classes: e.g., airplane, kite, balloon
- Fine-tune with more diverse data (weather, lighting conditions)
