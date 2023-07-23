<h1>Apply Filters to SQL Queries</h1>


<h2>Description</h2>
This project consists of demonstrating how to to use SQL with filters to perform security-related tasksupdate file permissions for certain files and directories within "projects" directory. The permissions do not currently reflect the level of authorization that should be given. Checking and updating these permissions will help keep their system secure. To complete this task, I performed the following tasks:

<br />


<h2>Language</h2>

- <b>SQL</b> 


<h2>Environment Used </h2>

- <b>Linux/Bash</b> 

<h2>Project Walk-Through:</h2>

<p align="center">
<b>Retrieve after hours failed login attempts:</b> <br>
                                    
The following code demonstrates how I created a SQL query to filter for failed login attempts that occurred after business hours.
 <p align="center"> 
<img src="https://i.imgur.com/GL3lBoY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br>
<br />
<p align=” justify”>
The first part of the screenshot is my query, and the second part is a portion of the output. This query filters for failed login attempts that occurred after 18:00. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an AND operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition is login_time > '18:00', which filters for the login attempts that occurred after 18:00. The second condition is success = FALSE, which filters for the failed login attempts. 
<br />
<br />
<p align="center">
<b>Retrieve login attempts on specficic dates:</b>  <br/>
  
I determined that a suspicious event occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or on the day before needs to be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred on specific dates.

<p align="center">
<img src="https://i.imgur.com/cmQDUrn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br>
<br />
<p align=” justify”>
The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an OR operator to filter my results to output only login attempts that occurred on either 2022-05-09 or 2022-05-08. The first condition is login_date = '2022-05-09', which filters for logins on 2022-05-09. The second condition is login_date = '2022-05-08', which filters for logins on 2022-05-08.
<br />
<br />
<p align="center">
<b>Retrieve login attempts outside of Mexico:</b> <br/>

After investigating the organization’s data on login attempts, I believe there is an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated.

The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico. 

<p align="center">
<img src="https://i.imgur.com/3x3cADQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
  
The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred in countries other than Mexico. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with NOT to filter for countries other than Mexico. I used LIKE with MEX% as the pattern to match because the dataset represents Mexico as MEX and MEXICO. The percentage sign (%) represents any number of unspecified characters when used with LIKE. 
<br />
<br />
<p align="center">
<b>Retrieve employees in Marketing:</b> <br/>

I now want to update the computers for certain employees in the Marketing department. To do this, I have to get information on which employee machines to update.

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Marketing department in the East building.

<p align="center">
<img src="https://i.imgur.com/WTfHHUI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br /> 
<p align=” justify”>
The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Marketing department in the East building. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with AND to filter for employees who work in the Marketing department and in the East building. I used LIKE with East% as the pattern to match because the data in the office column represents the East building with the specific office number. The first condition is the department = 'Marketing' portion, which filters for employees in the Marketing department. The second condition is the office LIKE 'East%' portion, which filters for employees in the East building.
  <br /> 
  <br /> 
<p align="center">
<b>Retrieve employees in Finance or Sales:</b> <br/>

The machines for employees in the Finance and Sales departments also need to be updated. Since a different security update is needed, I have to get information on employees only from these two departments.

The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Finance or Sales departments.

<p align="center">
<img src="https://i.imgur.com/mFQ7Xk8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br /> 
<p align=” justify”>
The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Finance and Sales departments. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with OR to filter for employees who are in the Finance and Sales departments. I used the OR operator instead of AND because I want all employees who are in either department. The first condition is department = 'Finance', which filters for employees from the Finance department. The second condition is department = 'Sales', which filters for employees from the Sales department.
<p align="center">
<br />
<p align="center">
<b>Retrieve employees not in IT:</b> <br/>

One more security update needs to be executred on employees who are not in the Information Technology department. To make the update, I first have to get information on these employees.

The following demonstrates how I created a SQL query to filter for employee machines from employees not in the  Information Technology department.

<p align="center">
<img src="https://i.imgur.com/LaBvyrS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br /> 
The first part of the screenshot is my query, and the second part is a portion of the output. The query returns all employees not in the Information Technology department. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with NOT to filter for employees not in this department.
<br />
<br /> 
<p align="center">
<b>Summary</b> <br/>
  
<p align=” justify”>
I applied filters to SQL queries to get specific information on login attempts and employee machines. I used two different tables, log_in_attempts and employees. I used the AND, OR, and NOT operators to filter for the specific information needed for each task. I also used LIKE and the percentage sign (%) wildcard to filter for patterns.
<br />
<br />
