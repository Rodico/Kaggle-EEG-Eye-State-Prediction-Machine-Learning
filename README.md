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
- Key finding: Weak individual correlations (max 0.064) indicated non-linear relationships

### 2. Data Preprocessing
- Train/test split (80/20)
- Feature scaling using StandardScaler
- No feature engineering required (raw sensor data was sufficient)

### 3. Model Development

#### Baseline: Logistic Regression
- **Accuracy**: 56.91%
- **Recall**: 79% (closed), 32% (open)
- **Issue**: Linear model couldn't capture complex sensor interactions

#### Final Model: Random Forest
- **Accuracy**: 92.16% (**+35% improvement**)
- **Recall**: 96% (closed), 88% (open)
- **Key advantage**: Captures non-linear patterns and feature interactions

## 📈 Results

| Model | Accuracy | Precision (Closed) | Recall (Closed) | Precision (Open) | Recall (Open) |
|-------|----------|-------------------|-----------------|------------------|---------------|
| Logistic Regression | 56.91% | 0.57 | 0.79 | 0.57 | 0.32 |
| **Random Forest** | **92.16%** | **0.90** | **0.96** | **0.95** | **0.88** |

### Feature Importance
Top 3 most predictive sensors:
1. **O1** (11.7%) - Occipital left (visual cortex)
2. **P7** (10.5%) - Parietal left  
3. **F7** (9.1%) - Frontal left

The dominance of O1 (visual processing region) validates the biological relevance of the model.

## 💡 Key Insights

1. **Model Selection Matters**: Weak individual feature correlations indicated the need for ensemble methods
2. **Healthcare Metrics**: Balanced recall across classes is critical - accuracy alone is insufficient
3. **Domain Validation**: Feature importance aligned with neuroscience (visual cortex sensors most predictive)
4. **Real-world Applicability**: High accuracy on both classes makes this suitable for production systems

## 🛠️ Technologies Used

- **Python 3.x**
- **pandas** - Data manipulation
- **scikit-learn** - ML models and preprocessing
- **matplotlib/seaborn** - Visualization
- **Google Colab** - Development environment

## 🚀 How to Run
```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/eeg-eye-state-prediction.git

# Install dependencies
pip install pandas numpy scikit-learn matplotlib seaborn

# Run the notebook
jupyter notebook eeg_eye_state_classifier.ipynb
```

## 📝 Future Improvements

- Implement deep learning approaches (LSTM/CNN for time-series patterns)
- Cross-validation for more robust performance estimates
- Hyperparameter tuning using GridSearchCV
- Real-time prediction pipeline for live EEG data
- Explore explainability methods (SHAP values)

## 🎓 Lessons Learned

- Always start with a simple baseline model to understand the problem
- Weak correlations don't mean bad data - they indicate non-linear relationships
- Feature importance analysis helps validate model decisions with domain knowledge
- Healthcare applications require balanced performance across all classes

*This project was developed as part of preparing for ML engineering roles in healthcare AI.*
