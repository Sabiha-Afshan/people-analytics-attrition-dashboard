# ETL and Data Preparation

## Extract

The anonymised employee dataset was imported into Power BI from a structured source file.

## Transform

Power Query was used to:

- Review the dataset structure and column names
- Validate numerical and categorical data types
- Check for duplicate employee records
- Check for null and missing values
- Review inconsistent category values
- Standardise employee attributes
- Prepare numerical fields for analysis
- Remove unnecessary fields where applicable

Duplicate and null checks were completed, and no material data-quality issues were identified.

Additional calculated categories were created for:

- Age groups
- Salary bands
- Job-level labels
- Job-satisfaction levels
- Work-life-balance levels
- Business-travel categories
- Overtime categories
- Promotion-gap bands
- Role-tenure bands

Custom sort fields were created to preserve the correct business order of grouped categories.

## Load

The cleaned employee table was loaded into the Power BI data model.

DAX measures were then created for workforce KPIs, attrition analysis, employee segmentation and benchmark comparisons.
