# 1. Total Employees

Total Employees =
DISTINCTCOUNT('Employee Data'[EmployeeNumber])

# 2. Attrition Count

Attrition Count =
CALCULATE(
    [Total Employees],
    'Employee Data'[Attrition] = "Yes"
)

# 3. Active Employees

Active Employees =
CALCULATE(
    [Total Employees],
    'Employee Data'[Attrition] = "No"
)

# 4. Attrition Rate

Attrition Rate =
DIVIDE(
    [Attrition Count],
    [Total Employees],
    0
)

# 5. Average Age

Average Age =
AVERAGE('Employee Data'[Age])

# 6. Average Monthly Income

Average Monthly Income =
AVERAGE('Employee Data'[MonthlyIncome])

# 7. Average Years at Company

Average Years at Company =
AVERAGE('Employee Data'[YearsAtCompany])

# 8. Female Employees

Female Employees =
CALCULATE(
    [Total Employees],
    'Employee Data'[Gender] = "Female"
)

# 9. Male Employees

Male Employees =
CALCULATE(
    [Total Employees],
    'Employee Data'[Gender] = "Male"
)

# 10. Average Total Working Years

Average Total Working Years =
AVERAGE('Employee Data'[TotalWorkingYears])

# 11. Overtime Employees

Overtime Employees =
CALCULATE(
    [Total Employees],
    'Employee Data'[OverTime] = "Yes"
)

# 12. Overtime Employee Percentage

Overtime Employee Percentage =
DIVIDE(
    [Overtime Employees],
    [Total Employees],
    0
)

# 13. Average Income

Average Income =
AVERAGE('Employee Data'[MonthlyIncome])

# 14. Create Overtime Attrition Rate measure

Overtime Attrition Rate =
DIVIDE(
    CALCULATE(
        [Attrition Count],
        'Employee Data'[OverTime] = "Yes"
    ),
    CALCULATE(
        [Total Employees],
        'Employee Data'[OverTime] = "Yes"
    ),
    0
)

# 15. Non-Overtime Attrition Rate

Non-Overtime Attrition Rate =
DIVIDE(
    CALCULATE(
        [Attrition Count],
        'Employee Data'[OverTime] = "No"
    ),
    CALCULATE(
        [Total Employees],
        'Employee Data'[OverTime] = "No"
    ),
    0
)

# 16. Overtime Attrition Gap

Shows the difference between overtime and non-overtime attrition rates.

Overtime Attrition Gap =
[Overtime Attrition Rate] - [Non-Overtime Attrition Rate]

# 17. First-Year Attrition Rate

First-Year Attrition Rate =
DIVIDE(
    CALCULATE(
        [Attrition Count],
        'Employee Data'[YearsAtCompany] <= 1
    ),
    CALCULATE(
        [Total Employees],
        'Employee Data'[YearsAtCompany] <= 1
    ),
    0
)

# 18. Male share of attrition

Male Attrition Share =
DIVIDE(
    CALCULATE(
        [Attrition Count],
        'Employee Data'[Gender] = "Male"
    ),
    [Attrition Count],
    0
)

# 19. Female share of attrition

Female Attrition Share =
DIVIDE(
    CALCULATE(
        [Attrition Count],
        'Employee Data'[Gender] = "Female"
    ),
    [Attrition Count],
    0
)

# 20. Creating Male Attrition Remainder measure because to create a donut chart, it will need both the filled portion and the remaining portion.

Male Attrition Remainder = 1 - [Male Attrition Share]

# 21. Creating Female Attrition Remainder measure 

Female Attrition Remainder = 1 - [Female Attrition Share]

# 22. Creating Company Attrition benchmark measure:

Company Attrition Benchmark = 
CALCULATE(
    [Attrition Rate],
    REMOVEFILTERS('Employee Data'[OverTime]),
    REMOVEFILTERS('Employee Data'[Overtime Label])
)

# 23. Creating Job Level Benchmark measure:

Job Level Benchmark = 
CALCULATE(
    [Attrition Rate],
    REMOVEFILTERS('Employee Data'[JobLevel]),
    REMOVEFILTERS('Employee Data'[Job Level Label]),
    REMOVEFILTERS('Employee Data'[Job Level Sort])
)

# 24. Income Benchmark - 

This calculates the average monthly income across all job roles by removing the current JobRole filter.Without REMOVEFILTERS, Power BI would calculate a different income value for each role. With it, the measure returns one common benchmark—approximately 6.5K (Also verifiable from Demographics page’s Average Monthly Income KPI).

Income Benchmark =
CALCULATE(
    [Average Monthly Income],
    REMOVEFILTERS('Employee Data'[JobRole])
)

# 25. Role Attrition Benchmark - 

This calculates the overall attrition rate by removing the current job-role filter. It should return approximately 16.1% (Verifiable from Company Attrition benchmark (Overtime) and Job Level Benchmark).

Role Attrition Benchmark =
CALCULATE(
    [Attrition Rate],
    REMOVEFILTERS('Employee Data'[JobRole])
)
