# Gene Expression & Hypoxia Classification

This project investigates whether **hypoxic** (low oxygen) and **normoxic** cells can be distinguished using single-cell RNA sequencing data and machine learning approaches.

---

## 📖 Project Description

The datasets come from two human breast cancer cell lines:
- **MCF7** → luminal subtype  
- **HCC1806** → basal subtype  

Data were generated with two scRNA-seq technologies:
- **SMART-seq**
- **DROP-seq**

For each combination, three dataset versions are provided:
1. **Unfiltered** → raw count matrices, no preprocessing.  
2. **Filtered** → low-quality cells/genes removed.  
3. **Normalized** → systematic biases corrected for comparability.  

- *Unfiltered* data allow quality exploration and raw structure analysis.  
- *Filtered/normalized* datasets are the main inputs for machine learning.  

---

## 🔬 Methodology

### 1. **Unsupervised Learning**
- PCA (2D/3D projections)
- Clustering (KMeans and others)  
→ To assess whether hypoxic vs normoxic cells naturally form distinct groups.

### 2. **Supervised Learning**
- Preprocessing: filtering, normalization, standardization  
- Algorithms trained:  
  - Logistic Regression  
  - k-Nearest Neighbors  
  - Support Vector Machine  
  - Random Forest  
  - Multi-Layer Perceptron  

- **Evaluation**: 5-fold cross-validation + holdout sets  
- **Feature selection**: Random Forest → top 50 informative genes per dataset  
- **Consensus panel**: 28 recurrent genes across datasets  
- **Cross-dataset generalization**: train on one dataset, test on others (restricted to 70 shared genes)  
- **Champion models**: hyperparameter-tuned pipelines on four representative datasets → applied to anonymized external test files.

---

## 🌍 Motivation

Cancer is one of the leading causes of mortality worldwide, driven by complex biological processes.  
**Hypoxia**—low oxygen in the tumor microenvironment—promotes disease progression, treatment resistance, and poor outcomes.  

Identifying hypoxic cells is therefore crucial.  
This project asks:  
👉 *Can we computationally identify hypoxic cells based on gene expression?*  

By applying **Artificial Intelligence** to biomedical data, this work illustrates how new technologies can advance medicine and support precision oncology.

---

## 📂 Data Availability

The datasets used in this project (single-cell RNA-seq from MCF7 and HCC1806 cell lines) are **not included in this repository** due to licensing and sharing restrictions.

To reproduce the analysis:
- Contact the dataset providers or refer to the original publications.
- Alternatively, replace the file paths in the notebooks with your own scRNA-seq data.

The provided **notebooks** contain the full preprocessing, analysis, and modeling pipeline and can be adapted to similar datasets.

