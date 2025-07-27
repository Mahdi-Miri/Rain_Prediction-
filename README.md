# Predicting next-day rain in Australia with advanced analytics.

This project aims to predict the probability of rainfall in Australia for the next day using meteorological data and advanced machine learning models. This is a binary classification task where the output is a "Yes" or "No" prediction for rainfall.

🎯 Project Goal
The main objective of this project is to build an accurate and reliable machine learning model to predict next-day rainfall based on the current day's weather data. Such predictions can be valuable for planning in various sectors, including agriculture, travel, and other weather-dependent activities.

💾 Dataset
The data used in this project comprises over 10 years of daily weather records from numerous weather stations across Australia.


Rows: 145,460 




Columns: 23 


Data Source: Kaggle Weather Dataset 

Key features in this dataset include minimum and maximum temperatures, rainfall amount, humidity, wind speed and direction, atmospheric pressure, and sunshine hours. 

🛠️ Project Methodology
This project followed a comprehensive pipeline, from data analysis to model building and evaluation.

1. Exploratory Data Analysis (EDA)

Feature Identification: Numerical and categorical features were identified and separated. 


Missing Value Analysis: Missing values in each column were calculated and analyzed. Columns with more than 35% missing data (e.g., 

Sunshine, Evaporation) were dropped. 


Feature Distribution Analysis: Histograms were plotted to examine the distribution of numerical features. 


Outlier Detection: Outliers were identified using boxplots and Z-scores, particularly for the Rainfall feature. 


Correlation Analysis:


Numerical Features: The Pearson correlation matrix was used to investigate linear relationships. High correlation was observed between different temperature readings and between pressure readings at different times of the day. 



Categorical Features: Cramér's V statistic was used to analyze the association between categorical features. 


2. Preprocessing & Feature Engineering
Handling Missing Values:


Mean Imputation: Used for normally distributed features like temperatures. 


Median Imputation: Applied to skewed features such as pressure, humidity, and wind speed. 


Mode Imputation: Used for categorical features like wind direction. 


Handling Outliers: To mitigate the impact of outliers, their values were capped using the IQR method. A log transform (

log(1+x)) was applied to the Rainfall feature. 

Feature Engineering:

New features like 

HumidityDiff (difference between morning and afternoon humidity), TempRange (daily temperature range), and WindDiff (difference in wind speeds) were created. 

Temporal features such as month and year were extracted from the date column. 

Encoding:


Cyclical Features: Sine and cosine transformations were used for wind direction features to preserve their circular nature. 


Categorical Features: LabelEncoder was used for features like Location and RainToday. 

3. Model Development and Evaluation
Several models were trained and evaluated for this classification task:


Logistic Regression 


Random Forest 


XGBoost (tuned with Optuna) 


Artificial Neural Network (ANN) 


ANN with Embeddings for categorical features 


TabNet 

Ensemble Models:


Weighted Voting Ensemble: Combined predictions from XGBoost and ANN models. 

Models were evaluated using metrics such as 

Accuracy, Precision, Recall, F1-Score, and the ROC-AUC curve
