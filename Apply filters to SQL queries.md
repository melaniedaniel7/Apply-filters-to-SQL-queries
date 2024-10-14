# Apply filters to SQL queries

Disclaimer: This project was created as part of my learning journey through the Google Professional Cybersecurity Certificate offered on Coursera. 
Some activities and content within this project were provided by the course as part of my coursework. All credit for such content belongs to Google 
and Coursera, and I acknowledge their role in supporting the completion of this project.

Be sure to include the following in your completed activity:
- Screenshots of your queries or typed versions of the queries
- Explanations of your queries
- A project description at the beginning
- A summary at the end
- Details on using LIKE to search for a pattern
- Details on filtering for dates and times
- Details on using AND and OR to filter on multiple conditions
- Details on using NOT in filters

Scenario:
You are a security professional at a large organization. Part of your job is to investigate security issues to help keep the system secure. 
You recently discovered some potential security issues that involve login attempts and employee machines.
Your task is to examine the organization’s data in their employees and log_in_attempts tables. 
You’ll need to use SQL filters to retrieve records from different datasets and investigate the potential security issues.

### Project description
Describe what you accomplish through SQL.
In the Project description section, give a general overview of the scenario and what you accomplish through SQL. Write two to four sentences.


### Retrieve after hours failed login attempts
You recently discovered a potential security incident that occurred after business hours. 
To investigate this, you need to query the log_in_attempts table and review after hours login activity. 
Use filters in SQL to create a query that identifies all failed login attempts that occurred after 18:00. 
(The time of the login attempt is found in the login_time column. The success column contains a value of 0 
when a login attempt failed; you can use either a value of 0 or FALSE in your query to identify failed login attempts.)
Describe your query and how it works.



### Retrieve login attempts on specific dates
A suspicious event occurred on 2022-05-09. To investigate this event, you want to review all login attempts which occurred on this day and the day before. 
Use filters in SQL to create a query that identifies all login attempts that occurred on 2022-05-09 or 2022-05-08. 
(The date of the login attempt is found in the login_date column.)
Describe your query and how it works.



### Retrieve login attempts outside of Mexico
There’s been suspicious activity with login attempts, but the team has determined that this activity didn't originate in Mexico. 
Now, you need to investigate login attempts that occurred outside of Mexico. 
Use filters in SQL to create a query that identifies all login attempts that occurred outside of Mexico. 
(When referring to Mexico, the country column contains values of both MEX and MEXICO, and you need to use the LIKE keyword with % to make sure your query reflects this.)
Describe your query and how it works.



### Retrieve employees in Marketing
Your team wants to perform security updates on specific employee machines in the Marketing department. 
You’re responsible for getting information on these employee machines and will need to query the employees table. 
Use filters in SQL to create a query that identifies all employees in the Marketing department for all offices in the East building.
(The department of the employee is found in the department column, which contains values that include Marketing. 
The office is found in the office column. Some examples of values in this column are East-170, East-320, and North-434. 
You’ll need to use the LIKE keyword with % to filter for the East building.)
Describe your query and how it works.



### Retrieve employees in Finance or Sales
Your team now needs to perform a different security update on machines for employees in the Sales and Finance departments. 
Use filters in SQL to create a query that identifies all employees in the Sales or Finance departments. 
(The department of the employee is found in the department column, which contains values that include Sales and Finance.)
Describe your query and how it works.



### Retrieve all employees not in IT
Your team needs to make one more update to employee machines. 
The employees who are in the Information Technology department already had this update, but employees in all other departments need it. 
Use filters in SQL to create a query which identifies all employees not in the IT department. 
(The department of the employee is found in the department column, which contains values that include Information Technology.)
Describe your query and how it works.



### Summary
In the Summary section, provide a short summary of the previous tasks and connect them to the scenario. Write approximately two to four sentences.
