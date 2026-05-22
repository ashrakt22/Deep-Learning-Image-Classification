# Image Classification on CIFAR-10 Dataset
## Deep Learning Project

---

## Project Overview
This project implements a Convolutional Neural Network (CNN) to classify images from the CIFAR-10 dataset into 10 categories:

✈️ Airplane | 🚗 Automobile | 🐦 Bird | 🐱 Cat | 🦌 Deer | 🐶 Dog | 🐸 Frog | 🐴 Horse | 🚢 Ship | 🚛 Truck

---
## Problem Description
Image classification is the task of assigning a label to an input image. 

In this project, the goal is to correctly classify images into one of 
10 categories: airplane, automobile, bird, cat, deer, dog, frog, horse, 
ship, and truck.

This is a multi-class classification problem where:
- Input  → a 32x32 RGB image
- Output → one of 10 class labels

The challenge is building a model that generalizes well to unseen images,
not just the ones it was trained on.
---
## Dataset
- **Name:** CIFAR-10
- **Source:** https://www.cs.toronto.edu/~kriz/cifar.html
- **Train size:** 50,000 images
- **Test size:** 10,000 images
- **Image size:** 32x32 pixels (RGB)
- **Classes:** 10

---

## Model Architecture
A CNN model with the following structure:
- 3 Convolutional Blocks (Conv2d → BatchNorm → ReLU → MaxPool)
- AdaptiveAvgPool2d
- Flatten
- Fully Connected Layers with Dropout (0.5)
- Output: 10 classes

---

## Preprocessing
- Random Horizontal Flip (Data Augmentation)
- Random Crop (Data Augmentation)
- Normalization (mean=0.5, std=0.5)

---

## Experiments

| Experiment | Optimizer | Learning Rate | Test Accuracy | Test Loss |
|------------|-----------|---------------|---------------|-----------|
| Experiment 1 | Adam | 0.001 | 77.26% | 0.6717 |
| Experiment 2 | SGD  | 0.010 | 77.52% | 0.6538 |

---

## Training Progress

### Experiment 1 — Adam (lr=0.001)
| Epoch | Train Loss | Train Acc | Val Loss | Val Acc |
|-------|-----------|-----------|----------|---------|
| 1  | 1.6127 | 39.93% | 1.1932 | 56.97% |
| 2  | 1.3135 | 52.19% | 1.0398 | 62.83% |
| 3  | 1.1913 | 57.37% | 0.9275 | 66.97% |
| 4  | 1.1017 | 60.76% | 0.8455 | 69.79% |
| 5  | 1.0449 | 63.36% | 0.7989 | 71.57% |
| 6  | 0.9866 | 65.67% | 0.7627 | 73.08% |
| 7  | 0.9415 | 67.44% | 0.7202 | 74.88% |
| 8  | 0.9015 | 69.03% | 0.6767 | 76.35% |
| 9  | 0.8578 | 70.67% | 0.6682 | 76.79% |
| 10 | 0.8271 | 71.74% | 0.6717 | 77.26% |

### Experiment 2 — SGD (lr=0.01, momentum=0.9)
| Epoch | Train Loss | Train Acc | Val Loss | Val Acc |
|-------|-----------|-----------|----------|---------|
| 1  | 1.8440 | 30.86% | 1.4598 | 46.54% |
| 2  | 1.5053 | 44.56% | 1.0868 | 61.20% |
| 3  | 1.2441 | 55.68% | 1.0356 | 63.06% |
| 4  | 1.0888 | 61.79% | 0.8818 | 68.39% |
| 5  | 0.9892 | 65.71% | 0.8083 | 71.05% |
| 6  | 0.9190 | 68.37% | 0.7305 | 74.24% |
| 7  | 0.8617 | 70.36% | 0.7261 | 74.31% |
| 8  | 0.8177 | 72.00% | 0.7075 | 75.69% |
| 9  | 0.7813 | 73.08% | 0.6381 | 78.30% |
| 10 | 0.7470 | 74.29% | 0.6538 | 77.52% |

---

## Results Analysis
- Both experiments achieved ~77% test accuracy after 10 epochs
- **Adam** converged faster — reached 56.97% accuracy at Epoch 1 vs SGD's 46.54%
- **SGD** achieved slightly better final accuracy (77.52% vs 77.26%) and lower loss (0.6538 vs 0.6717)
- Both models show consistent improvement across all 10 epochs with no overfitting

---

## How to Run
1. Open `DL_Project_CIFAR10.ipynb` in Google Colab
2. Run all cells from top to bottom
3. CIFAR-10 will download automatically
4. Results and plots will appear at the end

---

## Requirements
- Python 3.x
- PyTorch
- torchvision
- matplotlib

---

## References
- CIFAR-10 Dataset: https://www.cs.toronto.edu/~kriz/cifar.html
- Practice Sheet 5 - Badr University in Assiut, School of AI & Data Management
