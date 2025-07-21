# Customer Churn Prediction

## Objective

The objective of this project is to build a machine learning model that can predict whether a customer is likely to churn (i.e., leave the bank). By identifying the customers most at risk, the bank can take proactive steps to retain them and reduce revenue loss.

---

## Approach

- **Data Loading and Exploration**
  - The dataset was loaded from a CSV file and its structure examined using `.shape`, `.head()`, and `.info()` functions.
  - Irrelevant columns such as `RowNumber`, `CustomerId`, and `Surname` were dropped as they do not contribute to the prediction.

- **Data Cleaning and Preparation**
  - Checked for and confirmed the absence of missing values.
  - Categorical variables were handled using encoding:
    - `Gender` was label-encoded (Male/Female converted to 1/0).
    - `Geography` was one-hot encoded, with the first category dropped to avoid multicollinearity.

- **Model Building**
  - Features (`X`) and target (`y`, representing churn) were separated.
  - Data was split into training and testing sets (80/20 split).
  - A **Random Forest Classifier** was trained due to its effectiveness in handling classification tasks and its ability to provide feature importance scores.

- **Model Evaluation**
  - The model was evaluated using **accuracy score** and a **confusion matrix**.

- **Feature Importance Analysis**
  - The Random Forest model's built-in feature importance method was used to determine which variables most influence churn predictions.
  - Results were visualized using a bar plot for clear understanding.

---

## Model Accuracy

- The **Random Forest Classifier** achieved an accuracy of approximately **( 86.60%)** on the test dataset.
- The confusion matrix revealed that the model was effective in distinguishing between churned and retained customers, though some false positives and negatives were present as expected.

---
## Feature Importance Insights

- The top factors influencing customer churn in the model were:
  - **Age** — most influential factor; older customers tend to churn more.
  - **EstimatedSalary** and **CreditScore** — showed strong importance in influencing churn.
  - **Balance** and **NumOfProducts** — also contributed significantly to model predictions.
  - **Tenure** — moderately important, indicating how long a customer has been with the bank affects their likelihood to stay.

- Less influential features included:

  
  - **IsActiveMember**
  - **Geography (Germany and Spain)**
  - **Gender**
  - **HasCrCard**
    
- These insights help in understanding which customer attributes most affect churn behavior, allowing the bank to design better retention strategies.