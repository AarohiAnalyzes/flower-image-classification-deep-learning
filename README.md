# 🌸 Flower Image Classification using Deep Learning

An end-to-end deep learning project for multi-class flower image classification using TensorFlow and Keras. This project compares three different approaches: a custom Convolutional Neural Network (CNN), Transfer Learning with MobileNetV2, and Fine-Tuning of MobileNetV2. The models are evaluated using multiple performance metrics, confusion matrices, error analysis, and Grad-CAM explainability.

---

## 📌 Project Overview

This project investigates the effectiveness of different deep learning techniques for classifying flower images into five species and compares the performance of:

- Custom CNN trained from scratch
- Transfer Learning using MobileNetV2
- Fine-Tuned MobileNetV2

The objective is to understand the advantages of transfer learning on small datasets and analyze model behavior through explainability techniques.

---

## 🎯 Problem Statement

Given an input flower image, predict its corresponding species from the following five classes:

- 🌼 Daisy
- 🌻 Dandelion
- 🌹 Rose
- 🌻 Sunflower
- 🌷 Tulip

This is a supervised multi-class image classification problem.

---

## 📂 Dataset

**Dataset:** TensorFlow Flower Photos Dataset

| Property | Value |
|----------|-------|
| Images | 3,670 |
| Classes | 5 |
| Image Size | Resized to 160 × 160 |
| Train Split | 70% |
| Validation Split | 15% |
| Test Split | 15% |

The dataset was split using stratified sampling to preserve class distribution while preventing data leakage between training, validation, and testing datasets.

---

## 🏗️ Methodology

The project follows the pipeline below:

```
Dataset
    │
    ▼
Image Preprocessing
    │
    ▼
Train / Validation / Test Split
    │
    ▼
Model Training
 ├── Custom CNN
 ├── Transfer Learning (MobileNetV2)
 └── Fine-Tuning MobileNetV2
    │
    ▼
Model Evaluation
    │
    ▼
Error Analysis
    │
    ▼
Grad-CAM Explainability
```

---

## 🧠 Deep Learning Models

### 1️⃣ Custom CNN

A CNN designed and trained entirely from scratch.

Architecture:

- Convolution Blocks
- Batch Normalization
- Max Pooling
- Global Average Pooling
- Dense Classification Layer

Characteristics:

- ~110K trainable parameters
- Baseline model
- Trained only on flower dataset

---

### 2️⃣ Transfer Learning

A pretrained MobileNetV2 model trained on ImageNet was used as a fixed feature extractor.

Characteristics:

- Frozen feature extractor
- Only classification head trained
- Approximately 6.4K trainable parameters
- Faster convergence
- Highest overall performance

---

### 3️⃣ Fine-Tuned MobileNetV2

The upper layers of MobileNetV2 were unfrozen for fine-tuning.

Characteristics:

- ~1.9M trainable parameters
- Very small learning rate
- Slight overfitting due to limited dataset size
- No performance improvement over frozen MobileNetV2

---

## 📊 Experimental Results

| Model | Accuracy | Precision | Recall | F1 Score |
|--------|----------|-----------|--------|----------|
| Custom CNN | 71.7% | 71.4% | 71.2% | 71.2% |
| Transfer Learning (MobileNetV2) | **90.0%** | **90.0%** | **89.9%** | **89.9%** |
| Fine-Tuned MobileNetV2 | 89.3% | 89.3% | 89.3% | 89.3% |

---

## 🔍 Key Findings

- Transfer Learning significantly outperformed the custom CNN while requiring far fewer trainable parameters.
- Fine-tuning did not improve performance due to the relatively small dataset.
- Transfer Learning reached high validation accuracy much faster than the other models.
- The experiment demonstrates the effectiveness of pretrained models for limited datasets.

---

## 📉 Error Analysis

Model predictions were analyzed using confusion matrices and misclassified examples.

Major observations:

- Roses and tulips were the most frequently confused classes.
- Sunflowers were the easiest class to classify.
- Many misclassifications were caused by genuine visual similarity rather than model failure.
- Some errors originated from noisy or ambiguous images within the dataset.

---

## 🔥 Explainability using Grad-CAM

Grad-CAM was used to visualize the regions contributing to model predictions.

Key observations:

- Correct predictions focused primarily on the flower itself.
- Misclassified roses and tulips showed attention concentrated on visually similar petal structures.
- The visual explanations supported the observed confusion patterns.

---

## 🛠️ Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Jupyter Notebook

---

## 👩‍💻 Author

**Aarohi Mistry**

Master's Student in Data Science  
University of Milano-Bicocca

---
