# Treatment-Resistant Schizophrenia (TRS) Predictive Model

A machine learning project that predicts Treatment-Resistant Schizophrenia (TRS) from multimodal clinical data, including laboratory parameters, genetic markers, neuroimaging features, and demographic information.

Developed as part of the *Introduction to Machine Learning* (IAA) course at Universitat Politecnica de Catalunya (UPC), and submitted to a Kaggle competition on TRS prediction.

---

## Overview

Treatment-Resistant Schizophrenia (TRS) affects a subset of patients with schizophrenia who do not respond adequately to standard antipsychotic treatments. Early identification is clinically valuable, as it enables timely escalation to alternative therapies.

This project frames TRS identification as a binary classification problem: predict whether a patient will exhibit treatment resistance (TRS=1) or respond to standard treatment (NTRS=0).

---

## Dataset

The dataset originates from *Nature npj Schizophrenia (2021)* and was made available through Kaggle. The training set is moderately imbalanced (NTRS: 6,162 / TRS: 2,838; ratio ~2.17), covering demographic, laboratory, genetic, and neuroimaging features.

---

## Methodology & Model Architecture
The project explored three different machine learning models: Support Vector Machines (SVM), XGBoost, and Logistic Regression. 

After a comparative analysis, **Logistic Regression** was selected. Despite achieving similar performance metrics to SVM and XGBoost (macro F1 differences of less than 1.5%), it provided the optimal balance between performance, computational simplicity, and clinical interpretability. 

The final architecture is a **custom Logistic Regression implemented from scratch** using mini-batch gradient descent. It incorporates L2 regularization, positive class weighting to handle the imbalance, early stopping, and `GridSearchCV` for hyperparameter tuning.

---

## Results

- Cross-validation Macro F1: **0.5790 ± 0.0179**
- Validation Macro F1 (threshold 0.55): **0.5876**
- Kaggle external test Macro F1: **0.57**
- ROC-AUC: **0.63** | PR-AUC: **0.42**

Strongest predictor: `Initial_response` (coefficient = -0.457).

---

## Limitations and Ethical Considerations

Model assumes linear relationships, has moderate discriminative capacity, and has not undergone clinical validation. It must not be used for diagnosis or therapeutic decisions.

---

## References

- [Kaggle Competition](https://www.kaggle.com/competitions/trs-prediction-iaa-2024-25q1) | [Dataset source](https://www.nature.com/articles/s41537-021-00170-0) | [scikit-learn](https://scikit-learn.org/stable/modules/linear_model.html)

---
