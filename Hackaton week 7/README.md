# 🫁 SPARK 2026 — Chest X-Ray Pneumonia Classification Challenge

## 📌 Overview

This project is part of the **SPARK Academy 2026 Mini Challenge Series**, designed to apply deep learning techniques to a real-world medical imaging problem.

The objective is to build a **Convolutional Neural Network (CNN) from scratch using PyTorch** to classify pediatric chest X-ray images into:

- **0 — Normal**
- **1 — Pneumonia**

This task reflects real-world applications of AI in radiology and clinical decision support.

---

## 🎯 Objective

Develop a complete deep learning pipeline that:

- Trains a CNN from scratch (no transfer learning)
- Accurately classifies chest X-ray images
- Generalizes well on unseen data

📊 **Evaluation Metric:** Macro F1-Score

---

## 🌍 Clinical Context

Pneumonia is one of the leading causes of death among children under five, especially in Sub-Saharan Africa.

Due to the shortage of radiologists, many hospitals face delays in diagnosis. A reliable AI model can:

- Assist in early detection
- Serve as a triage tool
- Help prioritize high-risk cases

---

## 📊 Dataset Description

The dataset is derived from:

> **Chest X-Ray Images (Pneumonia)** — Kermany et al., 2018

### Key Characteristics

| Property | Value |
|----------|-------|
| Modality | Chest X-ray |
| View | Anterior-Posterior (AP) |
| Color | Grayscale |
| Patients | Pediatric (1–5 years old) |
| Format | JPEG |
| Source | Guangzhou Women and Children's Medical Center |

---

## 📁 Dataset Structure

dataset/
├── train/
│ ├── NORMAL/
│ └── PNEUMONIA/
├── val/
│ ├── NORMAL/
│ └── PNEUMONIA/
└── test/


- `train/` and `val/`: labeled datasets  
- `test/`: unlabeled dataset for submission  

---

## 📄 CSV Files

| File | Description |
|------|------------|
| `train.csv` | Training data with labels |
| `val.csv` | Validation data with labels |
| `test.csv` | Test data (no labels) |
| `sample_submission.csv` | Submission template |

### Columns

- `id`: Unique identifier (e.g., `CXR_00001`)  
- `filepath`: Relative path to image  
- `filename`: Image file name  
- `target`: Label (0 = Normal, 1 = Pneumonia)  

⚠️ **Important Constraints:**

- Do NOT use `id`, `filename`, or `filepath` as features  
- Only image data should be used for training  

---

## ⚖️ Class Distribution

The dataset is **imbalanced**:

- ~74% Pneumonia  
- ~26% Normal  

### Recommended Strategies

- Class weighting in loss function  
- Oversampling minority class  
- Data augmentation  

---

## 🧠 Modeling Requirements

You must implement the full deep learning pipeline:

### 1. Preprocessing

- Resize images (e.g., `224 × 224`)  
- Normalize pixel values  
- Optionally compute dataset mean and standard deviation  

### 2. Data Augmentation

- Improve generalization  
- Examples: rotation, flipping, etc.  

### 3. CNN Architecture (From Scratch)

Use PyTorch modules such as:

- `nn.Conv2d`  
- `nn.MaxPool2d`  
- `nn.BatchNorm2d`  
- `nn.ReLU`  
- `nn.Dropout`  
- `nn.Linear`  

### 4. Training Loop

- Forward pass  
- Loss computation  
- Backpropagation  
- Metric tracking  

### 5. Validation

- Monitor performance on validation set  
- Prevent overfitting  

### 6. Evaluation

- F1-score (primary metric)  
- Confusion matrix  
- ROC-AUC  

### 7. Loss Function

- `nn.BCEWithLogitsLoss` OR  
- `nn.CrossEntropyLoss`  

---

## 📏 Evaluation Metric

The competition uses **Macro F1-Score**, which:

- Computes F1-score per class  
- Averages them equally  

⚠️ This ensures both classes are equally important despite imbalance.  

---

## 🚫 Rules & Constraints

- ❌ No transfer learning (pretrained models are NOT allowed)  
- ❌ Do NOT use test data during training or tuning  
- ❌ Do NOT use metadata as predictive features  
- ✅ Notebook must be fully reproducible  

---

## 📤 Kaggle Submission

Submit a CSV file with the following format:
id,target
CXR_00001,0
CXR_00002,1
...


- Must match `sample_submission.csv`  
- Predictions generated from `test.csv`  

---

## 📦 Deliverables

Each team must submit:

### 1. Kaggle Submission

- Prediction CSV file  

### 2. Jupyter Notebook

- Clean, well-commented, fully executable  

### 3. One-Page PDF Summary

Must include:

- Team name  
- Team members and roles  
- Model architecture and approach  
- Best leaderboard F1-score  

---

## 📧 Email Submission

**To:** `spark@cameramriafrica.org`  
**Subject:** `SPARK2026 Mini Challenge Submission — TEAMNAME`  

### Email Body

Team Name:

Team Members:

Full Name | Email | Role
...

### Attachments

- `TEAMNAME_summary.pdf`  
- `TEAMNAME_notebook.ipynb`  

---

## ⏰ Deadline

📅 **Friday, April 10, 2026 — 11:59 PM (GMT+1)**  

---

## 🧾 Citation

Kermany, D., Goldbaum, M., Cai, W. et al. (2018).  
*Identifying Medical Diagnoses and Treatable Diseases by Image-Based Deep Learning*  
Cell, 172(5), 1122–1131  
https://doi.org/10.1016/j.cell.2018.02.010  

---

## 💡 Notes for the Team

- This is a **team-only competition**  
- Use the Kaggle leaderboard to track performance  
- Document all decisions clearly in your notebook  
- Focus on **generalization and robustness**  

---