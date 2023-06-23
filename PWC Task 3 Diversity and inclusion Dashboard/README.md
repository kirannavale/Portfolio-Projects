# PWC Power BI Virtual work experience - Diversity and Inclusion Analysis

## Problem Statement :

The purpose of this task is to:

- Define proper KPIs in hiring, promotion, performance and turnover
- Create a visualisation for the HR manager that reflects all relevant Key Performance indicators(KPIs) and metrics in the dataset.

Calculating the following measures could help to define proper KPIs:

- Number of men
- Number of women
- Number of leavers
- % employees promoted (FY21)
- % of women promoted
- % of hires men
- % of hires women
- % turnover 
- Average performance rating: men
- Average Performance rating: women

## Datasource :

Dataset used for this task was presented by [Pwc](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) and Diversity and Inclusion dataset:

Dataset: [Diversity and Inclusion](https://github.com/kirannavale/Portfolio-Projects/blob/main/PWC%20Task%203%20Diversity%20and%20inclusion%20Dashboard/03%20Diversity-Inclusion-Dataset.xlsx)

## Data Preparation:

Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Diversity and Inclusion dataset is give table named:

- `Diversity and Inclusion dataset` which has `500 rows and 31 Column` of observation

Data Cleaning for the dataset was done in the power query editor as follows:
- Changed the header row of dataset
- Replaced  the value is `New hire FY20?` N coverted No and Y converted Yes
- Replaced  the value is `In base group for turnover FY20` N coverted No and Y converted Yes
- Replaced  the value is `Promotion in FY20?` N coverted No and Y converted Yes
- Removed Unnecessary columns 
- Removed Unnecessary rows
- Each of the columns in the table were validated to have the correct data type

## Data Modeling:
And then dataset was cleaned and transformed, it was ready to the data modeled.

- The `diversity and inclusion` tables as show below:

![Screenshot (53)](https://github.com/kirannavale/Portfolio-Projects/assets/34519689/dac94191-7186-4399-93a9-76da698c5cc2)

## Data Analysis (DAX):

Measures used in  all visualization are:

- #of leavers = `CALCULATE(COUNTA('HR Manager'[Employee ID]), 'HR Manager'[Leaver FY] IN { "FY20" })`

- #of men =`Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Male"))`

- #of women = `Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Female"))`

- % employees promoted (FY21) =`Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Promotion in FY21?]="Yes")),Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[In base group for Promotion FY21]="Yes")))`

- % of hires men = `Divide('HR Manager'[# of men],('HR Manager'[# of men]+'HR Manager'[# of women]))`

- % of hires women = `Divide('HR Manager'[# of women],('HR Manager'[# of women]+'HR Manager'[# of men]))`

- % Promotees who were men = `Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Male")),distinctcount('HR Manager'[Employee ID]))`

- % Promotees who were women = `Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Female")),distinctcount('HR Manager'[Employee ID]))`

- % Turnover = `Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[FY20 leaver?]="Yes")),Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[In base group for turnover FY20]="Y"))+Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager',NOT('HR Manager'[Department @01.07.2020]=BLANK()))),2))`

- Avg Rating Men = `Calculate(Average('HR Manager'[FY20 Performance Rating]),Filter('HR Manager','HR Manager'[Gender]="Male"))`

- Avg Rating Women = `Calculate(Average('HR Manager'[FY20 Performance Rating]),Filter('HR Manager','HR Manager'[Gender]="Female"))`

## Data Visualization:

Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

Shows visualizations from Diversity and Inclusion:

| Diversity and inclusion HR Dashboard 1 |
| ----------- |
|![PWC Task 3 - Diversity and inclusion Dashboard_page-0002](https://github.com/kirannavale/Portfolio-Projects/assets/34519689/bf61fc4d-13ad-42e9-9efa-a56551dd2b84)|

| Diversity and inclusion HR Dashboard 2 |
| ----------- |
| ![PWC Task 3 - Diversity and inclusion Dashboard_page-0003](https://github.com/kirannavale/Portfolio-Projects/assets/34519689/a30e6684-8ea0-49fd-83c8-1b5bda855984)|

## Insights:

As shown the data Visualization, It can be deduced that:

- 41 % Female hires of the year and 59 % Male hires of the years.
- 53.8% of promoted were Female in the Junior Officer category, the highest for the year.
- 47% of promoted were Male in the Junior Officer category, the lowest for the year.
- Director is the highest Average time of job level promoted in this year.
- Finance department 22% highest turnover of the year.
- Average Rating Female 2.42%
- Average Rating Male 2.41%
- Employees promoted year of 2021 is  54.34% Male and 45.66% Female.
- The most common age group is 20-29 having 223 employees fall in this category.

---

