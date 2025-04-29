This project focuses on detecting fraudulent credit card transactions using machine learning algorithms. The dataset is provided by Kaggle and contains a set of features that can help distinguish between fraudulent and legitimate transactions. The goal is to train a model that can effectively predict fraud while handling class imbalance and ensuring optimal model performance.

Dataset-
The dataset used in this project consists of 284,807 credit card transactions, including 492 fraudulent ones (0.172% fraud). The data contains the following features:
Time: Time elapsed since the first transaction.
V1-V28: Principal components derived from PCA transformation (anonymized features).
Amount: Transaction amount.
Class: Target variable where 1 represents fraudulent transactions and 0 represents legitimate ones.

Approach
1. Data Exploration-
Loaded the dataset and performed exploratory data analysis (EDA) to examine data types, missing values, and the distribution of fraudulent and non-fraudulent transactions.
Visualized the class distribution to highlight the class imbalance, with fraudulent transactions accounting for only 0.172% of the dataset.

2. Data Preprocessing-
Handling Class Imbalance: Used the SMOTE technique to oversample the minority class (fraudulent transactions) to balance the class distribution and improve model performance.

Feature Engineering:
Scaling: Applied StandardScaler to the Amount feature to standardize it.
Hour Feature: Extracted the hour of the day from the Time feature to help the model identify time-based patterns.
Amount Percentile: Created a new feature based on the transaction amount, categorized into different percentiles to capture the relative spending behavior.
Amount Spender Category: Introduced a categorical feature based on the transaction amount to classify transactions as "low_spender_risky", "mid_spender_safe", or "high_spender_risky".
One-Hot Encoding: Applied one-hot encoding to the amount_spender_category feature to convert categorical values into numerical representations suitable for modeling.

3. Data Visualization-
Visualized the class distribution to further highlight the imbalance.
Analyzed the fraud rate across different amount_percentile categories to explore patterns that could indicate fraudulent behavior.

4. Model Development-
Split the dataset into training (80%) and testing (20%) sets.
Trained multiple machine learning models, including Logistic Regression, Random Forest, and XGBoost, to predict fraudulent transactions.
Evaluated the models using several performance metrics such as:
Accuracy
Precision
Recall
F1-Score

5. Model Evaluation-
The models were evaluated based on their ability to handle class imbalance and their performance on detecting fraudulent transactions, which is critical due to the rarity of fraud in the dataset.
Cross-validation was used to evaluate model stability and prevent overfitting.
