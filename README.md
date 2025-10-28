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

2️⃣ Models Implemented
The following models were trained and evaluated separately for detection and classification:
| Model | Accuracy (Detection) | Accuracy (Classification) |
|:--|:--:|:--:|
| Linear Regression | 0.7384 | 0.0324 |
| Logistic Regression | 0.9536 | 0.316 |
| Polynomial Regression | 0.9914 | 0.945 |
| Multi-Layer Perceptron (MLP) | 0.9806 🥉| 0.886 |
| Naive Bayes | 0.9942 | 0.797 |
| Decision Tree | 0.9821 🥇 | 0.865 |
| Support Vector Machine (SVM) | 0.9924 | 0.317 |
| K-Nearest Neighbors (KNN) | 0.9924 🥈 | 0.8246 |

📊 Model Comparison

The project concludes with graphical comparisons of:

Accuracy vs. Model

Error (MSE) vs. Model

These visualizations clearly demonstrate that Decision Tree, MLP, and KNN models achieved the highest detection accuracy, while Polynomial Regression provided the best balance for classification.

🧮 Key Functions
from sklearn.metrics import accuracy_score, mean_squared_error
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression, LogisticRegression
from sklearn.neural_network import MLPClassifier
from sklearn.tree import DecisionTreeClassifier
from sklearn.naive_bayes import GaussianNB
from sklearn.svm import SVC, LinearSVC
from sklearn.neighbors import KNeighborsClassifier

🧾 Results Summary

Detection Model Performance:

Best: Decision Tree → 99.4% Accuracy, 0.0058 MSE

Worst: Linear Regression → 1.8% Accuracy, 0.2437 MSE

Classification Model Performance:

Best: Polynomial Regression → 94.5% Accuracy, 0.0134 MSE

Worst: Logistic Regression → 31.6% Accuracy, 37.83 MSE

🚀 Technologies Used

Python 3.11

Scikit-Learn

NumPy & Pandas

Matplotlib & Seaborn

Google Colab

📈 Conclusion

This project provides a comparative analysis of multiple ML models for fault detection and classification in electrical systems.
It demonstrates that nonlinear and ensemble-based approaches (Decision Tree, MLP, Polynomial Regression) outperform simple linear models, offering higher accuracy and reliability for real-world power system fault analysis.
