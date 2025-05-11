# 💼 Sure Tomorrow Insurance Machine Learning Project

## 🧠 Project Overview
The project involves building and evaluating multiple machine learning solutions for Sure Tomorrow, an insurance company aiming to enhance customer insights and decision-making. The tasks includes identifying similar customers, predicting benefit eligibility, estimating the number of benefits through regression modeling, and implementing data masking techniques to ensure privacy without compromising model performance. 

## 📌 Problem Statement
Sure Tomorrow Insurance wants to leverage machine learning to:
  - Find customers similar to a given customer for marketing targeting.
  - Predict whether a new customer will receive insurance benefits.
  - Predict the number of insurance benefits a customer will likely receive.
  - Protect personal client data while maintaining model accuracy.
  - 
## 🛠 Tasks & Approach
### Task 1: Customer Similarity
**Goal:** Find customers similar to a given customer for marketing targeting.
**Approach:**
  - Used K-Nearest Neighbors (KNN) algorithm.
  - Features standardized before fitting the model.
  - Distance metrics used to find comparable customers.

### Task 2: Binary Classification - Will the customer receive benefits?
**Goal:** Predict whether a customer is likely to receive at least one benefit.
**Approach:**
  - Converted target to binary (1 if benefits > 0).
  - Baseline: DummyClassifier for comparison.
  - Trained and evaluated models (Logistic Regression, Random Forest).
  - Measured performance using accuracy, precision, recall, and F1-score.
**Insights:**
  - Trained models significantly outperformed the dummy classifier.
  - A trained model can do worse only if underfitting/overfitting or trained on poor features.

### Task 3: Regression - How many benefits?
**Goal:** Predict the number of insurance benefits using regression.
**Approach:**
  -  Used Linear Regression as the main model.
  -  Evaluated performance using RMSE.
  -  Verified assumptions of linearity and checked residuals.
**Result:**
  - Model returned a reasonable RMSE and can be used as a baseline for future regression improvements.

### Task 4: Data Masking (Obfuscation)
**Goal:** Protect personal data (data masking) while preserving model performance.
**Approach:**
  - Applied random matrix multiplication for linear transformation of features.
  - Ensured the transformation is invertible only with access to the transformation matrix.
  - Retrained regression model on obfuscated data.
**Result:**
  - Model performance remained consistent before and after masking.
  - Data successfully obfuscated without loss in prediction quality.

## 📂 Datasets
  - Features:
      - `gender` - Gender
      - `age` - Age
      - `income` - Salary
      - `family_members` - Number of Family Members
   - Target:
      - `insurance_benefits` - Number of benefits received over the last 5 years

## 💻 How to Run the Project
  1. Clone the repository.
  2. Install dependencies:
     ```bash
     pip install pandas scikit-learn matplotlib seaborn
  3. Run the notebook:
     ```bash
     jupyter notebook insurance_us.ipynb

## 📈 Results Summary
| Task   | Model Used            | Key Metric               | Result                 |
| ------ | --------------------- | -----------------        | ---------------------- |
| Task 1 | Nearest Neighbors     | Scaled and Unscaled data | Working as intended    |
| Task 2 | KNN-based classifier  | F1-score                 | Better than dummy      |
| Task 3 | Linear Regression     | RMSE                     | Acceptable baseline    |
| Task 4 | Obfuscated Regression | RMSE                     | Comparable to original |
