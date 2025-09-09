# Coffee Roaster Quality Prediction

# Project Overview

This project focuses on predicting coffee roaster quality using sensor and environmental data. It applies the full machine learning pipeline, from data exploration to productionization.

The main objectives were:

1. Explore sensor & quality data through EDA.

2. Perform data preprocessing (missing values, outliers, scaling).

3. Build and evaluate multiple regression models.

4. Apply hyperparameter tuning to optimize top models.

5. Draw business insights to improve roasting consistency.

# Exploratory Data Analysis (EDA)

1. Shape & data types: Verified dataset dimensions, numerical sensor data, and target quality variable.

2. Univariate analysis: Plotted distributions & boxplots of sensors and quality. Identified skewness and outliers.

3. Bivariate analysis: Correlation matrix and scatterplots showed weak linear trends but strong non-linear patterns.

4. Insights: Tree-based models expected to perform better than linear ones.

# Data Preprocessing

1. Missing value treatment: Dropped/replaced missing values (<5%).

2. Outlier treatment: Detected via boxplots; capped extreme values where necessary.

3. Data leakage check: Ensured no overlap between train/test splits.

# Model Building

We built 8 regression models:

1. Linear Regression

2. Ridge Regression

3. Lasso Regression

4. Decision Tree

5. Random Forest

6. Bagging Regressor

7. Gradient Boosting

8. HistGradientBoosting

 #Model Evaluation (Baseline)

Evaluation was performed using 5-fold CV (RMSE & R²).

Key Results:

1. RandomForest: Best performer (RMSE ≈ 5.24, R² ≈ 0.898).

2. Bagging DTR: Strong results (RMSE ≈ 5.78, R² ≈ 0.875).

3. DecisionTree: Moderate (RMSE ≈ 7.78, R² ≈ 0.774).

4. Linear models: Performed poorly (R² ≈ 0.02 or worse).

Insight: Dataset exhibits non-linear patterns, making tree ensembles more suitable.

# Hyperparameter Tuning

We tuned the top 3 models (RandomForest, Bagging, DecisionTree) using randomized search with smaller grids for efficiency.

1. RandomForest showed the most improvement, reducing variance and stabilizing predictions.

2. Boosting methods, though weaker at baseline, are expected to improve with more tuning.

# Final Model Selection

1. Chosen Model: RandomForest

2. Reasoning: Lowest RMSE, highest R², stable across folds, and interpretable feature importances.

3. Test Set Performance: Strong generalization confirmed.

# Productionization

The final RandomForest model was deployed via a Scikit-learn pipeline, ensuring:

1. Automatic preprocessing

2. Consistent feature scaling

3. Reproducibility for new unseen data

# Business Insights & Conclusions

1. Quality prediction is best explained by non-linear interactions in sensor readings.

2. RandomForest provides accurate & stable predictions, making it suitable for real-time quality monitoring.

3. Sensor calibration and monitoring of chambers can further enhance process optimization.

# Repository Structure
📦 Coffee-Roaster-Quality
 ┣ 📜 README.md
 ┣ 📜 Roasters.csv              # Dataset
 ┣ 📜 notebook.ipynb            # Full Google Colab notebook
 ┣ 📜 requirements.txt          # Dependencies
 ┗ 📂 models/
    ┗ 📜 final_randomforest.pkl # Production model

# Tech Stack

Python (Pandas, NumPy, Matplotlib, Seaborn)

Scikit-learn (Regression, Ensemble, Pipelines)

Google Colab (development environment)

# How to Run

Clone the repository

git clone https://github.com/yourusername/Coffee-Roaster-Quality.git
cd Coffee-Roaster-Quality


Install dependencies

pip install -r requirements.txt


Run the notebook in Google Colab or Jupyter

# Project Outcome

This project demonstrates how machine learning can be used for process optimization in coffee roasting. With accurate prediction of quality, businesses can:

Maintain consistent quality standards

Reduce waste from failed roasts

Improve customer satisfaction
