Asteroid Panic Level Classification
This repository contains a Jupyter Notebook that builds a binary classification machine learning model to predict whether an approaching asteroid would cause “high panic” (panic level ≥ 4) or “low panic”, based on a publicly available asteroid dataset from Kaggle.
Overview
The notebook processes asteroid data, performs data cleaning, feature engineering, and trains two models:
-Logistic Regression
-Random Forest Classifier
The goal is to classify asteroids into binary panic categories derived from the original panic_level column.
Key steps include:
Loading and exploring the dataset

Handling missing values (e.g., filling NaNs in Sentry-related fields with defaults like 0 or -10)

Creating a binary target variable (panic_binary)

Feature selection (distance, velocity, magnitude, Sentry metrics, etc.)

Data splitting, scaling, and model training

Evaluation using accuracy, precision, recall, F1-score, and confusion matrix

Feature importance analysis for the Random Forest model

Dataset

The dataset is from Kaggle: NASA Asteroid Impact Dataset. It includes features such as:

Asteroid designation and full name

Close approach date, distance (AU), velocity (km/s), absolute magnitude

Risk metrics (e.g., Sentry impact probability, Palermo scale)

Derived columns like panic_level, threat_category, and panic_verdict

The notebook loads the CSV file:

/kaggle/input/nasa-asteroid-impact-dataset/asteroid_dataset_20251019.csv

Requirements

Python: 3.12+

Libraries: pandas, numpy, scikit-learn, matplotlib

Install dependencies using:

pip install pandas numpy scikit-learn matplotlib

Usage
1. Clone the repository:
git clone https://github.com/beakal882/asteroid-panic-level-classification.git

2. Open the notebook:
jupyter notebook asteroid-panic-level-classification.ipynb

3. Run the cells sequentially to load data, train models, and view results.

Notes

The dataset spans from 2020 to 2100, including both past and predicted future events.

Binary classification threshold: Panic level ≥ 4 → high panic (1), else low panic (0)

Model performance:

Random Forest generally outperforms Logistic Regression but may overfit

Hyperparameters tuned: max_depth=20, min_samples_leaf=35

Visualizations include a target balance bar plot
