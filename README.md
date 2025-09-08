🤰 Maternal Health Risk Prediction

📌 Introduction

📝 Problem statement: Predict the maternal health risk category (low, mid, high) for pregnant women using clinical features (age, blood pressure, blood sugar, body temperature, heart rate, etc.).

🎯 Objective: Build and compare classification models to predict maternal health risk and identify important predictors for early intervention.

📊 Dataset: It uses a tabular dataset containing clinical measurements for pregnant women. Key features include Age, SystolicBP, DiastolicBP, BS (blood sugar), BodyTemp, HeartRate, and a target RiskLevel with categories: low risk, mid risk, high risk.

( Dataset taken from Kaggle. )

🔎 Steps of Analysis
1️⃣ Data Loading & Inspection

📥 Read dataset into DataFrame & view first rows

🔍 Check data types, missing values, basic stats

2️⃣ Data Cleaning & Preprocessing

 Handle missing values

Encode categorical target (RiskLevel)

Scale features (if needed)

Train/test split

3️⃣ Exploratory Data Analysis (EDA)

📦 Class distribution for RiskLevel

📈 Histograms & Boxplots → feature distributions & outliers

🔥 Correlation Heatmap → check multicollinearity

🎨 Pairplots/Scatter plots → class separation

4️⃣ Model Building

Trained multiple classification models: Logistic Regression, Decision Tree Classifier, Random Forest Classifier, Support Vector Classifier (SVC) 

For some models, multiple hyperparameter variants were evaluated (e.g. for Random Forest & Decision Tree).


5️⃣ Evaluation

📑 Metrics: Accuracy, Precision, Recall, F1-score

🟦 Confusion Matrices with plots

📊 Feature Importance (Random Forest)

📈 Results

Logistic Regression: 61% 

Decision Tree: 86% 

Random Forest: 87–88% (Best performer)

SVC: 67% 

🔎 Key Takeaways:

Overall findings: Random Forest performed best in these experiments (up to ~88% accuracy), meaning it made the fewest overall mistakes when predicting the three risk categories on the test set. Logistic Regression performed worst among the reported runs (61% accuracy), which suggests the relationship between features and risk level is not purely linear. 

Class-wise performance: The classification reports show that some classes (for example, mid risk) may have lower recall or f1-score in certain models — indicating those cases are harder for the model to correctly identify. The low-risk and high-risk classes generally achieved better precision/recall depending on the model.
Random Forest gave the best accuracy (~88%) 

📊 Explanation of Key Graphs

 Class Distribution Bar Chart → shows balance/imbalance

📈 Histograms & Boxplots → reveal skewness/outliers (e.g., BP extremes)

 Correlation Heatmap → detect multicollinearity

🎨 Pairplots → check feature separability by RiskLevel

Feature Importance (RF) → SystolicBP, Age, etc., most predictive

Confusion Matrix → shows which classes are confused (e.g., mid risk → low risk)

📏 Model Performance Metrics

Accuracy: 0.61, 0.86, 0.87, 0.88, 0.67

Precision: Correctness of positive predictions

Recall: Coverage of actual positives

F1-Score: Balance of precision & recall

💡 Insight: A high precision but low recall on high risk → model misses cases but avoids false alarms

🛠️ Technologies Used

 Python 3

📦 Libraries:

pandas, numpy → data handling

matplotlib, seaborn → visualization

scikit-learn → models & evaluation
