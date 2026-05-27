# Patient Diet Program Analytics & Prediction System

A complete data science pipeline for analyzing patient outcomes in diet programs, identifying natural patient profiles, and predicting weight change after 6 months.

**Course:** Elementos de Inteligencia Artificial e Ciencia de Dados (EIACD) 2025/26  
**Institution:** Universidade da Beira Interior

## Project Overview

This project analyzes a healthcare dataset of 1,000 patients enrolled in 10 different diet programs, supervised by 20 nutritionists. The goal is to understand what factors predict weight loss success and provide actionable insights for nutritionists.

## Pipeline

| Task | Description | Output |
|------|-------------|--------|
| **Task 1** | Data Integration — merge 4 CSV tables into a unified dataset | `merged_dataset.csv` (2,523 rows) |
| **Task 2** | Data Cleaning — remove redundant columns, fix outliers, handle missing values | `cleaned_dataset.csv` (2,370 rows) |
| **Task 3** | Exploratory Data Analysis — distributions, correlations, categorical breakdowns | 11 visualization plots |
| **Task 4** | Unsupervised Learning — K-Means clustering to identify patient profiles | `clustered_dataset.csv`, `cluster_profiles.csv` |
| **Task 5** | Supervised Learning — predict weight change with 4 regression models | `model_comparison.csv`, feature importance |
| **Task 6** | Critical Discussion — synthesize findings and limitations | Documentation |

## Data

| File | Rows | Description |
|------|------|-------------|
| `patients.csv` | 1,000 | Demographics: sex, age, height, weight, BMI, smoking, sleep, motivation |
| `diets.csv` | 10 | Diet specs: type, macronutrient composition, sodium, fiber |
| `nutritionists.csv` | 20 | Nutritionist metadata: approach, experience, specialty |
| `outcomes.csv` | 2,523 | Program results: adherence, motivation during program, weight change at 6 months |

## Key Findings

- **Adherence is the strongest predictor** of weight loss (correlation: -0.67 with weight change)
- **Best model:** Random Forest achieves R² = 0.908, MAE = 1.62 kg on test set
- **4 natural patient clusters** identified via K-Means:
  - Low-motivation patients (worst outcomes: -13.75 kg)
  - Tall/heavy men (best outcomes: -27.41 kg)
  - High-BMI women (-23.70 kg)
  - Young, normal-weight patients (-21.56 kg)
- **Low-carb diets** outperform others (-24 kg avg vs -20 kg for Mediterranean)
- **Strict nutritionist approach** produces best results (-24 kg avg)

## How to Run

```bash
# Install dependencies
pip install pandas numpy scikit-learn matplotlib seaborn

# Run tasks sequentially
cd src
python task1_integration.py
python task2_cleaning.py
python task3_eda.py
python task4_clustering.py
python task5_prediction.py
```

## Project Structure

```
Project1/
├── data/                  # Raw input data (4 CSV files)
├── src/                   # Source code (5 Python scripts)
│   ├── task1_integration.py
│   ├── task2_cleaning.py
│   ├── task3_eda.py
│   ├── task4_clustering.py
│   └── task5_prediction.py
├── docs/                  # Task documentation (6 markdown files)
├── outputs/               # Generated outputs
│   ├── *.csv              # Processed datasets & model results
│   └── plots/             # 11 visualization PNGs
└── README.md
```

## Technologies

- Python 3.9+
- pandas, numpy — data manipulation
- scikit-learn — machine learning (K-Means, Linear Regression, KNN, Decision Tree, Random Forest)
- matplotlib, seaborn — visualization
