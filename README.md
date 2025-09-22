🌱 Robust Plant Disease Classification Using Transfer Learning and Explainable AI

This repository contains the implementation of a plant disease classification system using Transfer Learning and Explainable AI (XAI) techniques. The project focuses on helping farmers by not only predicting plant diseases from leaf images but also generating simple, farmer-friendly explanations using Grad-CAM visualizations.

🌍 Introduction

Plant diseases threaten food security by reducing crop yields and quality. Traditional disease detection is time-consuming and often requires expert knowledge. This project leverages deep learning with transfer learning to classify plant diseases automatically and integrates XAI techniques to make the results interpretable for farmers.

Key Features:

Automated plant disease classification.

Models trained with DenseNet121 and ResNet50.

Grad-CAM-based visual explanations of predictions.

Generates farmer-friendly textual explanations.

📊 Dataset

Source: New Plant Diseases Dataset (Augmented) on Kaggle

Size: 87,867 images across 38 classes.

Split:

Training: 52,720

Validation: 17,573

Test: 17,574

🔄 Pipeline Overview

Data Preparation

Image loading & labeling

Stratified train/val/test split

Data augmentation for training

Model Training

Transfer learning with pre-trained backbones

Fine-tuning DenseNet121 and ResNet50

EarlyStopping & ModelCheckpoint callbacks

Evaluation

Metrics: Accuracy, Loss

DenseNet121 achieved ~92.4% test accuracy

Explainability

Grad-CAM visualizations

Farmer-friendly explanations

🧠 Models Used

DenseNet121 ✅ (best performing, 92.4% accuracy)

ResNet50 (lower accuracy, ~29%)

Models initially considered: EfficientNetB4, MobileNetV2, DenseNet121, ResNet50 → Final training used DenseNet121 & ResNet50.

📈 Results
Model	Test Accuracy	Test Loss
DenseNet121	92.4%	0.2396
ResNet50	29.2%	2.7103

🔍 Explainable AI (XAI)

We implemented Grad-CAM to visualize important regions of input leaves that influenced the model’s decision.
Additionally, a function predict_and_explain(image) provides:

Predicted disease

Confidence score

Simple, farmer-friendly explanation

Example Output:

{
  "prediction": "Tomato___Early_blight",
  "confidence": "100%",
  "explanation": "Your plant is likely affected by Tomato Early Blight. I am 100% sure. This disease often shows as spots or patches on the leaves. You might want to look for specific signs."
}
