# MSR_CNN_project
# Comparative Analysis of Optimizer Efficiency for CNN Training on the MNIST Dataset
### Evaluating Adaptive and Non-Adaptive Algorithms in a 3-Layer Architecture

![Python](https://img.shields.io/badge/Python-3.11.9-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)
![Keras](https://img.shields.io/badge/Keras-Enabled-red.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

## Project Overview
This repository contains the research and implementation of a Comparative Analysis of six different optimization techniques used to train a **Convolutional Neural Network (CNN)** on the **MNIST dataset**. The study focuses on the trade-offs between convergence speed, validation accuracy, and generalization capabilities of adaptive and non-adaptive optimizers.

## Network Architecture
The model uses a standardized 3-layer CNN architecture to ensure a fair comparison:
- **Convolutional Base:** 32, 64, and 128 filters ($3 \times 3$ kernels) with ReLU activation.
- **Pooling:** Max Pooling ($2 \times 2$) for spatial downsampling.
- **Regularization:** Dropout (0.25) to prevent overfitting.
- **Total Trainable Parameters:** **167,114**.



---

## Optimizers Evaluated
1. **SGD (Stochastic Gradient Descent):** The baseline non-adaptive method.
2. **SGD Momentum:** Adds "velocity" to overcome local minima.
3. **Adagrad:** Adaptive learning rate based on parameter frequency.
4. **RMSprop:** Normalizes gradients using a moving average of squared gradients.
5. **Adam:** Combines Momentum and RMSprop logic.
6. **AdamW:** Features **Decoupled Weight Decay** for superior generalization.

---

## Key Results
| Optimizer | Validation Accuracy (%) | Validation Loss | Training Time (s) |
| :--- | :---: | :---: | :---: |
| **AdamW** | **99.35%** | **0.0263** | 266.79 |
| **Adam** | 99.34% | 0.0298 | 289.55 |
| **RMSprop** | 99.22% | 0.0396 | 274.25 |
| **SGD Momentum** | 99.13% | **0.0232** | 228.84 |
| **Adagrad** | 98.66% | 0.0412 | 258.12 |
| **SGD** | 98.50% | 0.0451 | **215.79** |



### Conclusions
- **AdamW** emerged as the most efficient optimizer, balancing high precision (99.35%) with faster convergence than standard Adam.
- **Decoupled Weight Decay** in AdamW successfully reduced generalization error.
- **Adaptive methods** reached >98% accuracy after the very first epoch, significantly outperforming static SGD in early-stage training.
