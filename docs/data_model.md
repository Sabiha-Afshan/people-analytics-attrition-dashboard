# Data Model

## Overview

The Power BI solution uses a single employee level table named `Employee Data`.

Each row represents one employee, identified using `EmployeeNumber`.

This structure is suitable because the project uses one static HR dataset.

## Main Fields

The table contains:

- demographics
- department and job role
- income
- overtime
- satisfaction
- work-life balance
- tenure
- promotion history
- attrition status

## Calculated Columns

Business friendly grouping fields were created for:

- age
- tenure
- salary
- education
- job level
- job satisfaction
- work-life balance
- promotion gap

Sort columns were also created so these groups appear in the correct order.

## Measures

Reusable DAX measures were created for:

- total employees
- active employees
- attrition count
- attrition rate
- average age
- average income
- average tenure
- overtime metrics
- first-year attrition
- benchmark comparisons

These measures respond dynamically to dashboard filters.

## Model Validation

The model was validated against the following totals:

- Total Employees: 1,470
- Active Employees: 1,233
- Attrition Count: 237
- Attrition Rate: 16.12%

## Limitation

The current model does not include historical snapshots, manager hierarchy, recruitment data or exit interview data.

For production use, it could be extended into a star schema with separate employee, department, job role and date tables.