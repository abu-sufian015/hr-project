# hr-project
### This project used based on customer requirement ,used tools like power-BI.

#### Project requirements

 - How many people are in each job?
 - Gender break-down of the staff
 - Age spread of the staff
 - Which jobs pay more?
 - Top earners in each job
 - Qualification vs. Salary
 - Staff growth trend over time
 - Employee filter by starting letter
 - Leave balance analysis
 - Quick HR Dashboard


##### Some important formulas and calculations:
 - countrows= count each rows per table
   

###### Explanation of Formula Each Part: <br>
VAR currentdate = LASTDATE(employes[Date of Join]) <br>

This variable currentdate stores the latest (most recent) date from the employes[Date of Join] column.<br>

LASTDATE() returns the last date available in the current filter context.<br>

RETURN CALCULATE([maincount], ALL(employes[Date of Join]), employes[Date of Join] <= currentdate)<br>

The CALCULATE function modifies the calculation of [maincount] while applying certain conditions:<br>

ALL(employes[Date of Join]): Removes any existing filters from the Date of Join column, ensuring that the entire table is considered.<br>

employes[Date of Join] <= currentdate: Applies a filter to include only employees who joined on or before the currentdate.<br>

What This Measure Does
It calculates the cumulative total of [maincount] up to the most recent Date of Join.<br>

Essentially, this measure gives the running total of employees who have joined up to the latest available date.<br>



2️⃣ Measures & Calculations (DAX) <br>
Check DAX measures in Modeling → Manage Measures <br>
🔹 Common HR KPIs in Power BI: <br>
✅ Total Employees → COUNTROWS(Employees)<br>
✅ Active Employees → CALCULATE(COUNTROWS(Employees), Employees[Status] = "Active")<br>
✅ Cumulative Employee Count → (Your DAX formula from before)<br>
✅ Average Salary → AVERAGE(Salary[Salary Amount])<br>
✅ Absenteeism Rate → DIVIDE(COUNT(Attendance[Absent]), COUNT(Attendance[Date]))<br>
