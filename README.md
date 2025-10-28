# Fault Detection and Classification

## Project Overview
This project implements multiple machine learning models to detect and classify electrical faults in a three-phase power system using current (Ia, Ib, Ic) and voltage (Va, Vb, Vc) data. The workflow involves data preprocessing, model training using various algorithms, evaluation of accuracy/error metrics, and visualization for model comparison.
All experiments were performed using Python in Google Colab.

## Dataset

Two datasets were used:

detect_dataset.xlsx → Used for fault detection (binary classification: fault/no-fault)

classData.csv → Used for fault classification (multi-class: A, B, C, G)

### Features:

Ia, Ib, Ic, Va, Vb, Vc

### Targets:

Detection target: Output (S) → 0 = No Fault, 1 = Fault

Classification target: A, B, C, G → fault type identifiers

## Methodology
1️⃣ Data Preprocessing
 - Missing columns were dropped (dropna(axis=1)).
 - Data split into train (67%) and test (33%) sets using train_test_split().
 - Normalized class distribution visualized using Seaborn bar plots.

<p align="center">   
<img width="630" height="470" alt="image" src="https://github.com/user-attachments/assets/923b6f38-194d-42c7-916d-d39660ad8fea" />
</p>

2️⃣ Models Implemented
The following models were trained and evaluated separately for detection and classification:
<div align="center">

| Model | Accuracy (Detection) | Accuracy (Classification) |
|:--|:--:|:--:|
| Linear Regression | 0.0179 | 0.0324 |
| Logistic Regression | 0.7384 | 0.3156 |
| Polynomial Regression | 0.9536 | 0.9451 🥇|
| Multi-Layer Perceptron (MLP) | 0.9917 🥉| 0.8829 🥈|
| Naive Bayes | 0.9806 | 0.7969 |
| Decision Tree | 0.9939 🥇 | 0.8674 🥉|
| Support Vector Machine (SVM) | 0.9821 | 0.3168 |
| K-Nearest Neighbors (KNN) | 0.9924 🥈 | 0.8247 |

</div>

## Model Comparison

The project concludes with graphical comparisons of:

1️⃣ **Detection Model Comparison**:
<p align="center">
<img width="1314" height="461" alt="image" src="https://github.com/user-attachments/assets/8ac29765-2004-4b8f-9b75-901e0d6252c6" />
</p>

2️⃣ **Classification Model Comparison**:
<p align="center">
<img width="1314" height="461" alt="image" src="https://github.com/user-attachments/assets/8c872590-d4de-4574-8e36-a8e2b0a898a7" />
</p>

These visualizations clearly demonstrate that Decision Tree, MLP, and KNN models achieved the highest detection accuracy, while Polynomial Regression provided the best balance for classification.

## Results Summary

#### Detection Model Performance

→ $${\color{green}Best}$$: Decision Tree with 99.39% Accuracy, 0.0058 MSE 

→ $${\color{red}Worst}$$: Linear Regression with 1.8% Accuracy, 0.2437 MSE


### Classification Model Performance 

→ $${\color{green}Best}$$: Polynomial Regression with 94.5% Accuracy, 0.0134 MSE

→ $${\color{red}Worst}$$: Logistic Regression with 31.6% Accuracy, 37.83 MSE

## Conclusion

This project provides a comparative analysis of multiple ML models for fault detection and classification in electrical systems.
It demonstrates that nonlinear and ensemble-based approaches (Decision Tree, MLP, Polynomial Regression) outperform simple linear models, offering higher accuracy and reliability for real-world power system fault analysis.
