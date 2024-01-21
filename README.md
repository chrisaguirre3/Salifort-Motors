# Salifort Motors

### Description 

Providing data-driven recommendations to help retain employees at Salifort Motors company and building/selecting a model that 
will predict whether an employee will leave the company. # data-projects

### Problem Statement 

Employee retention/satisfaction levels at Salifort Motors company are low.

### Task 

Analyze HR employee data to determine the important factors contributing to employee retention/satisfaction and build,
test, evaluate, and choose the best machine learning/logistic regression model(s) that predict(s) whether an employee will leave
the company.

### The Dataset

- Rows: 15,000
- Columns: 10

<table style="border-collapse: collapse; border-spacing: 0; margin: 0; padding: 0;">
  <tr style="margin: 0; padding: 0;">
    <td style="margin: 0; padding: 0; border: none; align: left;">
      <img src="Salifort Motors Dataset Variables.png" alt="Dataset Variables" width="600" height="500" style="width:4000px;margin: 0; padding: 0; display: block;"/>
    </td>
  </tr>
</table>

[Link to Dataset](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction?select=HR_comma_sep.csv)

### Analysis Plan

1. Import necessary libraries/modules
2. Perform initial EDA
3. Conduct data cleaning
   - Rename columns for readability/conciseness
   - Nulls
   - Duplicates
   - Outliers
4. Perform full EDA (analyzing relationships between each variable with every other variable, prioritizing analysis for variable
   relationships with the highest correlations)
   - Data wrangling and feature engineering
6. EDA summary with resulting recommendations
7. Build/evaluate Logistic Regression model with no interaction terms
8. Build/evaluate Logistic Regression model that includes interaction terms (based on correlation mapping and EDA findings)
9. Build/evaluate a third Logistic Regression model with additional interaction terms (based on correlation mapping and EDA findings)
10. Build/evaluate two Decision Tree models - one optimized for F1 score and one optimized for Recall score*
11. Build/evaluate two Random Forest models - one optimized for F1 score and one optimized for Recall score*
12. Build/evaluate two XGBoost models - one optimized for F1 score and one optimized for Recall score*
13. Compare performance across the models and choose the best model(s) for deployment
14. Provide final recommendations/next steps

*Separate machine learning models were built and optimized for F1 score and Recall score for each type of model. Optimizing for Recall
score maximizes model performance in correctly predicting all the employees who would leave the company. Optimizing for F1 score maximizes model
balanced performance in correctly predicting both employees who would leave and stay.

**Feature Importances from the machine learning models were used to further guide EDA.

---

### Repository Files

**See the [Jupyter Notebook]((Jupyter)_Salifort_Motors_Chris%20Aguirre_08NOV23.ipynb) in this repository to view all analysis, model construction/evaluation/selection, and exhaustive findings/recommendations.**

**See the [Executive Summary](Salifort%20Motors%20Executive%20Summary_Chris%20Aguirre.pdf) in this repository, outlining key findings, recommendations, next steps, and champion predictive models to deploy.**
