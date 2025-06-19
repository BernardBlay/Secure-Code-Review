# Secure-Code-Review

## 🔍 Overview
As part of my internship with **CodeAlpha**, I conducted a **secure coding review** of a public Flask-based web application. The app is a simple **Flask login system** that demonstrates user authentication and session management. 

This task aimed to reinforce best practices in **secure coding** and simulate vulnerability auditing on a real-world Python web application. 

---

## 👨🏽‍💻 Why This Project?

Given my passion for **cybersecurity**, this review was a hands-on exercise to better understand common web vulnerabilities, including:
- **Authentication issues**
- **Session management flaws**
- **Form security vulnerabilities**

With my background in **network anomaly detection** and **packet sniffing tools**, reviewing a Flask-based web app allowed me to explore the security landscape of modern Python web applications.

---

## 🧠 Key Issues Found

| # | Vulnerability                 | Risk Level | Recommendation                                      |
|---|-------------------------------|------------|-----------------------------------------------------|
| 1 | Hardcoded Credentials         | 🔴 High     | Use environment variables; hash passwords           |
| 2 | Plaintext Password Checking   | 🔴 High     | Use hashed password storage via Werkzeug            |
| 3 | Debug Mode Enabled            | 🔴 High     | Disable `debug=True` in production                  |
| 4 | No CSRF Protection            | 🟡 Medium   | Use Flask-WTF for CSRF tokens                       |
| 5 | No Rate Limiting              | 🟡 Medium   | Add `Flask-Limiter` to protect against brute-force  |

> 📌 A full technical breakdown of each issue and remediation step is included in the `SECURE_CODING_REVIEW.md` file.

---

## 🛠 Tools & Techniques Used

- 🔎 **Manual code inspection**
- 🛡️ **Best practices from OWASP Top 10**
- 📦 **Static analyzer: [Bandit](https://bandit.readthedocs.io/en/latest/)**
- ✅ Experience from my personal work on:
  - Packet Sniffer Dashboard (Flask + Python)
  - Lightweight Anomaly Detection System

---

## 📘 Outcome

This task helped sharpen my ability to:
- Think like an attacker and defender
- Recognize insecure coding habits early
- Recommend practical, low-cost security enhancements

---

## 📄 Report File

Read the full secure code audit here:  
📂 `SECURE_CODING_REVIEW.md`

---

## 🔐 About Me

I'm **Bernard Blay**, a cybersecurity student and tech advocate. During this internship, I've focused on making security tools **accessible**, **educational**, and **effective**, especially for users in environments with limited awareness.

My internship projects are part of a bigger mission:  
➡️ To help more people build safely, and think critically about how systems are protected.


