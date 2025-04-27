
# Titanic Survival Prediction Using Logistic Regression

## Project Overview
This project is a part of a virtual internship at Codsoft and involves predicting Titanic passenger survival using logistic regression. The dataset, containing information such as passenger age, gender, ticket class, fare, and survival status, serves as the foundation for this analysis. Using SAS Visual Analytics, the project showcases data preprocessing, feature engineering, and the application of logistic regression to build a predictive model. It also includes insightful visualizations that reveal survival trends across different features.



### Problem Statement

Use the Titanic dataset to build a model that predicts whether a
 passenger on the Titanic survived or not. This is a classic beginner
 project with readily available data.
 The dataset typically used for this project contains information
 about individual passengers, such as their age, gender, ticket
 class, fare, cabin, and whether or not they survived.

#### Dataset Description

Dataset used:
- The source of the data is from codsoft
- Columns feature :- PassengerId: Unique ID for each passenger.
- Survived: Target variable (0 = Did not survive, 1 = Survived).
- Pclass: Ticket class (1 = First, 2 = Second, 3 = Third).
- Sex, Age, Fare, etc.

##### Steps in the Project

Step 1: Data Loading
- Import the Titanic dataset into SAS Visual Analytics. Ensure the columns (Survived, Sex, Age, Pclass, etc.) are loaded correctly and formatted appropriately.

Step 2: Data Preprocessing
- Handle Missing Values:- Use imputation techniques (e.g., mean for Age, "Unknown" for Cabin).

- Encode Categorical Variables:- Convert Sex, Embarked, etc., into numerical formats (e.g., binary or one-hot encoding).

- Feature Scaling (if necessary):- Normalize columns like Fare for better model performance.


Step 3: Feature Selection
- Identify the most relevant features for predicting survival (Pclass, Sex, Age, Fare, etc.).
- Drop irrelevant or redundant columns (e.g., Name, Ticket, PassengerId).


Step 4: Model Building
- Use logistic regression to predict survival (Survived as the target variable).- Logistic regression calculates probabilities for survival based on the input features.
- Add Survived in Response.
- Add Age, SibSp, Parch, Fare in Continuous effects.
- Add Sex, Embarked, Pclass in Classification effects. 

Step 5: Model Training
- Split the data into training and testing sets .
- Train the logistic regression model on the training data, allowing it to learn relationships between predictors and the target variable.

Step 6: Model Testing
- Use the testing dataset to evaluate the model’s accuracy and predictive power.
- Generate metrics such as:- Accuracy
- Confusion Matrix
- Precision, Recall, F1-score
- ROC Curve (AUC)

Step 7: Scatter Plot
- Drag Scatter Plot object
-Add Age and Frequency in Measure.
-Add Sex in Color.

Step 8: Interpret Results
- Examine regression coefficients, odds ratios, and p-values to understand the importance of predictors.
- Identify key survival trends, e.g., higher survival rates for women and first-class passengers.

Step 9: Visualization
- Create graphs to illustrate:- Predicted probabilities.
- Confusion matrix for performance evaluation.
- Survival patterns based on features like Pclass, Sex, Age, and Fare.


# Insights

# Model accuracy:

For this model, the accuracy in the TRAIN partition at the cutoff of 0.5 is 0.78.

Accuracy is the proportion of observations that are correctly classified as either an event or non-event, calculated at various cutoff values. Cutoff values range from 0 to 1, inclusive, in increments of 0.01. At each cutoff value, the predicted target classification is determined by whether P_Survived1, which is the predicted probability of the event "1" for the target Survived, is greater than or equal to the cutoff value. When P_Survived1 is greater than or equal to the cutoff value, then the predicted classification is the event, otherwise it is a non-event. When the predicted classification and the actual classification are both events (true positives) or both non-events (true negatives), the observation is correctly classified. If the predicted classification and actual classification disagree, then the observation is incorrectly classified. Accuracy is calculated as (true positives + true negatives) / (total observations).

Snap of Model Accuracy:

![Image](https://github.com/user-attachments/assets/ed482bce-4d8b-4836-9942-5fdb441237ca)

# Model Confusion Matrix:

The confusion matrix plot displays the number of observations predicting each response level. A greater number of observations where the observed level and predicted level are the same indicates a better model. For this data, the percentages of each observed value that are correctly predicted are as follows: 0 - 86.08% and 1 - 71.18%.

Snap of Confusion Matrix:

![Image](https://github.com/user-attachments/assets/7a1d1ada-b0da-476a-ac87-49284e2fe3e3)
# Model F1 Score:

For this model, the F1 score on the TRAIN partition at a cutoff of 0.5 is 0.677. The F1 score balances precision and recall, which are derived from the confusion matrix at different cutoffs (ranging from 0 to 1 in steps of 0.01). Predictions are classified as events if the predicted probability (P_Survived1) meets or exceeds the cutoff. The confusion matrix records true positives (TP), false positives (FP), false negatives (FN), and true negatives (TN). Precision is calculated as TP / (TP + FP), and recall (sensitivity) as TP / (TP + FN).

Snap of F1 Score:

![Image](https://github.com/user-attachments/assets/49847627-bec4-4df5-9423-32bc313ab378)
# Model ROC Curve:

The ROC curve plots sensitivity (true positive rate) against 1-specificity (false positive rate), based on confusion matrix values calculated across various cutoff points. The KS Cutoff line marks the cutoff (at 0.55) where the difference between sensitivity (0.594) and 1-specificity (0.084) is greatest for the TRAIN partition. At each cutoff (ranging from 0 to 1), a prediction is classified as an event if the predicted probability (P_Survived1) meets or exceeds the cutoff. Confusion matrices show true positives (TP), false positives (FP), false negatives (FN), and true negatives (TN). Sensitivity = TP / (TP + FN), while 1-specificity = FP / (TN + FP). A ROC curve closer to the upper-left corner suggests a better model, while a diagonal curve indicates random performance.

Snap of ROC Curve:
![Image](https://github.com/user-attachments/assets/46e112c0-01a3-4051-860a-dbd7f9ab3268)

# Key Trends in the Scatter Plot
- Children's Survival:- Younger passengers (e.g., children under 10) are likely clustered closer to Survived = 1, indicating higher survival rates.

- Adults' Survival:- Adults may show mixed outcomes, with some points near Survived = 0 and others near Survived = 1. You might observe a higher proportion of survival for certain subgroups (e.g., females or first-class ticket holders.

# Model Conclusion:

Sex: Women (Sex = Female) had significantly higher survival rates compared to men (Sex = Male).

Fare: A positive correlation was observed between fare amount and survival, indicating that passengers who paid higher fares had better chances.

Passenger class: Passengers in first class (Pclass = 1) were more likely to survive compared to those in second (Pclass = 2) or third class (Pclass = 3).

Age: Younger passengers, especially children, showed better survival probabilities, while elderly passengers had lower chances.

Snap of Scatter Plot:


![Image](https://github.com/user-attachments/assets/a89b2153-693a-4453-a214-b0989ecbc243)








# Project Summary
The champion model for this project is Logistic Regression from the "Logistic_Regression-Model Pipeline" pipeline. The model was chosen based on the KS (Youden) for the Train partition (0.51). 78% of the Train partition was correctly classified using the Logistic Regression model. The five most important factors are Sex, Fare, Age, Pclass, and Embarked.






