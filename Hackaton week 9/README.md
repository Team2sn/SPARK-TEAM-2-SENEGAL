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
## Overview week 8

In Week 8, you implemented **U-Net from scratch** to segment breast lesions in ultrasound images. Every weight in the encoder was randomly initialised and learned from the SPARK training set alone.

This week, you will replace the encoder with a **pretrained backbone**, a network whose lower layers already know how to detect edges, textures, and structural patterns from training on millions of natural images. Your job is to graft this encoder onto a segmentation decoder and fine-tune the combined system for the breast ultrasound domain.

This is how real-world medical image segmentation models are built. Pure from-scratch training is rarely used in practice outside of large-scale data regimes. Pretrained encoders consistently outperform random initialisation in low-data medical imaging settings, where the number of annotated images is limited and every gradient step counts.

---

## What You Will Do

- Replace the U-Net encoder with a pretrained backbone of your team's choice  
- Pair it with a U-Net-style decoder (your own implementation or a simple one you design)  
- Fine-tune the full model on the SPARK breast ultrasound training set  
- Compare your Dice score to your Week 8 U-Net baseline  

---

## Key Learning Objectives

- Understand the encoder-decoder segmentation paradigm and how pretrained encoders fit in  
- Know how to load pretrained weights and connect them to a custom decoder  
- Experience the tradeoffs of feature extraction vs. full fine-tuning in segmentation  
- Reflect on domain shift: what does it mean for a model trained on cats and cars to segment tumours?

## Overview week 7

In Week 7, you built a CNN from scratch to classify chest X-rays as **Normal** or **Pneumonia**. You defined every layer, initialised every weight, and trained the entire network from random initialisation.

This week, you will take a different approach: start from a model that has already learned to see.

**Transfer learning** allows a network pretrained on a large dataset, typically ImageNet, to be adapted to a new task with far less data and training time. In medical imaging, this matters enormously — clinical datasets are small, labelling is expensive, and models that converge faster can be validated and deployed sooner.

Your task is the same as Week 7: **binary classification** of chest X-rays as Normal or Pneumonia. The dataset is the same. The difference is in how you build your model.

---

## What You Will Do

- Load a pretrained backbone of your choice (ResNet, EfficientNet, DenseNet, or any other)  
- Fine-tune the model on the SPARK chest X-ray dataset  
- Experiment with freezing and unfreezing layers, learning rate schedules, and augmentation strategies  
- Compare your results to your Week 7 CNN-from-scratch baseline  

---

## Key Learning Objectives

- Understand the mechanics of transfer learning: **feature extraction vs. fine-tuning**  
- Know how to adapt a pretrained ImageNet backbone to a new domain  
- Experience the practical tradeoffs of freezing layers, learning rate warmup, and domain shift  
- Situate this within the broader clinical AI pipeline — pretrained models are the norm in production systems  
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
