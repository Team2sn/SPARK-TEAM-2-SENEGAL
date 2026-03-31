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

## 📊 Dataset Description

The dataset is derived from the **UCI Heart Disease Dataset**, combining patient records from four medical institutions across three countries.

The objective is to predict whether a patient has heart disease based on clinical measurements.

---

## 📁 Files

- **train.csv**  
  Contains 690 patient records with clinical features and the target label.  
  Used for training and validation.

- **test.csv**  
  Contains 230 patient records with clinical features only.  
  The target label is not provided. Predictions must be generated for submission.

- **sample_submission.csv**  
  Example submission file with the correct format (`id`, `target`).  
  Replace the `target` column with your predictions.

---

## 🧾 Features Description

| Column     | Description |
|-----------|------------|
| id        | Unique identifier for each patient |
| age       | Age of the patient (years) |
| sex       | Biological sex (Male, Female) |
| cp        | Chest pain type (typical angina, atypical angina, non-anginal, asymptomatic) |
| trestbps  | Resting blood pressure (mmHg) |
| chol      | Serum cholesterol (mg/dl) |
| fbs       | Fasting blood sugar > 120 mg/dl (True/False) |
| restecg   | Resting ECG results |
| thalach   | Maximum heart rate achieved |
| exang     | Exercise-induced angina (True/False) |
| oldpeak   | ST depression induced by exercise |
| slope     | Slope of peak exercise ST segment |
| ca        | Number of major vessels (0–3) *(may contain missing values)* |
| thal      | Thalassemia type *(may contain missing values)* |
| origin    | Data collection site |
| target    | Target variable (0 = no disease, 1 = disease) *(train only)* |

---

## 🧠 Clinical Terms

- **ECG / restecg** → Electrical activity of the heart  
- **ST depression / oldpeak** → Indicator of reduced blood flow during exercise  
- **ST segment / slope** → Marker of cardiac stress  
- **Angina / exang** → Chest pain due to reduced blood flow  
- **Thalassemia / thal** → Blood disorder affecting oxygen transport  
- **Fluoroscopy / ca** → Imaging technique showing vessel blockage  
- **fbs** → High blood sugar, linked to cardiovascular risk  

---

## ⚠️ Important Notes

- `ca` and `thal` contain missing values → must be handled during preprocessing  
  (e.g., median, mode, or row removal)

- The `id` column:
  - is **not a feature**
  - must **not be used for prediction**

- The `origin` column:
  - indicates the data source
  - can be used as a feature if relevant

---

## 🎯 Objective

Build a machine learning model to predict the `target` variable:

- **0** → No heart disease  
- **1** → Heart disease present  

---

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
