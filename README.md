# Principal Component Analysis (PCA): Theoretical and Experimental Study  
### Internship Research Project  
Conducted at Naval Physical and Oceanographic Laboratory (NPOL), DRDO  
**June – July 2025**

---

##  Overview

This repository presents a research-oriented study and experimental validation of **Principal Component Analysis (PCA)** conducted during my internship at NPOL, DRDO.

The objective was not merely to apply PCA, but to deeply understand:

- Why PCA maximizes variance  
- Why the covariance matrix formulation is used  
- Why eigenvectors define principal directions  
- How eigen decomposition relates to Singular Value Decomposition (SVD)  
- When PCA succeeds and where its limitations arise  

This work combines mathematical derivation, conceptual reasoning, and experimental validation on real datasets.

---

##  Research Motivation

High-dimensional datasets often contain:

- Redundant features  
- Correlated variables  
- Noise components  
- Computational inefficiencies  

PCA transforms data into an orthogonal basis that captures maximum variance in descending order, reducing dimensionality while preserving dominant structure.

The internship emphasized understanding PCA from first principles rather than treating it as a black-box library function.

---

##  Mathematical Foundation

Let the mean-centered data matrix be:

X ∈ ℝ^(m × n)

### Covariance Matrix

Cₓ = (1 / (n − 1)) XᵀX

- Diagonal entries → Feature variances  
- Off-diagonal entries → Feature covariances  

PCA seeks a transformation matrix P such that:

P Cₓ Pᵀ = D  

where D is diagonal.

---

### Eigen Decomposition

Cₓ v = λ v

- v → Eigenvectors (principal directions)  
- λ → Eigenvalues (variance captured along that direction)  

Principal components correspond to eigenvectors associated with the largest eigenvalues.

Projection:

Y = Eᵀ X

---

##  PCA via Singular Value Decomposition (SVD)

Alternatively,

X = U Σ Vᵀ

- V contains principal directions  
- Singular values relate directly to eigenvalues  

The equivalence between eigen decomposition and SVD was explored and analyzed during the internship.

---

##  Dimensionality Reduction Principle

To reduce dimensionality:

1. Sort eigenvalues in descending order  
2. Select top k eigenvectors  
3. Project data onto the reduced basis  

This preserves maximum variance while discarding low-variance noise components.

---

##  Experimental Validation

PCA was applied to:

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

### Key Observations

- Early components capture dominant structure  
- Later components contain negligible variance  
- Standardization is critical before PCA  
- Eigenvalues directly correspond to variance magnitude  
- Variance maximization aligns with minimum reconstruction error  
- PCA assumes linear structure in data  

---

##  Limitations

- Assumes linear relationships  
- Sensitive to feature scaling  
- Unsupervised (does not consider output labels)  
- May fail for highly non-linear manifolds  

Possible extensions:

- Kernel PCA  
- Independent Component Analysis (ICA)  

---

##  Key Learning Outcomes

- Developed strong mathematical understanding of PCA  
- Derived covariance-based optimization objective  
- Understood eigen decomposition and orthogonality  
- Explored PCA as both variance maximization and SVD formulation  
- Validated theory through implementation and visualization  
- Analyzed limitations and real-world applicability  

---

##  Tools & Technologies

- Python  
- NumPy  
- Matplotlib  
- scikit-learn  
- Jupyter Notebook  

---

##  Repository Structure
```
principal-component-analysis/
│
├── notebooks/
│   └── pca_analysis.ipynb
│
├── report/
│   └── Intership_PCA_Report.pdf
│
├── requirements.txt
├── .gitignore
└── README.md
```

##  Internship Research Report

The detailed theoretical analysis and derivations are documented in the internship report:

🔗 [View Full Internship Report](report/Intership_PCA_Report.pdf)

---

##  Internship Context

This research-oriented study was conducted at:

Naval Physical and Oceanographic Laboratory (NPOL)  
Defence Research and Development Organisation (DRDO), Government of India  

Under the mentorship of senior research scientists.

---

##  Conclusion

This project transformed PCA from a theoretical concept into a fully understood analytical tool.

By connecting linear algebra, optimization, and statistical reasoning, this work reinforced the importance of mathematical foundations in machine learning.

The study bridges theory and implementation, demonstrating conceptual clarity and experimental validation.
