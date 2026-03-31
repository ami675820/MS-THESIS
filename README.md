
# Uncertainty Estimation in Regression Using Additive Models and Gaussian Processes

## Overview

This repository contains the implementation and thesis work for the project:

**Uncertainty Estimation in Regression Using Additive Models and Gaussian Processes**

completed as part of the **BS–MS Dual Degree in Data Science and Engineering at IISER Bhopal (2025)**.

This work proposes a hybrid regression framework that integrates **Neural Additive Models (NAM)**, **Random Fourier Features (RFF)**, and **Gaussian Processes (GPs)** to produce accurate predictions together with reliable uncertainty estimates while preserving interpretability.

---

## Motivation

Most regression models produce only point predictions without indicating how confident those predictions are. However, uncertainty estimation is essential in applications such as:

* healthcare decision systems
* financial forecasting
* robotics
* environmental modeling
* scientific prediction tasks

This project focuses on building regression models that provide both **accurate predictions and calibrated uncertainty estimates** while maintaining transparency in model behavior.

---

## Proposed Method

The proposed framework combines three key components:

### Neural Additive Models (NAM)

Neural Additive Models enable feature-wise interpretability by allowing each feature to contribute independently to the prediction through learned shape functions.

This improves transparency compared to standard deep learning models.

---

### Random Fourier Features (RFF)

Random Fourier Features are used to approximate kernel functions efficiently, enabling scalable Gaussian Process-style modeling while maintaining computational feasibility.

RFF allows the model to capture complex nonlinear relationships without the high computational cost of traditional kernel methods.

---

### Sequential Gaussian Process Residual Modeling

Uncertainty estimation is performed through a sequential pipeline of three Gaussian Processes:

1. The first Gaussian Process models residual errors to improve prediction accuracy
2. The second Gaussian Process estimates heteroscedastic variance to capture input-dependent uncertainty
3. The third Gaussian Process refines remaining residual patterns for improved predictive reliability

The final prediction combines contributions from the base GP-NAM model and residual corrections learned by the Gaussian Processes.

---

## Residual Distribution Modeling Extensions

To further improve uncertainty modeling, two probabilistic residual-learning approaches were explored:

### Gaussian Mixture Regression (GMR)

Residuals are modeled using Gaussian mixture components selected via Bayesian Information Criterion (BIC).

### Mixture Density Network (MDN)

Residual distributions are modeled using a neural-network-based mixture density framework that learns:

* mixture means
* variances
* mixing coefficients

This provides a richer probabilistic description of prediction uncertainty.

---

## Evaluation Metrics

Model performance is evaluated using standard probabilistic regression metrics:

* RMSE (Root Mean Square Error) — measures prediction accuracy
* ECE (Expected Calibration Error) — evaluates calibration quality
* NLPD (Negative Log Predictive Density) — measures uncertainty reliability

Lower values indicate better performance.

---

## Datasets

The model is evaluated on multiple benchmark regression datasets from the UCI repository, including datasets with varying complexity and size to test both predictive performance and uncertainty calibration.

---

## Key Contributions

This work introduces:

* A hybrid GP-NAM regression framework for interpretable prediction
* Scalable kernel approximation using Random Fourier Features
* A sequential three-stage Gaussian Process uncertainty estimation pipeline
* Heteroscedastic uncertainty modeling
* Residual uncertainty refinement using mixture-based probabilistic models
* An interpretability index combining complexity, fidelity, and decomposability measures
* Empirical validation across multiple benchmark regression datasets

---


---

## Experimental Results

The proposed framework demonstrates:

* improved predictive performance
* calibrated uncertainty estimation
* interpretable feature-wise contributions
* robustness across multiple datasets

Experiments also show that the proposed three-GP residual modeling pipeline provides a strong balance between model complexity and predictive performance.

---

## Applications

This framework can be applied in domains requiring reliable uncertainty-aware regression:

* scientific modeling
* decision support systems
* risk-sensitive prediction
* interpretable machine learning
* probabilistic forecasting

---

## Author

**Amish Anand**
BS–MS Dual Degree
Department of Data Science and Engineering
Indian Institute of Science Education and Research (IISER) Bhopal
2025

---

## Citation

If you use this work in your research, please cite:

```
@thesis{anand2025uncertainty,
title={Uncertainty Estimation in Regression Using Additive Models and Gaussian Processes},
author={Amish Anand},
year={2025},
institution={Indian Institute of Science Education and Research Bhopal}
}
```

---

## License

This repository is intended for academic and research use.
