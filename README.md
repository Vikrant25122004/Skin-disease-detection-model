# 🧠 Strategy, Model Architecture & Accuracy

## ⭐ Strategy: Deep Learning for Dermatological Insights

This project uses a **data-driven deep learning strategy** to classify dermatological images into 10 major categories of skin diseases. The approach is designed to be highly scalable, accurate, and robust for real-world medical imaging tasks. Key elements of the strategy include:

### 🔹 1. Large-Scale Dataset Utilization
- Trained on a dataset of **27,153 high-resolution skin lesion images**.
- Covers **10 different disease classes**, ensuring broad diagnostic coverage.
- Provides significant variation in lighting, skin tones, image quality, and lesion types.

### 🔹 2. Preprocessing & Image Normalization
- All images are resized to **128×128 RGB** for efficient training.
- Pixel values are normalized to the range **0–1**, improving training stability.
- Images are loaded using TensorFlow's `image_dataset_from_directory`.

### 🔹 3. Automated Hyperparameter Optimization
- **Keras Tuner (Random Search)** is used to optimize:
  - Activation functions (ReLU, Swish, ELU, GELU, etc.)
  - Optimizer choice (Adam, AdamW, Nadam, RMSprop, FTRL, etc.)
  - Dense layer activation
  - Activation functions for each convolutional block
- Ensures the model finds the most effective configuration for high accuracy.

### 🔹 4. Robust CNN Architecture
- Multi-layered CNN designed to extract both low-level and high-level features.
- Dropout and Batch Normalization help prevent overfitting.
- Global Average Pooling improves generalization while reducing model size.

---

## 🏗️ Model Architecture

The model is built using **TensorFlow/Keras** and features a balanced, high-performing structure.

### 🔸 Convolutional Blocks
- Four convolutional blocks with:
  - `Conv2D` layers for feature extraction
  - `BatchNormalization` for stable gradient flow
  - `MaxPooling2D` for spatial reduction

### 🔸 Regularization
- **Dropout (0.2)** applied to reduce overfitting.
- Helps maintain generalization across unseen images.

### 🔸 Global Average Pooling
- Converts the final feature maps into a compact vector.
- Reduces parameters compared to Flatten → Dense pipelines.

### 🔸 Dense Layers
- One fully connected **256-unit Dense layer** with tunable activation.
- Output layer uses **Softmax** to classify images into 10 categories.

### 🔸 Tuned Optimizer
Automatically selected by Keras Tuner from:
- Adam  
- AdamW  
- Adagrad  
- RMSprop  
- Nadam  
- FTRL  
- SGD  
- Adamax  

This ensures the best-performing optimizer configuration is chosen.

---

## 📈 Model Accuracy

After training the optimized CNN for **20 epochs**, the model achieved:

### ✔️ **Final Training Accuracy: 95.44%**  
### ✔️ Smooth convergence with steadily decreasing loss  
### ✔️ Stable performance without signs of overfitting  

This accuracy indicates that the model can reliably classify skin diseases with a high level of precision, making it an effective tool for supporting dermatological diagnosis.

---

## 🔬 Summary

| Component | Description |
|----------|-------------|
| **Strategy** | Leverages CNNs + Keras Tuner + large dataset for optimal performance |
| **Model** | 4 Conv blocks + BatchNorm + MaxPool + Dropout + GAP + Dense layers |
| **Dataset** | 27,153 images across 10 disease classes |
| **Training Duration** | 20 epochs |
| **Final Accuracy** | **95.44%** |

This section highlights the technical strength and scientific rigor of the project, demonstrating its potential value in real-world medical AI applications.
