# 🦠 Malaria Cell Images Detection using Deep Learning

This project develops and compares several deep learning models to classify microscopic blood smear images into **Parasitized** (malaria-infected) and **Uninfected** categories.

We implement and train:
- A custom **Basic CNN** model
- **ResNet18** (from scratch)
- **EfficientNet-B0** (from scratch)
- **DenseNet121** (from scratch)

The project explores **training from scratch** without transfer learning, focusing on model architecture effectiveness, evaluation metrics, and real-world readiness.

---

## 📖 Project Overview

Malaria remains a major global health issue, especially in under-resourced regions. Early detection through blood smear analysis is critical but labor-intensive and expertise-dependent.  

This project applies deep learning models to automate malaria cell image classification, achieving high accuracy while maintaining transparency through loss/accuracy monitoring and detailed metric evaluations.

---

## 🛠️ Methodology

1. **Dataset**:  
   - Malaria Cell Images Dataset from NIH
   - 2 Classes: **Parasitized** and **Uninfected**
   - Image Size: 224x224 pixels, RGB channels

2. **Data Processing**:  
   - Resize images to 224x224
   - Normalize pixel values to match ImageNet mean and std
   - Split dataset into **Training**, **Validation**, and **Test** sets

3. **Model Training**:
   - All models initialized with random weights (no pretraining).
   - Optimizer: Adam
   - Loss Function: CrossEntropyLoss
   - Learning Rate: 0.001
   - Batch Size: 32
   - Epochs: 10

4. **Evaluation**:
   - Training and Validation Loss/Accuracy per Epoch
   - Final Test Accuracy
   - Confusion Matrix
   - Precision, Recall, F1-Score
   - Precision-Recall Curves (PR Curves)

---

## 🧠 Model Architectures

| Model | Description |
|:------|:------------|
| Basic CNN | Simple custom-built CNN with 4 convolutional blocks and fully connected layers |
| ResNet18 | Residual Network with skip connections for deeper learning |
| EfficientNet-B0 | Scalable and parameter-efficient CNN architecture |
| DenseNet121 | Densely connected convolutional network for feature reuse |

All models were modified for **binary classification** by adjusting the final layers.

---

## 📊 Evaluation Metrics

We evaluated each model on the following metrics:

- **Accuracy** (Training, Validation, Test)
- **Precision**
- **Recall**
- **F1-Score**
- **Confusion Matrix**
- **PR Curves and Average Precision**

This multi-metric evaluation ensures model reliability, especially important in a medical diagnosis context.

---

## 🧪 Results Summary

| Model | Training Accuracy | Validation Accuracy | Test Accuracy |
|:------|:------------------|:--------------------|:--------------|
| Basic CNN | ~94% | ~95% | ~95% |
| ResNet18 | ~93–94% | ~93% | ~93% |
| EfficientNet-B0 | ~95% | ~95% | ~95% |
| DenseNet121 | ~94% | ~94% | ~94% |

- **EfficientNet-B0** slightly outperformed the others overall in validation and test accuracy.
- **Basic CNN** surprisingly performed competitively with deeper models due to sufficient dataset size.
- All models showed minimal overfitting after 10 epochs.

PR Curves showed very high **Average Precision** (~0.95) across all models, confirming excellent precision-recall trade-offs.

---

## ⚙️ How to Use This Project

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/malaria-detection-cnn.git
   cd malaria-detection-cnn
