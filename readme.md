# 🔍 Predicting Explosive Weapon Types in Conflict Zones (2025 Dataset)

## 📘 Overview

This project uses incident-level data from 2025 to predict the **type of explosive weapon** used in violent attacks in conflict-affected regions such as Ukraine and the Occupied Palestinian Territories. The goal is to support humanitarian efforts by identifying patterns in weapon use based on features such as location, sector affected, and reported perpetrator.

All data, code, and visualizations referenced in this project are included locally in this repository. No external or third-party files are required.

---

## 👥 Stakeholders

The intended stakeholders for this work are:
- United Nations agencies
- International Committee of the Red Cross (ICRC)
- NGOs and humanitarian responders

These organizations can use the insights generated here to anticipate weapon use trends, improve protective strategies, and support data-driven advocacy on the use of explosive weapons in populated areas.

---

## 🎯 Problem Statement

This project aims to build a machine learning model that predicts the **type of explosive weapon** used in an incident based on:
- Country and region
- Sector affected (e.g. health, education)
- Reported perpetrator
- Geographical precision

This supports more informed humanitarian responses and fills in gaps where weapon types may be missing or underreported.

---

## 📂 Dataset

- **File used:** `2025-explosive-weapons-incident-data.xlsx`
- **Source fields include:**
  - `Country`, `Region`, `Admin 1`
  - `Sector Affected`, `Reported Perpetrator`
  - `Weapon Type` (target variable)
  - Coordinates and contextual impact fields

---

## 🔍 Data Understanding and Preparation

Key steps in preparing the data included:
- Dropping columns with over 80% missing values (e.g., `Aid Workers Killed`, `Food Security`)
- Removing rows where the target column `Weapon Type` was missing
- Label and one-hot encoding categorical variables
- Filling missing data with `"Unknown"` or appropriate defaults

---

## 📥 Import Datasets

The dataset was imported from the local file:

```plaintext
2025-explosive-weapons-incident-data.xlsx
```


## 📊 Model Evaluation

Two models were trained and evaluated to predict the type of explosive weapon used.
### ✅ Logistic Regression

    Accuracy: ~77%

    Weighted Avg F1-score: 0.67

    Macro Avg F1-score: 0.11

    Performs well on the majority class but fails on rare classes due to class imbalance

### 🌲 Decision Tree Classifier

    Accuracy: ~84%

    Weighted Avg F1-score: 0.83

    Macro Avg F1-score: 0.29

    Better handles class imbalance and gives more balanced performance across classes

### 🔁 Model Comparison

|Metric                       |Logistic Regression                |Decision Tree     |
|-----------------------------|-----------------------------------|------------------|
|Accuracy                     |       0.77	                      | 0.84             |
|Weighted F1-score            |   0.67           	              | 0.83             |
|Macro F1-score               |	     0.11	                      | 0.29             |
|Class Imbalance           	  |   Poor handling	                  | Better handling  |

## ✅ Conclusion:
The Decision Tree outperforms Logistic Regression across all metrics, especially in predicting minority classes, making it more suitable for this task.