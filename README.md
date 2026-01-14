# Intel Image Classification

## Project Overview

This notebook implements Deep Learning models to automatically classify natural scenes into 6 categories (buildings, forest, glacier, mountain, sea, street) using the Intel Image Classification dataset. The project compares three CNN architectures to identify the optimal balance between accuracy and computational efficiency.

**Dataset Source:** [Kaggle - Intel Image Classification](https://www.kaggle.com/datasets/puneet6060/intel-image-classification)

## Algorithms Tested

- **Base CNN** (simple 3-layer architecture)
- **Intermediate CNN** (with Batch Normalization)
- **Transfer Learning** (MobileNetV2 pre-trained on ImageNet)

## Methodology

After comprehensive Exploratory Data Analysis, data augmentation, and preprocessing, three CNN architectures are trained and evaluated using:

- Training/validation accuracy curves
- Confusion matrix analysis
- Per-class precision/recall metrics
- Confidence score distribution on unseen data

The optimal model is **Transfer Learning (MobileNetV2)** with **K=3 convolutional blocks**, achieving **89.97% test accuracy**.

## Key Features

- Data augmentation (rotation, zoom, flip) for improved generalization
- Batch Normalization for training stability
- Early Stopping and Learning Rate Reduction callbacks
- Confusion matrix analysis identifying main misclassifications
- Production simulation on unlabeled prediction set
- Confidence-based filtering strategy for deployment

## Results

Transfer Learning (MobileNetV2) is selected as the optimal solution, achieving **89.97% accuracy** and **0.283 loss** on the test set. While the Intermediate CNN shows competitive performance (87.83%), Transfer Learning is chosen for its superior accuracy, leveraging ImageNet pre-trained features. The analysis identifies glacier↔mountain and street↔buildings as the main confusion pairs, with per-class accuracy ranging from 82.4% (glacier) to 96.2% (sea).

## Dataset Variables

| Category | Description |
|----------|-------------|
| `buildings` | Architectural structures and buildings |
| `forest` | Dense vegetation and forest areas |
| `glacier` | Glacial landscapes and ice formations |
| `mountain` | Mountain ranges and peaks |
| `sea` | Ocean, sea, and coastal views |
| `street` | Urban street scenes |

**Dataset size:** ~25,000 images (150×150 RGB), resized to 96×96 for efficiency

---

*This notebook is part of the Coursera IBM Machine Learning Professional Certificate program.*
