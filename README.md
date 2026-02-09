# Rainfall-Prediction-Improved-Accuracy-
Improved rainfall prediction system using Random Forest with SMOTE, cyclic wind direction encoding, feature selection, and hyperparameter tuning. Achieved 77% accuracy and 0.86 ROC-AUC, significantly improving recall, F1-score, and generalization compared to the baseline model.
---

## 📂 Dataset
- File: `Rainfall.csv`
- Records: 366
- Target Variable: `rainfall` (Binary: Yes / No)

### Features Used
- Pressure  
- Maximum Temperature  
- Temperature  
- Minimum Temperature  
- Dew Point  
- Humidity  
- Cloud Cover  
- Sunshine  
- Wind Direction  
- Wind Speed  

---

## 🛠️ Technologies Used
- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn  
- Imbalanced-learn (SMOTE)  

---

## ⚙️ Key Improvements Over Baseline Model

| Technique | Benefit |
|---------|--------|
SMOTE | Solved class imbalance without discarding real data |
Cyclic wind direction encoding | Preserved circular nature of wind direction |
Feature selection | Reduced noise and multicollinearity |
Hyperparameter tuning | Optimized bias–variance tradeoff |
Better evaluation metrics | Reliable performance on imbalanced data |

---

## 🌪️ Wind Direction Encoding
Wind direction is a cyclic feature (0° ≈ 360°).  
It is encoded using sine and cosine transformations:

winddir_sin = sin(θ)
winddir_cos = cos(θ)


This prevents incorrect distance interpretation by the model.

---

## ⚖️ Class Imbalance Handling
Instead of random downsampling (used in the baseline model), this version applies:

### ✅ SMOTE (Synthetic Minority Oversampling Technique)
- Retains all original samples
- Generates synthetic minority-class data
- Improves recall and F1-score

---

## 🧠 Feature Engineering & Selection
- Model-based feature selection using Random Forest
- Removed redundant and weak features
- Applied feature scaling for model stability and future extensibility

---

## 🤖 Machine Learning Model
### Tuned Random Forest Classifier
Hyperparameters optimized using GridSearchCV:
- Number of trees
- Maximum depth
- Minimum samples per split
- Leaf size
- Class weighting

---

## 📊 Model Performance (Actual Results)

### Classification Report
Class 0 (No Rain):
Precision: 0.63
Recall: 0.71
F1-score: 0.67

Class 1 (Rain):
Precision: 0.85
Recall: 0.80
F1-score: 0.82

Overall Accuracy: 77%
ROC-AUC Score: 0.86


---

## 📈 Performance Comparison

| Metric | Baseline Model | Improved Model |
|------|---------------|----------------|
Accuracy | ~68–70% | **77%** |
F1-score (Rain) | ~0.70 | **0.82** |
ROC-AUC | ~0.75 | **0.86** |
Generalization | Moderate | **Strong** |

✅ Clear improvement in recall, F1-score, and discrimination ability.

---

## 🧪 Prediction Support
The model supports:
- Single-input prediction
- Batch prediction
- Probability-based output

Predictions are generated using a fully consistent preprocessing pipeline saved via pickle.

---

## 🏆 Conclusion
This project demonstrates a complete evolution from a baseline machine learning model to an optimized, high-accuracy rainfall prediction system using industry-relevant ML practices and evaluation techniques.

---

## 🔮 Future Enhancements
- XGBoost / LightGBM integration
- Real-time weather API input
- Web deployment (Flask / Streamlit)
- Model monitoring and retraining
