# 🐟 Fish Image Classification using CNN & VGG16

This project demonstrates the use of **Deep Learning** and **Transfer Learning** techniques for **classifying different fish species** from images.  
It combines a **Convolutional Neural Network (CNN)** with a **VGG16 pretrained model** to achieve **high accuracy (~98%)**.

---

## 📌 Motivation

Aquaculture and fisheries research often require **automated fish recognition systems** for monitoring, disease detection, and species classification.  
Traditional manual classification is time-consuming and error-prone.  
By leveraging **deep learning** on image datasets, we can build accurate, scalable, and real-time classification models.

---

## 📂 Dataset

- **Source:** Custom dataset (`Fish_Dataset`)  
- **Total Images:** 9020  
- **Classes (9 fish species):**
  - Black Sea Sprat  
  - Gilt-Head Bream  
  - Striped Red Mullet  
  - Shrimp  
  - Red Mullet  
  - Horse Mackerel  
  - Trout  
  - Red Sea Bream  
  - Sea Bass  

### 📊 Dataset Split:
- **Training Set:** 6494 images  
- **Validation Set:** 1624 images  
- **Test Set:** 902 images  

Each class contains ~1000 samples ensuring a **balanced dataset**.

---

## ⚙️ Methodology

### 1. Data Preprocessing
- Removed irrelevant ground-truth mask files.  
- Used **ImageDataGenerator** for:
  - Data augmentation (shear, zoom, flip, rotation).  
  - Normalization (`rescale=1./255`).  

### 2. Model Architecture
#### 🔹 Transfer Learning (VGG16 Backbone)
- Loaded VGG16 pretrained on **ImageNet**.  
- Excluded top layers (`include_top=False`).  
- Frozen base layers to retain pretrained weights.  

#### 🔹 Custom CNN Layers
- Additional **Conv2D + MaxPooling** layers.  
- Fully connected **Dense layers** with ReLU activation.  
- Dropout for regularization.  
- Final Softmax layer → **9 output neurons (classes)**.

### 3. Training Configuration
- **Optimizer:** Adam (lr=0.001)  
- **Loss Function:** Categorical Crossentropy  
- **Batch Size:** 32  
- **Epochs:** 10  

---

## 📈 Results

### 🔹 Accuracy & Loss
- **Training Accuracy:** 98.00%  
- **Validation Accuracy:** 97.35%  
- **Test Accuracy:** 98.78%  

- **Training Loss:** 6.02%  
- **Validation Loss:** 7.21%  
- **Test Loss:** 3.96%  

### 🔹 Confusion Matrix
- High precision and recall across all 9 classes.  
- Very few misclassifications observed (mostly between visually similar species).  

---

## 📊 Visualizations

- 📌 **Sample Images Preview** from each fish class.  
- 📌 **Class Distribution Bar Plot** showing balanced dataset.  
- 📌 **Training vs Validation Accuracy** curve.  
- 📌 **Training vs Validation Loss** curve.  
- 📌 **Confusion Matrix Heatmap** for evaluation.  

---

## 🚀 How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/fish-classification-cnn.git
   cd fish-classification-cnn
