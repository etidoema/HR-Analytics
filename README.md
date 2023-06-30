# HR-Analytics


## Introduction

  The core goal of this case study is to build a report using a fictitious dataset from a tech company atlas lab, the HR team want to be able to monitor key metrics on employees
  
##### Primary goal: Monitor key HR metrics on employees
##### Secondary goal:  Understand what factors impact attrition

### Data Sourcing

1) Educationallevel.csv
2) Employee.csv
3) Performancerating.csv
4) RatingLevel.csv
5) SatistifiedLevel.csv


  “Fact” OR “Dim” were added at the beginning of each table name, depending on its type. All newly loaded tables were reviewed , and the columns are correctly formatted as text, numbers , and dates as expected in the metadata sheet.

## Data Transformation

Data cleaning was performed per table. The table appeared to be clean. The quality of each column is 100% with no error or nulls. Below is a preview of the tables:

![](dimeducationlevel.png)  ![](dimemployee.png)  ![](dimratinglevel.png)  ![](dimsatisfiedlevel.png) ![](factpermancerating.png)


## Date dimension and relating tables
  In a Power BI report, a dedicated date table is highly recommended for accurate date and time reporting. Modelling data is one of the four pillars of Power Bi report development as it enables us to connect different data tables together in the form of a star or snow schema.



### Data Model Design
  The data required for this analysis are located in various tables. Therfore, appropriate modelling is required. A star Schema is designed with the FactPerformance table representing the fact table containing all redundant data, and to which other dimension tables are modelled or connected to, using the column that is common. FactPerformance Table has been modelled. Having a many to one or one to many relationship with its dimension tables. Some relationship in the model are not active. This was activated using USERELATIONSHIP() function in DAX.  
  
![](Data_Model.png)  


1) FactperformanceRating Table using the "PerformanceID"
2) DimEmployee Table using the "EmployeeID"
3) Dimeducation Table using "EducationLevelID"
4) DimRatingLevel Table via "RatingID"
5) DimDate Table via  "Date"
6) DimSatisfiedLevel Table via "SatisfactionID"

### Date dimension and relating tables
In a Power BI report, a dedicated date table is highly recommended for accurate date and time reporting. Modelling data is one of the four pillars of Power Bi report development as it enables us to connect different data tables together in the form of a star or snow schema.



### Data Analyst / Visualization


The leadership team at Atlas Labs is looking to have visibility on high-level metrics about the sate of its employees, in particular, the organization is looking to understand the attrition at the company.
My goal is to explore the available data and calculate this key measure that will be useful throughout the case study.

Step 1
--> Create a new empty table called _Measure
--> Create two measures: ActiveEmployees and InactiveEmployees inside the _Measures tables, which takes count of all employees that are currently active or inactive, respectively, we will use DimEmployee[Attrition] to determine whether an employee is inactive.
--> Calculate % Attrtion Rate based on the previous measures as a percentage with 1 decimal place






