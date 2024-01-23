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
2. Perform initial EDA [code/output](https://nbviewer.org/github/chrisaguirre3/Salifort-Motors/blob/main/%28Jupyter%29_Salifort_Motors_Chris%20Aguirre_FINAL.ipynb#initial-eda)
3. Conduct data cleaning [code/output](https://nbviewer.org/github/chrisaguirre3/Salifort-Motors/blob/main/%28Jupyter%29_Salifort_Motors_Chris%20Aguirre_FINAL.ipynb#initial-eda)
   - Rename columns for readability/conciseness
   - Nulls
   - Duplicates
   - Outliers
4. Perform full EDA (analyzing relationships between each variable with every other variable, prioritizing analysis for variable
   relationships with the highest correlations) [code/output](https://nbviewer.org/github/chrisaguirre3/Salifort-Motors/blob/main/%28Jupyter%29_Salifort_Motors_Chris%20Aguirre_FINAL.ipynb#eda)
   - Data wrangling and feature engineering
6. EDA summary with resulting recommendations [EDA summary](https://nbviewer.org/github/chrisaguirre3/Salifort-Motors/blob/main/%28Jupyter%29_Salifort_Motors_Chris%20Aguirre_FINAL.ipynb#edasummary)
7. Build/evaluate Logistic Regression model with no interaction terms [code/output](https://nbviewer.org/github/chrisaguirre3/Salifort-Motors/blob/main/%28Jupyter%29_Salifort_Motors_Chris%20Aguirre_FINAL.ipynb#lr1)
8. Build/evaluate Logistic Regression model that includes interaction terms (based on correlation mapping and EDA findings) [code/output](https://nbviewer.org/github/chrisaguirre3/Salifort-Motors/blob/main/%28Jupyter%29_Salifort_Motors_Chris%20Aguirre_FINAL.ipynb#lr2)
9. Build/evaluate a third Logistic Regression model with additional interaction terms (based on correlation mapping and EDA findings) [code/output](https://nbviewer.org/github/chrisaguirre3/Salifort-Motors/blob/main/%28Jupyter%29_Salifort_Motors_Chris%20Aguirre_FINAL.ipynb#lr3)
10. Build/evaluate two Decision Tree models - one optimized for F1 score and one optimized for Recall score* [code/output](https://nbviewer.org/github/chrisaguirre3/Salifort-Motors/blob/main/%28Jupyter%29_Salifort_Motors_Chris%20Aguirre_FINAL.ipynb#dt_f1)
11. Build/evaluate two Random Forest models - one optimized for F1 score and one optimized for Recall score* [code/output](https://nbviewer.org/github/chrisaguirre3/Salifort-Motors/blob/main/%28Jupyter%29_Salifort_Motors_Chris%20Aguirre_FINAL.ipynb#rf_f1)
12. Build/evaluate two XGBoost models - one optimized for F1 score and one optimized for Recall score* [code/output](https://nbviewer.org/github/chrisaguirre3/Salifort-Motors/blob/main/%28Jupyter%29_Salifort_Motors_Chris%20Aguirre_FINAL.ipynb#xgb_f1)
13. Compare performance across the models and choose the best model(s) for deployment
    [model selection/evaluation](https://nbviewer.org/github/chrisaguirre3/Salifort-Motors/blob/main/%28Jupyter%29_Salifort_Motors_Chris%20Aguirre_FINAL.ipynb#model-selection)
14. Provide final recommendations/next steps [final recommendations/next steps](https://nbviewer.org/github/chrisaguirre3/Salifort-Motors/blob/main/%28Jupyter%29_Salifort_Motors_Chris%20Aguirre_FINAL.ipynb#recommendations)

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

**Data Duplicates.**

HR should find the source(s) of the duplicates found in this dataset and figure out a way to eliminate or at least decrease them in future data gathering efforts. A few duplicates is not a real issue but when duplicates make up a large portion of the data (in this case over 20%), they inflate survey response rates and can cause data gathering efforts to stop prematurely when the data gathering team thinks they have enough unique responses, but in fact do not due to the duplicate reponses. If the duplicate responses in this dataset were instead unique responses, that would have meant that much more data to use for analysis and training/testing predictive models.

### Recommendations

**Project Workload.**

Managers should strive to assign 3-4 projects to a majority of their employees and should not assign more than 5 projects to an employee unless that employee and his/her manager is sure they can handle it without unduly increasing their work hours.

Managers should closely monitor how their employees are handling their project workload on a regular basis. If it becomes apparent that an employee is having to consistently spend significantly more time working with additional project workload, it may be the manager's best interest to cut back that employee's workload and redistribute projects until that employee is able to handle more without increasing their work hours.

**Job Candidate Screening.**

Recruiters and hiring managers would do well to thoroughly screen job candidates before hiring them to weed out potential underperformers. Do the job candidates have strong work ethic and are able to efficiently get results? Do they have the knowledge/skills/experience necessary to be successful in their hired role? Will they be committed to the company's success?

**Employee Hours Worked.**

Management should create a company culture where employees feel they can work normal 8-hour workdays on a regular basis and not be penalized. In fact, employees who are able to efficiently and effectively get work done within regular hours should be recognized and rewarded.

**Employee Evaluation Criteria.**

Building on the last recommendation regarding employee hours worked, management should ensure their employee evaluation criteria is tied to employees getting results vs. working longer hours or on more projects. Management should lead this change in organizational culture so employees know that achieving results is more important. Greater quantity doesn't necessarily equate to greater quality/better results for the company.

If an employee is eager to take on more projects and/or work longer hours and is able to achieve the same level of results or better, that can be decided on a case by case basis by the manager - but the employee shouldn't think this is necessary for them to receive a strong evaluation. Management should make this clear.

**5-Year Tenure Employee Incentivization.**

Since 5-year tenure employees have by far the greatest percentage within a tenure year group that left the company, the company should implement special incentives for employees to stay with the company beyond 5 years. These could include higher salary raises at 5 years, additional vacation days, time-based restricted stock, promotion, public recognition of company contribution, or other incentives.

**Top Talent Retention.**

Since the same tenure groups of employees who had the highest percentages of employees leave the company also appear to be the top talent tenure groups in the company overall, incentives directed towards these tenure groups should take into account that they consist of top talent. This would justify higher levels of pay, promotion, or other such similar incentives mentioned previously.

**Employee Salaries Overhaul.**

It doesn't make sense that the employees who do the most work and have the highest evaluation scores also have among the lowest salaries in the company. Management/Finance should take a serious look at how salaries are determined for its employees, especially for the top performers in tenures 4-6, and ensure it is commensurate with the value employees bring to the company.

**Employee Promotions.**

Not enough employees are being promoted overall. The US average promotion rate of 45% over 5 years is about *26* times higher than Salifort's 5 year promotion rate.

In addition to working on the most projects, having the highest evaluation scores, and having among the lowest salaries in the company, employees with 4 and 5 years tenure also have the lowest promotion rates in the company.

Promotion is another tool management can use to retain employees, especially top talent employees deserving of it. Management and HR should look at employee promotions across the board and ensure that consistent promotion criteria is used throughout the company and that the employees most deserving of promotion get promoted.

**EHS Program Improvement.**

Even though a higher percentage of employees who had a work accident stayed at the company than employees who did not have a work accident, a 15.4% accident rate is too high. That's about 6 times higher than the average accident rate in the US and about 9 times higher than the average accident rate in the UK. It is important to provide a safe work environment for employees. The company's EHS team and management should work to find the root causes of these accidents and implement engineered or other best solutions to eliminate or at least mitigate the environmental factors that led to these accidents. Implementing an incentivized proactive program of identifying and correcting hazard observations throughout the company would be a good way to prevent identified hazards from causing safety incidents down the line.

---

### Repository Files

**See the [Jupyter Notebook]((Jupyter)_Salifort_Motors_Chris%20Aguirre_FINAL.ipynb) in this repository to view all analysis, model construction/evaluation/selection, and exhaustive findings/recommendations.**

**See the [Executive Summary](Salifort%20Motors%20Executive%20Summary_Chris%20Aguirre.pdf) in this repository, outlining key findings, recommendations, next steps, and champion predictive models to deploy.**
