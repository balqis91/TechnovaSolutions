#  Technova Solutions Employee & Project Management Dashboard
<img width="1160" height="645" alt="image" src="https://github.com/user-attachments/assets/44efec4d-46e9-4561-8bad-1b1f1397ea94" />

##  Overview  
This project leverages **MySQL** and **Power BI** to analyze employee distribution, project assignments, and organizational performance at Technova Solutions.  
It demonstrates **database schema design**, **DAX calculations**, and **interactive dashboards** for HR and management decision-making.  

The solution includes:  
-  **SQL Database** with Employees, Departments, and Projects  
-  **Power BI Dashboard** for employee and project analytics  
-  **Key Metrics** such as total employees, projects, and average years of service  
-  **DAX Measures** for deeper insights  

---




### Data Model  
<img width="1091" height="606" alt="image" src="https://github.com/user-attachments/assets/0eef64b3-b4b4-43ed-b03d-4ae076199f93" />


---

##  Database Schema  

**Employees Table**
- `EmployeeID` (PK)  
- `FirstName`  
- `LastName`  
- `FullName`  
- `Email`  
- `Phone_No`  
- `DepartmentID` (FK → Departments)  

**Departments Table**
- `DepartmentID` (PK)  
- `DepartmentName`  
- `ManagerID`  

**Projects Table**
- `ProjectID` (PK)  
- `ProjectName`  
- `Start_Date`  
- `End_Date`  
- `EmployeeID` (FK → Employees)  

**Date Table**
- `Date`  
- `Day of Week`  
- `Month`  
- `Quarter`  
- `Year`  

---

##  DAX Measures  

Some DAX calculations used in Power BI:

```DAX
-- Total Employees
TotalEmployees = COUNTROWS(Employees)

-- Total Projects
TotalProjects = COUNTROWS(Projects)

-- Average Years of Service
AverageYearOfService = AVERAGE(Employees[YearsOfService])

-- Employees per Department
EmployeesPerDepartment = COUNTROWS(Employees)

-- Projects per Employee
ProjectsPerEmployee = COUNTROWS(Projects) / COUNTROWS(Employees)

-- Recently Hired Employees
RecentlyHired = CALCULATE(
    COUNTROWS(Employees),
    FILTER(Employees, Employees[YearsOfService] <= 2)
)
 Findings
Total Employees: 50 across all departments

Total Projects: 50 active projects

Average Years of Service: 5.7 years

Recently Hired Employees: 2 new hires

Top Department by Projects: Finance (15 projects)

Top 10 Employees: Cynthia Hines, Jeffrey Evans, Jonathan Holmes, etc.

  Conclusion
The Technova Solutions Dashboard provides HR and leadership teams with insights into workforce distribution, project assignments, and tenure analysis.

Future Improvements

Add performance ratings per employee

Track project deadlines vs completion

Include salary and cost analysis

 Tools Used
MySQL – Database design and schema creation

Power BI – Dashboard creation and interactive reporting

DAX – Advanced measures and calculations

ER Modeling – Data model design for relational integrity

 Created by Balikisu Ajoke Oniyide




