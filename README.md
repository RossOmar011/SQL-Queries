# SQL-Queries
Scenario: LoginAttempts
# Applying Filters to SQL Queries

## Project Description
In an effort to make our system more secure, my organization has tasked me with ensuring the system's safety, investigating potential security issues, and updating employee computers as necessary. Here’s how I used SQL queries with filters to achieve various security-related tasks:

# Retrieve After-Hours Failed Login Attempts

A potential security incident occurred after business hours (after 18:00). To investigate, I needed to filter for all failed login attempts that happened after hours.

SELECT * FROM log_in_attempts
WHERE login_time > '18:00' AND success = FALSE;

Objective:
* Identify failed login attempts occurring after 18:00.

Conditions:
* login_time > '18:00' filters for login attempts after business hours.
* success = FALSE filters for failed login attempts.
 
# Retrieve Login Attempts on Specific Dates

A suspicious event happened on 2022-05-09. I had to filter for login attempts that occurred on 2022-05-09 and the day before (2022-05-08) for investigation.

SELECT * FROM log_in_attempts
WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';

Objective:
* Investigate login attempts on the suspicious dates.

Conditions:
* login_date = '2022-05-09' filters for login attempts on 2022-05-09.
* login_date = '2022-05-08' filters for login attempts on 2022-05-08.


# Retrieve Login Attempts Outside of Mexico

I suspected issues with login attempts originating from outside Mexico. I needed to filter these login attempts for further investigation.

SELECT * FROM log_in_attempts
WHERE country NOT LIKE 'MEX%';

Objective:
* Identify login attempts from countries other than Mexico.

Conditions:
* country NOT LIKE 'MEX%' filters for login attempts from outside Mexico, using MEX% to cover variations in country representation (e.g., MEX or MEXICO).


# Retrieve Employees in Marketing
To update computers for employees in the Marketing department located in the East building, I needed specific employee information.

SELECT * FROM employees
WHERE department = 'Marketing' AND office LIKE 'East%';

Objective:
* Find employees in Marketing within the East building.

Conditions:
* department = 'Marketing' filters for employees in the Marketing department.
* office LIKE 'East%' filters for employees in the East building.


# Retrieve Employees in Finance or Sales

For a different security update, I needed to get information on employees in the Finance and Sales departments.

SELECT * FROM employees
WHERE department = 'Finance' OR department = 'Sales';

Objective:
* Find employees in Finance or Sales departments.

Conditions:
* department = 'Finance' filters for employees in the Finance department.
* department = 'Sales' filters for employees in the Sales department.

# Retrieve All Employees Not in IT

Finally, for a security update targeting non-IT employees, I had to filter out employees in the Information Technology department.

SELECT * FROM employees
WHERE department != 'IT';

Objective: 
* Exclude employees in the IT department.

Conditions:
* department != 'IT' filters for employees not in the Information Technology department.


#### Summary

By applying various SQL filters and operators such as AND, OR, NOT, and LIKE, I was able to retrieve specific information about login attempts and employee machines. This detailed filtering helped in investigating security incidents and updating employee computers efficiently.
##
## Incident Report Analysis

|   | Incident |
| ------------- | ------------- |
| Summary  | The investigation involves querying various datasets to identify suspicious login attempts and specific employee machines that require security updates. By using SQL filters, you can retrieve the necessary records to address the potential security issues and ensure the system remains secure  |
| Idenitfy  | The incident affected the security of the organization's systems, specifically involving login attempts and employee machines. The potential security issues discovered included after-hours login attempts, suspicious events on specific dates, and login attempts outside of Mexico. Additionally, the incident required security updates for employee machines in the Marketing, Sales, and Finance departments, as well as for employees in all departments except the Information Technology department  |
| Protect  | To protect internal assets, it is crucial to implement comprehensive policies, procedures, training, and tools that help mitigate cybersecurity threats. This involves several key actions: Implementing Multi-Factor Authentication (MFA), Updating Security Policies and Procedures, Performing Targeted Security Updates  |
| Detect  | To address potential security incidents and improve monitoring capabilities, the organization should focus on several key areas. First, implementing multi-factor authentication (MFA) can significantly reduce the risk of unauthorized access by requiring a second form of verification in addition to the password.  |
| Respond  | To respond to a security incident, the organization should first isolate affected systems to prevent the spread of the incident, which may involve disconnecting systems from the network or disabling user accounts. Next, the incident response team should be activated to assess the situation and coordinate response efforts. For neutralization, security tools and techniques should be used to identify and eliminate threats, such as removing malware, closing vulnerabilities, and blocking malicious IP addresses. Finally, ensure that all affected systems are updated with the latest security patches to prevent further exploitation |
| Recover  | To recover from a security incident, the organization should first restore systems to normal operation by recovering data and assets from backups, ensuring the integrity of the restored data to confirm it is free from any malicious modifications. Following this, a post-incident review should be conducted to analyze the incident, understand its root cause, scope, and impact, and document all findings and lessons learned to improve future incident response efforts  |



