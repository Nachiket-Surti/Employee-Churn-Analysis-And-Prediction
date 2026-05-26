# Power BI Dashboard Guide

## Goal
Create an interactive Employee Churn Dashboard in Power BI using the dataset:

`data/HR_comma_sep.csv`

## Step 1: Install Power BI Desktop
Download and install **Power BI Desktop** from Microsoft Store or the official Microsoft Power BI website.

## Step 2: Import the Data
1. Open Power BI Desktop.
2. Click **Get Data**.
3. Choose **Text/CSV**.
4. Select `HR_comma_sep.csv`.
5. Click **Transform Data**.
6. Check that columns are detected correctly:
   - Numeric: satisfaction_level, last_evaluation, number_project, average_monthly_hours, time_spend_company, left
   - Text: department, salary
7. Click **Close & Apply**.

## Step 3: Rename Fields for Readability
In Power BI, rename columns visually:
- `left` → `Employee Left`
- `average_monthly_hours` → `Average Monthly Hours`
- `time_spend_company` → `Years at Company`
- `number_project` → `Number of Projects`
- `promotion_last_5years` → `Promotion Last 5 Years`
- `Work_accident` → `Work Accident`

## Step 4: Create Measures
Go to **Modeling > New Measure** and create these DAX measures based on your rename.

```DAX
Total Employees = COUNTROWS(HR_comma_sep)

Employees Left = CALCULATE(COUNTROWS(HR_comma_sep), HR_comma_sep[left] = 1)

Employees Stayed = CALCULATE(COUNTROWS(HR_comma_sep), HR_comma_sep[left] = 0)

Churn Rate = DIVIDE([Employees Left], [Total Employees])

Average Satisfaction = AVERAGE(HR_comma_sep[satisfaction_level])

Average Monthly Hours = AVERAGE(HR_comma_sep[average_monthly_hours])

Average Evaluation = AVERAGE(HR_comma_sep[last_evaluation])

Promotion Rate = DIVIDE(
    CALCULATE(COUNTROWS(HR_comma_sep), HR_comma_sep[promotion_last_5years] = 1),
    [Total Employees]
)
```

Format `Churn Rate` and `Promotion Rate` as percentages.

## Step 5: Dashboard Layout

### Top KPI Cards
Created four card visuals:
1. Total Employees
2. Employees Left
3. Churn Rate
4. Promotion Rate
5. Average Satisfaction

### Main Visuals
1. **Bar Chart:** Churn Rate by Department
   - Axis: department
   - Values: Churn Rate

2. **Column Chart:** Churn Rate by Salary
   - Axis: salary
   - Values: Churn Rate

3. **Column Chart:** Churn Rate by Years at Company
   - Axis: time_spend_company
   - Values: Churn Rate

4. **Bar Chart:** Churn Rate by Number of Projects
   - Axis: number_project
   - Values: Churn Rate

5. **Scatter Plot:** Satisfaction vs Average Monthly Hours
   - X-axis: satisfaction_level
   - Y-axis: average_monthly_hours
   - Legend: left

### Slicers
Add slicers for:
- department
- salary
- time_spend_company
- Work_accident
- promotion_last_5years

## Step 6: Dashboard Story
My dashboard answers:
- How many employees left?
- Which departments have the highest churn?
- Does salary level affect churn?
- Does workload affect churn?
- Which tenure group is most at risk?
- What employee segments should HR prioritize?

## Step 7: Dashboard Title
**Employee Churn & Retention Risk Dashboard**

## Expected KPI Values
- Total Employees: **14,999**
- Employees Left: **3,571**
- Churn Rate: **23.81%**
- Promotion Rate: **2.13%**
- Average Satisfaction: **0.61**
