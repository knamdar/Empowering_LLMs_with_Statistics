# Empowering Large Language Models with Statistics: A Practical Tutorial for Medical Imaging

**Statistical Methods in Imaging (SMI) Conference, 2026**

## Instructors
* **Ernest (Khashayar) Namdar** (Contact: [ernest.namdar@utoronto.ca](mailto:ernest.namdar@utoronto.ca))
* **Dominik A. Deniffel**
* **Pascal Tyrrell**

---

## Overview

Welcome to the official repository for the SMI 2026 tutorial: *Empowering Large Language Models with Statistics: A Practical Tutorial for Medical Imaging*. 

This tutorial is designed to bridge the gap between advanced Large Language Models (LLMs) and rigorous statistical methodologies in the context of medical imaging and precision medicine. Through a series of hands-on Jupyter Notebooks, we explore how to extract robust, probabilistic, and statistically verifiable insights from both Encoder and Decoder LLMs.

The tutorial focuses on the clinical task of **Acute Ischemic Stroke (AIS)** classification from radiology MRI reports.

## Repository Structure

The tutorial is divided into four main modules, each containing its own code, data, and results directories:

### Part 1: Encoder LLM for Classification
Focuses on feature extraction and baseline classification using Encoder-based LLMs.
* Extracting robust embeddings (e.g., BioClinical ModernBERT).
* Dimensionality reduction and visualization (PCA, UMAP).
* Establishing machine learning baselines (LightGBM, Random Forest, TF-IDF).
* Statistical error analysis, subgroup evaluation, and ensemble agreement.

### Part 2: Decoder LLM for Classification
Explores zero-shot and prompted classification using Decoder-based LLMs (e.g., `microsoft/MediPhi`).
* Designing deterministic generation pipelines.
* Extracting log-probabilities directly from the model's logits for statistical evaluation.
* Forcing structured JSON outputs using Pydantic.
* Conducting pairwise paired t-tests to compare Encoder and Decoder pipelines across cross-validation folds.

### Part 3: ROC Analysis & Probability Thresholding
Applies advanced statistical thresholding techniques to continuous LLM probabilities.
* Converting probabilities to hard labels using standard 0.5 cutoffs, Youden's J Point, and the **B-Point Method** (Namdar et al., 2024).
* Implementing unbiased K-Fold cross-validation for out-of-sample threshold calculation.
* Visualizing performance via annotated confusion matrices and ROC curve overlays.

### Part 4: Uncertainty Measurement
Quantifies the predictive uncertainty of Decoder LLMs through input perturbation.
* Rephrasing radiology reports via LLM summarization and improved writing prompts.
* Measuring the variance (uncertainty) in predicted probabilities across perturbed inputs.
* Binning analysis to empirically demonstrate the correlation between model uncertainty and ROC-AUC degradation.

---

## Setup & Requirements

The notebooks in this repository are intended to be run in a GPU-accelerated environment (e.g., CUDA-enabled).

### Key Dependencies
* `python >= 3.9`
* `torch`
* `transformers`
* `scikit-learn`
* `pandas` & `numpy`
* `matplotlib` & `seaborn`
* `pydantic`

## Citation

If you utilize the B-Point thresholding method or other advanced ROC analytics discussed in this tutorial, please cite:

```bibtex
@inproceedings{namdar2024advanced,
   author = {Khashayar Namdar and Farzad Khalvati},
   booktitle = {IEEE-EMBS International Conference on Biomedical and Health Informatics},
   title = {Advanced Receiver Operating Characteristic Curve Analysis to Identify Outliers in Binary Machine Learning Classifications for Precision Medicine},
   url = {https://openreview.net/forum?id=9VCv8bLKdq},
   year = {2024}
}
```
