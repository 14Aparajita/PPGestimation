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

## Repository Structure

```text
.
├── outputs/
│   └── true_vs_pred_sbp.png     # Ground truth vs predicted SBP visualization
├── project.ipynb               # Main Jupyter notebook (preprocessing, features, models)
├── fds_report.pdf              # Detailed project/report documentation
└── README.md                   # Project overview and documentation
