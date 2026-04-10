# Driver Behavior Detection Enhanced

This project improves a baseline driver behavior detection model using a ResNet-based architecture.  
Various experiments were conducted to enhance performance through input design, model architecture, and training strategies.

---

## Overview
The project focuses on classifying driver behaviors from image data.  
Unlike a simple baseline approach, this work explores multiple design choices and analyzes their impact on performance.

---

## Method

### ROI-based Multi-Input Strategy
- Input regions: Full Image, Head, Hand
- Initially included additional regions, but removed due to overfitting and inefficiency
- Final design uses only informative regions to improve performance

### Data Augmentation
- Color-based augmentation (brightness, contrast)
- Spatial transformations applied carefully
- Flip augmentation was avoided due to label inconsistency

### Model Architecture
- ResNet backbone for feature extraction
- Experiments with attention-based structures:
  - SE Block
  - Tri-View Gated Head
- Independent branch design improved representation power

---

## Improvements

Key improvements over baseline:

- Removal of unnecessary ROI inputs to reduce overfitting
- Better feature focus on head region for critical class separation
- Stabilized training through augmentation tuning
- Use of CutMix to improve generalization

---

## Experiments

### Failure Case Analysis
- Confusion between "Safe Driving (c0)" and "Talking to Passenger (c9)"
- Similar head pose caused misclassification

### Augmentation Strategy
- Mixup degraded performance due to loss of clear features
- CutMix improved generalization and reduced overfitting

### Model Design Experiments
- Attention-based structures improved feature utilization
- Overly complex models led to overfitting in small datasets

---

## Results
- Final Kaggle Score: 0.206
- Best Validation Loss: 0.16

---

## Key Contributions
- Designed ROI-based multi-input structure (Full, Head, Hand)
- Reduced overfitting by removing less informative regions
- Improved generalization using CutMix augmentation
- Conducted extensive experiments on model architecture and training strategies

---
## Experimental Insights
- Head region is critical for distinguishing confusing classes (c0 vs c9)
- Overly complex architectures led to overfitting on limited data
- Data augmentation strategy significantly impacted performance

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
