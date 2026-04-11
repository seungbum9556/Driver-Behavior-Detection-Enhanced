# Driver State Classification (Image-based)

A computer vision model for classifying driver states using CNN-based architectures (ResNet, EfficientNet) with ROI-based multi-input design.

---

## Overview
This project focuses on classifying driver behaviors from image data.
To improve baseline performance, various approaches were explored including ROI-based input design, model architecture optimization, and data augmentation strategies.

---

## Method

### ROI-based Multi-Input Strategy
- Input regions: Full Image, Head, Hand
- Removed less informative regions to reduce overfitting
- Final design focuses on key regions for better feature representation

### Model Architecture
- ResNet backbone for feature extraction
- Applied attention-based techniques:
  - SE Block
  - Tri-View Gated Head
- Independent branch design improved representation power

### Data Augmentation
- Color-based augmentation (brightness, contrast)
- CutMix applied to improve generalization
- Flip augmentation avoided due to label inconsistency

---

## Experiments

### Failure Case Analysis
- Confusion between "Safe Driving (c0)" and "Talking to Passenger (c9)"
- Similar head pose caused misclassification

### Model & Augmentation Insights
- CutMix improved generalization and reduced overfitting
- Mixup degraded performance due to loss of clear features
- Complex architectures led to overfitting on limited data

---

## Results

- **Kaggle Score: 0.206**
- **Best Validation Loss: 0.16**

---

## Key Contributions

- Designed ROI-based multi-input structure (Full, Head, Hand)
- Improved generalization using CutMix augmentation
- Reduced overfitting by removing less informative regions
- Conducted extensive experiments on model architecture

---

## Tech Stack

- Python
- PyTorch
- ResNet
- Computer Vision

---

## How to Run

```bash
pip install -r requirements.txt
python train.py
