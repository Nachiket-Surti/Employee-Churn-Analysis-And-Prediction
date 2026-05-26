# Power BI DAX Measures

```DAX
Total Employees = COUNTROWS(employee_churn_clean)

Employees Left = CALCULATE(COUNTROWS(employee_churn_clean), employee_churn_clean[left] = 1)

Employees Stayed = CALCULATE(COUNTROWS(employee_churn_clean), employee_churn_clean[left] = 0)

Churn Rate = DIVIDE([Employees Left], [Total Employees])

Average Satisfaction = AVERAGE(employee_churn_clean[satisfaction_level])

Average Monthly Hours = AVERAGE(employee_churn_clean[average_monthly_hours])

Average Evaluation = AVERAGE(employee_churn_clean[last_evaluation])

Promotion Count = CALCULATE(COUNTROWS(employee_churn_clean), employee_churn_clean[promotion_last_5years] = 1)

Promotion Rate = DIVIDE([Promotion Count], [Total Employees])

Work Accident Count = CALCULATE(COUNTROWS(employee_churn_clean), employee_churn_clean[Work_accident] = 1)

No Work Accident Count = CALCULATE(COUNTROWS(employee_churn_clean), employee_churn_clean[Work_accident] = 0)
```
