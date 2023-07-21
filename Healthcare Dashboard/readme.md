# Financial Dashboard

## Description
Financial Analysis is a Business enforcement duty that involves systematic patterns and trends in Financial State. Pattern information can help Company deploy resources more effectively and detectives.
This solution empowers financial personnel to make informed decisions regarding the financial performance of your company. Developed using the latest Power BI functionality, this solution is easy-to-use and highly customizable to match your company’s branding. 

KPIs include :
1. Total Revenues
2. COGS (Cost of Goods Sold )
3. Operating Income
4. Operating Income %
5. Gross Margin 
6. Gross Margin %
7. Total Assets
8. Current Liabilities
9. Liquidity Ratio
10. Debt to Equity ratio
11. OpEx (Operating Expense)
12. OpEx to Revenues Ratio
13. Current Assets
14. Total Liabilities
15. Working Capital
16. Working Capital Ratio
17. Depreciation & Amortization
18. Total Equity
19. Interest & Taxes
20. Net Income
21. Net Income %


## Datasource :

Dataset used for this task was presented by [Pwc](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) and call centre trends dataset:

Dataset: [Call Centre Trends](https://github.com/kirannavale/Portfolio-Projects/blob/main/PWC%20Call%20Centre%20Trends%20Dashboard/01%20Call-Center-Dataset.xlsx)

## Data Preparation:

Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Call Centre Trends dataset is give table named:

- `Call Center trends dataset` which has `10 columns and 5000 rows` of observation

Data Cleaning for the dataset was done in the power query editor as follows:

- Removed Unnecessary columns
- Removed Unnecessary rows
- Each of the columns in the table were validated to have the correct data type

## Data Modeling:

And then dataset was cleaned and transformed, it was ready to the data modeled.

- The `measure table` and `call centre trends` tables as show below:

-![227766088-7fe8f2b3-b4b3-4cfd-a925-0895874ea956](https://github.com/kirannavale/Portfolio-Projects/assets/34519689/e5d33d5d-cfab-40e6-a9ca-f1f70814344a)

## Data Analysis (DAX):

Measures used in  all visualization are:

- Average of seed of answerd = `AVERAGE('call centre trends'[Speed of answer in seconds])`

- Average of statisfaction = `AVERAGE('call centre trends'[Satisfaction rating])`

- Count satisfation rating = `COUNT('call centre trends'[Satisfaction rating])`

- Overall Customer Satisfation = `DIVIDE([Possitive satisfation rating],[Count satisfation rating],0)`

- Possitive satisfation rating = `CALCULATE(COUNT('call centre trends'[Satisfaction rating]),FILTER('call centre trends','call centre trends'[Satisfaction rating] IN {4,5}))`

- resolved calls = `COUNTX(FILTER('call centre trends','call centre trends'[Resolved] = "Yes"), 'call centre trends'[Resolved])`

- Unresolved calls = `COUNTX(FILTER('call centre trends','call centre trends'[Resolved] = "No"), 'call centre trends'[Resolved])`

- total calls =  `CALCULATE('Table'[total calls answered] + 'Table'[total calls unanswred])`

- total calls answered = `COUNTX(FILTER('call centre trends','call centre trends'[Answered (Y/N)] = "Yes"),'call centre trends'[Answered (Y/N)])`

- total calls unanswred =`COUNTX(FILTER('call centre trends','call centre trends'[Answered (Y/N)] = "No"), 'call centre trends'[Answered (Y/N)])`

## Data Visualization (Dashboard) :

Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

Shows visualizations from Call Center Trends :

| Call Centre Trends (Overview) |
| ----------- |
| ![PWC Task 1 - Call Centre Dashboard-1](https://github.com/kirannavale/Portfolio-Projects/assets/34519689/70645f44-518a-4ec5-ac6d-1deb69e4a3f3)|


| Call Centre Trends (Agent's Performance) |
| ----------- |
| ![PWC Task 1 - Call Centre Dashboard-2](https://github.com/kirannavale/Portfolio-Projects/assets/34519689/b764894a-61b9-4e8d-8b53-dea37320ce33)|

## Insights :

As shown by Data Visualization, It can be deduced that:

- Most of the satisfaction ratings from each call are 3 and 4.
- The average satisfaction rating has decreased over the span of three months. January brought the highest satisfaction rating and march the lowest.
- The percentage of issue resolved in January was the highest, with a dip in February. It increased again in march.
- The majority of calls come in the morning.
- The average speed of answer by Joe is the highest.
- The call resolution rate of Jim is the highest, even though the average speed of his answers is lower compared to those of Joe, Martha and Dan. The call answered by - him are also higher than the average number of calls answered.
- Becky's speed of answer is the lowest among all, and her rate of calls resolved is higher. She is in the 5th position in the call resolution rate. 
- Martha has the highest  speed of answered in the sec

---






