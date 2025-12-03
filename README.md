MelanoSpectra: Hyperspectral Melanoma Stage Detection Using 3D CNN

MelanoSpectra is a deep learning–based system designed to detect melanoma stages using hyperspectral imaging (HSI).  
The project leverages a **3D U-Net–based convolutional architecture** that extracts both spectral and spatial information, enabling more accurate melanoma assessment than traditional RGB imaging.

 Project Overview

Melanoma is one of the most aggressive forms of skin cancer, and early-stage detection is critical for improving patient survival.  
Traditional dermatological imaging methods capture only spatial features, while HSI captures reflectance values across multiple wavelength bands, enabling biochemical-level insights.

MelanoSpectra:

- Processes multi-band HSI image stacks
- Extracts 3D spectral–spatial patches
- Classifies melanoma severity into stages:
  - Stage I
  - Stage II
  - Stage III
  - Stage IV
- Provides an easy-to-use Gradio web interface for inference and testing

 Model Architecture
The system uses a modified 3D U-Net classifier, built with PyTorch:
- Encoder with 3D Convolution + BatchNorm + ReLU
- 3D MaxPooling for hierarchical feature extraction
- Skip connections for spatial retention
- Global Average Pooling and Fully Connected layer for final classification

Dataset Format
The model expects hyperspectral image stacks in either format:

| Input Type | Format | Shape Example |
|-----------|--------|---------------|
| Full HSI Cube | `.bmp` slices loaded into a cube | `(H, W, Bands)` |
| Demo Input | Single `.bmp` image | Auto-expanded to spectral cube for user testing |

Training Summary

- Framework: PyTorch
- Training Environment: Google Colab GPU
- Optimizer: Adam
- Loss Function: CrossEntropyLoss
- Epochs: 5
- Metrics tracked:
  - Accuracy
  - Precision
  - Recall
  - F1-Score


