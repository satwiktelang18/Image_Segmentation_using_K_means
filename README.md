# 🚀 Image Segmentation using K-Means

> 🎯 A Computer Vision project that performs color-based image segmentation using K-Means clustering in RGB space.

---

## 📌 Overview

This project demonstrates image segmentation using the K-Means clustering algorithm. Each pixel is treated as a data point and grouped into clusters based on color similarity.

Different values of **K (3, 5, 20)** are used to analyze how segmentation quality and detail change.

---

## ✨ Features

- 📷 Works on multiple images (6 datasets)
- 🎨 RGB color space clustering
- 🔍 Comparison of different K values
- ⚡ Optimized for higher K using resizing
- 📊 Visual comparison of results

---

## 🛠️ Tech Stack

- Python  
- OpenCV  
- NumPy  
- Matplotlib  

---

## 📂 Dataset

The project uses the following images:

- tunnel.jpg  
- scenery.jpg  
- peppers.png  
- islands.png  
- butterfly.png  
- beach.png  

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the repository
```bash
git clone https://github.com/satwiktelang18/Image_Segmentation_using_K_means.git
cd Image_Segmentation_using_K_means
```

### 2. Install dependencies
```bash
pip install opencv-python numpy matplotlib
```

---

## ▶️ How to Run

### Option 1 (Jupyter Notebook)
```bash
jupyter notebook
```
Open the file `image-segmentation-k-means.ipynb` and run all cells.

### Option 2 (Command Line)
```bash
jupyter nbconvert --to script image-segmentation-k-means.ipynb
python image-segmentation-k-means.py
```
**Note:** Make sure all image files are present in the same directory before running.
---
## 📈 Observations 

- Increasing K increases segmentation detail
- Lower K gives simpler regions
- Higher K increases computation cost
- Image resizing improves performance for large K

## 🧠 Conclusion

K-Means clustering is an effective method for color-based image segmentation. The choice of K significantly affects the level of detail and computational efficiency. Moderate values such as K = 3 or K = 5 provide meaningful segmentation, while higher values increase complexity with limited additional benefit.

---
