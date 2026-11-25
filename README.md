# Neem Leaf Disease Classification Using CNN

A Deep Learning project for classifying Neem (*Azadirachta indica*) leaf images into three categories using a Custom Convolutional Neural Network (CNN). This project investigates the impact of Data Augmentation on CNN classification performance.

## Project Overview

Neem leaves can be affected by different conditions and diseases. This project develops a CNN-based image classification model to identify three Neem leaf categories:

- **Chlorotic**
- **Disease**
- **Healthy**

Two CNN experiments are conducted:
1. Baseline CNN without Data Augmentation.
2. CNN with Data Augmentation.

The objective is to compare their performance and evaluate whether Data Augmentation improves the model's generalization ability.

## Dataset

**Dataset Name:** Azadirachta Indica Leaf Disease and Health Classification Dataset

**Source:** [Mendeley Data – Neem Leaf Dataset](https://data.mendeley.com/datasets/7fh5k2kvx6/1)

The dataset contains 3,900 images divided into three classes.

| Dataset Split | Images |
|---|---:|
| Training | 3,000 |
| Validation | 450 |
| Testing | 450 |
| **Total** | **3,900** |

Each class contains 1,000 training images, 150 validation images, and 150 testing images.

## CNN Architecture

A custom CNN was implemented from scratch using PyTorch.

The architecture consists of:

- Four Convolutional Layers
- ReLU Activation Functions
- Max Pooling Layers
- Flatten Layer
- Fully Connected Layers
- Dropout (0.5)
- Output Layer with 3 classes

### Model Configuration

| Parameter | Value |
|---|---|
| Framework | PyTorch |
| Input Image Size | 224 × 224 |
| Batch Size | 32 |
| Epochs | 25 |
| Optimizer | Adam |
| Learning Rate | 0.001 |
| Loss Function | CrossEntropyLoss |
| Hardware | NVIDIA Tesla T4 GPU |

## Data Augmentation

Data Augmentation was applied to the training images to improve model generalization.

The following techniques were used:

- Random Horizontal Flip
- Random Rotation (±10°)
- Color Jitter (Brightness, Contrast, Saturation)
- Image Padding and Resizing

No random augmentation was applied to validation or test images.

## Experimental Results

Two experiments were conducted to evaluate the effect of Data Augmentation.

### Baseline CNN (Without Data Augmentation)

| Metric | Result |
|---|---:|
| Final Training Accuracy | 97.40% |
| Best Validation Accuracy | 89.11% |
| Test Accuracy | **87.33%** |
| Lowest Validation Loss | 0.2947 |

### CNN with Data Augmentation

| Metric | Result |
|---|---:|
| Final Training Accuracy | 89.50% |
| Best Validation Accuracy | 93.33% |
| Test Accuracy | **92.89%** |
| Lowest Validation Loss | 0.1608 |

### Performance Comparison

| Metric | Baseline CNN | CNN with Augmentation |
|---|---:|---:|
| Training Accuracy | 97.40% | 89.50% |
| Validation Accuracy | 89.11% | 93.33% |
| Test Accuracy | 87.33% | 92.89% |

**Test Accuracy Improvement: +5.56 Percentage Points**

The augmented CNN achieved better validation and testing performance than the baseline model.

## Classification Report

### Baseline CNN

| Class | Precision | Recall | F1-Score |
|---|---:|---:|---:|
| Chlorotic | 0.83 | 0.85 | 0.84 |
| Disease | 0.84 | 0.79 | 0.81 |
| Healthy | 0.95 | 0.98 | 0.97 |

### CNN with Data Augmentation

| Class | Precision | Recall | F1-Score |
|---|---:|---:|---:|
| Chlorotic | 0.92 | 0.92 | 0.92 |
| Disease | 0.90 | 0.90 | 0.90 |
| Healthy | 0.97 | 0.97 | 0.97 |

## Conclusion

The experimental results demonstrate that Data Augmentation improved the performance of the custom CNN model.

The baseline CNN achieved 87.33% test accuracy, while the augmented CNN achieved 92.89%, representing an improvement of 5.56 percentage points.

Although the augmented model achieved lower training accuracy, it performed better on unseen validation and test images. This indicates improved generalization and suggests that Data Augmentation helped reduce overfitting.

## Technologies Used

- Python
- PyTorch
- NumPy
- Matplotlib
- Scikit-learn
- Google Colab
- CUDA / NVIDIA Tesla T4 GPU

## How to Run

1. Clone this repository:

   ```bash
   git clone https://github.com/Ibrar5456/Neem-Leaf-Disease-Classification-CNN.git
   ```

2. Install the required libraries:

   ```bash
   pip install torch torchvision numpy matplotlib scikit-learn pillow
   ```

3. Download the dataset from [Mendeley Data](https://data.mendeley.com/datasets/7fh5k2kvx6/1).

4. Upload the dataset to your Google Drive or configure the dataset path in the notebook.

5. Open `Neem_Leaf_CNN_With_Data_Augmentation.ipynb` in Google Colab.

6. Run the notebook cells sequentially.

## Repository Contents

- `Neem_Leaf_CNN_With_Data_Augmentation.ipynb` – Complete implementation, training, evaluation, and comparison experiments.
- `README.md` – Project documentation.

## Author

**Md. Ibrar Mahmud Rasin**

BSc in Computer Science and Engineering  
American International University-Bangladesh (AIUB)
