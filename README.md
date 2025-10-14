
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

## 🧩 Models Implemented

Based on the categories defined in Shu et al.’s survey, the following models are implemented using **scikit-image**:

### 1. Edge-Based Model
#### **Geodesic Active Contour (GAC)**
- Finds object boundaries by evolving a contour toward strong edges (image gradients).  
- Sensitive to the initial contour placement and image contrast.  
- Works best on images with clear, well-defined edges.

---

### 2. Region-Based Models
#### **Chan–Vese (CV)**
- Divides the image into two regions with different average intensities.  
- Uses global image information and can handle weak or blurred edges.


---

### 3. Hybrid Model
#### **Local and Global Intensity Fitting (LGIF) Simulation**
- Combines **region** and **edge** information.  
- Creates a “hybrid input” image by merging the original MRI intensities with an edge map.  
- This forces the algorithm to consider both global intensity variations and local edge details.  
- Useful for **intensity-inhomogeneous medical images**.

---

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



