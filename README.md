# Protein Metal Partial Charge Prediction

This project explores machine learning methods for predicting **partial charges** of metal ions bound in protein environments.

Metal centers in proteins (e.g., zinc, iron, magnesium) experience highly heterogeneous local environments. Accurately modeling their partial charges is important for:
- molecular dynamics force fields
- quantum chemistry approximations
- mechanistic interpretation of active sites

This capstone project implements an ML-based regression pipeline to learn partial charges from structural and chemical features of the metal environment.

---
---

## 🧪 Dataset: **tmQM_X**

This project uses the **tmQM_X dataset**, a high-quality quantum-mechanical dataset containing:

- Transition metal complexes  
- Atomistic structures  
- Reference partial charges  
- QM-derived physical descriptors  

tmQM_X is widely used for:
- QM surrogate modeling  
- ML-based force-field development  
- Transition metal chemistry research  

In this project, the dataset is filtered to focus on **protein-like coordination environments** and **metal centers relevant to biochemistry**.

---

## 🧠 Project Overview

### **Goal**
Predict continuous-valued **partial charges** for metal ions based on the local environment surrounding each metal site.

### **Input Features**
Depending on the notebook workflow, features may include:

- Coordination number  
- Distances to coordinating atoms  
- Neighbor atom types  
- Local geometry descriptors  
- One-hot encoded ligand information  
- Atomic properties (Z, electronegativity, valence, etc.)  

### **Output**
A single **regressed partial charge value** per metal center.

### **Task Type**
Supervised regression.

---

## 🔬 Methods

### **Models**
The notebook explores one or more regression approaches, such as:

- Fully connected neural networks (PyTorch)  
- Random Forest Regressors  
- Gradient Boosted Trees  
- Baseline linear models  

### **Loss Functions**
- Mean Squared Error (MSE)  
- Mean Absolute Error (MAE)

### **Evaluation Metrics**
- RMSE  
- MAE  
- Predicted vs. True charge scatter plots  
- Error distribution histograms  
- Feature importance (tree-based models)  

---

## 📊 Key Visualizations

*(After uploading your PNG images into `figures/`, update the filenames below to match.)*

### **Training Loss Curve**
![Training loss](figures/loss_curve.png)

Shows convergence behavior and potential overfitting.

---

### **Predicted vs True Partial Charges**
![Predicted vs true](figures/predicted_vs_true_charges.png)

The ideal model outputs would fall along a diagonal line; deviation indicates error.

---

### **Error Distribution**
![Error distribution](figures/error_distribution.png)

Histogram of prediction errors (predicted – true), revealing model spread and outliers.

---

### **Feature Importance (if applicable)**
![Feature importance](figures/feature_importance.png)

Highlights which descriptors contribute most strongly to predicting metal charges.

---

## 🚀 How to Run

### **Option 1 — Google Colab (Recommended)**
1. Open the notebook in `notebooks/`.
2. Upload the tmQM_X dataset or point the notebook to your dataset directory.
3. Run all cells.

### **Option 2 — Local Jupyter**
Requirements:

```bash
pip install numpy pandas matplotlib scikit-learn torch tqdm
```
📝 Notes
	•	This repository represents an academic capstone project exploring the interface of machine learning and computational chemistry.
	•	The tmQM_X dataset allows leveraging high-quality QM-level labels for ML-driven prediction.
	•	The workflow is modular and can be extended to additional metals, larger datasets, or more advanced neural network architectures.

⸻

✨ Future Work
	•	Expand feature engineering to include 3D graph-based descriptors
	•	Experiment with Graph Neural Networks (GNNs) for metal-site environments
	•	Integrate QM-derived features such as frontier orbitals
	•	Deploy model as a simple web API for real-time prediction
