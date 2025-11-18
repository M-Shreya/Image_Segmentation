
# Variational Methods for Medical Image Segmentation

This project implements and compares several **classical variational methods** for segmenting brain tumors from MRI scans.  
It is based on the concepts described in the survey paper:
> **"Variational methods with application to medical image segmentation: A survey"**  
> *Shu et al., Neurocomputing, 2025.*

The aim is to apply these **non-learning-based algorithms** to real medical imaging data and analyze their effectiveness.  
All implementations are designed to run smoothly in **Google Colab**.


## 🧬 About the Dataset

The project uses the **RSNA-MICCAI Brain Tumor Radiogenomic Classification** dataset, available on Kaggle:

🔗 [Dataset Link](https://www.kaggle.com/competitions/rsna-miccai-brain-tumor-radiogenomic-classification/data)

> ⚠️ The dataset is very large (>130 GB uncompressed).  
> To make experimentation manageable, a smaller subset of **200 patients** from the `train/` folder is used.  
> This subset still provides diverse MRI slices for testing segmentation models without causing storage or runtime issues.

---

# 🧩 Segmentation Methods

### **1. Geodesic Active Contour (GAC) – Edge-Based**
- Evolves contour toward strong image gradients.  
- Works well for well-defined boundaries.  
- Parameters: `num_iter=400`, `balloon=-1`, `threshold=0.3`.

### **2. Random Walker – Graph-Based**
- Probabilistic segmentation using foreground & background seeds.  
- Uses: `beta=1000`, intelligent marker placement.  
- Good for complex shapes and noisy regions.

### **3. Chan–Vese (CV) – Region-Based**
- Based on global intensity statistics.  
- Does not rely on edges; performs well on blurred MRI boundaries.  
- Parameters: `num_iter=300`, `lambda1=lambda2=200`.

### **4. Region-Scalable Fitting (RSF) – Local Region-Based**
- Handles intensity inhomogeneity using local fitting energies.  
- Good for MRI with nonuniform illumination.  
- Parameters include: `sigma=3`, `lambda1=lambda2=200`.

### **5. Hybrid Model – Intensity + Edge Fusion**
- Combines MRI intensity with Sobel gradient:  
  `hybrid = 0.85 * image + 0.15 * gradient`  
- Segmented using Morphological Chan–Vese.  
- Strong performance on weak-edge MRI scans.



## 🚀 Getting Started

This project is designed for execution in **Google Colab** for ease of setup and GPU access.

### ✅ Prerequisites
- A **Google Account** (for Colab and Drive)
- A **Kaggle Account** (for dataset access)

---

### 🛠️ Installation and Setup

1. **Download the Dataset**  
   Download the ZIP file from the Kaggle competition page:
   
2. **Upload to Google Drive**  
Upload the `.zip` file to the root directory of your Google Drive.

3. **Run the Project**  
   Open the provided Google Colab notebook, mount your Google Drive, and run all the cells in sequence.  
   The code will automatically extract, load, and process the data for segmentation.



