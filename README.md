# Weather Image Classification with Deep Learning

This project implements and compares various Deep Learning architectures (ResNet, VGG19, InceptionV1, MobileNet) to classify weather conditions from images. Using transfer learning, the models are trained to distinguish between five different weather types: Cloudy, Foggy, Rainy, Snowy, and Sunny.

## 📌 Project Overview

**Goal:** Build an accurate image classifier for weather conditions.  
**Dataset:** 5-Class Weather Status Image Classification from Kaggle.  
**Approach:** Transfer Learning using pre-trained weights (ImageNet) with data augmentation and fine-tuning strategies.  

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

### ResNet (PyTorch)

### VGG-19 (TensorFlow/Keras)

### Inception-V1 (GoogLeNet)

### MobileNet (TensorFlow/Keras)

## ⚙️ Methodology

**Data Augmentation:** To tackle class imbalance and improve generalization, techniques such as Random Horizontal Flip, Rotation, Color Jitter (Brightness/Contrast), and Random Crops were applied.

**Transfer Learning:**
- Stage 1: Freeze the feature extractor backbone (e.g., ResNet) and train only the custom classification head.
- Stage 2: "Fine-tune" by unfreezing the last convolutional block (e.g., layer4) and retraining with a lower learning rate (1e-4) to adapt features to the weather domain.

**Evaluation:** Models are evaluated using Accuracy, Confusion Matrices, and Classification Reports (Precision, Recall, F1-Score).
