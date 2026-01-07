# EEG Eye State Prediction using Machine Learning

Predicting eye state (open/closed) from EEG brain wave data using ensemble methods. Achieved 92% accuracy by identifying non-linear feature interactions across 14 sensor channels.

## 🎯 Project Overview

This project demonstrates building a binary classifier for biomedical signal data, with applications in:
- Fatigue detection systems
- Driver alertness monitoring  
- Brain-computer interfaces
- Accessibility technology for individuals with motor impairments

## 📊 Dataset

- **Source**: EEG Eye State Dataset (UCI ML Repository)
- **Size**: 14,980 samples
- **Features**: 14 EEG sensor readings (AF3, AF4, F3, F4, F7, F8, FC5, FC6, T7, T8, P7, P8, O1, O2)
- **Target**: Binary classification (0 = eyes closed, 1 = eyes open)
- **Balance**: 55% closed, 45% open

## 🔬 Methodology

### 1. Exploratory Data Analysis
- Checked data quality (no missing values)
- Analyzed feature distributions and correlations
- Key finding: Weak individual correlations (max
