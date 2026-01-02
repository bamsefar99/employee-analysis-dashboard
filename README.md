#Employee Analysis Dashboard
Analyze employee data with Python and Power BI.
Features

Calculates age, tenure, department, and collar type
Visualizes distributions (age, tenure, department, collar type)
Exports enhanced data for Power BI

#Quick Start
Import employee_dataset_with_analysis.xlsx into Power BI.
DAX Formulas (with explanations)


##Age:
Age = DATEDIFF('Employees'[Birthday], TODAY(), YEAR)
Years between birthday and today


##Tenure:
YearsInCompany = DATEDIFF('Employees'[StartDate], TODAY(), DAY) / 365
Days between start date and today, divided by 365


##Tenure Group:
YearsInCompanyGroup = SWITCH(TRUE(), ...)
Groups tenure into ranges (e.g., "1-5 years")


##Collar Type:
CollarType = IF('Employees'[Position] = "Warehouse", "Blue-Collar", "White-Collar")
Classifies by position


##Department/Collar Counts:
Count ... = CALCULATE(COUNTROWS('Employees'), ...)
Counts employees by department or collar type


##Averages:
Average Age = AVERAGEX('Employees', [Age])
Average YearsInCompany = AVERAGEX('Employees', [YearsInCompany])
Calculates averages


##Department Percentage:
Percent by Department = DIVIDE(COUNTROWS('Employees'), CALCULATE(COUNTROWS('Employees'), ALL('Employees')), 0)
Percentage of employees per department


#Suggested Visuals

Bar chart: Tenure groups
Pie chart: Blue vs White Collar
Cards: Average age & tenure
