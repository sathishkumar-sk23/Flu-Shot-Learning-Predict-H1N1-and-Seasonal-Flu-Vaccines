### 🧬 Vaccine Prediction (DrivenData Competition)

This project was developed as part of the **[DrivenData Flu Shot Learning: Predict H1N1 and Seasonal Flu Vaccines](https://www.drivendata.org/competitions/66/flu-shot-learning/)** competition. The goal is to predict the likelihood of individuals receiving H1N1 and seasonal flu vaccines using survey data.

---

### Project Structure

```bash
├── data/
│   ├── submission_format.csv
│   ├── test_set_features.csv
│   ├── training_set_features.csv
│   └── training_set_labels.csv
│
├── model/
│   ├── final_columns.pkl              # Final column order used in model training
│   ├── gradientboosting_h1n1.pkl      # Trained GradientBoosting model for H1N1
│   ├── xgboost_seasonal.pkl           # Trained XGBoost model for Seasonal
│   └── label_encoders.pkl             # LabelEncoders used for consistent preprocessing
│
├── notebooks/
│   ├── VaccinePrediction_Analysis.ipynb # Data cleaning, analysis 
│   └── VaccinePrediction_Modeling.ipynb # Preprocessing, Model training, evaluation and submission
│
├── submission_data/
│   └── submission.csv                 # Final predictions for submission
│
└── README.md                          # Project overview and guide
```

---

### Objective

Predict the probability that an individual received the **H1N1 vaccine** and the **seasonal flu vaccine** based on:
- Demographic information
- Opinions on vaccines and risks
- Health conditions

---

### Models Used

| Vaccine Type | Model Used          | ROC-AUC Score |
|--------------|---------------------|----------------|
| H1N1         | Gradient Boosting    | 0.8649         |
| Seasonal     | XGBoost              | 0.8651         |

> Final submission AUROC: **0.8600**

---

### Evaluation Metric

**ROC-AUC (Receiver Operating Characteristic - Area Under Curve)**  
This metric evaluates the model's ability to distinguish between the classes.

---

### How to Run

1. Clone the repo and install dependencies  
2. Run `notebooks/VaccinePrediction_Modeling.ipynb` to:
   - Preprocess the data
   - Load models
   - Generate prediction probabilities
   - Save submission

---

### Submission Format

CSV with three columns:
```csv
respondent_id,h1n1_vaccine,seasonal_vaccine
0,0.234,0.876
1,0.567,0.443
...
```

---

### Final Thoughts

- Carefully matched train-test features using saved encoder and column order
- Tuned models using GridSearchCV
- Maximized ROC-AUC through hyperparameter optimization

---
