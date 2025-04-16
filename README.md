# 👶🧓 Image Age Detection using CNN

This project is a deep learning-based web application that predicts a person's **age** from a facial image. It uses a **Convolutional Neural Network (CNN)** trained on labeled facial data and is deployed through a simple **Flask web app**.

---

## 🎯 Objective

To build an application that can estimate a person's age based on their face in an image. This has practical applications in:
- Surveillance and security systems
- Marketing and audience segmentation
- Age-specific user experiences

---

## 🗃️ Dataset

- **Source**: [UTKFace Dataset](https://susanqq.github.io/UTKFace/)
- Contains 20,000+ facial images with labels for:
  - **Age** (0 to 116)
  - Gender
  - Ethnicity
- Used **age labels** for this project

### 🔧 Preprocessing
- Image resizing (128x128)
- Normalization (pixel values scaled to [0, 1])
- Grayscale conversion (optional)
- Data augmentation: rotation, zoom, flip

---

## 🧠 Model Architecture

- **Model Type**: Convolutional Neural Network (CNN)
- **Architecture**:
  - 3x Conv2D + MaxPooling layers
  - Flatten
  - Dense(512) with ReLU
  - Dropout + BatchNorm
  - Output: Single neuron for **regression** (age)

### ⚙️ Loss & Optimization
- **Loss**: Mean Absolute Error (MAE)
- **Optimizer**: Adam
- **Callbacks**: EarlyStopping, ReduceLROnPlateau

---

## 🚀 Training

- Split: 80% training / 20% validation
- Epochs: 50 (with early stopping)
- Goal: Achieve MAE < 5 years

---

## 🌐 Web App (Flask Deployment)

Simple Flask app that allows users to upload an image and returns the predicted age.

### 📂 `app.py` Flow
1. Upload image via browser
2. Image is saved and processed
3. Model predicts the age
4. Output is displayed on the result page

---

## 🛠️ Installation & Usage

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/image-age-detector.git
cd image-age-detector
