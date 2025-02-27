**Title of the project: Revenue Analysis Based on Online Shopping Patterns.**
Name: Dhanya Vijayakumar
Organization: Entri Elevate
Date: [28/02/2025]
1. **Overview of Problem Statement:** E-commerce businesses need accurate revenue prediction to optimize marketing strategies, manage inventory, and improve customer experience. This project aims to build a robust machine learning model that analysis customer purchase data and identifies critical features that insights whether a user session on an e-commerce website will result in revenue generation.
2. **Objective:** To develop a model using machine learning techniques to uncover significant behavioral and transactional patterns that impact revenue.
3.** Data Description:**
3.1 **Source:**__ https://archive.ics.uci.edu/dataset/468/online+shoppers+purchasing+intention+dataset 
3.2 **Features:**__
3.2.1 Session-based features: PageValues, BounceRates, ExitRates, ProductRelated, Administrative, Informational, SpecialDay
3.2.2 User-specific features: OperatingSystems, Browser, Region, TrafficType, VisitorType, Weekend, Month
3.2.3 Target variable: Revenue (Binary: 0 = No purchase, 1 = Purchase)
4. **Data Collection:** Dataset is imported from Google Drive in Excel format and initial analysis performed to understand data distribution, relationships, and potential patterns.
5. **Data Preprocessing - Data Cleaning:**
✔ Checked for missing values (No missing values detected).
✔ Removed 125 duplicate rows to ensure data integrity.
✔ Addressed outliers using Interquartile Range (IQR) method for features like BounceRates, ExitRates, PageValues, ProductRelated, Administrative.
✔ Transformed skewed data using log, square root, and Yeo-Johnson transformations.
6. **Exploratory Data Analysis (EDA): **
**6.1 Univariate Analysis:**__
✔ Histograms, Boxplots for numerical features.
✔ Count plots for categorical variables.
**6.2 Bivariate Analysis:**__
✔ Scatter plots for Revenue vs. PageValues, BounceRates, ExitRates, ProductRelated.
✔ Heatmap correlation matrix.
✔ Pair plots for key features.
✔ Line plots for Monthly & Weekly revenue trends.
_Findings:_
PageValues & ProductRelated features are the strongest predictors of revenue.
BounceRates & ExitRates have weak negative correlation with revenue.
Revenue peaks in November and on weekends.
7. **Feature Engineering:**
✔ One-hot encoding applied to categorical features like Month, VisitorType.
✔ Label encoding applied where necessary.
8. **Feature Selection:**
✔ Used Random Forest Feature Importance to rank features.
✔ Dropped ProductRelated (high correlation with ProductRelated_Duration) and BounceRates (high correlation with ExitRates) to remove redundancy.
9. **Feature Scaling:**
✔ Standardization (Z-score normalization) for Linear Regression & SVR.
✔ Min-Max Scaling for Neural Networks.
10. **Split Data into Training and Testing Sets:**
✔ 80% training, 20% testing split using train_test_split().
11. **Build the ML Model:**
✔ Implemented five regression models:
Linear Regression (Baseline)
Random Forest Regressor
XGBoost Regressor
Support Vector Regressor (SVR)
Neural Network Regressor (MLP Regressor)
12. **Model Evaluation:**
Regression Metrics Used:
✔ Mean Squared Error (MSE)
✔ Mean Absolute Error (MAE)
✔ Root Mean Squared Error (RMSE)
✔ R² Score
Model	                 MSE	        MAE	        RMSE	     R² Score
Linear Regression	     0.1003	      0.2024	    0.3168	   0.2776
Random Forest	         0.0758	      0.1451	    0.2753	   0.4542
XGBoost	               0.0768	      0.1436	    0.2772	   0.4468
SVR	                   0.1319	      0.2200	    0.3631	   0.0507
Neural Network	       0.0832	      0.1666	    0.2885	   0.4007
✔ Random Forest & XGBoost outperformed all other models regarding R² Score and lower RMSE.
13 **Hyperparameter Tuning:**
✔ XGBoost Optimized with RandomizedSearchCV
✔ Random Forest Optimized with GridSearchCV
**Best Parameters for XGBoost:**__
✔ subsample: 0.8, n_estimators: 100, max_depth: 5, learning_rate: 0.05, gamma: 0.1, colsample_bytree: 0.6
Best Parameters for Random Forest:
✔ bootstrap: True, max_depth: 5, min_samples_leaf: 2, min_samples_split: 2, n_estimators: 200
✔ Final Evaluation After Tuning:
Model	              MSE	    MAE	    RMSE	  R² Score
Tuned XGBoost	      0.0734	0.1482	0.2710	0.4714
Tuned Random Forest	0.0731	0.1436	0.2704	0.4735
✔ Random Forest slightly outperformed XGBoost post-tuning.
14. **Test with Unseen Data:**  Models tested on unseen data, results validated using regression metrics.
15. **Conclusion:**
Random Forest & XGBoost are the best models for revenue prediction.
PageValues & ProductRelated interactions are the key drivers for purchases.
Higher exit and bounce rates negatively affect revenue.
Revenue peaks on weekends & in November, indicating seasonal sales patterns.
**Limitations:**__
It is needed to explore more behavioural features to improve model accuracy.


