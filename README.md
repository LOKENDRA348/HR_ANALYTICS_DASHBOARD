##HR_ANALYTICS_DASHBOARD
#Overview of HR Analytics Dashboard
The HR Analytics Dashboard in Power BI provides an in-depth analysis of workforce trends, helping HR teams make data-driven decisions. It includes key performance indicators (KPIs) such as total employees, attrition percentage, promotion rate, average performance scores, and salary distribution.
The dashboard features visualizations like stacked bar charts to analyze attrition by department, line charts to compare salary vs. performance, and funnel charts to assess salary distribution across job roles. Additionally, a donut chart highlights regional salary trends, while a treemap tracks leave patterns across departments.
By analyzing these metrics, HR teams can identify turnover trends, evaluate pay equity, and optimize workforce planning. The dashboard enables businesses to enhance employee satisfaction, improve retention strategies, and ensure fair compensation. With interactive filters and slicers, users can dynamically explore insights based on different regions and employee attributes, making this an essential tool for HR decision-making

Step 1: Load Data
Source: Excel file (already cleaned).
Action: Load data into Power BI.
Initial Setup:
Use a Textbox to write "HR Analytics Dashboard" as a title.
Add a Slicer for the Region column and set its format to Tile for better visibility.
Step 2: Data Transformation
Tool: Power Query Editor
Action: The data is already clean, so the only transformation applied is:
Sorting the Department column in ascending order for better organization.
#Step 3: Data Modeling
Schema Type: Flat Schema (only one table used).
Structure: The table contains both quantitative (numeric) and descriptive (categorical) data.
Reason for Flat Schema: Since all required data is in a single table, no relationships are needed.
Step 4: Creating DAX Measures for KPI Cards
KPI Name	DAX Formula
Total Employees	Total_Employe = COUNT(Sheet1[Employee_ID])
Attrition Percentage	Total_Attrition_Percentage = DIVIDE(COUNTROWS(FILTER(Sheet1,Sheet1[Attrition]="Yes")), COUNTROWS(Sheet1))
Average Employee Performance	Avg_Employee_Performance = AVERAGE(Sheet1[Performance Score])
Promotion Rate	Promotion_Rate = DIVIDE(COUNTROWS(FILTER(Sheet1,Sheet1[Promotion]="Yes")),COUNTROWS(Sheet1))
Average Work Hours per Week	Avg_Work_Hours_per_Week = AVERAGE(Sheet1[Work Hours/Week])
Total Male Employees	Total_Male = COUNTROWS(FILTER(Sheet1,Sheet1[Gender]="Male"))
Total Female Employees	Total_Female = COUNTROWS(FILTER(Sheet1,Sheet1[Gender]="Female"))
Average Training Hours	Avg_Training_Hour = AVERAGE(Sheet1[Training Hours])
Step 5: Adding Visuals & Their Analysis
1️ Stacked Bar Chart
X-Axis: Employee ID
Y-Axis: Department
Legend: Attrition
Insight:
Helps identify departments with high attrition rates.
Shows whether employee turnover is concentrated in specific departments.
2️ Stacked Column Chart
X-Axis: Department
Y-Axis: Sum of Salary
Insight:
Compares salary distribution across different departments.
Identifies departments with the highest payroll expenses.
3️ Gauge Chart
Value: Average Employee Performance
Insight:
Provides a quick view of the overall employee performance score.
Helps in tracking performance improvement over time.
4️ Stacked Column Chart
X-Axis: Age
Y-Axis: Attrition
Legend: Gender
Insight:
Shows which age groups have higher attrition rates.
Helps in identifying if a specific gender in certain age groups is leaving more frequently.
5️ Line Chart
X-Axis: Department
Y-Axis: Salary
Secondary Y-Axis: Average Employee Performance
Insight:
Visualizes the relationship between salary and employee performance in each department.
Identifies whether higher salaries correlate with better performance.
6️ Donut Chart
Legend: Region
Values: Salary
Insight:
Displays salary distribution across different regions.
Helps analyze regional salary disparities.
7️ Funnel Chart
Category: Job Role
Value: Salary
Insight:
Highlights which job roles receive higher salaries.
Helps understand if salary distribution is fair across roles.
8️ Treemap
Category: Department
Value: Leave Taken
Insight:
Shows which departments have the highest leave requests.
Helps HR analyze work-life balance trends in different departments.
