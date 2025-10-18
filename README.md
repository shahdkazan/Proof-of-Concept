AgriVision – Plant Disease Detection System

AgriVision is a proof-of-concept (PoC) deep learning system for tomato crop disease detection.
It integrates a trained EfficientNetV2S model with a Tkinter-based GUI to provide offline disease diagnosis, Arabic support, and simple treatment guidance.

Project Overview

AgriVision demonstrates how lightweight AI can assist farmers in identifying tomato leaf diseases using offline image classification.
The system outputs the detected disease name (in English and Arabic), a confidence score, possible causes, and recommended treatments.

Features

Offline inference using a pre-trained EfficientNetV2S model

Simple Tkinter graphical interface

Disease details in both English and Arabic

Three supported classes:

Tomato_Early_Blight

Tomato_Healthy

Tomato_Leaf_Miner

Clear explanations of cause and suggested treatment

Mobile-compatible model structure (TensorFlow Lite ready)

Dataset Information

AgriVision uses a combined dataset from two public sources to ensure variety and balance.

1. PlantVillage Dataset

Source: Kaggle – PlantVillage Dataset

Classes Used: Tomato – Early Blight, Tomato – Healthy

Description: Contains over 50,000 labeled images across several crop diseases, widely used for benchmarking.

2. Tomato Leaf Miner Dataset

Source: Mendeley Data – Tomato Leaf Miner Dataset

Classes Used: Tomato – Leaf Miner

Description: Real-world field images affected by Tuta absoluta (tomato leaf miner), captured under diverse conditions.

Dataset Structure
AgriVision_PoC/
│
├── Tomato_Healthy/
├── Tomato_Early_Blight/
└── Tomato_Leaf_Miner/

Model Training

The model training script builds and trains an EfficientNetV2S-based classifier on the dataset.

Training Workflow

Load and preprocess images (resize to 384×384, normalize, encode labels).

Split data into train, validation, and test sets.

Apply data augmentation (rotation, shifting, flipping, zooming).

Fine-tune a pre-trained EfficientNetV2S base model.

Train with early stopping and learning rate reduction.

Evaluate and save the best model.

Model Architecture
EfficientNetV2S (pretrained, frozen base)
 → GlobalAveragePooling2D
 → Dropout(0.3)
 → Dense(512, relu)
 → Dropout(0.3)
 → Dense(num_classes, softmax)

Training Parameters
Parameter	Value
Optimizer	Adam (lr=1e-3)
Loss	Sparse categorical crossentropy
Batch Size	32
Epochs	12
Callbacks	EarlyStopping, ReduceLROnPlateau
Output

The trained model is saved as:

POC3_EfficientNetV2S.h5

Evaluation Results

Typical results on validation and test data:

Metric	Value
Accuracy	96–98%
Precision	96%
Recall	97%
F1-Score	96–97%

Generated plots:

Accuracy and loss curves

Confusion matrix heatmap

Classification report by class

GUI Application

A Tkinter-based GUI named AgriVision provides an intuitive interface for image classification.

Features

Upload and classify tomato leaf images

Displays:

Disease prediction (English and Arabic)

Confidence percentage

Simple cause and treatment message

Offline operation using the saved .h5 model

Agriculture-themed color palette

### Dataset Structure
The datasets are organized in the following structure for training:
AgriVision_PoC/
├── Tomato_Healthy/
├── Tomato_Early_Blight/
└── Tomato_Leaf_Miner/
