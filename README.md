# HR Analytics Dashboard — Power BI

---

## Dashboard Preview

![HR Dashboard](dashboard.png)

---

## Overview

An interactive HR Analytics Dashboard built in Power BI to analyze employee attrition, workforce demographics, and retention patterns. The dashboard enables HR teams to identify high-risk employee segments, understand the key drivers of attrition, and make data-driven decisions to reduce turnover and improve retention strategy.

---

## Business Problem

Employee attrition is a major organizational challenge — increasing hiring costs, reducing team productivity, and disrupting business continuity. Traditional HR reporting lacks the interactivity to quickly identify *who* is leaving, *why*, and *when*.

This dashboard addresses that by providing:
- Real-time filtering by department, gender, education, and job role
- Visual breakdown of attrition across age, salary, and tenure segments
- Actionable insights to support HR retention planning

---

## Key Metrics

| Metric | Value |
|--------|-------|
| Total Employees | 1,470 |
| Attrition Count | 237 |
| Attrition Rate | 16% |
| Average Age | 37 years |
| Average Salary | $6.5K/month |
| Average Tenure | 7.0 years |

---

## Dataset

The HR dataset is embedded within `HR Dashboard.pbix` and contains the following fields:

| Field | Description |
|-------|-------------|
| Age | Employee age |
| Gender | Male / Female |
| Department | HR, R&D, Sales |
| Job Role | Laboratory Technician, Sales Executive, Manager, etc. |
| Education Field | Life Sciences, Medical, Marketing, Technical Degree, etc. |
| Monthly Income | Employee monthly salary |
| Years at Company | Total years of employment |
| Attrition | Yes / No — whether the employee left |
| Job Satisfaction | Satisfaction rating (1–4) |
| Years Since Last Promotion | Time since last promotion |

---

## DAX Measures Used

```dax
-- Attrition Rate
Attrition Rate = DIVIDE([Attrition Count], [Total Employees], 0)

-- Attrition Count
Attrition Count = CALCULATE(COUNT('HR Data'[Attrition]), 'HR Data'[Attrition] = "Yes")

-- Average Salary
Avg Salary = AVERAGE('HR Data'[MonthlyIncome])

-- Average Age
Avg Age = AVERAGE('HR Data'[Age])

-- Average Tenure
Avg Tenure = AVERAGE('HR Data'[YearsAtCompany])
```

---

## Dashboard Insights

### Attrition by Age
- Highest attrition in the **26–35 age group** — early-career employees most likely to leave
- Attrition decreases steadily after age 40

### Attrition by Salary Slab
- Employees earning **≤ $5K/month** show significantly higher attrition
- Higher salary slabs (10K+) retain employees more effectively

### Attrition by Job Role
- **Laboratory Technicians** and **Sales Executives** have the highest turnover
- Managerial roles show the lowest attrition rates

### Attrition by Education
- **Life Sciences** and **Medical** backgrounds make up the majority of the workforce
- Technical Degree holders show relatively lower attrition

### Attrition by Tenure
- Most employees leave within the **first 1–3 years**
- Attrition drops significantly after 5+ years — loyalty increases with tenure

### Attrition by Gender
- Male employees show slightly higher attrition count overall
- Gender-based patterns visible across departments and roles

---

## Visualizations Included

| Visual | Type |
|--------|------|
| Attrition by Education | Donut Chart |
| Attrition by Age | Bar Chart |
| Attrition by Salary Slab | Bar Chart |
| Attrition by Years at Company | Line / Area Chart |
| Attrition by Job Role | Matrix / Table |
| Attrition by Gender | Grouped Bar Chart |
| KPI Cards | Total Employees, Attrition Count, Attrition Rate, Avg Age, Avg Salary, Avg Tenure |

---

## Dashboard Features

**Interactive Filters**
- Department (HR, R&D, Sales)
- Education Field
- Gender
- Job Role

**Power Query Transformations**
- Data type standardization
- Null value handling
- Column renaming and formatting
- Calculated columns for salary slabs and age groups

---

## Project Structure

```
├── HR Dashboard.pbix    # Power BI dashboard file (data + visuals + DAX)
├── dashboard.png        # Dashboard screenshot preview
└── README.md            # Project documentation
```

---

## How to Open

```
1. Download HR Dashboard.pbix from this repository
2. Install Power BI Desktop (free):
   https://www.microsoft.com/en-us/power-platform/products/power-bi/desktop
3. Open HR Dashboard.pbix in Power BI Desktop
4. Use the filter panel to explore attrition by department, gender, and role
```

> **Note:** The dataset is fully embedded inside the `.pbix` file — no separate data file download needed.

---

## Business Impact

- Identifies **high-risk employee segments** for proactive retention action
- Supports **HR strategy planning** with clear visual evidence
- Pinpoints **salary and tenure thresholds** where attrition spikes
- Enables **department-level reporting** for targeted intervention
- Reduces guesswork in workforce planning with data-backed decisions

---

## Tools & Technologies

| Tool | Purpose |
|------|---------|
| Power BI Desktop | Dashboard design and publishing |
| DAX | Custom measures and KPI calculations |
| Power Query (M) | Data transformation and cleaning |
| Data Modeling | Relationships and calculated columns |

---

## Author
Ramu Battu

**Ramu Battu**
MS in Data Analytics — California State University, Fresno
📧 ramuusa61@gmail.com
