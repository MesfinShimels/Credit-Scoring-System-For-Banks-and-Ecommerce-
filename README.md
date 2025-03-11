Bank Credit Scoring System for E-commerce and Banking
Overview
This repository contains a complete implementation of a Credit Scoring System designed for banks and e-commerce platforms. The project is built using RFMS formalism — analyzing Recency (R), Frequency (F), Monetary (M), and Subscription Status (S) to classify customers into low-risk and high-risk groups. The system assigns credit scores based on behavioral patterns, empowering platforms to enable Buy Now, Pay Later (BNPL) services.
The model leverages machine learning techniques, including Random Forest, Weight of Evidence (WoE) binning, and risk probability estimation, to deliver an accurate credit risk assessment.
Business Objective
The goal is to automate credit scoring for e-commerce and banking platforms, helping businesses:
Reduce credit default risk.
Offer personalized credit limits.
Enable frictionless, instant credit approvals.
Improve customer segmentation.
Project Structure
.
├── dashboard/
│   └── app.py                     # Main dashboard application for visualization and model interaction
├── data/
│   ├── cleaned/                  # Cleaned datasets ready for modeling
│   └── raw/                      # Raw transactional data
│       ├── clean_data.csv
│       ├── final_df.csv
│       └── final_merged_data.csv
├── log/                          # Logging for data analysis and model training
│   ├── eda_analysis.log
│   └── rfms_classifier.log
├── logs/                         # Model evaluation logs
│   ├── model_evaluator_<timestamp>.log
├── model/
│   └── random_forest_model.pkl   # Trained Random Forest model
├── notebooks/
│   ├── bank_feature_engineering.ipynb
│   ├── Model_building.ipynb
│   └── WoE_estimator.ipynb       # Jupyter notebooks for development and experimentation
├── scripts/
│   ├── Bati_Bank_EDA.py          # EDA and feature exploration script
│   ├── bati_bank_feature_engineering.py
│   ├── calculate_RFMS_score.py   # RFMS score calculation
│   ├── model_development_scripts.py
│   └── WoE_evaluate.py           # WoE binning and evaluation
├── src/                         # Source code for the API or additional services
├── tests/                       # Unit and integration tests
├── .gitignore
├── random_forest_model.pkl      # Finalized machine learning model
├── README.md                    # Project documentation (this file)
└── requirements.txt             # Required packages and dependencies
Data
The project uses customer transaction data with the following key features:
TransactionId, AccountId, CustomerId: Unique identifiers.
Amount, Value: Transaction value and amount.
ProductId, ProductCategory: Details of purchased items.
SubscriptionId, PricingStrategy: Subscription and pricing details.
TransactionStartTime: Time of the transaction.
FraudResult: Label indicating fraud (if available).
Key Features
1. Exploratory Data Analysis (EDA)
Summary statistics, distribution plots, outlier detection.
Transaction patterns and customer segmentation.
2. Feature Engineering
Calculating RFMS scores.
Weight of Evidence (WoE) and Information Value (IV) for feature encoding.
Handling missing values and normalizing features.
3. Model Development
Training a Random Forest Classifier.
Hyperparameter tuning using GridSearchCV.
Model evaluation with metrics like Precision, Recall, AUC-ROC.
4. Model Deployment
Saving models as .pkl files.
Dashboard for visualizing customer credit scores.
API integration using FastAPI.
How to Run the Project
1.Clone the Repository:
git clone https://github.com/your-repo/Bank-Credit-Scoring-Model.git
cd Bank-Credit-Scoring-Model
1.Install Dependencies:
pip install -r requirements.txt
1.Run the Model Training Pipeline:
python scripts/model_development_scripts.py
1.Launch the Dashboard:
python dashboard/app.py
The dashboard will be accessible at http://localhost:5000.
Future Improvements
Add support for deep learning models.
Implement real-time transaction monitoring.
Expand dataset to include more behavioral features.
Contributors
Mesfin Shimelis
Collaborators — 
License
This project is licensed under the MIT License.