# dynamic-pricing-optimization-ml
Machine Learning-based Dynamic Pricing and Demand Optimization system that predicts demand and recommends profit-maximizing prices using XGBoost and SHAP.


Dynamic Pricing & Demand Optimization (ML)
Overview

This project builds a machine learning pipeline to predict product demand and recommend optimal pricing for profit maximization.

The goal is simple:
Determine the best price that maximizes profit without significantly reducing demand.



Key Features
Demand forecasting using XGBoost
Feature engineering:
Lag demand features
Rolling averages (7-day, 14-day)
Integration of:
Competitor pricing
Discounts
Profit-based price optimization
SHAP-based model interpretability
Price sensitivity analysis

Tech Stack
Python
Pandas, NumPy
Scikit-learn
XGBoost
SHAP
Matplotlib, Seaborn


Project Workflow
1. Data Preparation
Merged multiple datasets (orders, products, inventory, pricing, discounts)
Performed data cleaning and validation
Ensured proper time alignment (avoiding data leakage)

2. Feature Engineering
Lag features (previous demand values)
Rolling averages for demand trends
Price-related features (average price, competitor price, discount %)
Time-based features (day, month)

3. Model Training
Model used: XGBoost Regressor
Time-based train-test split (no random shuffling)
Hyperparameter tuning using randomized search
4. Evaluation
Metrics:
MAE (Mean Absolute Error)
RMSE (Root Mean Squared Error)
Compared against baseline models

5. Model Explainability
Used SHAP values to interpret predictions
Identified key drivers:
Price
Competitor price
Demand history

6. Price Optimization
Simulated demand across different price points

Calculated profit using:

Profit = (Price - Cost) × Demand

Selected price that maximizes expected profit

7. Price Sensitivity Analysis
Analyzed demand vs price behavior
Studied profit variation across pricing strategies


Results & Insights
Price and competitor pricing significantly impact demand
Demand history (lag features) is a strong predictor
In some cases, increasing price improved profit without major demand drop
Model performs reasonably without external factors (e.g., promotions, seasonality)


Limitations
No external data (holidays, marketing campaigns)
Assumes historical patterns remain consistent
Limited real-world constraints (inventory, customer behavior changes)


Future Improvements
Add external features (seasonality, events)
Use advanced time-series models (LSTM, Prophet)
Deploy as a real-time pricing system
Explore reinforcement learning for dynamic pricing

Notes

This project demonstrates a structured ML pipeline for pricing decisions. It is not production-ready but reflects how data-driven pricing strategies can be developed and evaluated.

