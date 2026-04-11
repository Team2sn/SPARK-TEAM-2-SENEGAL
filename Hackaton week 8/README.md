# 🧠 SPARK 2026 — Breast Lesion Segmentation Challenge  
### Team 2 Senegal

---

## 📌 Table of Contents
- [1. Project Overview](#1-project-overview)
- [2. Clinical Context](#2-clinical-context)
- [3. Objective](#3-objective)
- [4. Dataset Description](#4-dataset-description)
- [5. Data Structure](#5-data-structure)
- [6. Data Format](#6-data-format)
- [7. Problem Formulation](#7-problem-formulation)
- [8. Evaluation Metric](#8-evaluation-metric)
- [9. Submission Format](#9-submission-format)
- [10. Methodology](#10-methodology)
- [11. Model Architecture](#11-model-architecture)
- [12. Training Strategy](#12-training-strategy)
- [13. Experimentation & Improvements](#13-experimentation--improvements)
- [14. Competition Rules & Constraints](#14-competition-rules--constraints)
- [15. Deliverables](#15-deliverables)
- [16. Reproducibility](#16-reproducibility)
- [17. References](#17-references)

---

## 1. Project Overview

This project is part of the **SPARK Academy 2026 Mini Challenge**, focused on **medical image segmentation**.

The task is to build a deep learning model capable of **automatically detecting and segmenting breast lesions** from ultrasound images.

This is a **team-based Kaggle competition**, where performance is evaluated using the **Dice coefficient**.

---

## 2. Clinical Context

Breast cancer is one of the leading causes of death among women worldwide, causing over **670,000 deaths annually**.

In many regions, especially in Sub-Saharan Africa:
- Radiologists are scarce  
- Ultrasound machines are widely available  

👉 This project aims to:
- Assist clinicians in tumour localisation  
- Improve early diagnosis  
- Provide AI support in low-resource settings  

---

## 3. Objective

The goal is to:

> Build a **binary segmentation model** that predicts the location of breast lesions in ultrasound images.

### Input:
- Ultrasound image  

### Output:
- Binary mask:
  - `1` → lesion  
  - `0` → background  

---

## 4. Dataset Description

The dataset is a curated combination of:

- **BUSI (Breast Ultrasound Images Dataset)**  
- **BUS-BRA (Breast Ultrasound Brazil Dataset)**  

#### dataset drive link : https://drive.google.com/drive/folders/1vHyhDW9Xj2ZvnkJSIQwS05mp514qOTuD?usp=drive_link

### Preprocessing applied:
- Deduplication  
- Standardization  
- Unified naming convention  

---

## 5. Data Structure

```
dataset/
│
├── train/
│   ├── images/
│   ├── masks/
│   └── train.csv
│
├── val/
│   ├── images/
│   ├── masks/
│   └── val.csv
│
├── test/
│   ├── images/
│   └── test.csv
│
└── sample_submission.csv
```

---

## 6. Data Format

### Images
- Format: PNG  
- Type: Grayscale  

### Masks
- Format: PNG  
- Type: Binary  

Pixel values:
- `255` → lesion  
- `0` → background  

### Naming Convention

| Type  | Example |
|------|--------|
| Image | `sp_train_0001.png` |
| Mask  | `sp_train_0001_mask.png` |

---

## 7. Problem Formulation

This is a **Binary Semantic Segmentation** problem.

For each image:
- Predict a mask of the same size  
- Classify each pixel independently  

---

## 8. Evaluation Metric

The model is evaluated using the **Dice Similarity Coefficient**:

```
Dice = (2 × |Prediction ∩ GroundTruth|) / (|Prediction| + |GroundTruth|)
```

### Interpretation:
- `1.0` → Perfect overlap  
- `0.0` → No overlap  

Final score:
> Mean Dice across all test images  

---

## 9. Submission Format

The submission must be a `.csv` file:

```
image_id,rle_mask
sp_test_0001.png,145 3 512 7
sp_test_0002.png,
```

### Important:
- `image_id` must match exactly  
- `rle_mask` must be encoded using **Run-Length Encoding (RLE)**  
- Empty string = no lesion  

---

## 10. Methodology

### 1. Data Preparation
- Load images and masks  
- Normalize pixel values  
- Resize images if needed  

### 2. Data Augmentation
- Horizontal / vertical flips  
- Rotation  
- Scaling  

### 3. Training
- Train model on training set  
- Validate on validation set  

### 4. Evaluation
- Monitor Dice score  
- Prevent overfitting  

---

## 11. Model Architecture

### Baseline: U-Net (from scratch)

Structure:
- Encoder (downsampling)
- Bottleneck
- Decoder (upsampling)
- Skip connections

⚠️ Constraints:
- No pretrained models  
- No segmentation libraries  

---

## 12. Training Strategy

### Loss Functions
- Dice Loss  
- Binary Cross Entropy (BCE)  
- BCE + Dice combined  

### Optimizer
- Adam  

### Other techniques
- Learning rate scheduling  
- Batch training  

---

## 13. Experimentation & Improvements

### Architecture
- Deeper U-Net  
- Attention mechanisms  
- Residual connections  

### Data
- Advanced augmentation  
- Class balancing  

### Training
- Hyperparameter tuning  
- Loss function optimization  

---

## 14. Competition Rules & Constraints

### Required
- Use PyTorch  
- Implement U-Net from scratch  

```python
torch.manual_seed(360)
numpy.random.seed(360)
```

### Forbidden
- Pretrained models  
- External datasets  
- AutoML tools  

---

## 15. Deliverables

### 1. PDF Summary
- Team name  
- Members and roles  
- Approach  
- Best Dice score  

### 2. Notebook
- Clean and reproducible  
- Fully commented  
- Runs without errors  

### 3. Kaggle Submission
- CSV file  

### 4. Email Submission

```
To: spark@cameramriafrica.org
Subject: SPARK2026 Mini Challenge Submission — TEAMNAME
```

---

## 16. Reproducibility

To ensure reproducibility:

- Fix random seeds  
- Document all steps  
- Use consistent preprocessing  
- Ensure notebook runs end-to-end  

---

## 17. References

- Al-Dhabyani et al. (2020) — BUSI Dataset  
- Gómez-Flores et al. (2024) — BUS-BRA Dataset  

---

## 🚀 Final Notes

This project focuses on:
- Deep learning fundamentals  
- Medical image segmentation  
- Real-world AI applications  

👉 Strategy:
- Start with a simple U-Net  
- Improve step by step  
- Document everything  
