
# AgriVision – Proof of Concept (PoC)

A Proof of Concept for **AgriVision**, a deep learning–based plant disease detection system using **EfficientNetV2S** and **TensorFlow Lite**.
This PoC validates the feasibility of classifying tomato leaf diseases and demonstrates a lightweight GUI prototype for offline or mobile use.

---

## Overview

The PoC implements a minimal version of the AgriVision pipeline, focusing on:

* Testing model performance on a small dataset.
* Demonstrating the core workflow of disease classification.
* Generating a deployable TensorFlow Lite model.
* Providing a simple GUI interface for prediction.

---

## Dataset

Two public datasets were combined to form three tomato leaf classes:

| Dataset                                    | Source                                                               | Classes Used                            | Images per Class |
| ------------------------------------------ | -------------------------------------------------------------------- | --------------------------------------- | ---------------- |
| **PlantVillage Dataset**                   | [Kaggle](https://www.kaggle.com/datasets/arjuntejaswi/plant-village) | Tomato – Early Blight, Tomato – Healthy | 100 each         |
| **Tomato Leaf Image Dataset (TLID/PTLID)** | [Mendeley](https://data.mendeley.com/datasets/kt64b2kh89/2)          | Tomato – Leaf Miner                     | 100              |

All images were resized to **384×384** and normalized.
The data were split into training, validation, and testing sets.

---

## Model Development

* **Architecture:** EfficientNetV2S (pre-trained on ImageNet)
* **Framework:** TensorFlow / Keras
* **Training:** 12 epochs with early stopping and learning rate scheduling
* **Augmentation:** Rotation, flipping, zooming, and shifting
* **Optimizer:** Adam (learning rate = 1e-3)
* **Loss Function:** Sparse categorical cross-entropy

### Saved Models

* `POC3_EfficientNetV2S.h5` – trained model
* `POC3_EfficientNetV2S.tflite` – converted TensorFlow Lite version for mobile deployment


---

## Graphical User Interface (GUI)

A lightweight GUI prototype was built using **Tkinter** to demonstrate user interaction.

### Features

* Upload a tomato leaf image for instant prediction
* Display of:

  * Disease name (English and Arabic)
  * Cause description
  * Suggested treatment
* Simple agriculture-inspired design


---

## Directory Structure

```
AgriVision_PoC/
│
├── poc_model.ipynb          # Model training and evaluation
├── poc_app.py               # GUI interface
├── POC3_EfficientNetV2S.h5  # Saved Keras model
├── POC3_EfficientNetV2S.tflite # Converted TensorFlow Lite model
└── README.md
```

---

## Results

* The PoC successfully demonstrated the feasibility of deep learning–based disease detection.
* The model achieved high accuracy on the test subset despite limited data.
* The TFLite model ensures readiness for future mobile and offline deployment.

---

## Future Work

* Extend to additional crops and diseases.
* Integrate into a mobile application with TensorFlow Lite.
* Incorporate weather and location-based advisory features.
* Enhance dataset diversity for improved generalization.

---


