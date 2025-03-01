# Apply filters to SQL queries

Disclaimer: This project was created as part of my learning journey through the Google Professional Cybersecurity Certificate offered on Coursera. 
Some activities and content within this project were provided by the course as part of my coursework. All credit for such content belongs to Google 
and Coursera, and I acknowledge their role in supporting the completion of this project.

### Project description
In this activity I acted as a security professional at a large organization. Part of my job was to investigate security issues to help keep the system secure and update employee computers as needed. 
In this scenario I recently discovered some potential security issues that involved login attempts and employee machines.
My task was to examine the organization’s data in their employees and log_in_attempts tables. 
I used SQL filters to retrieve records from different datasets and investigate the potential security issues.
The steps I took to complete this task can be seen below.

### Retrieve after hours failed login attempts
I recently discovered a potential security incident that occurred after business hours. 
To investigate this, I needed to query the `log_in_attempts` table and review after hours login activity. 

I used the greater than operator `>`, the equals `=` operator and the `AND` operator in SQL to create a query that identified all failed login attempts that occurred after 18:00.

In the image below I used the `SELECT *` query to select all columns in the database. 
I then used the `FROM` query to filter data from the `log_in_attempts` table.
Finally, I used the `WHERE` clause to filter for failed login attempts recorded afterhours in the `login_time` column.

To review the `login_time` column for afterhours only, the greater than `>` operator is used followed by the time `18:00`. The greater than operator specifies that I am only interested in data after the specified time period.

💡 Time is considered a distinct data type in SQL and is treated as a literal value, which means it needs to be enclosed in single quotes when queried.

The `AND` operator is used becuase I have two conditions that I want met simultaneously.

To identify failed login attempts I used the fact that MySQL utilizes Boolean data. This means that the Boolean value `1` represents `TRUE` and the Boolean value `0` represents `FALSE`. These can be used interchangeably. In the image below I specified the condition of failed login attempts using `success = FALSE` followed by a semiclon `;` to signify the end of the query. The equals `=` operator paired with `success` and `FALSE` indicates that the login attempt condition must return unsuccessful login attempt results.

💡 Boolean values are not placed in single quotes because they are not string data, they are Boolean data.

The image below highlightes the operators used in green, Boolean data in pink, and the correlation between login time and failed login attempts in blue.

<img src="https://github.com/melaniedaniel7/Apply-filters-to-SQL-queries/blob/f9e24f12755d646bf57b094d2d1e97a77d6cf6fc/Screenshot%202024-10-14%20at%2014.19.14.png" width="600" />

### Retrieve login attempts on specific dates
A suspicious event occurred on 2022-05-09. To investigate this event, I reviewed all login attempts which occurred on this day and the day before. 

I used the equals `=` operator and the `OR` operator in SQL to create a query that identifies all login attempts that occurred on 2022-05-09 or 2022-05-08.

The image below shows how I used the `WHERE` clause to filter for the specific data I am looking for in the `log_in_attempts table`. 
The date of the login attempt is found in the `login_date` column.

The `OR` operator specifies that either condition can be met. I use this operator becuase I want data about login attempts that specifically occured on either `2022-05-08` or `2022-05-09`.

💡 Dates are considered a distinct data type in SQL and are treated as literal values, which means they need to be enclosed in single quotes when queried.

The equals `=` operator indicates that any data I am looking for in the database must have that exact date reflected in the `login_date` column. The equals operator is exclusive, which means that it does not indlude the value of comparison.

💡 When using the `OR` operator the column being specified for each condition must be repeted in full. This is shown in the image below in pink.

The image below highlights the operators used in green and the result of either condition being met for the dates specified for login attempts in blue.

<img src="https://github.com/melaniedaniel7/Apply-filters-to-SQL-queries/blob/13093a11094c40e649ebcd9622f97f638a88bd52/Screenshot%202024-10-14%20at%2015.21.31.png" width="600" />

### Retrieve login attempts outside of Mexico
There was suspicious activity with login attempts, but the team determined that this activity did not originate in Mexico. 
Here I needed to investigate login attempts that occurred outside of Mexico.

I used the `NOT` operator, and the `LIKE` filter paired with the `%` wildcard in SQL to create a query that identifies all login attempts that occurred outside of Mexico. 

I used the `NOT` operator because the suspecious login activity happened in countries excluding Mexico. The `NOT` operator negates a condition.

The `LIKE` filter is used to search for a pattern in a column. In this scenario the `LIKE` filter is searching for a pattern where login attempts where made outside of Mexico.

