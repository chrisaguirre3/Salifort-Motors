### Description 

Providing data-driven recommendations to help retain employees at Salifort Motors company and building/selecting a model that 
will predict whether an employee will leave the company. # data-projects

### Problem Statement 

Employee retention/satisfaction levels at Salifort Motors company are low.

### Task 

Analyze HR employee data to determine the important factors contributing to employee retention/satisfaction and build,
test, evaluate, and choose the best machine learning/logistic regression model(s) that predict(s) whether an employee will leave
the company.

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
5. EDA summary with resulting recommendations
6. Build/evaluate Logistic Regression model with no interaction terms
7. Build/evaluate Logistic Regression model that includes interaction terms (based on correlation mapping and EDA findings)
8. Build/evaluate a third Logistic Regression model with additional interaction terms (based on correlation mapping and EDA findings)
9. Build/evaluate two Decision Tree models - one optimized for F1 score and one optimized for Recall score*
10. Build/evaluate two Random Forest models - one optimized for F1 score and one optimized for Recall score*
11. Build/evaluate two XGBoost models - one optimized for F1 score and one optimized for Recall score*
12. Compare performance across the models and choose the best model(s) for deployment
13. Provide final recommendations/next steps

*Separate machine learning models were built and optimized for F1 score and Recall score for each type of model. Optimizing for Recall
score maximizes model performance in correctly predicting all the employees who would leave the company. Optimizing for F1 score maximizes model
balanced performance in correctly predicting both employees who would leave and stay.

**See Jupyter notebook at (Jupyter)_Salifort_Motors_Chris Aguirre_08NOV23.ipynb in this repository to view all analysis, model construction/evaluation, and 
findings/recommendations.**
