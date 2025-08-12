# Industrial Problem: Production Downtime in Manufacturing

![Dashboard_Page_1](/MD-1.png)

## Introduction: - 
•	
•	This Dashboard was created for Manufacturing plants often face unexpected **machine downtime, causing loss of productivity, increased costs, and missed delivery deadlines**.
 Plant managers struggle to pinpoint why, when, and where downtime are happening.
•	To monitor, analyze, and reduce machine downtime in a manufacturing environment by providing multi-level insights into causes, trends, and responsible factors.
And, 
**Provide high-level visibility into plant performance and downtime trends**. 
•	
## Skills Showcased
•	
•	**DATA TRANSFORMATION (ETL) WITH POWER QUERY:**
•	Cleaned, shaped and prepared the raw data for analysis by handling blanks, changing data types, and creating new columns. 

## KPI Questions for Downtime Analysis
 **Overall Performance**
1. What is the total downtime (hours/minutes) for the selected period?
2. How many downtime events occurred?
3. What is the average downtime per day?
4. What is the average downtime per machine?
5. What is the trend of downtime over time — is it increasing or decreasing?
6. Which operator has the highest downtime events?
7. Is downtime higher in a specific shift (A, B, or C)?
8. Are we meeting the downtime reduction target this month?
9. Which areas require urgent improvement to meet yearly goals?
10. What Downtime Reason have a maximum impact?

**Measures and DAX**

1. Average Downtime per Day = 
AVERAGEX(
  SUMMARIZE('Downtime Data', 'Downtime Data'[Downtime_Start].[Date], "DailyTotal", SUM('Downtime Data'[Downtime_Minutes])),
  [DailyTotal])

2. DayFromStart = DAY('Downtime Data'[Downtime_Start])
   
3. Downtime Hours = 
DATEDIFF('Downtime Data'[Downtime_Start], 'Downtime Data'[Downtime_End], HOUR)

4. Downtime Minutes = 
DATEDIFF('Downtime Data'[Downtime_Start], 'Downtime Data'[Downtime_End], MINUTE)
  
## Page 1 – Machine Downtime

![Dashboard_Page_1](/MD-1.png)
	
 **KPI Cards (Max, Min, Count, Average Downtime)**
•	Type: Card Visual
•	Purpose: Quickly display key performance indicators for downtime.
•	Metrics shown:
•	*Max Downtime in Minutes
•	Min Downtime in Minutes
•	Count of Downtime Minutes
•	Average Downtime in Minutes*

**Pie Chart – Sum of Downtime Hours by Operator**
•	Type: Pie Chart
•	Purpose: Shows each operator’s contribution to total downtime.
•	Feature: Easy to compare downtime percentages between operators.
•	Example Insight: Ravi accounts for 25% of total downtime.

**Line Chart – Sum of Downtime Hours by Month and Day**
•	Type: Line Chart
•	Purpose: Displays downtime trend over days in a month.
•	Feature: Detect peak downtime days for targeted analysis.
•	Example Insight: Downtime peaked on 11th July.

**Bar Chart – Sum of Downtime Hours by Department**
•	Type: Clustered Bar Chart
•	Purpose: Compare total downtime between departments.
•	Feature: Highlights most impacted departments.
•	Example Insight: Assembly had the highest downtime.
	
**Matrix Table – Machine Downtime in Hours per Shift**
•	Type: Matrix
•	Purpose: Cross-analysis of machine downtime by shift.
•	Feature: Shows department totals, machine totals, and shift     totals in one view.
•	Example Insight: M02, M03 & M04 has highest total downtime across shifts.

**Insight Text- All important information about the visuals and overview.**
 Highest downtime contributor: Ravi — 25% of total downtime hours
Ali (23.08%) and John (21.15%)
Assembly: 22 hours (highest downtime)
Machine ID  M02 and M03 should be a priority for replacement and schedule check because from 01 July to 11 July. it showed a maximum downtime.
From a duration of  01 July to 11 July  Shift A and B  observe a major downtime due to staffing, workload, and machine health.
.Focus improvement initiatives on Assembly — preventive maintenance, workflow optimization, or operator training.

