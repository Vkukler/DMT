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

The raw dataset file (`dataset_mood_smartphone.csv`) is excluded from version control via `.gitignore`. To reproduce the analysis, place the CSV file in the project root before running the notebook.

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

## Methods

- Exploratory data analysis & visualisation
- Feature engineering from time-series smartphone logs
- Classification / regression models to predict mood scores
- Model evaluation (cross-validation, RMSE, accuracy)

## Course

MSc Data Mining — University project.
