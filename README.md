# Fraud Detection with Drift Monitoring

## Overview

This project implements a fraud detection system using supervised and unsupervised machine learning techniques. It also includes statistical data drift monitoring to identify changes in transaction data that may affect model performance.

## Objectives

- Detect fraudulent credit card transactions.
- Handle highly imbalanced fraud data.
- Compare supervised and unsupervised machine learning approaches.
- Evaluate models using precision, recall, F1-score and PR-AUC.
- Detect changes in data distributions using statistical drift detection.
- Simulate data drift and generate automated drift alerts.
- Analyze the trade-off between false positives and false negatives.

## Dataset

The project uses the Credit Card Fraud Detection dataset from Kaggle.

Dataset source:

https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

The dataset contains anonymized credit card transactions with a highly imbalanced target variable.

The dataset itself is not included in this repository. Download `creditcard.csv` from Kaggle and upload it to the project environment before running the notebook.

## Machine Learning Models

### Random Forest

A supervised Random Forest classifier is used to learn patterns associated with fraudulent transactions. Class weighting is used to address class imbalance.

### Isolation Forest

Isolation Forest is used as an unsupervised anomaly detection approach. It identifies unusual transactions without directly using fraud labels during training.

## Model Evaluation

The models are evaluated using:

- Precision
- Recall
- F1-score
- PR-AUC
- Confusion matrix

The project also examines false positives and false negatives because they have different consequences in fraud detection.

## Data Drift Monitoring

The dataset is divided into reference and current transaction periods.

The Kolmogorov-Smirnov statistical test is used to compare feature distributions between these periods.

A feature is considered to show statistically significant drift when:

`p-value < 0.05`

An automated alert is generated when drift is detected.

## Simulated Drift

To test the monitoring system, transaction amounts are artificially increased in a copy of the current dataset.

The drift detector is then run again to verify that the system can identify the artificial distribution change.

## Technologies Used

- Python
- Google Colab
- Pandas
- NumPy
- Scikit-learn
- SciPy
- Matplotlib

## Project Structure

```text
Fraud-Detection-Drift-Monitoring/
├── fraud_detection.ipynb
├── README.md
└── requirements.txt
