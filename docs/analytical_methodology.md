# Analytical Methodology

## 1. Objective

The objective of this project was to analyse employee level HR data and build an interactive Power BI decision support solution for workforce profiling, attrition analysis and retention planning.

The analysis was designed to help HR and business leaders understand:

1. How the workforce is distributed
2. Where employee attrition is concentrated
3. Which groups show elevated attrition
4. Which workplace and career factors are associated with retention
5. Which employee segments may require further investigation.

The project is descriptive and diagnostic. It does not predict individual employee attrition and does not establish causal relationships.

---

## 2. Data Preparation

The employee dataset was imported into Power BI using Power Query.

The preparation process included:

1. Reviewing column names and data types
2. Checking employee level records
3. Retaining `EmployeeNumber` as the unique employee identifier
4. Removing constant columns that did not contribute to analysis
5. Validating workforce and attrition totals
6. Preparing the dataset for segmentation and KPI reporting.

The following constant columns were removed:

- `EmployeeCount`
- `Over18`
- `StandardHours`

These columns contained the same value for every employee and did not provide analytical value.

---

## 3. Employee Segmentation

Calculated columns were created to convert numerical fields into business friendly groups.

The main segmentation fields included:

### Age Group

- 18–25
- 26–35
- 36–45
- 46–55
- 56+

### Tenure Band

- 0–1 Years
- 2–3 Years
- 4–5 Years
- 6–10 Years
- 11+ Years

### Salary Slab

- Up to 5K
- 5K–10K
- 10K–15K
- 15K+

### Job Level

- Entry Level
- Junior / Associate
- Mid-Level
- Executive
- Senior

### Promotion Gap

- Promoted This Year
- 1–2 Years
- 3–5 Years
- 6–10 Years
- 11+ Years

Additional labels were created for:

- Education level
- Overtime status
- Business travel
- Job satisfaction
- Work-life balance.

Sort columns were created to ensure the categories appeared in the correct business order.

---

## 4. KPI Design

Reusable DAX measures were created so that all KPIs respond dynamically to filters and slicers.

The main KPIs included:

- Total Employees
- Active Employees
- Attrition Count
- Attrition Rate
- Average Age
- Average Monthly Income
- Average Years at Company
- Average Total Working Years
- Overtime Employee Percentage
- Overtime Attrition Rate
- Overtime Attrition Gap
- First-Year Attrition Rate
- Male Attrition Share
- Female Attrition Share

Distinct employee count was used to ensure each employee was counted once.

---

## 5. Rate, Count and Exposure Analysis

Attrition was analysed using three different views:

### Attrition Count

Shows how many employees left. This helps measure operational impact and exit volume.

### Attrition Rate

Shows the percentage of employees who left within a specific group. This helps compare risk across groups of different sizes.

### Employee Exposure

Shows how many employees belong to a particular risk group. This helps distinguish between:

- a small group with a high attrition rate
- a large group with moderate attrition
- a group combining high attrition and high employee exposure.

Using these measures together reduces the risk of drawing conclusions from percentages alone.

---

## 6. Benchmark Analysis

Company level benchmark measures were created using DAX filter-context control.

These benchmarks included:

- overall company attrition rate
- job-level attrition benchmark
- average monthly income benchmark
- job-role attrition benchmark

Benchmark lines were used to identify employee groups that were above or below the company average.

For example, the job-role income and attrition chart separates roles into four broad areas:

- lower income and higher attrition;
- higher income and higher attrition;
- lower income and lower attrition;
- higher income and lower attrition.

This supports prioritisation without claiming that income alone causes attrition.

---

## 7. Dashboard Structure

The dashboard was organised into five pages.

### Dashboard Overview

Introduces the project and provides page navigation.

### Workforce Profile and Demographics

Establishes the workforce baseline using department, age, education, job role and gender analysis.

### Employee Attrition Overview

Summarises overall attrition and compares rate, count and share across workforce groups.

### Employee Attrition Segmentation

Identifies employee segments with elevated attrition using job role, gender, salary and overtime.

### Retention Drivers and Career Development

Examines job level, satisfaction, work-life balance, promotion gaps, income and business travel.

---

## 8. Analytical Interpretation

The dashboard was interpreted using the following principles:

### Rates and counts were not treated as the same measure

A large department may contribute the highest number of exits without having the highest attrition rate.

### Small groups were interpreted carefully

A small number of exits can create a high percentage in a small employee group.

### Associations were not treated as causes

The analysis identifies relationships between employee characteristics and attrition. It does not prove that overtime, income, satisfaction, work-life balance or promotion timing directly caused employees to leave.

### Non-linear patterns were retained

Not every relationship followed a simple increasing or decreasing pattern. For example, work-life balance and promotion-gap analysis showed non-linear results, so the interpretation did not assume that each category change produced a consistent reduction in attrition.

---

## 9. Quality Assurance

The dashboard was validated against expected totals and known results.

Key checks included:

- Total Employees = 1,470
- Active Employees = 1,233
- Attrition Count = 237
- Attrition Rate = 16.12%
- Male Employees = 882
- Female Employees = 588
- Overtime Employees = 416
- Overtime Attrition Rate = 30.5%
- Non-Overtime Attrition Rate = 10.4%
- Overtime Attrition Gap = approximately 20.1 percentage points

Additional checks included:

- correct sort order for category bands
- correct filter behaviour
- agreement between KPI cards and visuals
- correct benchmark behaviour
- consistent percentage formatting
- functioning navigation buttons.

---

## 10. Business Recommendation Framework

Recommendations were developed using three elements:

1. Evidence : What the dashboard showed.
2. Interpretation : What the pattern may mean for the business.
3. Recommended Action : What HR or business leaders could investigate or test.

Examples included:

- reviewing workload and overtime conditions
- investigating high risk job roles
- reviewing entry level retention
- examining promotion and career development gaps
- conducting targeted employee-listening sessions
- tracking retention interventions over time.

These recommendations are decision support suggestions and not proven treatments.

---

## 11. Limitations

The methodology has several limitations:

- the dataset is static and historical
- exit reasons were not available
- manager level factors were not included
- intervention outcomes were not available
- the analysis does not establish causation
- the dashboard does not provide real time monitoring
- some employee groups contain small populations
- the project does not predict individual employee attrition.

---

## 12. Production Requirements

Before production deployment, the solution would require:

- connection to an approved HR data source
- scheduled refresh
- data quality monitoring
- role based access control
- row level security where required
- protection of employee personal information
- documented KPI ownership
- user-acceptance testing
- deployment through controlled Power BI workspaces
- ongoing validation of measures
- tracking of retention interventions and outcomes.