# Photoplethysmography-Based Blood Pressure Prediction Using Machine Learning

![Python](https://img.shields.io/badge/python-3.8%2B-blue)
![License](https://img.shields.io/badge/license-Academic%20Use-green)
![Status](https://img.shields.io/badge/status-Research%20Prototype-orange)
![Conference](https://img.shields.io/badge/Format-IEEE%20Conference-blueviolet)

---

## Abstract
Continuous blood pressure (BP) monitoring is essential for early diagnosis and management of cardiovascular diseases; however, conventional cuff-based techniques are unsuitable for long-term and wearable use. This repository presents an **IEEE-style research implementation** for **cuffless blood pressure estimation** using **photoplethysmography (PPG)** signals. The proposed framework integrates robust signal preprocessing, extensive handcrafted feature extraction, and classical machine learning regression models enhanced through ensemble learning to estimate **Systolic Blood Pressure (SBP)**, **Diastolic Blood Pressure (DBP)**, and **Arterial Blood Pressure (ABP)**.

---

## Authors
**Aparajita Vaish**  
Department of Electronics and Communication Engineering  
IIIT Naya Raipur, India  

**Komendra Sahu**  
Department of Data Science and Artificial Intelligence  
IIIT Naya Raipur, India  

**Aayush Sahu**  
Department of Data Science and Artificial Intelligence  
IIIT Naya Raipur, India  

---

## Keywords
Photoplethysmography, Blood Pressure Estimation, Feature Engineering, Machine Learning, Ensemble Learning, Wearable Healthcare

---

## 1. Introduction
Photoplethysmography (PPG) is a non-invasive optical sensing technique widely adopted in wearable health-monitoring devices to capture blood volume changes in peripheral tissues. Although PPG does not directly measure blood pressure, its waveform morphology reflects cardiovascular properties such as arterial stiffness and vascular resistance. This project proposes a **feature-engineered, interpretable machine learning pipeline** designed for scalability, robustness, and real-time wearable healthcare applications.

---

## 2. Dataset Description
- **Signal Type:** Photoplethysmography (PPG)  
- **Sampling Frequency:** 125 Hz  
- **Window Length:** 875 samples  
- **Data Format:** HDF5  
- **Scale:** Approximately 9 million signal windows  
- **Target Labels:** SBP, DBP, ABP  

A **subject-independent train–test split** is adopted to prevent data leakage and ensure realistic generalization across unseen subjects.

---

## 3. Methodology

### 3.1 Signal Preprocessing
The raw PPG signals undergo a multi-stage preprocessing pipeline:
- Butterworth bandpass filtering (0.5–8 Hz)
- Wavelet-based denoising using Daubechies (db6)
- Savitzky–Golay smoothing
- Z-score normalization

### 3.2 Feature Engineering
A comprehensive set of handcrafted features is extracted:
- **Time-domain features:** Mean, variance, skewness, kurtosis, extrema, pulse amplitude, area under curve (AUC)  
- **Derivative-based features:** Acceleration plethysmogram (APG) waves (a, b, c, d, e) and their ratios  
- **Frequency-domain features:** FFT-based dominant frequency, spectral energy in physiological bands  

### 3.3 Machine Learning Models
The following regression models are implemented and evaluated:
- K-Nearest Neighbors (KNN) Regression  
- Support Vector Regression (SVR)  
- Random Forest Regression  

### 3.4 Ensemble Learning
To improve robustness and accuracy, ensemble strategies are employed:
- Voting Regressor  
- Stacking Regressor  

---

## 4. Evaluation Metrics
Model performance is assessed using standard regression metrics:
- Mean Absolute Error (MAE)  
- Root Mean Square Error (RMSE)  
- Coefficient of Determination (R²)  

---

## 5. Results

| Blood Pressure Type | MAE (mmHg) | RMSE (mmHg) | R² |
|---------------------|------------|-------------|----|
| SBP | 5.63 | 8.67 | 0.7856 |
| DBP | 2.70 | 4.09 | 0.7463 |
| ABP | 3.42 | 5.21 | 0.7755 |

The stacking ensemble model demonstrates superior overall performance, validating the effectiveness of feature-based ensemble learning for cuffless blood pressure estimation.

---

## 6. Visualization Results

### True vs Predicted SBP
![True vs Predicted SBP](outputs/true_vs_pred_sbp.png)

This plot illustrates the correlation between ground-truth systolic blood pressure values and the model’s predictions, highlighting the regression accuracy and consistency.

---

## 7. Repository Structure

```text
.
├── outputs/
│   └── true_vs_pred_sbp.png     # Ground truth vs predicted SBP visualization
├── project.ipynb               # Main Jupyter notebook (preprocessing, features, models)
├── fds_report.pdf              # Detailed project / final report
└── README.md                   # Project documentation
```

## 8. Limitations
- Sensitivity to motion artifacts  
- Absence of subject-specific calibration  
- Dependence on fixed windowing  

---

## 9. Future Work
- Beat-level segmentation and adaptive windowing  
- Hybrid deep learning + feature-based models  
- Personalized calibration using transfer learning  
- Deployment on wearable hardware platforms  

---

## 10. Citation
If you use this work, please cite it as an IEEE conference paper.

---

## 11. License
This repository is intended **strictly for academic and research use**.
