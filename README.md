# Salifort Motors

### Description 

Providing data-driven recommendations to help retain employees at Salifort Motors company and building/selecting a model that 
will predict whether an employee will leave the company.

### Problem Statement 

Employee retention/satisfaction levels at Salifort Motors company are low.

### Task 

Analyze HR employee data to determine the important factors contributing to employee retention/satisfaction and build,
test, evaluate, and choose the best machine learning/logistic regression model(s) that predict(s) whether an employee will leave
the company.

### The Dataset

- **Rows:** 15,000
- **Columns:** 10

<table style="border-collapse: collapse; border-spacing: 0; margin: 0; padding: 0;">
  <tr style="margin: 0; padding: 0;">
    <td style="margin: 0; padding: 0; border: none; align: left;">
      <img src="Salifort Motors Dataset Variables.png" alt="Dataset Variables" width="600" height="450" style="width:4000px;margin: 0; padding: 0; display: block;"/>
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

### Notes on Dataset Improvement

It would be prudent to get more detail from HR on how sampling was conducted to judge whether this dataset is likely to be truly representative of the population (the entire company). If this dataset is not representative, making inferences with a predictive model based on it would be inaccurate.

Actual salary amounts instead of categories would likely make 'salary' a better predictor variable for the outcome variable 'left'. I would not have any ethical concerns about this as long as the data remains anonymized and is made available for use only upon employee consent. Also, job titles aren't included in the dataset. This was a variable that the executive team specifically called out to use in analysis. Additionally, including more than just the last evaluation for each employee could be insightful - perhaps the last two to three evaluations. More generally, it's unclear over what timeframe some of these variables cover - it would be useful to know how various variables progressed over time, such as for satisfaction level, evaluations, number of projects, average monthly hours, when work accidents occurred, what departments employees worked in over time, and salary.

Additionally, it would be useful to know, in addition to the number of projects, the level of project complexity/scope - these would likely go together as a useful interaction variable to include in predictive modeling.

Also, if Salifort Motors conducted additional periodic Organizational Health Surveys (OHS), there could be a wealth of valuable information from those to include in this dataset to better predict whether an employee will leave vs. stay. Examples of additional useful information might include job titles, whether employees feel safe and valued at work, whether they trust their managers, how they view their team environment, whether they feel their pay level is fair, whether they feel that their job is secure, whether they feel there is ample opportunity for career growth in the company, whether they feel fulfilled with the work they do in their job, how employees would define what the company culture is, etc.

HR should consolidate data from employee exit interviews to determine reasons why employees left. This data would be helpful in both predicting employees that might leave as well as in determining changes to be made to better retain employees.

Lastly, the satisfaction level variable could be a source of data leakage when used to train the predictive models since it may not be a variable that will be available in the future when the chosen model is deployed. If it will be available, through periodic company-wide Organizational Health Surveys or otherwise, then data leakage will not be a concern. However, if it will not be available moving forward, then the projected effectiveness of the chosen model might be somewhat inflated.

Including the above information in the dataset would greatly improve the company's ability to gain insights into what contributes to employee satisfaction/dissatisfaction and whether an employee is likely to leave vs. stay.

---

### Repository Files

**See the [Jupyter Notebook]((Jupyter)_Salifort_Motors_Chris%20Aguirre_08NOV23.ipynb) in this repository to view all analysis, model construction/evaluation/selection, and exhaustive findings/recommendations.**

**See the [Executive Summary](Salifort%20Motors%20Executive%20Summary_Chris%20Aguirre.pdf) in this repository, outlining key findings, recommendations, next steps, and champion predictive models to deploy.**
