Project Title

Maternal Health Risk Prediction

Introduction

Problem statement: Predict the maternal health risk category (low, mid, high) for pregnant women using clinical features (age, blood pressure, blood sugar, body temperature, heart rate, etc.).

Objective: Build and compare classification models to predict maternal health risk and identify important predictors to help with early intervention.

Dataset description: The notebook uses a tabular dataset containing clinical measurements for pregnant women. Key features include Age, SystolicBP, DiastolicBP, BS (blood sugar), BodyTemp, HeartRate, and a target RiskLevel with categories: low risk, mid risk, high risk.

Steps of Analysis

Data loading and initial inspection

Read the dataset into a DataFrame and view the first few rows.

Check data types, missing values, and basic statistics.

Data cleaning & preprocessing

Handle missing values (if present).

Encode categorical target variable (RiskLevel).

Feature scaling where required for some models.

Train/test split.

Exploratory Data Analysis (EDA)

Class distribution for RiskLevel.

Univariate summaries (histograms/boxplots) for numeric features.

Pairwise relationships/correlation heatmap to check collinearity and relationships with the target.

Model building

Trained multiple classification models (as executed in the notebook):

Logistic Regression

Decision Tree Classifier

Random Forest Classifier

Support Vector Classifier (SVC)

For some models, multiple hyperparameter variants were evaluated (e.g. different Random Forest setups).

Evaluation

Used classification_report (precision, recall, f1-score) and accuracy.

Generated confusion matrices and plotted important visualizations.

Explanation of Results:

 Model accuracies observed are as follows:

Logistic Regression: 61% accuracy

Decision Tree: ~86% accuracy (two evaluated variants)

Random Forest: 87% and 88% accuracy (two hyperparameter runs)

SVC (Support Vector Classifier): 67% accuracy

Overall findings: Random Forest performed best in these experiments (up to ~88% accuracy), meaning it made the fewest overall mistakes when predicting the three risk categories on the test set. Logistic Regression performed worst among the reported runs (61% accuracy), which suggests the relationship between features and risk level is not purely linear.

Class-wise performance: The classification reports show that some classes (for example, mid risk) may have lower recall or f1-score in certain models — indicating those cases are harder for the model to correctly identify. The low risk and high risk classes generally achieved better precision/recall depending on model.

Explanation of Key Graphs / Plots

(Insights into plots)

Class distribution bar chart: Count of samples in each RiskLevel category.

Pattern visible: The three classes are present with counts (approx. split shown). If one class is much larger, it may bias models.

Meaning: If classes are imbalanced, consider sampling strategies or metric choice (e.g., macro F1).

Histograms / Boxplots for each feature plotted: Distribution of values for Age, SystolicBP, etc.

Pattern visible: Outliers or skewness in features (e.g., some high BP values).

Meaning: Outliers may need handling; skewed features may benefit from transformation.

Correlation heatmap plotting: Pearson correlation coefficients between numeric features.

Pattern visible: If two features are highly correlated, this shows multicollinearity, which affects the model. To get rid of that, one feature can be dropped or combined.

Pairplot / Scatter plots colored by RiskLevel plotting: Pairwise scatter plots with points colored by the target class.

Pattern visible: Whether classes are separable in feature space; overlapping indicates harder classification.

Meaning: Visual cue for model choice — if separable, simpler models may suffice.

Feature importance (Random Forest) plotting: Importance score of each feature from the Random Forest model.

Pattern visible: Some features (e.g., SystolicBP or Age) may contribute more to predictions.

Meaning: Useful for domain insights — prioritise monitoring of high-importance features clinically.

The Confusion Matrix is plotted: Counts of true vs predicted classes.

Pattern visible: Which classes are most often confused (e.g., mid risk predicted as low risk).

Meaning: Helps identify where model mistakes cluster and guides error analysis or class-specific improvements.

Model Performance Metrics:

Accuracy: Fraction of correctly predicted samples. ( Values found by different models: 0.61, 0.86, 0.87, 0.88, 0.67 in various runs.)

Precision (per class): When the model predicted a class, how often it was correct.

Recall (per class): Of all actual instances of a class, how many the model detected.

F1-score: Harmonic mean of precision and recall — useful when class balance matters.

Use the per-class precision/recall/F1 to understand specific class behaviour — e.g., a high precision but low recall on high risk would mean the model is conservative (few false alarms) but misses some actual high-risk patients.

Technologies Used

Python 3

Libraries:

pandas, numpy (data handling)

matplotlib, seaborn (visualization)

scikit-learn (models, metrics)
