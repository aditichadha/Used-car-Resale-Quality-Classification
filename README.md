# Used-car-Resale-Quality-Classification

## Project Overview

This project aims to build a machine learning model that helps an auto-dealer make informed decisions when purchasing used cars at auctions. The model classifies whether a car will be a liability (1) or an asset (0) for the dealer based on historical data of cars bought at auctions.

## Problem Definition

An auto-dealer needs to make careful deliberations before buying used cars to avoid costly repairs, transportation costs, and market losses. Using historical auction data, this project attempts to predict whether a car will be an asset or a liability.

## Data Source

The dataset for this project was obtained from Kaggle and includes information on the wear and tear of cars bought at auctions. The dataset consists of 67,211 rows and 31 columns, including the target variable 'Class' which indicates if a car is a liability (1) or an asset (0).

- [Dataset Link](https://www.kaggle.com/datasets/ulrikthygepedersen/car-kick)

## Data Exploration

Initial data exploration involved checking for null values, understanding data distributions, and identifying important features. Key steps included:
- Removing redundant columns such as purchase date and vehicle year.
- Handling imbalanced target classes, where class 1 (liability) constitutes only about 10% of the dataset.
- Segregating numerical and categorical columns for appropriate analysis techniques.
- Evaluating the categories in categorical columns and removing those with high cardinality to reduce model complexity.

## Model Building

### Baseline Models

Several baseline models were built without any sampling techniques to serve as a starting point:
- Logistic Regression
- Decision Tree
- Random Forest
- K-Nearest Neighbors (KNN)
- XGBoost
- LightGBM

### Handling Imbalanced Data

To address the imbalanced dataset, two approaches were implemented:
- **Oversampling using SMOTE**: Synthetic Minority Oversampling Technique was used to generate new samples for the minority class.
- **Undersampling**: Reducing the size of the majority class to balance the class distribution.

### Model Evaluation and Selection

Models were evaluated based on the F1 Score, considering the trade-off between precision and recall. The final model chosen was the hyperparameter-tuned LightGBM classifier trained on the under-sampled data, as it provided the best performance.

## Performance Diagnostics and Evaluation

The final LightGBM model achieved the following metrics:
- **Accuracy**: ~63%
- **Precision**: 0.15
- **Recall**: 0.63
- **F1 Score**: 0.24
- **AUC**: 0.63

These metrics indicate the model's capability to correctly identify cars that are likely liabilities, despite the overall accuracy being moderate due to the imbalanced nature of the dataset.

## Conclusion

The project demonstrates that while handling imbalanced datasets is challenging, appropriate techniques such as undersampling and hyperparameter tuning can significantly improve model performance. The final model helps auto-dealers predict whether a used car will be a liability, aiding in better decision-making during auctions.

