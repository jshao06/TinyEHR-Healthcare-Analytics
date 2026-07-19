## TinyEHR Healthcare Analytics & Machine Learning

### Overview

This project demonstrates a healthcare analysis using the TinyEHR synthetic electronic health record (EHR) dataset. The project uses ***SQLite***, **pandas**, ***seaborn***, and **scikit-learn** to transform relational healthcare data into patient-level machine learning datasets, visualize the data distribution and build predictive models.

It mainly contains two study cases ***diabetes prediction*** and ***hypertension prediction***. The second case is the primary one, covering the complete data science lifecycle from database exploration to model evaluation.

---

### Objectives

- Build a local SQLite healthcare database from TinyEHR
- Explore the database schema and data quality
- Extract patient-level features using SQL
- Engineer clinical features for machine learning
- Train and compare multiple classification models
- Evaluate model performance
- Analyze model result

---

### Technologies

| Category | Technologies |
|-----------|--------------|
| Programming | Python 3 |
| Database | SQLite |
| Query Language | SQL |
| Data Analysis | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn, plotly |
| Machine Learning | Scikit-learn |
| Development | Jupyter Notebook |

---

### Project Structure

```text
TinyEHR-Healthcare-Analytics
│
├── data/
│   ├── tinyehr_mimic_format.db (Not included due to the size over the GitHub file upload limit)
│   ├── hypertension_features.csv
│   └── tinyehr_diabetes_dataset.csv
│
├── images/
│   ├── 03_Hypertension_Database_Exploration-Admissions.png
│   ├── 03_Hypertension_Database_Exploration-Age.png
│   ├── 03_Hypertension_Database_Exploration-Gender.png
│   └── 03_Hypertension_Database_Exploration-Rows for Each Table.png
|
├── notebooks/
│   ├── 01_Read_Data_from_TinyEHR.ipynb
│   ├── 02_Build_a_Diabetes_Dataset_with_TinyEHR.ipynb
│   ├── 03_Hypertension_Database_Exploration.ipynb
│   ├── 04_Hypertension_Feature_Engineering.ipynb
│   └── 05_Hypertension_Prediction.ipynb
│
└── README.md
```

---
### Workflow

```
TinyEHR Database
        │
        ▼
SQLite Database
        │
        ▼
Database Exploration
        │
        ▼
SQL Feature Extraction
        │
        ▼
Feature Engineering
        │
        ▼
Machine Learning
        │
        ▼
Model Evaluation
```

---

### Notebook Summary

#### 1) 01_Read_Data_from_TinyEHR.ipynb

- Build a local SQLite database
- Connect and read data using Python
- Inspect tables
  
  
#### 2) 02_Build_a_Diabetes_Dataset_with_TinyEHR.ipynb

Create a patient-level diabetes dataset from multiple relational tables.

- SQL query
- Aggregation
- Dataset generation
- Some feature engineering

  
#### 3) 03_Hypertension_Database_Exploration.ipynb

Explore the healthcare database before feature engineering.

- Database schema
- Table relationships
- Missing values
- Data distributions
- Patient demographics

  
#### 4) 04_Hypertension_Feature_Engineering.ipynb

Converts relational healthcare data into a machine learning dataset.

- Patient demographics
  - ***age***
  - ***gender***
- Laboratory aggregation
  - ***glucose_max***
  - ***glucose_min***
  - ***creatinine_mean***
  - ***sodium_mean***
- Blood pressure vitals aggregation
  - ***systolic_mean***
  - ***systolic_max***
  - ***diastolic_mean***
  - ***diastolic_max***
- Admissions aggregation
  - ***num_admissions***
  - ***first_admission_year***
  - ***latest_admission_year***
  - ***avg_stay_days***
- Diagnoses aggregation
  - ***num_diagnosis***
- Prescriptions count
  - ***num_medication***
- Missing value assessment
- Correlation heatmap
- Feature distribution plot

  
#### 5) 05_Hypertension_Prediction.ipynb

Machine learning workflow:

- Load data and review EDA
- Data preprocessing
- Train multiple machine learning models
- Models comparison
- Hyperparameters tuning
- Best model and its evaluation

Models evaluated:

- Logistic Regression
- Decision Tree
- Random Forest

Evaluation metrics:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

---

#### Results

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|-------|---------:|----------:|-------:|---:|--------:|
| Logistic Regression | ***`0.67`*** | 0.684176 | ***`0.707273`*** | 0.667399 | ***`0.748222`*** |
| Random Forest | 0.61 | 0.688312 | 0.667273 | 0.626502 | 0.678697 |
| Decision Tree | 0.66 | ***`0.725397`*** | 0.663636 | ***`0.680605`*** | 0.662929 |

For this dataset, Logistic Regression achieved the highest Accuracy, Recall and ROC-AUC, indicating the strongest overall performance.
