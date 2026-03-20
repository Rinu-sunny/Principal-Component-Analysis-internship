# Principal Component Analysis (PCA): Theoretical and Experimental Study

## Internship Research Project  
Conducted at Naval Physical and Oceanographic Laboratory (NPOL), DRDO  
June – July 2025  

---

##  Overview

This repository presents a research-oriented study and implementation of **Principal Component Analysis (PCA)** carried out during my internship at the Naval Physical and Oceanographic Laboratory (NPOL), DRDO.

The objective of this work was not only to implement PCA, but to deeply understand:

- Why PCA maximizes variance  
- Why the covariance matrix formulation is used  
- Why eigenvectors define principal directions  
- How SVD and eigen decomposition are related  
- When PCA succeeds and when it fails  

This study combines mathematical derivation, conceptual reasoning, and experimental validation on real datasets.

---

## Research Motivation

High-dimensional datasets often contain:

- Redundant features  
- Correlated variables  
- Noise components  
- Computational inefficiencies  

PCA addresses these issues by transforming data into an orthogonal basis that captures maximum variance in descending order.

This project investigates PCA from first principles, rather than treating it as a black-box library function.

---

## Mathematical Foundation

Given a mean-centered data matrix:

X ∈ ℝ^(m×n)

### Covariance Matrix

Cₓ = (1 / (n - 1)) X Xᵀ

- Diagonal entries → feature variances  
- Off-diagonal entries → feature covariances  

PCA seeks a transformation matrix **P** such that:

P Cₓ Pᵀ = D  

Where **D** is diagonal.

---

###  Eigen Decomposition

Cₓ v = λ v  

- v → Eigenvectors (principal directions)  
- λ → Eigenvalues (variance captured along that direction)  

Principal components are the eigenvectors corresponding to the largest eigenvalues.

Projection:

Y = Eᵀ X  

---

###  PCA via Singular Value Decomposition (SVD)

Alternatively,

X = U Σ Vᵀ  

Where:
- V contains principal directions  
- Singular values relate to eigenvalues  

This equivalence was explored and analyzed during the study.

---

## Dimensionality Reduction Principle

To reduce dimensionality:

1. Sort eigenvalues in descending order  
2. Select top k eigenvectors  
3. Project data onto reduced basis  

This preserves maximum variance while discarding low-variance noise components.

---

##  Implementation Details

Two forms of implementation were explored:

### PCA using NumPy (Eigen Decomposition)
- Manual covariance computation  
- Eigenvalue and eigenvector extraction  
- Sorting and projection  

### PCA using scikit-learn
Library used: scikit-learn  
- StandardScaler for normalization  
- PCA for dimensionality reduction  
- Variance analysis  

---

##  Experimental Validation

PCA was applied to two real datasets:

- Diabetes Dataset  
- Breast Cancer Dataset  

Each dataset was:

- Standardized (Z-score normalization)  
- Transformed using PCA  
- Evaluated using:
  - Eigenvalue (Scree) Plot  
  - Cumulative Explained Variance  
  - PC1 vs PC2 Projection  
  - PC1 vs Last Principal Component  

These visualizations confirmed theoretical expectations:
- Early components capture dominant structure  
- Later components contain negligible variance  

---

## Observations

- Standardization is critical before PCA  
- Eigenvalues directly correspond to variance magnitude  
- Variance maximization aligns with minimum reconstruction error  
- PCA effectively filters noise and redundancy  
- PCA assumes linear structure in data  

---

##  Limitations

- Assumes linear relationships  
- Sensitive to feature scaling  
- Does not consider output labels (unsupervised)  
- May fail for highly non-linear manifolds  

Possible extensions:
- Kernel PCA  
- Independent Component Analysis (ICA)  

---

## Key Learning Outcomes

- Developed mathematical understanding of PCA  
- Derived covariance-based optimization objective  
- Understood eigen decomposition and orthogonality  
- Explored PCA as both variance maximization and SVD formulation  
- Validated theory through implementation and visualization  
- Studied limitations and real-world applicability  

---

##  Tools & Technologies

- Python  
- NumPy  
- Matplotlib  
- scikit-learn  
- Jupyter Notebook  

---

## Repository Structure

```
principal-component-analysis/
│
├── notebooks/
│   └── pca_analysis.ipynb
│
├── src/
│   ├── pca_from_scratch.py
│   └── pca_with_sklearn.py
│
├── report/
│   └── Internship_PCA_Report.pdf
│
├── requirements.txt
└── README.md
```

---

## Conclusion

This project transformed PCA from a theoretical concept into a fully understood analytical tool.  

By connecting linear algebra, optimization, and statistical reasoning, this work reinforced the importance of foundational mathematics in machine learning.

The study bridges theory and implementation, demonstrating both conceptual clarity and experimental validation.

---

##  Internship Context

This research-oriented study was conducted as part of a structured Machine Learning internship at:

Naval Physical and Oceanographic Laboratory (NPOL), 
Defence Research and Development Organisation (DRDO), 
Government of India  

Under the mentorship of senior research scientists.

---
