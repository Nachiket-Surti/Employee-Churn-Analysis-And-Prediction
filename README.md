# Employee Churn Analysis & Prediction


## Project Summary

This project analyzes employee attrition using **Python, machine learning, clustering, feature importance, and Power BI**.  
The goal is to help HR teams identify employees at risk of leaving, understand the main churn drivers, and translate the analysis into practical retention actions.

The project is designed as an end-to-end analytics case study: from raw HR data to insights, modeling, dashboarding, and business recommendations.

## Business Problem

Employee turnover increases hiring cost, onboarding effort, productivity loss, and knowledge drain.  
Instead of only reporting who left, this project answers four business questions:

1. Which employees are most likely to leave?
2. What factors are associated with employee churn?
3. Are there different types of churn behavior?
4. What actions can HR take to reduce attrition?

## Dataset

The dataset contains **14,999 employee records** with the following information:

| Category | Fields |
|---|---|
| Engagement | satisfaction_level, last_evaluation |
| Workload | number_project, average_monthly_hours |
| Tenure | time_spend_company |
| HR Factors | Work_accident, promotion_last_5years, salary |
| Organization | department |
| Target | left |

### Data Dictionary
| Column | Meaning |
|---|---|
| `satisfaction_level` | Employee satisfaction score from 0 to 1 |
| `last_evaluation` | Latest performance evaluation score |
| `number_project` | Number of projects assigned |
| `average_monthly_hours` | Average monthly working hours |
| `time_spend_company` | Years spent at the company |
| `Work_accident` | Whether the employee had a workplace accident |
| `promotion_last_5years` | Whether the employee was promoted in the last 5 years |
| `department` | Employee department |
| `salary` | Salary level: low, medium, high |
| `left` | Churn target variable 0-stayed and 1-left |

## Methodology

1. Loaded and inspected employee HR data.
2. Performed exploratory data analysis on satisfaction, workload, salary, promotions, tenure, and department.
3. Used K-Means clustering to segment employees into behavior-based churn profiles.
4. Built Logistic Regression and Random Forest churn prediction models.
5. Evaluated models using Accuracy, Precision, Recall, F1-score, and ROC-AUC.
6. Interpreted Random Forest feature importance.
7. Converted model findings into HR retention recommendations.

## Top Churn Drivers

The strongest churn predictors were:

1. Satisfaction level
2. Time spent at the company
3. Number of projects
4. Average monthly hours
5. Last evaluation score

## Key Results

| Metric | Result |
|---|---:|
| Total Employees | 14,999 |
| Employees Left | 3,571 |
| Overall Churn Rate | 23.81% |
| Average Satisfaction | 0.61 |
| Model ROC-AUC | 0.9796 |
| Model F1 Score | 0.9749 |

## Main Insights

- **Low satisfaction is the strongest churn signal.**
- Employees with extreme workloads and many projects show high attrition risk.
- Employees with **low salary** have a much higher churn rate than employees with high salary.
- Tenure matters: employees around the mid-tenure range show elevated churn.
- Clustering identified multiple churn segments, including **Burnout Risk**, **Disengaged / Underutilized**, **Long-Tenure Flight Risk**, and **Stable Engaged** employees.

## Power BI Dashboard

The dashboard summarizes executive HR insights:

- Total employees
- Employees left
- Churn rate
- Average satisfaction
- Churn by department
- Churn by salary
- Churn by tenure
- Churn by number of projects
- Interactive slicers for department, salary, work accident, promotion, and years at company

## Machine Learning

A Logistic Regression and Random Forest classification model was trained to predict employee churn. But Random Forest was found to be better than LR.
The model uses numeric HR metrics and categorical employee information after proper train-test splitting and one-hot encoding.

Model metrics:

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 0.758 | 0.469 | 0.227 | 0.306 | 0.574 |
| Random Forest | 0.988 | 0.987 | 0.963 | 0.975 | 0.980 |

## Employee Segmentation

KMeans clustering was used to group employees into interpretable workforce segments.

| Segment | Business Meaning |
|---|---|
| Burnout Risk | Low satisfaction, high hours, many projects, high churn |
| Disengaged / Underutilized | Lower satisfaction, lower workload, high churn |
| Long-Tenure Flight Risk | Experienced employees with elevated attrition |
| Stable Engaged | Higher satisfaction, sustainable workload, low churn |

## Recommended HR Actions

| Risk Area | Recommended Action |
|---|---|
| Burnout | Reduce workload, monitor overtime, rebalance projects |
| Disengagement | Improve career coaching, mentorship, and role fit |
| Long-tenure churn | Create promotion pathways and retention incentives |
| Salary risk | Review compensation competitiveness |
| Department churn | Investigate management practices and workload distribution |

## Repository Structure

```text
employee_churn_anatysis_and_prediction/
├── data/
├── assests/
├── notebook/
├── powerbi/
├── README.md/
├── requirements.txt/
├── Data_Dictionary/
├── reports/
└── project_summary.docx/
```

## How to Run

```bash
pip install -r requirements.txt
jupyter notebook notebook/Employee_Churn_Analysis_And_Prediction.ipynb
```

## Tools Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Power BI
- Jupyter Notebook

## Portfolio Value

This project demonstrates data cleaning, exploratory analysis, machine learning, clustering, dashboarding, model interpretation, and business communication.
