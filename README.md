# Social Media Advertisement Performance – Machine Learning Project

## Project Overview
This project analyzes and predicts user interactions using the **Social Media Advertisement Performance** dataset, a synthetic yet realistic dataset simulating engagement with advertising campaigns on platforms such as Facebook and Instagram.  
All data were generated using Python libraries such as **Faker** and **NumPy**, ensuring complete privacy with no personally identifiable information (PII).

The dataset follows a relational structure of four tables:
- **Users** – demographic and interest-based profiles (age, gender, country, interests)  
- **Campaigns** – strategic campaign details (budget, duration, start and end dates)  
- **Ads** – creative assets linked to campaigns with targeting parameters  
- **Ad Events** – user interactions ranging from Impression to Purchase  

The goal is to build a **supervised classification model** that predicts the type of user event (`event_type`) based on demographic, campaign, and ad-level features.

---

## Objectives
- Identify the main factors that influence user engagement.  
- Predict the likelihood of active engagement (Click, Like, Share, Comment, Purchase).  
- Provide actionable insights for improving digital marketing strategies.  
- Evaluate model performance using Accuracy, Precision, Recall, F1-score, and AUC.

---

## Data Preparation
All four dataset tables were merged into one consistent and clean dataset.  
Key preprocessing steps included:
- Removing duplicates and inconsistent demographic entries.  
- Converting date columns and creating temporal features (year, month, hour, is_weekend).  
- Merging all datasets into `df_after_prep.csv`.  

---

## Exploratory Data Analysis (EDA)
EDA was performed using **AutoViz**, **Seaborn**, and **Matplotlib**.  
Main findings:
- The dataset is **highly imbalanced** (≈85% “Impression” events).  
- Majority of users are aged **18–34**, with higher engagement among female users.  
- Peak engagement occurs **early morning and late evening**.  
- Numeric features (age, budget, duration) show weak correlation with engagement type.  

---

## Feature Engineering and Selection
- Created a new variable `daily_budget` (budget per campaign day).  
- Transformed user and campaign interests into binary variables.  
- Applied feature selection using **Lasso**, **Ridge**, **Random Forest**, and **Gradient Boosting**.  
- Retained 23 most consistent and meaningful predictors.  

---

## Model Selection and Fine Tuning
Seven models were tested:
`DecisionTree`, `RandomForest`, `XGBoost`, `GradientBoosting`, `AdaBoost`, `LogisticRegression`, `SVM`

**SMOTE** was used to balance the training set.  
**XGBoost** achieved the best results:
- Mean F1 ≈ 0.82  
- Mean AUC ≈ 0.89  
- Stable across 5-Fold Cross-Validation  

Final model selection was based on its balance of **recall, precision, and robustness**.

---

## Key Insights
- **Engagement Timing:** Higher conversion before/after work hours.  
- **Targeting Precision:** Health, Finance, and Gaming audiences show the strongest alignment.  
- **Model Threshold Calibration:** Small threshold shifts significantly affect recall and precision.  
- **Reusable Framework:** The final pipeline supports retraining and integration into dashboards or APIs.

---

## Deployment and Beneficiaries
The predictive model can be integrated into **campaign dashboards or APIs** to:
- Predict engagement likelihood in real time.  
- Support **audience segmentation** and **budget optimization**.  
- Allow retraining with new data for ongoing improvement.  

Beneficiaries include digital marketing teams, data analysts, and campaign strategists aiming to improve ROI and engagement efficiency.

---

## Tools and Libraries
- **Python, pandas, NumPy, scikit-learn, imbalanced-learn, XGBoost, Matplotlib, Seaborn, Folium, AutoViz**
- **Environment:** Jupyter Notebook / Google Colab

---

## Author
**Ron Levi**  
Sheba Medical Center – Data Science & Machine Learning Track  
[Dataset Source (Kaggle)](https://www.kaggle.com/datasets/alperenmyung/social-media-advertisement-performance)
