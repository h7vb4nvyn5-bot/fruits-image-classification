# Fruit Image Classification with SVM

A machine learning project for multi-class fruit image classification using handcrafted image features, PCA dimensionality reduction, and Support Vector Machine (SVM).

The project explores a traditional machine learning pipeline for image classification without using deep learning frameworks.

## Project Overview

This project aims to classify fruit images into multiple categories by extracting color and texture features from images and training an SVM classifier.

The complete pipeline includes:

**Image Preprocessing → Feature Extraction → Feature Standardization → PCA → SVM → Model Evaluation**

The dataset contains **583 fruit images from 7 categories**.

## Methods

### 1. Image Feature Extraction

Several handcrafted image features are extracted from each image.

**Color Features**

Color information is extracted from RGB/HSV representations to describe the overall color distribution of each fruit image.

**LBP (Local Binary Pattern)**

LBP features are used to capture local texture patterns in fruit surfaces.

**GLCM (Gray-Level Co-occurrence Matrix)**

GLCM features describe spatial relationships between pixel intensities and provide additional texture information.

### 2. Feature Preprocessing

The extracted features are standardized before model training to reduce the influence of different feature scales.

### 3. PCA Dimensionality Reduction

Principal Component Analysis (PCA) is applied to reduce feature dimensionality while preserving the most important information.

This helps reduce redundant features and improves the efficiency of model training.

### 4. SVM Classification

A Support Vector Machine with an RBF kernel is used for multi-class fruit classification.

Hyperparameters are optimized using:

- `GridSearchCV`
- 5-fold `StratifiedKFold`
- Macro F1 score (`f1_macro`)

Class weights are balanced during training to reduce the influence of class imbalance.

## Model Training

The dataset is divided into training and testing sets using an **80/20 stratified split**.

The main hyperparameters explored include:

- `C`
- `gamma`

The best parameter combination obtained during experimentation was:

```text
C = 10
gamma = 0.001
```

## Evaluation

The model is evaluated using multiple classification metrics:

- Accuracy
- Precision
- Recall
- F1-score
- Macro F1-score

A classification report is used to analyze the model's performance across different fruit categories.

## Tech Stack

- Python
- NumPy
- OpenCV
- scikit-image
- scikit-learn
- Matplotlib
- Jupyter Notebook

## Project Structure

```text
fruit-image-classification/
│
├── code_new.ipynb
└── README.md
```

`code_new.ipynb` contains the complete workflow, including image preprocessing, feature extraction, model training, hyperparameter tuning, and evaluation.

## Key Learning Outcomes

Through this project, I practiced:

- Image preprocessing with Python
- Handcrafted image feature extraction
- Feature standardization and dimensionality reduction
- Multi-class classification using SVM
- Hyperparameter tuning with cross-validation
- Model evaluation using multiple classification metrics
- Building a complete traditional machine learning workflow

## Notes

This project focuses on **traditional machine learning methods rather than deep learning**. The main goal is to explore how handcrafted color and texture features can be combined with PCA and SVM for multi-class image classification.
