# Predicted Mood from Phone Activity

A data mining project that predicts a person's mood based on smartphone activity data collected from sensors and usage logs.

## Overview

This project explores the relationship between smartphone usage patterns and self-reported mood scores. Using the **StudentLife / mood-smartphone dataset**, machine learning and data mining techniques are applied to build a predictive model.

## Repository Structure

```
predicted_mood_from_phone_activity/
├── notebook.ipynb          # Main analysis & modelling notebook
└── README.md
```

> **Note:** The dataset (`dataset_mood_smartphone.csv`) is not tracked by git due to its size. See *Data* section below.

## Data

The initial dataset (`dataset_mood_smartphone.csv`) contains smartphone usage logs and self-reported mood scores from the StudentLife study. It consists of raw event logs for activities and sensor readings—such as screen time, calls, SMS, and app usage categories—recorded alongside user identifiers and timestamps. The raw dataset file is excluded from version control via `.gitignore`. To reproduce the analysis, place the CSV file in the project root before running the notebook.

| Column type | Examples |
|---|---|
| Identifiers | `id`, `time` |
| Mood (target) | `mood` (self-reported 1–10 scale) |
| Activity & sensors | `activity`, `screen`, `call`, `sms`, `appCat.*` |

## Getting Started

1. **Clone the repo**
   ```bash
   git clone <repo-url>
   cd predicted_mood_from_phone_activity
   ```

2. **Add the dataset**  
   Place `dataset_mood_smartphone.csv` in the project root.

3. **Install dependencies**  
   A standard scientific Python stack is required:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn jupyter
   ```

4. **Run the notebook**
   ```bash
   jupyter notebook notebook.ipynb
   ```

## Workflow

The analysis in the notebook (`notebook.ipynb`) follows a structured tabular modeling pipeline:

1. **Preprocessing & Aggregation**: The raw event log is aggregated into a daily user-level table. Outliers are clipped using the IQR rule, and variables are aggregated per day (e.g., summed for durations/counts, averaged for continuous features).
2. **Exploratory Data Analysis (EDA)**: Analysis of dataset statistics, post-aggregation missingness, and target class distributions.
3. **Feature Engineering**: Data is split chronologically into train, validation, and test sets. Tabular features are constructed using daily lags (1–3 days), a 3-day rolling mean, and within-user centering. Sparse columns are removed and remaining missing values are imputed.
4. **Classification Modeling**: Random Forest models are trained to predict next-day mood categories. This phase includes comparing different imputation methods and feature selection strategies (such as backward selection).
5. **Numerical Prediction**: A Random Forest regressor is trained on the same tabular features to predict the continuous next-day mood score.
6. **Evaluation**: Final models are evaluated on the held-out test set.

## Course

MSc Data Mining — University project.
