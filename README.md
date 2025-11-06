 #🐱 Cat Breed Recognition using YOLOv8 and MobileNetV2

This project builds an **AI-based cat breed recognition system** that can automatically detect and classify different cat breeds from images.  
It combines **YOLOv8** (for object detection) and **MobileNetV2 Custom Head** (for breed classification), trained on the **Oxford-IIIT Pet Dataset**.

---

## 🚀 Features
- **Automatic detection** of cat regions using YOLOv8 (bounding box localization).  
- **Breed classification** with MobileNetV2 Custom Head (12 cat breeds).  
- **Data preprocessing**: filtering, resizing, normalization, augmentation (flip, rotation, zoom, shear).  
- **Lightweight and fast** — optimized for mobile or web deployment.  


---

## 🧠 Model Architecture

**1️⃣ YOLOv8** — detect and crop cats from original images.  
**2️⃣ MobileNetV2 (Custom Head)** — classify cropped images into 12 breeds.  
[Input Image] → YOLOv8 (detect cat) → crop region → MobileNetV2 → Breed Prediction

**Configuration:**
- Backbone: MobileNetV2 (pretrained on ImageNet)  
- Pooling: Global Average Pooling  
- Custom Head: Dense(128, ReLU) → Dropout(0.3) → Dense(64, ReLU) → Dropout(0.3) → Dense(12, Softmax)  
- Optimizer: Adam (lr=0.001)  
- Loss: Categorical Crossentropy  
- Epochs: 30 (with EarlyStopping=5)

---

## 📊 Dataset
**Oxford-IIIT Pet Dataset**  
- Developed by the Visual Geometry Group (VGG), University of Oxford.  
- Contains 37 classes (cats + dogs), ~7,000 images.  
- This project focuses on **12 cat breeds** extracted from the dataset.

---

## 📈 Results

| Metric | Training | Validation |
|---------|-----------|------------|
| Accuracy | 0.8708 | **0.9011** |
| Loss | 0.3567 | **0.2832** |
| Precision / Recall / F1-score | – | **~0.91** |

- No significant overfitting observed.  
- Confusion matrix shows strong breed-level differentiation (especially for Bombay, Persian, Sphynx).

---


📦 **GitHub Repository:** [https://github.com/waanuu/cat-breed-identification](https://github.com/waanuu/cat-breed-identification)


