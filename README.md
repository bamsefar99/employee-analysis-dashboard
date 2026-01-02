
# Employee Analysis Dashboard

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Python 3.8+](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Build: Passing](https://img.shields.io/badge/build-passing-brightgreen.svg)]()
[![Power BI: Ready](https://img.shields.io/badge/Power%20BI-ready-yellow.svg)]()

Analyze employee data with Python and Power BI.

---

## Table of Contents

- [Features](#features)
- [Quick Start](#quick-start)
- [DAX Formulas & Explanations](#dax-formulas--explanations)
- [Suggested Visuals](#suggested-visuals)

---

## Features
- Calculates age, tenure, department, and collar type
- Visualizes distributions (age, tenure, department, collar type)
- Exports enhanced data for Power BI

---

# DAX Formulas & Explanations

## Age:
Age = DATEDIFF('Employees'[Birthday], TODAY(), YEAR)
Years between birthday and today

## Tenure:
YearsInCompany = DATEDIFF('Employees'[StartDate], TODAY(), DAY) / 365
Days between start date and today, divided by 365

## Tenure Group:
YearsInCompanyGroup = SWITCH(TRUE(), ...)
Groups tenure into ranges (e.g., "1-5 years")

## Collar Type:
CollarType = IF('Employees'[Position] = "Warehouse", "Blue-Collar", "White-Collar")
Classifies by position

## Department/Collar Counts:
Count ... = CALCULATE(COUNTROWS('Employees'), ...)
Counts employees by department or collar type

## Averages:
Average Age = AVERAGEX('Employees', [Age])
Average YearsInCompany = AVERAGEX('Employees', [YearsInCompany])
Calculates averages

## Department Percentage:
Percent by Department = DIVIDE(COUNTROWS('Employees'), CALCULATE(COUNTROWS('Employees'), ALL('Employees')), 0)
Percentage of employees per department
