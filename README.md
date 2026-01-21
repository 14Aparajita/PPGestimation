```markdown
# Photoplethysmography-Based Blood Pressure Prediction Using Machine Learning

![Python](https://img.shields.io/badge/python-3.8%2B-blue)
![License](https://img.shields.io/badge/license-Academic%20Use-green)
![Status](https://img.shields.io/badge/status-Research%20Prototype-orange)
![Conference](https://img.shields.io/badge/Format-IEEE%20Conference-blueviolet)

---

## Abstract
Continuous blood pressure (BP) monitoring is essential for early diagnosis and management of cardiovascular diseases; however, conventional cuff-based techniques are unsuitable for long-term and wearable use. This repository implements an **IEEE-style research pipeline** for **cuffless blood pressure estimation** using **photoplethysmography (PPG)** signals. The framework integrates multi-stage signal preprocessing, extensive handcrafted feature engineering, and classical regression models enhanced through ensemble learning to estimate **SBP**, **DBP**, and **ABP**.

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
Photoplethysmography (PPG) is a non-invasive optical technique widely used in wearable devices to capture blood volume variations. Although PPG does not directly measure blood pressure, its waveform morphology encodes cardiovascular information related to arterial stiffness and hemodynamics. This project presents a **feature-engineered machine learning framework** designed for interpretability, scalability, and suitability for real-time wearable applications.

---

## 2. Dataset Description
- **Signal Type:** PPG  
- **Sampling Frequency:** 125 Hz  
- **Window Length:** 875 samples  
- **Storage Format:** HDF5  
- **Scale:** ~9 million signal windows  
- **Labels:** SBP, DBP, ABP  

A **subject-independent train–test split** is used to avoid data leakage and ensure generalization.

---

## 3. Methodology
### 3.1 Signal Preprocessing
- Butterworth bandpass filtering (0.5–8 Hz)
- Wavelet denoising (Daubechies db6)
- Savitzky–Golay smoothing
- Z-score normalization

### 3.2 Feature Engineering
- **Time-domain features:** mean, variance, extrema, pulse amplitude, AUC  
- **Derivative-based features:** APG waves (a, b, c, d, e) and ratios  
- **Frequency-domain features:** FFT-based dominant frequency and band energy  

### 3.3 Machine Learning Models
- K-Nearest Neighbors Regression  
- Support Vector Regression  
- Random Forest Regression  

### 3.4 Ensemble Learning
- Voting Regressor  
- Stacking Regressor  

---

## 4. Evaluation Metrics
- Mean Absolute Error (MAE)  
- Root Mean Square Error (RMSE)  
- Coefficient of Determination (R²)  

---

## 5. Results
| BP Type | MAE (mmHg) | RMSE (mmHg) | R² |
|-------|------------|-------------|----|
| SBP | 5.63 | 8.67 | 0.7856 |
| DBP | 2.70 | 4.09 | 0.7463 |
| ABP | 3.42 | 5.21 | 0.7755 |

The stacking ensemble model achieves the best overall performance, validating the effectiveness of feature-based ensemble learning for cuffless BP estimation.

---

## 6. Limitations
- Sensitivity to motion artifacts  
- Absence of subject-specific calibration  
- Dependence on fixed windowing  

---

## 7. Future Work
- Beat-level segmentation and adaptive windowing  
- Hybrid deep learning + feature-based models  
- Personalized calibration using transfer learning  
- Deployment on wearable hardware platforms  

---

## 8. Citation
If you use this work, please cite it as an IEEE conference paper.

---

## 9. License
This repository is intended **strictly for academic and research use**.
```

---

## 2. `requirements.txt` 

Create a file named **`requirements.txt`**:

```txt
python>=3.8
numpy
scipy
pandas
scikit-learn
matplotlib
pywavelets
h5py
joblib
tqdm
seaborn
statsmodels
```

---


---

## 4. `.gitignore`

```gitignore
__pycache__/
*.pyc
*.pyo
*.pyd
.env
.venv
data/raw/*
data/processed/*
results/logs/*
.ipynb_checkpoints/
```
