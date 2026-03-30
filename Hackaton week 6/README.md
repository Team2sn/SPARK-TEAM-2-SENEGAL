# 🫀 Heart Disease Prediction Challenge

**SPARK Academy 2026 — Mini Hackathon (Week 6)**

---

## 📌 Overview

This project is part of the SPARK Academy 2026 Hackathon Phase.
The objective is to build a **supervised machine learning model** capable of predicting the presence of heart disease using clinical patient data.

---

## 📓 Notebook

Access the project notebook here:  
👉 https://colab.research.google.com/drive/1kC0abUYF0LSGHODmprLDLVX5cR9Ci7K4?usp=sharing

---

## 🎯 Objective

Given a set of clinical features, predict:

* `0` → No heart disease
* `1` → Heart disease present

This is a **binary classification problem** evaluated on **macro-averaged F1-score**.

---

## 🧠 Clinical Context

Cardiovascular diseases are the leading cause of death globally and represent a growing burden in Africa.

This challenge explores whether machine learning can assist early diagnosis using **routine clinical measurements**, especially in low-resource environments.

---

## 📊 Dataset

The dataset is derived from the **UCI Heart Disease Dataset**, combining data from multiple international institutions:

* Cleveland Clinic Foundation (USA)
* Hungarian Institute of Cardiology (Hungary)
* University Hospital Zurich (Switzerland)
* V.A. Medical Center Long Beach (USA)

### Features:

* Age, sex
* Chest pain type
* Blood pressure
* Cholesterol
* ECG results
* Maximum heart rate
* Exercise-induced angina
* ... (14 features total)

---

## ⚙️ Problem Type

* Supervised Learning
* Binary Classification
* Imbalanced Dataset (~68% positive class)

---

## 📏 Evaluation Metric

**Macro F1-Score**

* Equal importance to both classes
* Penalises biased models
* More robust than accuracy for imbalanced data

---

## 🧪 Allowed Methods

✔️ Logistic Regression
✔️ Decision Trees
✔️ Random Forest
✔️ K-Nearest Neighbors
✔️ Support Vector Machine
✔️ Gradient Boosting

---

## 🚫 Restrictions

* ❌ No Deep Learning (TensorFlow, PyTorch, Keras)
* ❌ No AutoML tools
* ❌ No pre-trained models
* ❌ No external datasets
* ❌ No data leakage (test set must remain unseen)

---

## 📁 Project Structure

```
Hackathon Week 6/
├── data/
├── notebooks/
├── submissions/
└── README.md
```

---

## 📤 Submission Requirements

Each team must submit:

### 1. Kaggle Submission

* Format: `id, target`
* Uploaded to Kaggle platform

### 2. Jupyter Notebook

* Fully executable (top → bottom)
* Well documented with Markdown
* Reproducible (`random_state=42`)

### 3. One-Page PDF Summary

Includes:

* Team name
* Members and roles
* Approach description
* Best F1-score

---

## 🧾 Rules Summary

* Max **3 submissions/day**
* Max **2 final submissions**
* Teams are pre-assigned
* Single Kaggle account per team
* Data must remain private within participants

---

## ⚖️ License & Usage

Submissions grant the competition organisers a **non-exclusive license** for educational and research use.

---

## 🏁 Goal

Build a model that generalises well across populations and performs strongly on both classes — not just the majority class.

---

## 📚 Citation

Detrano et al. (1989), *American Journal of Cardiology*

---

## 🚀 Status

* ⏳ In progress
* 📊 Leaderboard tracking via Kaggle
* 🔁 Iterative model improvement

---
