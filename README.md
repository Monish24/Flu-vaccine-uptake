# Flu-vaccine-uptake ( Competition link : https://www.drivendata.org/competitions/66/flu-shot-learning/leaderboard/ )
Prediction and Analysis of H1N1 and Seasonal Flu Vaccine Uptake
Table of Contents
Abstract
Data Analysis
Merging Data
Detecting Missing Values
Data Pre-processing
Addressing Missing Value
Feature Engineering
Classification
Approach 1 (Monish Shah)
Findings from Data Analysis
Data Pre-processing Results
Model Performance and Results
Conclusion
Future Improvements
Abstract <a name="abstract"></a>
This GitHub repository contains the code and analysis for predicting and analyzing H1N1 and seasonal flu vaccine uptake using machine learning techniques. The dataset used for this analysis is the National 2009 H1N1 Flu Survey (NHFS) sponsored by the National Centre for Immunisation and Respiratory Diseases. The goal is to understand the factors influencing vaccine uptake and develop predictive models for vaccination behavior.

Data Analysis <a name="data-analysis"></a>
Merging Data <a name="merging-data"></a>
To ensure the training features and target labels are correctly combined, we merged the training data and labels using 'respondent id' as the primary key.

Detecting Missing Values <a name="detecting-missing-values"></a>
We conducted a thorough analysis of missing values to identify potential issues with the data. Key findings regarding missing values in various features were identified:

![image](https://github.com/Monish24/Flu-vaccine-uptake/assets/54630644/ded0b53b-6718-45fd-a809-9b84ad30c4de)

doctor recc h1n1 and doctor recc seasonal: Both features had 2160 missing values.
health insurance: This feature had the highest number of missing values (12,274).
education, income poverty, marital status, rent or own, employment status, employment industry, and employment occupation: These features were related to the socio-economic background of respondents and had missing values, indicating incomplete data.
We also explored correlations between features with missing values to guide imputation methods effectively.

Data Pre-processing <a name="data-pre-processing"></a>
Addressing Missing Values <a name="addressing-missing-values"></a>
We employed various methods to address missing values:

Categorical and ordinal columns with missing values were filled with 'Missing'.
Numerical columns with missing values were imputed with -1.
Feature Engineering <a name="feature-engineering"></a>
We performed feature engineering, including:

Creating a new feature called vaccine efficacy mean by aggregating mean values of efficacy columns.
Generating an interaction feature called h1n1 concern knowledge interaction to capture combined effects on the target variable.
Classification <a name="classification"></a>
We applied classification techniques, including ensemble methods, to predict vaccine uptake:

Utilized models like XGBoost, LGBM, CatBoost, and GBM.
Employed ensemble methods to combine model predictions for robustness and accuracy.
Evaluated models using the mean area under the receiver operating characteristic curve (AUC) with 5-fold cross-validation.
Findings from Data Analysis <a name="findings-from-data-analysis"></a>
Key features with missing values were identified.
Correlation matrices revealed relationships among features with missing values.
Insights were gained into the potential impact of certain features on vaccination behavior.
Data Pre-processing Results <a name="data-pre-processing-results"></a>
We evaluated different methods to fill missing values and found that filling categorical and ordinal features with 'Missing' and numerical features with -1 yielded the best results.
Model Performance and Results <a name="model-performance-and-results"></a>
AUC scores for models, including LGBoost, XGBoost, CatBoost, GBM, and the ensemble, were calculated.
XGBoost outperformed other models for seasonal vaccination prediction, while CatBoost performed best for H1N1 vaccination prediction.
The ensemble approach achieved a high AUC score of 0.8637, demonstrating robust and balanced predictions.

![image](https://github.com/Monish24/Flu-vaccine-uptake/assets/54630644/496b52ff-3a6f-46fd-8610-722e859fc79b)

Conclusion <a name="conclusion"></a>
In conclusion, our study analyzed and predicted H1N1 and seasonal flu vaccine uptake using machine learning. Key findings included the importance of doctor recommendations and respondents' perceptions of vaccine risk and efficacy in predicting vaccine uptake. Vulnerable populations, such as those aged 65 and above or with annual incomes below $75,000, were more likely to get vaccinated.

![image](https://github.com/Monish24/Flu-vaccine-uptake/assets/54630644/c82b7479-1b9c-4001-94ba-0b322a562ad4)
![image](https://github.com/Monish24/Flu-vaccine-uptake/assets/54630644/00f59df8-43b8-4bc7-a8f7-936b2c7f2c69)


Future Improvements <a name="future-improvements"></a>
We suggest the following future improvements:

Combining imputation methods for better handling of missing data.
Hyperparameter tuning with different sets for each model in the ensemble.
Training models on diverse datasets to create a more robust ensemble.
These recommendations aim to enhance model performance and our understanding of factors contributing to prediction errors for more reliable predictions.