The `%` wildcard is used because Mexico can be referred to as both `MEX` and `MEXICO` in the country column. The `%` wildcard substitutes for any number of character. This ensures that our query will acurately filter for countries excluding Mexico, regardless of the two format opetions Mexico can be recorded as in the country column.

The image below highlights the `NOT` operator in green, the `LIKE` filter  paired with the `%` wildcard in pink, and the results of countries where login attempts were made outside of Mexico in blue.

<img src="https://github.com/melaniedaniel7/Apply-filters-to-SQL-queries/blob/1ab585636d4683dd378a997847713cee62150d7a/Screenshot%202024-10-15%20at%2010.28.41.png" width="600" />

### Retrieve employees in Marketing
My team wanted to perform security updates on specific employee machines in the Marketing department. 
I am responsible for getting information on these employee machines and I needed to query the employees table. 

I used the equals `=` operator, the `AND` operator, and the `LIKE` filter paired with the `%` wildcard in SQL to create a query that identifies all employees in the Marketing department for all offices in the East building.

The department of the employee is found in the department column, which contains values that include Marketing. I used the equals `=` operator to specify that I only wanted data for this specific department. The equals operator is exclusive.

The `AND` operator specifies that both conditions must be met simultaneously. In this scenario the `AND` operator specifies that the condition of the department being Marketing and the condition of the offices being located in the East buildings must both be met simultaneously.

The `LIKE` filter is used to search for a pattern in a column. In this scenario the `LIKE` filter is searching for a pattern where employees machines from the Marketing department are specificaly located in offices located in the East buildings.

Office's can be found in the office column. In this scenario there are numerous East office buildings. For example, East-170 and East-320.
For this reason I used the `%` wildcard because I wanted to filter for any and every office that meets the other conditions and is located in the East buildings. 

The image below highlights the equals `=` operator and `AND` operator in green, the `LIKE` filter paired with the `%` wildcard in pink, and the two columns displaying the SQL query as successful in blue.

<img src="https://github.com/melaniedaniel7/Apply-filters-to-SQL-queries/blob/fb774e711af057ba261b278979773adde9fbacc9/Screenshot%202024-10-15%20at%2011.48.25.png" width="600" /> 

### Retrieve employees in Finance or Sales
My team then needed to perform a different security update on machines for employees in the Sales and Finance departments.

I used the equals `=` operator and the `OR` operator in SQL to create a query that identifies all employees in the Sales or Finance departments. 

The department of the employee is found in the department column, which contains values that include Sales and Finance.

I used the equals `=` operator to exclusively filter for employees found in the Sales or Finance department only.

I used the `OR` operator becuase I wanted to filter for employee machines that could be found in either department. The `OR` operator specifies that either condition can be met. 

💡 As mentioned previously: When using the `OR` operator, each condition must be specified in full speparately. This can be seen in pink in the image below where the two conditions both concern the department column. 

The image below highlights the equals `=` operator and `OR` operator in green, and the department column where our SQL query is focused on both Sales and Finance in blue.

<img src="https://github.com/melaniedaniel7/Apply-filters-to-SQL-queries/blob/55069a1795bbb3aa8f8a156cba7c72cebec5e314/Screenshot%202024-10-15%20at%2012.21.31.png" width="600" />

### Retrieve all employees not in IT
My team needed to make one more update to employee machines. 
The employees who are in the Information Technology department already had this update, but employees in all other departments need it.

I used the `NOT` operator and equals `=` operator in SQL to create a query which identifies all employees not in the IT department. 

The department of the employee is found in the department column, which contains values that include Information Technology.

The `NOT` operator negates a condition. I used the `NOT` operator because I wanted to filter for employee machines in every department excluding the Information Technology department.

The equals `=` operator exclusively specifies that the department to filter for is Information Technology. This paired with the `NOT` operator creates a SQL query that exclusively filters for employee machines in all departments, excluding Information Technology.

The image below highlights the `NOT` operator and the equals `=` operator in green, and the department column in blue.

<img src="https://github.com/melaniedaniel7/Apply-filters-to-SQL-queries/blob/7cb8286cfa828875b6cbb97e584874ea1fd6320c/Screenshot%202024-10-15%20at%2012.53.19.png" width="600" />

### Summary
I retrieved all failed login attempts after business hours using the `AND` operator. I retrieved all login attempts that occurred on specific dates using the `OR` operator. I retrieved logins that didn't originate in Mexico using the `NOT` operator. I retrieved information about certain employees in the Marketing department using the `AND` operator. I retrieved information about employees in the Finance or the Sales department using the `OR` operator. Finally, I obtained information about employees who are not in the Information Technology department using the `NOT` operator.
