# ServeSmart Military Object Detection

This repository contains an end-to-end object detection pipeline built using **YOLOv8** for detecting military and civilian assets from aerial and ground imagery. The project was developed as part of the **ServeSmart Hackathon**.

---

## 👥 Team Members
- Raj Kumar  
- Sahil Sejal Shah  

---

## 📌 Problem Overview
The objective of this project is to accurately detect and classify multiple object categories, including military vehicles, soldiers, weapons, and civilian assets, under challenging real-world conditions such as camouflage, occlusion, and scale variation.

---

## 🧠 Model & Approach
- **Model:** YOLOv8s (Ultralytics)
- **Pretraining:** COCO dataset
- **Task:** Multi-class object detection (12 classes)
- **Framework:** PyTorch + Ultralytics YOLO

The YOLOv8s model was selected to balance detection accuracy and computational efficiency, making it suitable for near real-time inference and deployment on resource-constrained systems.

---

## 🗂 Dataset
The dataset consists of annotated images in YOLO format and includes the following object classes:

camouflage_soldier, weapon, military_tank, military_truck, military_vehicle, civilian, soldier, civilian_vehicle, military_artillery, trench, military_aircraft, military_warship

---

## ⚙️ Training Details
- Image Size: 640 × 640  
- Batch Size: 16  
- Epochs: Up to 80 (early stopping enabled)  
- GPU: Tesla P100  
- Data Augmentation: Mosaic, HSV, scaling, flipping  

Early stopping was used to prevent overfitting and select the best-performing model checkpoint.

---

## 📊 Evaluation Metrics
The primary evaluation metric used is **mAP@50**, along with precision and recall.  
The final model achieved:

- **mAP@50 ≈ 0.54**
- Balanced precision and recall across most classes

---

## 🚀 Inference
Inference was performed on the test set using the best validation checkpoint. Predictions were generated in YOLO format with confidence scores for each detected object.

---

## 📁 Repository Contents
- `ServeSmart_ObjectDetection.ipynb` – Complete training and inference notebook  
- `military_fixed.yaml` – Dataset configuration file  
- `report.pdf` – Detailed project report  

---

## ⚠️ Notes
Due to dataset size and GPU requirements, the notebook is not intended to be fully re-run locally. Training and inference were performed on Kaggle.

---

## 📜 License
This project is intended for educational and research purposes.
ServeSmart Military Object Detection

Authors:
- Raj Kumar
- Sahil Sejal Shah

Model:
- YOLOv8s (Ultralytics)
- COCO pretrained weights

Description:
This project trains a YOLOv8s object detection model on a 12-class military dataset.
The model is optimized for efficiency and robustness using data augmentation and
early stopping. Predictions are generated in YOLO format with confidence scores.

How to Run:
1. Install dependencies: ultralytics, torch, opencv
2. Train using the notebook
3. Run inference using best.pt on test images
