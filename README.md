# Weather Image Classification with Deep Learning

This project implements and compares various Deep Learning architectures (ResNet50, VGG19, InceptionV1, MobileNet) to classify weather conditions from images. Using transfer learning, the models are trained to distinguish between five different weather types: Cloudy, Foggy, Rainy, Snowy, and Sunny.

## 📌 Project Overview

**Goal:** Build an accurate image classifier for weather conditions.  
**Dataset:** 5-Class Weather Status Image Classification from Kaggle.  
**Approach:** Transfer Learning using pre-trained weights (ImageNet) with data augmentation and fine-tuning strategies.  
**Frameworks:** PyTorch (ResNet50) and TensorFlow/Keras (VGG19, InceptionV1).

## 📂 Dataset Details

The dataset consists of images categorized into 5 classes:

☁️ Cloudy  
🌫️ Foggy  
🌧️ Rainy  
❄️ Snowy  
☀️ Sunny  

Pre-processing includes resizing (224x224), normalization, and data splitting (Train/Val/Test).

## 🛠️ Models & Architectures

The project explores multiple architectures:

### ResNet50 (PyTorch)
Strategy: Weights pre-trained on ImageNet.  
Training: Feature extraction (frozen backbone) followed by fine-tuning layer4 and the fully connected head.  
Optimizer: Adam with learning rate scheduling.  
Performance: Achieved ~81% validation accuracy (initial training).

### VGG19 (TensorFlow/Keras)
Deep CNN architecture known for its simplicity and depth (19 layers).  
Used for baseline comparison.

### InceptionV1 (GoogLeNet) & MobileNet
Explored for efficiency and multi-scale feature extraction.

## ⚙️ Methodology

**Data Augmentation:** To tackle class imbalance and improve generalization, techniques such as Random Horizontal Flip, Rotation, Color Jitter (Brightness/Contrast), and Random Crops were applied.

**Transfer Learning:**
- Stage 1: Freeze the feature extractor backbone (e.g., ResNet50) and train only the custom classification head.
- Stage 2: "Fine-tune" by unfreezing the last convolutional block (e.g., layer4) and retraining with a lower learning rate (1e-4) to adapt features to the weather domain.

**Evaluation:** Models are evaluated using Accuracy, Confusion Matrices, and Classification Reports (Precision, Recall, F1-Score).
