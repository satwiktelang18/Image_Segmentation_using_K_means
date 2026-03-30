<div align="center">

<img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white"/>
<img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white"/>
<img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white"/>
<img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge"/>

<br/><br/>

# 🎨 Image Segmentation using K-Means Clustering

> 📌 A Computer Vision project that performs color-based image segmentation using K-Means clustering in RGB space.

</div>

---

## 📖 Overview

This project demonstrates **image segmentation** using the **K-Means clustering algorithm** applied in RGB color space. Every pixel in an image is treated as a 3D data point `(R, G, B)` and grouped into **K clusters** based on color similarity — simplifying complex images into distinct color regions.

The project experiments with **K = 3, 5, and 20** across 6 different images to analyze how the number of clusters impacts segmentation quality and computational efficiency.

> 💡 Image segmentation is a foundational technique in Computer Vision — used in medical imaging, autonomous vehicles, satellite analysis, and object detection.

---

## ✨ Features

- 🖼️ Works on multiple images (6 different datasets)
- 🎨 RGB color space clustering — no labels needed
- 🔍 Comparison of K = 3, 5, and 20 segmentation levels
- ⚡ Optimized for higher K using image resizing
- 📊 3D RGB scatter plots for pre-clustering visualization
- 🗂️ Side-by-side visual comparison of all results

---

## 🛠️ Tech Stack

| Tool | Version | Purpose |
|------|---------|---------|
| **Python** | 3.x | Core language |
| **OpenCV** (`cv2`) | 4.x | Image I/O, color conversion, `cv2.kmeans()` |
| **NumPy** | latest | Array manipulation, pixel reshaping |
| **Matplotlib** | latest | 2D image grids & 3D RGB scatter plots |
| **Jupyter Notebook** | latest | Interactive experimentation environment |

---

## 📂 Project Structure

```
Image_Segmentation_using_K_means/
│
├── image_segmentation_k_means.ipynb   ← Main notebook (all code here)
│
├── tunnel.jpg                          ← Sample image 1
├── scenery.jpg                         ← Sample image 2
├── peppers.png                         ← Sample image 3
├── islands.png                         ← Sample image 4
├── butterfly.png                       ← Sample image 5
└── beach.png                           ← Sample image 6
```

---

## ⚙️ Environment Setup & Installation

> ✅ Follow these steps exactly. No prior setup is assumed.

### Prerequisites

Make sure you have the following installed on your system:
- Python 3.x → [Download here](https://www.python.org/downloads/)
- pip (comes bundled with Python)
- Git → [Download here](https://git-scm.com/)

---

### Step 1 — Clone the Repository

```bash
git clone https://github.com/satwiktelang18/Image_Segmentation_using_K_means.git
cd Image_Segmentation_using_K_means
```

---

### Step 2 — (Optional but Recommended) Create a Virtual Environment

```bash
# Create virtual environment
python -m venv venv

# Activate — Windows:
venv\Scripts\activate

# Activate — macOS/Linux:
source venv/bin/activate
```

---

### Step 3 — Install Dependencies

```bash
pip install opencv-python numpy matplotlib jupyter
```

**Packages installed:**

| Package | Install Command |
|---------|----------------|
| OpenCV | `pip install opencv-python` |
| NumPy | `pip install numpy` |
| Matplotlib | `pip install matplotlib` |
| Jupyter | `pip install jupyter` |

---

## ▶️ How to Run

### Option 1 — Jupyter Notebook (Recommended)

```bash
jupyter notebook
```

Open `image_segmentation_k_means.ipynb` in the browser and click **Run All Cells**.

---

### Option 2 — Command Line

```bash
# Convert notebook to Python script
jupyter nbconvert --to script image_segmentation_k_means.ipynb

# Run directly
python image_segmentation_k_means.py
```

> ⚠️ **Important:** All 6 image files (`tunnel.jpg`, `scenery.jpg`, `peppers.png`, `islands.png`, `butterfly.png`, `beach.png`) must be in the **same directory** as the notebook/script before running.

---

## 🧠 How It Works — Step by Step

```
Image Input  →  Reshape to (pixels × 3)  →  K-Means Clustering
     ↓                                              ↓
Display Result  ←  Reshape Back  ←  Map Labels to Centroid Colors
```

**1. Load & Display Images**
Read 6 images via OpenCV (`BGR → RGB`) and display them in a 2×3 grid.

**2. Visualize RGB Color Space**
Split each image into R, G, B channels → flatten → plot as a 3D scatter plot to see how pixel colors distribute before clustering.

**3. Preprocess for K-Means**
- Reshape: `(H, W, 3)` → `(H×W, 3)` so each pixel becomes one data point
- Convert to `float32` as required by `cv2.kmeans()`

**4. Apply K-Means Clustering**

```python
criteria = (cv2.TERM_CRITERIA_EPS + cv2.TERM_CRITERIA_MAX_ITER, 10, 1.0)
ret, label, center = cv2.kmeans(vectorized_img, K, None, criteria, 10, cv2.KMEANS_PP_CENTERS)
```

| Parameter | Value | Meaning |
|-----------|-------|---------|
| `K` | 3 / 5 / 20 | Number of color clusters |
| `attempts` | 10 | Reruns with different seeds; picks best |
| `MAX_ITER` | 10 | Max iterations per run |
| `epsilon` | 1.0 | Stops early if centroids barely move |
| `flags` | `KMEANS_PP_CENTERS` | Smart centroid initialization (K-Means++) |

**5. Reconstruct & Display**
Map each pixel's label → its centroid color → reshape back to `(H, W, 3)` → display segmented image.

**6. Experiment with K = 5 and K = 20**
Re-run with higher K values. For K=20, images are resized to `300×300` first for speed, then resized back.

---

## 📊 Results & Observations

| K Value | Segmentation | Speed | Best Use Case |
|---------|-------------|-------|---------------|
| **K = 3** | Coarse — dominant regions only | Very Fast | Simple foreground/background separation |
| **K = 5** | Balanced — meaningful distinct regions | Moderate | General-purpose segmentation |
| **K = 20** | Fine — subtle color variations | Slow | Near-lossless simplification |

> **Key Observation:** As K increases, the output converges toward the original image — more color detail but diminishing segmentation effect. Optimal K balances detail and efficiency.

---

## ✅ Conclusion

K-Means clustering is an effective, unsupervised method for color-based image segmentation. This project confirms:

- **Lower K** → faster, simpler — ideal for dominant region extraction  
- **Higher K** → richer detail — but computationally heavier  
- **K = 3 to 5** provides the best balance for most natural images  
- No labeled data required — strong baseline for unsupervised segmentation

---

## 📚 References

- [OpenCV K-Means Documentation](https://docs.opencv.org/4.x/d1/d5c/tutorial_py_kmeans_opencv.html)
- [Image Segmentation using K-Means — GeeksforGeeks](https://www.geeksforgeeks.org/image-segmentation-using-k-means-clustering/)
- [K-Means Clustering — Scikit-learn Concepts](https://scikit-learn.org/stable/modules/clustering.html#k-means)

---

<div align="center">

Made with ❤️ by [Satwik Telang](https://github.com/satwiktelang18)

</div>
