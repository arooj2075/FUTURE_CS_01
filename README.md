# FUTURE_CS_01
## Task 1: Security Testing on a Sample Web Application

### Objective:
To conduct security testing on a sample web application and identify vulnerabilities such as SQL injection, XSS, and authentication flaws.

### Tools Used:
- SQLMap (for SQL injection testing)
- Platform: Windows with Visual Studio Code

### Target:
- URL: https://demo.testfire.net/bank/login.aspx

### Methodology:
1. Used SQLMap to scan the login form for SQL injection.
2. Analyzed the `uid` parameter through POST requests.
3. Followed all redirections and cookie settings.
4. Tested multiple types of SQL injection:
   - Boolean-based
   - Error-based
   - Heuristic checks

### Results:
- No SQL injection vulnerability detected in the tested parameters.
- SQLMap concluded the parameters were not injectable.

###  Conclusion:
The login form on the test site was not vulnerable to SQL injection, indicating it may have proper security measures in place. SQLMap testing was successfully conducted, demonstrating knowledge of web security testing tools.

### Additional Testing:
### XSS Vulnerability Found
•	Vulnerability Type: Reflected Cross-Site Scripting (XSS)
•	Tested On: https://demo.testfire.net
•	Input Field: Search box on homepage
•	Payload Used:
Html
<script>alert("Arooj XSS")</script>
•	Result: A JavaScript alert box appeared saying “Arooj XSS” confirming XSS vulnerability.
•	Risk: An attacker can steal session cookies, deface pages, or redirect users.
•	Mitigation Suggestion: Sanitize and escape all user input in search fields using libraries or input validation.

### 🔹 Recommendations:
- Always use prepared statements and input validation to prevent SQL injection.
- Conduct regular penetration testing on all input fields.
