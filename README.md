# Actual-Vs-Budget-Dashboard

## Table of Contents

- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Tools](#tools)
- [Data Cleaning / Preparation](#data-cleaning-/-preparation)
- [Data Modelling](#data-modelling)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Dax, Functions and Formulas](#dax,-functions-and-formulas)
- [Results / Findings](#results-/-findings)
- [Recommendations](#recommendations)

### Project Overview


This project is a deep dive into the amount provided for each department in an organization as a spending budget for a particular period. It then compares the actual amount spent by each department so we can see which departments exceeded their budget and which did not.
This task involves using Power Query to format our data in the required format. We modelled the data using Power Pivot to connect our dimension table with our facts table.
At the end of the project, we were able to make recommendations based on our analysis and results. This helps the organization to decide on funds that will be allocated to each department.

### Data Source

Actual vs Budget Data: Finex Skills provided the primary data in "Actual vs Budget.csv". This file contains two sheets. The first shows the Actual amount spent by different departments in an organization, including the purpose of spending(account name), the names of the departments, and the actual amount spent.
The second sheet shows the budgeted amount for each department. It includes the same columns as the actual sheet.

### Tools

- Microsoft Excel (Data Cleaning, Data Analysis, Data Visualization)

### Data Cleaning / Preparation

- Converted each worksheet to a table and named them accordingly
- Utilized Power Query in assigning proper data type, putting the data in right shape and adding more helper columns.
- Append two tables to create a master table that provided more dimensional tables.

### Data Modelling

Power Pivot helps me model my data by creating a connection between my Fact and dimension tables. This will allow me to query my data correctly and answer any question that the stakeholders would want to see. 
The diagram view of the Power Pivot page shows me the schema, and all I did was drag and drop the columns I wanted to connect. 

### Exploratory Data Analysis

- What is the total actual amount spent by each department?
- Which of the departments did not exceed the budgeted amount?
- Which account names took up most of the budget for each department?
- What month had the lowest and highest spending in the organization?

![Actual spreadsheet](https://github.com/user-attachments/assets/67cf6a80-c7f6-4543-8ce1-a358665b3f63)

### DAX, Functions and Formulas

In the course of analysing this data, I utilised a couple of formulas and functions in Microsoft Excel, such as DAX, Cube functions, and context (this is my first time using this, and it came in handy since it works better with cube functions). 
I also applied some new techniques in Microsoft Excel, which I learnt from Finex Skills.
- Dax (=sum(actual[amount]) and (=sum(budget[amount])
- Cube functions (=CUBEVALUE("ThisWorkbookDataModel","[Measures].["&$G37&"]",Slicer_Department)
- ISNONTEXT (this test for if a cell is empty or not)
  (=IF(ISNONTEXT(CUBEVALUE("ThisWorkbookDataModel","[Measures].["&$G33&"]","[Calendar].[Month Name].["&H$32&"]",Slicer_Scenario,Slicer_Department)),
   CUBEVALUE("ThisWorkbookDataModel","[Measures].["&$G33&"]","[Calendar].[Month Name].["&H$32&"]",Slicer_Scenario,Slicer_Department),NA())

### Results / Findings

![Actual slicer](https://github.com/user-attachments/assets/ecd91218-f82a-4838-bbc4-4600d9023f83)

 - The Sales/Marketing department had the lowest variance and the highest actual spending in October.
 - The Corporate and project departments had the lowest spending in their budget.
 - The project department's lowest spending was on rent, and their highest spending was on salary.
 - The corporate lowest spending was on the telephone, and their highest was on conferences.
 - The lowest spending in the organization happened in June, and the highest was in October.

### Recommendations

- The sales & marketinng department should get more budget for their discount and cost of sales. These are areas where the organization generates revenue so increasing their spendings will yield positive results.
