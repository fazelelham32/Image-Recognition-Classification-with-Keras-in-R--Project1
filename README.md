# Image Recognition & Classification with Keras in R | TensorFlow

An image classification project implemented in **R** using **Keras**, **TensorFlow**, and **EBImage**. The project demonstrates the complete image classification workflow, including image preprocessing, neural network training, model evaluation, prediction, probability estimation, and confusion matrix analysis for binary image classification.

---

# Project Overview

This project develops a deep learning image classification model that distinguishes between two object categories:

- Airplanes
- Cars

The implementation covers the complete pipeline from loading raw images to evaluating classification performance using a fully connected neural network built with Keras.

---

# Project Objective

The objective of this project is to build a binary image classifier capable of recognizing airplane and car images after preprocessing and feature preparation using R and TensorFlow.

---

# Dataset

The dataset consists of:

| Category | Images |
|----------|--------|
| Airplanes | 6 |
| Cars | 6 |

Total images:

```
12 Images
```

Image filenames:

```
p1.jpg - p6.jpg
c1.jpg - c6.jpg
```

---

# Data Split

The dataset is divided into training and testing subsets.

Training:

- Plane Images: p1 – p5
- Car Images: c1 – c5

Testing:

- Plane Image: p6
- Car Image: c6

Dataset summary:

| Dataset | Images |
|----------|--------|
| Training | 10 |
| Testing | 2 |

---

# Software Stack

The project is implemented using:

- R
- RStudio
- Keras
- TensorFlow
- EBImage

TensorFlow is used as the backend for the Keras deep learning framework.

---

# Required Packages

The implementation requires:

- EBImage
- Keras

EBImage is used for image loading and preprocessing.

Keras is used for neural network construction and training.

---

# Image Processing Pipeline

The preprocessing workflow consists of:

```
Image Loading
      │
      ▼
Image Exploration
      │
      ▼
Image Resize
      │
      ▼
Image Reshape
      │
      ▼
Training Matrix
      │
      ▼
One-Hot Encoding
```

---

# Image Exploration

Before training, every image is inspected using:

- Image visualization
- Image dimensions
- Summary statistics
- Pixel intensity histogram

The project converts every image into numerical pixel values for neural network processing.

---

# Image Resizing

Original images have different dimensions.

To ensure consistent input size, every image is resized to:

```
28 × 28 × 3
```

After resizing, all images have identical dimensions.

---

# Image Reshaping

Each resized RGB image is transformed into a one-dimensional feature vector.

Input dimension:

```
28 × 28 × 3 = 2352 Features
```

Each image becomes a feature vector containing 2352 input values.

---

# Label Encoding

Binary labels are assigned as follows:

| Class | Label |
|--------|-------|
| Airplane | 0 |
| Car | 1 |

The labels are converted into categorical vectors using One-Hot Encoding before model training.

---

# Neural Network Architecture

The project implements a Sequential Neural Network.

Model architecture:

| Layer | Configuration |
|--------|---------------|
| Input | 2352 Features |
| Dense Layer 1 | 256 Neurons (ReLU) |
| Dense Layer 2 | 128 Neurons (ReLU) |
| Output Layer | 2 Neurons (Softmax) |

---

# Model Compilation

Training configuration:

| Component | Value |
|-----------|-------|
| Loss Function | Binary Crossentropy |
| Optimizer | RMSProp |
| Evaluation Metric | Accuracy |

---

# Training Configuration

Model training parameters:

| Parameter | Value |
|-----------|-------|
| Epochs | 30 |
| Batch Size | 32 |
| Validation Split | 20% |

Training uses:

- 80% of the training data for learning
- 20% for validation

---

# Training Workflow

```
Training Images
        │
        ▼
Resize Images
        │
        ▼
Flatten Images
        │
        ▼
One-Hot Encoding
        │
        ▼
Sequential Neural Network
        │
        ▼
Training
        │
        ▼
Validation
```

---

# Training Performance

Training history is monitored using:

- Training Loss
- Validation Loss
- Training Accuracy
- Validation Accuracy

Loss decreases during training while accuracy improves and stabilizes after several epochs.

---

# Model Evaluation

The trained model is evaluated on both:

- Training Dataset
- Testing Dataset

Evaluation metrics include:

- Loss
- Accuracy

---

# Training Results

Training performance:

| Metric | Value |
|--------|-------|
| Loss | 0.24 |
| Accuracy | 90% |

Training summary:

- Correct Predictions: 9
- Incorrect Predictions: 1

---

# Training Confusion Matrix

Training results indicate:

- Five airplane images correctly classified.
- Four car images correctly classified.
- One car image misclassified as an airplane.

---

# Probability Prediction

The model computes prediction probabilities for each class.

For every image, the classifier returns:

- Probability of belonging to the airplane class.
- Probability of belonging to the car class.

These probabilities are used to determine the predicted class.

---

# Testing Results

Testing dataset contains:

- One airplane image
- One car image

Performance:

| Metric | Value |
|--------|-------|
| Loss | 0.009 |
| Accuracy | 100% |

Both testing images are classified correctly.

---

# Test Confusion Matrix

Testing results show:

- Airplane correctly classified.
- Car correctly classified.

No misclassification occurs on the testing dataset.

---

# Prediction Pipeline

```
Input Image
      │
      ▼
EBImage
      │
      ▼
Resize
      │
      ▼
Flatten
      │
      ▼
Sequential Neural Network
      │
      ▼
Softmax Output
      │
      ▼
Prediction
      │
      ▼
Probability Estimation
      │
      ▼
Confusion Matrix
```

---

# Project Components

| Component | Purpose |
|-----------|---------|
| EBImage | Image loading and preprocessing |
| TensorFlow | Deep learning backend |
| Keras | Neural network implementation |
| Sequential Model | Binary image classifier |
| ReLU | Hidden layer activation |
| Softmax | Output classification |
| One-Hot Encoding | Label preparation |
| Binary Crossentropy | Loss computation |
| RMSProp | Model optimization |
| Confusion Matrix | Classification evaluation |

---

# Final Outcome

This project demonstrates a complete image classification workflow in R using Keras and TensorFlow. Images are loaded, resized, reshaped, encoded, and classified using a fully connected neural network. The trained model achieves **90% training accuracy** and **100% testing accuracy** on the provided airplane and car image dataset while providing probability-based predictions and confusion matrix evaluation.
