# Survival Analysis of ICU Patients Using Real-World EHR Data (MIMIC-IV)

1. Project Overview

-This project demonstrates an end-to-end real-world evidence (RWE) survival analysis using the publicly available MIMIC-IV electronic health records (EHR) dataset.
-The objective is to analyze short-term mortality risk among ICU patients and identify clinically relevant risk factors using classical survival analysis techniques.
-The project is designed to reflect real-world workflows in pharmaceutical and clinical data science, including cohort construction, censoring, and interpretable modeling.

2. Research Question

What patient characteristics are associated with increased short-term mortality among adult ICU patients?

Specifically:
-How does survival probability differ by sex and age?
-Which clinical variables are significantly associated with time-to-death?
-Can a Cox proportional hazards model provide interpretable risk estimates?

3. Data Source

-Dataset: MIMIC-IV (Medical Information Mart for Intensive Care)
-Provider: PhysioNet
-Type: Real-world hospital EHR data
-Population: Adult ICU patients (≥18 years)
-Access: Credentialed access approved by PhysioNet
-Raw data are not included in this repository due to data use restrictions.

4. Cohort Definition

Inclusion criteria:
-Adult patients (age ≥ 18)
-First ICU admission
-ICU length of stay ≥ 24 hours

Outcome definition:
-Event: All-cause in-hospital death
-Time-to-event: Time from ICU admission to death or discharge
-Censoring: Patients discharged alive

5. Methods
5.1 Data Processing

-Efficient querying of large EHR tables using DuckDB
-Cohort construction and feature engineering in R

5.2 Survival Analysis

-Kaplan–Meier survival curves
-Log-rank tests
-Cox proportional hazards regression

5.3 Tools

-R: tidyverse, survival, survminer, DBI
-Database: DuckDB (SQL executed within R)

6. Repository Structure
mimic-iv-survival/
│
├─ R/
│   ├─ 00_connect_db.R        # Database connection
│   ├─ 01_build_cohort.R     # Cohort construction
│   ├─ 02_feature_engineering.R
│   ├─ 03_kaplan_meier.R     # KM analysis
│   ├─ 04_cox_model.R        # Cox regression
│
├─ derived/                  # Processed cohort data (not raw EHR)
├─ figures/                  # Survival plots
├─ README.md

7. Key Results (Summary) # 수정하기 

-Survival probability decreases substantially with increasing age
-Male patients show higher mortality risk compared to female patients
-Cox regression identifies age and selected clinical indicators as significant risk factors
Detailed results and visualizations are available in the figures/ directory.

8. Ethical Considerations

-All analyses were conducted on de-identified patient data
-Data access was granted through PhysioNet credentialing
-The study complies with the MIMIC-IV Data Use Agreement

9. Relevance to Pharmaceutical & Clinical Data Science

This project reflects common tasks in:
-Real-world evidence (RWE) studies
-Epidemiology and outcomes research
-Health economics & outcomes research (HEOR)
-Clinical data science roles in pharmaceutical companies

It emphasizes:
-Transparent cohort definition
-Proper handling of censoring
-Interpretable statistical modeling

10. Author

Jinhee Kim
Marketing Scientist / Data Scientist
M.Sc. Statistics, LMU Munich
GitHub: github.com/Jinheekimmi
M.Sc. Statistics, LMU Munich
GitHub: [your-github-profile]
