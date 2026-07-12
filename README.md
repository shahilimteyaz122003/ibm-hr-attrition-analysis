[README.md](https://github.com/user-attachments/files/29942293/README.md)
# HR Employee Attrition Analysis

Exploratory Data Analysis of IBM's HR employee dataset to identify the key drivers behind employee attrition and provide actionable retention recommendations.

## Dataset
- **Source:** [IBM HR Analytics Employee Attrition & Performance - Kaggle](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)
- **Size:** 1,470 employees, 35 original columns
- **Fields:** Age, Attrition, Department, JobRole, MonthlyIncome, OverTime, YearsAtCompany, JobSatisfaction, WorkLifeBalance, and more

## Data Cleaning
- Verified no missing values and no duplicate rows (dataset arrived clean).
- Dropped 3 constant columns (`EmployeeCount`, `Over18`, `StandardHours`) — each had only a single unique value across all 1,470 rows, so they add zero analytical value.
- Dropped `EmployeeNumber` — a unique ID field, not a usable feature.
- Standardized column names to snake_case for consistent coding.
- Mapped numeric satisfaction/rating codes (1-4) to readable labels (e.g., `1 → Low`, `4 → Very High`) for clearer visuals and interpretation.

## Key Insights
- **Overall attrition rate: 16.1%** — roughly 1 in 6 employees left.
- **Sales department** has the highest attrition (20.6%); **Sales Representative** is the highest-risk role (39.8%).
- **OverTime is the strongest attrition driver:** employees working overtime leave at **30.5%**, more than triple the rate of those who don't (10.4%).
- Employees who leave earn **~$2,046 less per month** on average ($4,787 vs $6,833 for those who stay).
- Attrition skews toward **newer employees** — average tenure of those who leave is 5.1 years vs 7.4 years for those who stay.
- Poor work-life balance correlates with meaningfully higher attrition rates.

## Visuals
| Chart | Insight |
|---|---|
| Overall Attrition Rate | Company-wide attrition split |
| Attrition by Department | Which departments lose the most people |
| Attrition by OverTime | Overtime's outsized impact on attrition |
| Age Distribution by Attrition | Age profile of leavers vs stayers |
| Income by Attrition | Pay gap between those who stay and leave |
| Attrition by Job Role | Highest-risk roles |
| Years at Company by Attrition | Tenure patterns |
| Attrition by Work-Life Balance | Retention impact of WLB rating |

All visuals are in the `/visuals` folder.

## Business Recommendation
Prioritize retention efforts on Sales Representatives working overtime with below-average pay and under 3 years of tenure — this is the segment showing the highest combined attrition risk. Consider workload redistribution and targeted pay review for this group.

## Tools Used
- **Python:** Pandas (cleaning & analysis), Matplotlib & Seaborn (visualization)
- **Power BI:** Interactive dashboard (see `/dashboard` folder, if included)

## Project Structure
```
├── data/
│   ├── hr_attrition_raw.csv
│   └── hr_attrition_cleaned.csv
├── notebooks/
│   └── clean_and_analyze.py
├── visuals/
│   └── (8 chart images + insights_summary.txt)
└── README.md
```

## How to Run
```bash
pip install pandas matplotlib seaborn
python clean_and_analyze.py
```
