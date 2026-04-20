# 📘 SPARK 2026 — Week 9 Mini Challenge
## 🧠 Transfer Learning in Medical Imaging

---

## 📌 Objective
This project applies **transfer learning** to two medical imaging tasks:

- 🫁 Chest X-ray classification (pneumonia detection)
- 🎗️ Breast ultrasound segmentation (tumor detection)

👉 Goal: improve Week 7 (CNN) and Week 8 (U-Net) baselines using pretrained models.
👉 The data is available in the team's drive.
---

## 🧪 Tasks

### 🔹 1. CXR Classification
- Binary classification:
  - 0 = Normal
  - 1 = Pneumonia  
- Metric: **Macro F1-score**  
- Use pretrained CNNs (ResNet, EfficientNet, etc.)

---

### 🔹 2. BUS Segmentation
- Binary segmentation (lesion vs background)  
- Metric: **Dice coefficient**  
- Use U-Net with pretrained encoder  

---

## 📂 Dataset Structure

### 🫁 CXR

train/
NORMAL/
PNEUMONIA/
val/
NORMAL/
PNEUMONIA/
test/
train.csv
val.csv
test.csv


---

### 🎗️ BUS

train/
images/
masks/
val/
images/
masks/
test/
images/
train.csv
val.csv
test.csv


---

## ⚙️ Pipeline Summary
1. Preprocess (resize, normalize, augment)
2. Load pretrained model
3. Fine-tune on medical data
4. Evaluate:
   - CXR → F1-score
   - BUS → Dice score
5. Predict on test set and submit

---

## ⚖️ Key Challenges
- Imbalanced dataset (CXR)
- Domain shift (natural images → medical images)
- Choosing freeze/unfreeze strategy

---

## 📤 Submission
- Summary PDF (1 page)
- CXR notebook
- BUS notebook

---

## 🎯 Goal
Improve baseline models using transfer learning and achieve better clinical performance on both tasks.