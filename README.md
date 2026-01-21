# Photoplethysmography-Based Blood Pressure Prediction Using Machine Learning

![Python](https://img.shields.io/badge/python-3.8%2B-blue)
![License](https://img.shields.io/badge/license-Academic%20Use-green)
![Status](https://img.shields.io/badge/status-Research%20Prototype-orange)
![Conference](https://img.shields.io/badge/Format-IEEE%20Conference-blueviolet)

---

## Abstract
Continuous blood pressure (BP) monitoring is essential for early diagnosis and management of cardiovascular diseases; however, conventional cuff-based techniques are unsuitable for long-term and wearable use. This repository presents an **IEEE-style research pipeline** for **cuffless blood pressure estimation** using **photoplethysmography (PPG)** signals. The framework integrates multi-stage signal preprocessing, extensive handcrafted feature engineering, and classical regression models enhanced through ensemble learning to estimate **systolic blood pressure (SBP)**, **diastolic blood pressure (DBP)**, and **average blood pressure (ABP)**.

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
Photoplethysmography (PPG) is a non-invasive optical technique widely adopted in wearable healthcare devices to measure blood volume changes in peripheral tissues. Although PPG does not directly measure blood pressure, its waveform morphology encodes valuable cardiovascular information related to arterial stiffness and hemodynamics. This work proposes a **feature-driven machine learning framework** emphasizing interpretability, scalability, and suitability for real-time cuffless blood pressure monitoring.

---

## 2. Dataset Description
- **Signal Type:** Photoplethysmography (PPG)  
- **Sampling Frequency:** 125 Hz  
- **Window Length:** 875 samples  
- **Data Format:** HDF5  
- **Dataset Size:** Approximately 9 million signal windows  
- **Target Variables:** SBP, DBP, ABP  

A **subject-independent train–test split** is employed to prevent data leakage and ensure robust generalization across unseen subjects.

---

## Repository Structure

```text
.
├── outputs/
│   └── true_vs_pred_sbp.png     # Ground truth vs predicted SBP visualization
├── project.ipynb               # Main Jupyter notebook (preprocessing, features, models)
├── fds_report.pdf              # Detailed project report and documentation
└── README.md                   # Project overview and instructions
