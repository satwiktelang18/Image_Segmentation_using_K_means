# Image Segmentation using K-Means

## 📌 Overview
This project demonstrates image segmentation using the K-Means clustering algorithm in RGB color space. Each pixel of an image is treated as a data point and grouped into clusters based on color similarity. The project compares segmentation results for different values of K to analyze their impact.

Image segmentation is a technique in computer vision that divides an image into different segments. This can help identify specific objects, boundaries or patterns in the image.  Image is basically a set of given pixels and in image segmentation pixels with similar intensity are grouped together. Image segmentation creates a pixel-wise mask for objects in an image which gives us a better understanding of the object
---

## 🛠️ Technologies Used
- Python
- OpenCV
- NumPy
- Matplotlib

---

## 📂 Dataset
The project uses 6 sample images:
- tunnel.jpg  
- scenery.jpg  
- peppers.png  
- islands.png  
- butterfly.png  
- beach.png  

---

## ⚙️ Installation & Setup

### 1. Clone the repository
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

## 🧠 Conclusion

K-Means clustering is an effective method for color-based image segmentation. The choice of K significantly affects the level of detail and computational efficiency. Moderate values such as K = 3 or K = 5 provide meaningful segmentation, while higher values increase complexity with limited additional benefit.

---