## Page 2 – Downtime Reason

![Dashboard_Page_1](/MD-2.png)

**Large KPI Card – Operator Name**
•	Type: Card Visual
•	Purpose: Focuses on selected operator’s data.

**KPI Cards – Max & Min Downtime**
•	Type: Card Visual
•	Purpose: Shows downtime extremes for the selected operator.
	
**Table – Detailed Downtime Log**
•	Type: Table
•	Purpose: Lists of Department,Operator, Shift, Machine ID, Downtime Reason, Hours Downtime.
•	Feature: Filtered per operator.
•	Example Insight: Ravi and Ali as a operator have a Maximum downtime within Assembly Department.
	
**Tree Map – Count of Downtime Reason by Department**
•	Type: Tree Map
•	Purpose: Shows number of downtime cases by reason and department.
•	Feature: Size of box = downtime frequency.

**Donut Chart – Sum of Downtime Hours by Downtime Reason**
•	Type: Donut Chart
•	Purpose: Shows downtime breakdown by cause.
•	Example Insight: Sensor errors (28.85%), Mechanical Failure(23.08%), Overheating(21.15%) and Power Outage(17.31%).These almost cover around 90.39% reason for the downtime.

**Insight Text- All important information about the visuals and overview.**
Insights
Root Causes of Downtime in Assembly is due to power outage, Mechanical Failure, sensor error and Overheating.
Downtime is spread across A, B, and C shifts — no single shift is the sole problem, meaning the issue is likely machine- or process-related rather than Staff Scheduling.
Overall  Downtime profile highlights machine M02 & M03 and the Assembly department as high-risk areas.
Almost (90.39%) of Downtime Reason is due to Sensor error, Mechanical failure, Overheating, and Power Outage. Addressing this through preventive maintenance and sensor calibration could significantly reduce total downtime.

## Page 3 – Conclusion

![Dashboard_Page_1](/MD-3.png)
	
**Horizontal Bar Chart – Count of Downtime Reason by Department**
•	Type: Horizontal Bar Chart
•	Purpose: Compare downtime events by department.
	
**Table – Machine Downtime by Cause**
•	 Type: Table / Matrix
•	Purpose: Cross-tab of machines vs. downtime causes.
•	Feature: Total downtime events per machine.

**Type: Table / Matrix**
•	Purpose: Cross-tab of machines vs. downtime causes.
•	Feature: Total downtime events per machine.

**Bar Chart – Sum of Downtime Minutes by Department**
•	Type: Clustered Bar Chart
•	Purpose: Shows total downtime minutes in each department.

•**KPI Table – Operator Max/Min Downtime**
•	Type: Table
•	Purpose: Shows longest and shortest downtime events for each operator.

**Text Box – Problem Statement, Objectives, Benefits**
•	Type: Static Text Visual
•	Purpose: Summarizes business context, dashboard goals, and benefits.
	
**Filters/Slicers: Operator, Shift, Department, Machine ID**
**Color Coding: Used to highlight high values (red/orange) and low values (blue)**
**Interactivity: All visuals are connected — clicking on one filters others instantly**


## Conclusion

 Machine ID M04 ( Mechanical Failure, overheating & power outage), M03 (Mechanical Failure ,Power Outage, & Sensor Error), M02 (Sensor Error, mechanical failures, Maintenance & Overheating ) M01 (Overheating ,Sensor error)  need to Maintenance and part Replacement.

## Root Cause Action Plans              
Overheating: Improve cooling & load balancing.
Sensor Errors: Calibrate & replace faulty sensors.
Power Outages: Backup power solutions.
 Maintenance : implement preventive maintenance & operator training.
 root causes are likely machine- or system-related, not personnel-specific.

## Solution:
Predictive Maintenance need to implement.
Faulty Sensor need to change and maintain checklist.

