### Cyber Security Internship – Task 1 Report  
Name: Arooj  
Task: Security Testing on a Sample Web Application  
1. Objective
To perform security testing on a sample web application using ethical hacking tools and identify vulnerabilities such as SQL Injection.

### 2. Tools Used
SQLMap
Platform: Windows
Visual Studio Code (Terminal)

### 3. Target Application
Website: https://demo.testfire.net/bank/login.aspx

### 4. Testing Steps
Opened terminal in VS Code
Ran SQLMap using this command:
python sqlmap.py -u "https://demo.testfire.net/bank/login.aspx" --forms --batch
Accepted redirects, cookies, and filled form fields with random values

Allowed SQLMap to test  SQL injection 

### 5. Observations & Results
SQLMap analyzed the uid parameter in the login form
No SQL injection vulnerabilities were detected

Heuristic and boolean-based tests showed the field was not injectable
•	Target URL was tested with various SQL injection techniques
•	GET parameter query was not injectable
•	XSS vulnerability was suspected but not confirmed
•	SQLMap tested multiple databases (MySQL, PostgreSQL, Oracle, etc.)
•	Final output:
All tested parameters do not appear to be injectable
May be protected by WAF or similar security filters

### 6. Screenshots

### Screenshot:1
![My Screenshot](Screenshot%202025-05-13%20074541.png)
 


### Screenshot:2
![My Screenshot](Screenshot%202025-05-13%20074551.png)

### Screenshot:3
![My Screenshot](Screenshot%202025-05-13%20074601.png) 
### 7. Conclusion
SQLMap successfully tested the login form but found no SQL injection vulnerabilities. The site appears secure against this specific attack. This task helped in learning how to conduct penetration testing using automated tools.

### 8. Recommendations
Use parameterized queries in all inputs
Sanitize and validate user input
Perform regular vulnerability assessments

### Additional Testing:
XSS Vulnerability Found
Vulnerability Type: Reflected Cross-Site Scripting (XSS)
Tested On: https://demo.testfire.net
Input Field: Search box on homepage
### Screenshot:
![My Screenshot](Screenshot%202025-05-13%20074611.png)  

### •	Payload Used:
Html
<script>alert("Arooj XSS")</script>
•	Result: A JavaScript alert box appeared saying “Arooj XSS” confirming XSS vulnerability.





### Screenshot:
![My Screenshot](Screenshot%202025-05-13%20074617.png) https://github.com/arooj2075/FUTURE_CS_01/blob/main/Screenshot%202025-05-13%20074617.png
•	Risk: An attacker can steal session cookies, deface pages, or redirect users.
•	Mitigation Suggestion: Sanitize and escape all user input in search fields using libraries or input validation.
### Authentication Flaw Identified
•	Tested On: https://demo.testfire.net
•	Method: Attempted login using common default credentials
•	Credentials Used:
Username: admin  
Password: admin
•	Result: Successfully logged into the application using default credentials, indicating weak authentication practices.
### Risk:
•	Unauthorized users can gain access without proper credentials
•	May lead to data exposure or further exploitation
### Mitigation Suggestion:
•	Disable default accounts or enforce strong password changes
•	Implement account lockout mechanisms
•	Enforce strong password policies and multi-factor authentication


