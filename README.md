
# Lending Club Loan Default Prediction Project

This project applies machine learning techniques to predict loan defaults for Lending Club. Leveraging data preprocessing, exploratory data analysis (EDA), feature engineering, and model training, the project aims to identify high-risk loans, reduce non-performing loan ratios, and increase net interest income.
 

---

## Table of Contents

1. [Introduction](#introduction)
2. [Data Preprocessing](#data-preprocessing)
3. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
4. [Model Selection and Rationale](#model-selection-and-rationale)
5. [Model Performance and Evaluation](#model-performance-and-evaluation)
6. [Deployment and Scalability Considerations](#deployment-and-scalability-considerations)
7. [Estimated Impact and ROI](#estimated-impact-and-roi)
8. [Conclusion](#conclusion)

---

## Introduction

Loan default prediction is critical for financial institutions to mitigate risks and ensure profitability. This project, developed on Lending Club’s loan data, predicts the likelihood of loan defaults using advanced machine learning techniques, particularly Logistic Regression and CatBoost models.

## Data Preprocessing

The dataset required several preprocessing steps to enhance model performance, including:
- **Handling Missing Values**: Imputation techniques were applied based on the nature of each feature.
- **Scaling and Normalization**: Numerical features were scaled to improve model performance.
- **Encoding Categorical Variables**: Relevant categorical features, such as `term` and `grade`, were encoded for compatibility with machine learning models.

We created two main dataframes:
- **df_linear**: Used primarily for linear modeling approaches like logistic regression.
- **df_complex**: Included a more extensive preprocessing pipeline and used for complex algorithms such as CatBoost.

## Exploratory Data Analysis (EDA)


EDA was conducted to understand feature relationships and to explore any significant patterns in loan default data:
- **Feature Distributions**: Key features like `interest rate`, `loan amount`, and `fico scores` were visualized (see Sweetviz_Report on Git).
- **Correlation Analysis**: Relationships between `loan_default` and other features were analyzed using correlation matrices and point-biserial correlations.
- **SHAP Values**: For CatBoost, SHAP values were used to understand the contribution of each feature in model predictions.

## Model Selection and Rationale

**Logistic Regression (Baseline Model 2):**
- Chosen for simplicity, interpretability, and scalability in real-time environments.
- Baseline model performance metrics provided a foundation for model refinement.

**CatBoost (Challenger Model 3):**
- Selected due to its ability to handle categorical data and complex interactions efficiently.
- Outperformed logistic regression in recall, true default rate, and overall ROC-AUC, making it suitable for high-risk loan identification.

## Model Performance and Evaluation

Comparison of Baseline Model 2 and Challenger Model 3:
- **Baseline Model 2**:
    - True Default Rate: 61.7%
    - Non-Default Rate: 91.8%
    - False Default Rate: 8.2%
- **Challenger Model 3**:
    - True Default Rate: 85.7%
    - Non-Default Rate: 86.6%
    - False Default Rate: 13.4%

The increase in true default rate in Challenger Model 3 justifies its use, despite higher computation times. The enhanced predictive accuracy could result in significant reductions in loan losses and improvements in profitability.

## Deployment and Scalability Considerations

Given Lending Club’s large customer base, this solution considers deployment strategies to balance prediction quality with computational demands:
- **Real-Time Scoring**: Use Baseline Model 2 (Logistic Regression) for immediate scoring in lower-risk, high-frequency applications.
- **Batch Processing**: Deploy Challenger Model 3 in scheduled batch runs for high-risk segments where precision in risk assessment is prioritized.
- **Manual Monitoring**: Regularly monitor model performance and recalibrate as necessary, especially in evolving financial conditions.

## Estimated Impact and ROI

Using Challenger Model 3, the institution could potentially:
- **Reduce Loan Losses**: By targeting high-risk loans with greater precision, net interest income with the model increases to $178.1M.
- **Lower NPL Ratio**: Default prediction allows the business to lower the Non-Performing Loan Ratio (NPL) from 12.85% to 1.93%.
- **ROI**: The model’s impact directly translates to improved profitability and minimized loan write-offs, delivering high ROI and enhancing financial stability.

## Conclusion

The project successfully demonstrates the power of machine learning in financial risk management. By implementing Logistic Regression for real-time decisions and CatBoost for high-risk loan analysis, Lending Club can effectively manage loan portfolios, maximize revenue, and minimize risks.

---
