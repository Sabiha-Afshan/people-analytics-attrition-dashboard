# People Analytics Dashboard for Attrition and Retention Strategy

An interactive Power BI people analytics dashboard designed to analyse workforce composition, employee attrition, high risk workforce segments and the factors associated with employee retention.

## Executive Summary

The organization recorded 237 employee exits from a workforce of 1,470 employees, resulting in an overall attrition rate of 16.1%.

The analysis identified elevated attrition among overtime employees, entry level employees, frequent business travellers, employees reporting poor work-life balance and selected job roles.

The dashboard supports workforce planning, targeted retention initiatives, employee experience improvement and career development planning.

## Business Problem

Overall attrition figures do not explain which employee groups are leaving or which workplace conditions are associated with higher retention risk.

This project was developed to identify:

- Workforce groups with elevated attrition
- Departments and roles contributing the most employee exits
- Differences between attrition volume and attrition rate
- Workplace and career factors associated with retention
- Employee groups requiring targeted HR intervention

## Key Business Questions

1. What is the overall attrition rate?
2. Which departments and job roles experience the highest attrition?
3. How does overtime affect employee retention?
4. Which salary bands and job levels are most at risk?
5. How do satisfaction and work life balance relate to attrition?
6. Does frequent business travel influence retention?
7. How does time since the last promotion relate to attrition?
8. Which risk areas affect the largest employee populations?

## Dataset

The analysis used an anonymised employee level HR dataset containing 1,470 records.

The dataset included:

- Employee demographics
- Department and job role
- Job level
- Monthly income
- Overtime
- Business travel
- Job satisfaction
- Work life balance
- Company tenure
- Role tenure
- Promotion history
- Attrition status

## ETL and Data Preparation

Power Query was used to prepare the employee data before analysis.

The process included:

- Importing the raw dataset
- Validating column names and data types
- Checking for duplicate employee records
- Checking for null and missing values
- Reviewing invalid and inconsistent category values
- Standardizing business labels
- Preparing numerical fields
- Creating analysis ready employee groups
- Loading the transformed data into the Power BI model

Duplicate and null checks were completed, and no material data quality issues were identified.

Calculated groups were created for:

- Age
- Salary
- Job level
- Job satisfaction
- Work-life balance
- Overtime
- Promotion gap
- Role tenure

## Dashboard Pages

### 1. Dashboard Overview

Provides a central navigation hub for accessing the dashboard’s workforce, attrition, segmentation and retention analysis pages.

### 2. Workforce Profile and Demographics

Provides an overview of workforce size, employee demographics, departments, job roles, education, income, experience and company tenure.

### 3. Employee Attrition Overview

Summarizes overall attrition and examines exits across departments, age groups, education fields and company tenure.

### 4. Employee Attrition Segmentation

Identifies high risk employee groups through job role, gender, salary band and overtime analysis.

### 5. Retention Drivers and Career Development

Examines job level, business travel, job satisfaction, work life balance, promotion gaps, employee exposure and income related attrition.


## Key Insights

1. Overall attrition was 16.1%, representing 237 employee exits.
2. Overtime employees recorded 30.5% attrition, compared with 10.4% among non-overtime employees.
3. Poor work-life balance was associated with 31.3% attrition.
4. Entry-level employees recorded 26.3% attrition.
5. Sales Representatives recorded the highest job-role attrition rate at approximately 39.8%.
6. Recently promoted employees represented the largest promotion-related retention concern because they combined elevated attrition with the largest employee population.


## Tools and Technologies

- Power BI
- Power Query
- DAX
- ETL
- Data Modelling
- KPI Design
- People Analytics
- Business Intelligence
- Data Visualisation

## Repository Structure

```text
dashboard/  Power BI report
data/       Dataset notes and data dictionary
docs/       DAX, ETL and business documentation
images/     Dashboard screenshots
