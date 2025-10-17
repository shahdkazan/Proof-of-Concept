# Proof-of-Concept
Proof of Concept for AgriVision – a deep learning–based plant disease detection system using EfficientNetV2S and TensorFlow Lite for mobile deployment.

# AgriVision PoC – Plant Disease Detection

A proof-of-concept deep learning system for detecting plant diseases using **EfficientNetV2S** and **TensorFlow Lite**.

---

## Overview
This notebook demonstrates the full workflow for plant disease diagnosis, including:

- Dataset preparation and organization  
- Data preprocessing and augmentation  
- Transfer learning with **EfficientNetV2S**  
- Model evaluation and visualization  
- Conversion to `.tflite` format for mobile deployment  

The proof of concept validates the feasibility of a lightweight and mobile-compatible model for crop disease detection.

---

## Dataset

This project uses a combined dataset derived from two publicly available sources.

### 1. PlantVillage Dataset
- **Source:** [Kaggle – PlantVillage Dataset](https://www.kaggle.com/datasets/arjuntejaswi/plant-village)  
- **Classes Used:**  
  - Tomato – Early Blight  
  - Tomato – Healthy  
- **Description:**  
  The PlantVillage dataset includes over 50,000 labeled leaf images across several crops and diseases.  
  It is widely used for benchmarking plant disease classification models.

---

### 2. Tomato Leaf Miner Dataset
- **Source:** [Mendeley Data – Tomato Leaf Miner Dataset](https://data.mendeley.com/datasets/kt64b2kh89/2)  
- **Classes Used:**  
  - Tomato – Leaf Miner  
- **Description:**  
  Contains images of tomato leaves infested by *Tuta absoluta* (tomato leaf miner).  
  It provides diverse lighting and background conditions, enhancing model robustness.

---

### Dataset Structure
The datasets are organized in the following structure for training:
AgriVision_PoC/
├── Tomato_Healthy/
├── Tomato_Early_Blight/
└── Tomato_Leaf_Miner/
