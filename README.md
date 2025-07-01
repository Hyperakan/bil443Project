# Kidney Stone Detection in Ultrasound Images Using Deep Learning  
**BIL443 Project – TOBB University of Economics and Technology**  
**Author:** Hakan Doğan  


---

## 📌 Project Description

This project presents a deep learning-based approach for **automatic detection of kidney stones in ultrasound images**, utilizing two modern object detection architectures: **Faster R-CNN** and **YOLOv11**.

Unlike CT scans—which are costly and involve radiation—this study focuses on ultrasound (USG) as a more **accessible, affordable, and non-invasive** imaging method, despite its lower contrast and speckle noise challenges.

---

## 🧠 Models Used

### 🔹 Faster R-CNN  
- Implemented with **PyTorch** and **ResNet50 + FPN backbone**  
- Uses transfer learning and fine-tuning  
- High localization precision, but slower and prone to overfitting on small datasets

### 🔹 YOLOv11  
- Implemented via **Ultralytics API and CLI**  
- Trained with `yolo11m.pt` weights  
- Real-time detection capability with **high inference speed and accuracy**  
- Better suited for noisy and low-resource environments

---

## 📊 Dataset

- Source: [Roboflow Universe – Kidney Stone Ultrasound (ECCKD)](https://universe.roboflow.com/radiulogy/kidney-stone-ultrasound-ecckd)
- 5,431 labeled ultrasound images:
  - `Kidney Stone`: 15,107 bounding boxes
  - `Normal Kidney`: 2,280 bounding boxes
- Average resolution: 640×640 pixels  
- Augmentations: Horizontal/vertical flips, grayscale conversion, resizing  
- Split:
  - **90%** Training  
  - **5%** Validation  
  - **5%** Testing

---

## 📈 Results Summary

| Metric | YOLOv11m | Faster R-CNN |
|--------|----------|--------------|
| mAP@0.5 (average) | **0.789** | 0.684 |
| mAP@0.5 (Kidney Stone) | **0.598** | 0.143 |
| mAP@0.5 (Normal Kidney) | **0.979** | 0.450 |
| Inference Time (ms/image) | **23.3** | 109.87 |
| FPS | **43** | 9.1 |

---

## 🧪 Implementation Details

- Language: **Python**
- Frameworks: `PyTorch`, `Ultralytics YOLO`
- Platform: **Google Colab** (GPU accelerated)
- Tools:
  - `Albumentations` for augmentation
  - `Matplotlib`, `Seaborn` for visualizations

---

## 📁 Pretrained Model Weights

The trained model files can be accessed via Google Drive:  
🔗 [Download Trained Weights](https://drive.google.com/drive/folders/1B7lsA__as65SAlUUe_SgLQyzZ11yM986?usp=drive_link)

---

## 🎯 Key Contributions

- First comparative YOLOv11 vs Faster R-CNN implementation for kidney stone detection in ultrasound images  
- Modular training pipelines and reproducible experimentation  
- Demonstrated real-time detection potential of YOLOv11  
- Investigated effects of preprocessing, augmentation, and class simplification

