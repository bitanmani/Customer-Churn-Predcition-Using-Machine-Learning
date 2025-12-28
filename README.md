📊 Customer Churn Prediction using Machine Learning
🧩 Overview

This project builds an end-to-end customer churn prediction pipeline using the Telco Customer Churn dataset.
The objective is to identify customers likely to leave the service and highlight the main drivers influencing churn through machine-learning–based predictive modeling and explainable data analysis.

🗂️ Dataset

Source: WA_Fn-UseC_-Telco-Customer-Churn.csv

Rows: 7,043

Features: 21 (demographic, contract, service, and billing attributes)

Target Variable: Churn (Yes = 1, No = 0)

🧠 Workflow
1️⃣ Data Preprocessing

Removed redundant customerID column

Cleaned and converted TotalCharges from string to float

Encoded categorical features using LabelEncoder

Balanced classes using SMOTE to address minority churn samples

2️⃣ Exploratory Data Analysis (EDA)

Explored key relationships and customer behavior patterns:

Shorter tenure strongly correlates with higher churn

Month-to-month contracts show ~3× higher churn than yearly contracts

High-charge segments churn more frequently

Add-on services like Tech Support and Online Security reduce churn likelihood

3️⃣ Modeling

Three supervised learning algorithms were evaluated:

Decision Tree Classifier 🌳

Random Forest Classifier 🌲

XGBoost Classifier ⚡

Best performer: Random Forest (highest test accuracy and recall)

4️⃣ Evaluation Metrics

Accuracy

Precision, Recall, F1-Score

Confusion Matrix

5️⃣ Model Persistence & Inference

Models and encoders were serialized with pickle for reuse.
Inference pipeline allows prediction on new customer records in production.

🧰 Tools & Technologies
| Category      | Tools Used                                                                          |
| ------------- | ----------------------------------------------------------------------------------- |
| Language      | Python                                                                              |
| IDE           | Jupyter Notebook                                                                    |
| Libraries     | pandas, numpy, seaborn, matplotlib, scikit-learn, imbalanced-learn, xgboost, pickle |
| Visualization | Matplotlib, Seaborn                                                                 |
| ML Techniques | SMOTE, Decision Trees, Random Forests, XGBoost, Train-Test Split                    |
| Metrics       | Accuracy, Precision, Recall, F1-Score, Confusion Matrix                             |

🧑‍💻 Skills Demonstrated

Data Cleaning & Feature Engineering

Class Imbalance Handling (SMOTE)

Supervised Learning & Model Evaluation

Cross-Validation and Performance Comparison

Model Serialization & Deployment-ready Inference

Data Visualization & Insight Communication

🚧 Challenges Faced

| Challenge                             | Resolution                                           |
| ------------------------------------- | ---------------------------------------------------- |
| Blank strings in `TotalCharges`       | Converted blanks to numeric 0.0 before float casting |
| Severe class imbalance (26% churn)    | Applied SMOTE oversampling on training data          |
| Risk of overfitting                   | Used ensemble methods and validation split           |
| Encoding consistency during inference | Saved `LabelEncoder` mappings in `.pkl` files        |

💡 Key Insights

Month-to-month contracts, high monthly charges, and lack of tech support services are the strongest churn indicators.

Bundling long-term contracts with security or support plans may reduce churn by over 15%.

Automated churn prediction can guide retention campaigns and targeted discounts.

🔮 Future Improvements

Implement OneHotEncoder with ColumnTransformer for cleaner pipelines

Add Stratified K-Fold CV and Hyperparameter Tuning (GridSearchCV)

Incorporate ROC-AUC and Precision-Recall AUC metrics

Integrate SHAP or LIME for explainability

Deploy as an API using FastAPI/Streamlit

Build an interactive Power BI dashboard for business insights

🧾 Concepts Covered

Binary Classification

Feature Encoding

Class Imbalance Correction

Ensemble Learning

Model Evaluation Metrics

Model Deployment Workflow
