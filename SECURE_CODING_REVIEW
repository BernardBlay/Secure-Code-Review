![Status](https://img.shields.io/badge/Review-Complete-brightgreen)
![Security](https://img.shields.io/badge/Security-Checked-blue)
![License](https://img.shields.io/badge/License-MIT-lightgrey)
![Flask](https://img.shields.io/badge/Framework-Flask-red)
 [Python](https://img.shields.io/badge/Language-Python-blue)

# ✅ Secure Coding Review – Flask Web Application  
### CodeAlpha Internship – Bernard Blay

## 📌 Overview
This secure coding review was conducted as part of my **CodeAlpha Internship**. The review focused on a **Flask-based web application** that demonstrates user authentication and session management. The aim was to manually analyze the code and identify security vulnerabilities, followed by suggesting practical fixes based on secure coding principles.

During the review, I utilized a combination of **manual inspection** and **static analysis tools** to identify potential weaknesses. By following **best practices** from security frameworks and the **OWASP Top 10**, I was able to highlight common vulnerabilities that are often present in web applications.

---

## 🔍 Review Process
### 1. **Manual Code Inspection**
I thoroughly reviewed the **Flask app** code, focusing on:
- Authentication logic
- Form handling and submission
- Session management
- Error handling and debug configurations

### 2. **Static Code Analysis**
I used **Bandit**, a static code analyzer, to scan the codebase for known security issues related to Python code. This tool helped me identify common flaws like:
- Hardcoded credentials
- Insecure functions (e.g., `eval()`)
- Missing security features

### 3. **OWASP Guidelines**
I also cross-referenced the code with the **OWASP Top 10**, a list of the most critical security risks in web applications. This helped me ensure I covered common vulnerabilities like **SQL injection**, **cross-site scripting (XSS)**, and **cross-site request forgery (CSRF)**.

---

## 🧠 Vulnerabilities Found and Suggested Fixes

### **1. Hardcoded Credentials**
**Vulnerability**: The application has **hardcoded user credentials** (`USERNAME` and `PASSWORD`) inside the code, making it easy for attackers to access the application if they get a hold of the code.

**Why it's an issue**: Hardcoding sensitive information exposes the application to **unauthorized access** and **code leakage**. If someone gains access to the source code (e.g., via a public repo), they can easily use the credentials to log in and perform malicious activities.

**How to Fix**:  
- **Environment Variables**: Store credentials in environment variables or use a secrets manager.
- **Password Hashing**: Never store passwords in plain text. Use a strong hashing algorithm like `bcrypt` or `werkzeug.security.generate_password_hash()` to hash passwords before saving or comparing them.

### **2. Plaintext Password Checking**
**Vulnerability**: The application compares passwords in **plaintext** without hashing or any form of protection.

**Why it's an issue**: Plaintext password storage is a **critical security risk**. If an attacker gains access to the database or source code, they can easily retrieve passwords and compromise user accounts.

**How to Fix**:  
- Use `werkzeug.security`’s `generate_password_hash()` to hash passwords before saving them, and `check_password_hash()` to verify the password at login. This ensures that even if the data is leaked, passwords remain secure.

### **3. Debug Mode Enabled**
**Vulnerability**: The application has **debug mode enabled** (`debug=True`) in the production environment.

**Why it's an issue**: When **debug mode** is enabled, **detailed error messages** and internal server information are displayed to users. This exposes sensitive application details (like file paths and stack traces), which can be used by attackers to find vulnerabilities.

**How to Fix**:  
- Set `debug=False` in production. Ensure that the application never displays detailed error messages to end users.
- Use environment-specific configuration files or environment variables to manage production settings securely.

### **4. No CSRF Protection**
**Vulnerability**: The application does not implement **CSRF protection** for forms.

**Why it's an issue**: **Cross-Site Request Forgery (CSRF)** is an attack where a user is tricked into performing an action without their consent, usually by submitting a form that changes their account settings or performs an action on their behalf.

**How to Fix**:  
- Use **Flask-WTF** to enable CSRF protection in all forms. Flask-WTF automatically generates a **CSRF token** for each form submission, which ensures that only legitimate requests are accepted.

### **5. No Rate Limiting**
**Vulnerability**: There is no **rate limiting** on the login route or any other endpoints that could be abused.

**Why it's an issue**: Without rate limiting, the application is vulnerable to **brute-force attacks**, where an attacker tries many combinations of passwords to guess the correct one.

**How to Fix**:  
- Implement **rate limiting** with the help of **Flask-Limiter**. This tool can restrict the number of requests per IP address over a defined period, preventing brute-force attacks from overwhelming the server.

---

## 🛠 Tools & Techniques Used
- **Manual Code Review**: Carefully analyzing the Flask app’s code to identify vulnerabilities.
- **Bandit**: Static code analysis tool used to scan the codebase for known Python security issues.
- **OWASP Top 10**: Framework used to identify and mitigate common web application vulnerabilities.

---

## ✅ Conclusion
The secure coding review revealed several **critical security issues** within the application, including **hardcoded credentials**, **plaintext password storage**, and the lack of **CSRF protection** and **rate limiting**. By addressing these vulnerabilities, the application can be made much more secure and resilient to common web-based attacks.

The process of reviewing this application allowed me to:
- Deepen my understanding of **Flask web application security**
- Apply **OWASP security principles** to a real-world project
- Gain hands-on experience in performing **manual code audits** and using **static analysis tools**

---

> 📦 This file was created as part of Task 3 in the **CodeAlpha Internship Program** by Bernard Blay, focused on secure coding review and vulnerability identification in a Flask-based web app.
