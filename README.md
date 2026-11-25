# Neem Leaf Disease Classification Using Custom CNN

A Deep Learning project that classifies Neem (*Azadirachta indica*) leaf images into three categories using a Custom Convolutional Neural Network (CNN). This project compares CNN performance before and after applying Data Augmentation.

## 1. Project Overview

Neem leaves may exhibit different health conditions and diseases. This project aims to develop a CNN-based image classification model to identify three Neem leaf categories:

- Chlorotic
- Disease
- Healthy

Two experiments were performed:

1. **Baseline CNN:** Trained without Data Augmentation.
2. **Augmented CNN:** Trained with Data Augmentation.

The main objective is to evaluate how Data Augmentation affects model performance and generalization.

## 2. Dataset Description

**Dataset:** Azadirachta Indica Leaf Disease and Health Classification Dataset

**Source:** [Mendeley Data – Neem Leaf Dataset](https://data.mendeley.com/datasets/7fh5k2kvx6/1)

The dataset contains 3,900 images distributed across three classes.

| Dataset Split | Images |
|---|---:|
| Training | 3,000 |
| Validation | 450 |
| Testing | 450 |
| **Total** | **3,900** |

Each class contains:
- 1,000 training images
- 150 validation images
- 150 testing images

The dataset is balanced across all three classes.

## 3. Image Preprocessing

The notebook applies the following preprocessing steps:

- Converts images into a consistent input size of 224 × 224 pixels.
- Uses image padding to preserve the original aspect ratio.
- Uses black padding where required.
- Converts images into PyTorch tensors.

## 4. CNN Architecture

A custom Convolutional Neural Network was implemented from scratch using PyTorch.

The model consists of:

- Four convolutional layers.
- ReLU activation functions.
- Four Max Pooling layers.
- A Flatten layer.
- A fully connected layer with 512 neurons.
- Dropout with a probability of 0.5.
- An output layer with three neurons.

### Model Configuration

| Parameter | Value |
|---|---|
| Framework | PyTorch |
| Input Size | 224 × 224 |
| Batch Size | 32 |
| Number of Epochs | 25 |
| Optimizer | Adam |
| Learning Rate | 0.001 |
| Loss Function | CrossEntropyLoss |
| Dropout | 0.5 |
| GPU | NVIDIA Tesla T4 |
| Trainable Parameters | 26,080,579 |

## 5. Data Augmentation

Data Augmentation was applied only to the training dataset in the second experiment.

The techniques used were:

- Random Horizontal Flip (p = 0.5)
- Random Rotation (±10 degrees)
- Color Jitter:
  - Brightness: 0.15
  - Contrast: 0.15
  - Saturation: 0.10

Validation and test images were processed without random augmentation.

## 6. Experimental Results

Both models were trained for 25 epochs and evaluated using the same test dataset containing 450 images.

### 6.1 Baseline CNN (Without Data Augmentation)

| Metric | Result |
|---|---:|
| Final Training Accuracy | 97.40% |
| Best Validation Accuracy | 89.11% |
| Test Accuracy | **87.33%** |
| Lowest Validation Loss | 0.2947 |
| Epoch with Lowest Validation Loss | 14 |

### 6.2 CNN with Data Augmentation

| Metric | Result |
|---|---:|
| Final Training Accuracy | 89.50% |
| Best Validation Accuracy | 93.33% |
| Test Accuracy | **92.89%** |
| Lowest Validation Loss | 0.1608 |
| Epoch with Lowest Validation Loss | 23 |

### 6.3 Performance Comparison

| Metric | Baseline CNN | CNN with Augmentation |
|---|---:|---:|
| Final Training Accuracy | 97.40% | 89.50% |
| Best Validation Accuracy | 89.11% | 93.33% |
| Test Accuracy | 87.33% | 92.89% |

**Test Accuracy Improvement: 5.56 Percentage Points**

The CNN with Data Augmentation achieved better validation and test performance than the baseline CNN.

## 7. Classification Report

### 7.1 Baseline CNN

| Class | Precision | Recall | F1-Score | Support |
|---|---:|---:|---:|---:|
| Chlorotic | 0.83 | 0.85 | 0.84 | 150 |
| Disease | 0.84 | 0.79 | 0.81 | 150 |
| Healthy | 0.95 | 0.98 | 0.97 | 150 |
| **Macro Average** | **0.87** | **0.87** | **0.87** | **450** |
| **Weighted Average** | **0.87** | **0.87** | **0.87** | **450** |

### 7.2 CNN with Data Augmentation

| Class | Precision | Recall | F1-Score | Support |
|---|---:|---:|---:|---:|
| Chlorotic | 0.92 | 0.92 | 0.92 | 150 |
| Disease | 0.90 | 0.90 | 0.90 | 150 |
| Healthy | 0.97 | 0.97 | 0.97 | 150 |
| **Macro Average** | **0.93** | **0.93** | **0.93** | **450** |
| **Weighted Average** | **0.93** | **0.93** | **0.93** | **450** |

## 8. Conclusion

The experimental results demonstrate that Data Augmentation improved the classification performance of the custom CNN model.

The baseline CNN achieved 87.33% test accuracy, whereas the augmented CNN achieved 92.89% test accuracy, representing an improvement of 5.56 percentage points.

Although the augmented model achieved lower training accuracy, it performed better on validation and unseen test images. This suggests improved generalization and reduced overfitting.

Therefore, Data Augmentation proved beneficial for this Neem Leaf Classification task.

## 9. Technologies Used

- Python
- PyTorch
- Torchvision
- NumPy
- Matplotlib
- Scikit-learn
- Pillow (PIL)
- Google Colab
- CUDA

## 10. How to Run the Project

1. Clone the repository:

   ```bash
   git clone https://github.com/Ibrar5456/Neem-Leaf-Disease-Classification-CNN.git
   ```

2. Install the required libraries:

   ```bash
   pip install torch torchvision numpy matplotlib scikit-learn pillow
   ```

3. Download the dataset from [Mendeley Data](https://data.mendeley.com/datasets/7fh5k2kvx6/1).

4. Extract the dataset and organize it into Train, Validation, and Test folders, each containing the three class folders.

5. Open the notebook in Google Colab.

6. Configure the dataset path according to your environment.

7. Run the notebook cells sequentially.

## 11. Repository Structure

```text
Neem-Leaf-Disease-Classification-CNN/
│
├── Neem_Leaf_CNN_With_Data_Augmentation.ipynb
├── README.md
│
├── Models/
│   ├── best_cnn_model_baseline.pth
│   └── best_cnn_model_augmented.pth
│
└── Results/
    ├── training_accuracy.png
    ├── training_loss.png
    ├── confusion_matrix_baseline.png
    ├── confusion_matrix_augmented.png
    └── accuracy_comparison.png
```

## 12. Author

**Md. Ibrar Mahmud Rasin**

BSc in Computer Science and Engineering  
American International University-Bangladesh (AIUB)
