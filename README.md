# sql-injection-learning-lab
Hands-on SQL Injection (SQLi) demo showcasing insecure authentication, exploitation techniques, and secure coding practices.
# SQL Injection Demo Lab 🔐

This project is a hands-on demonstration of **SQL Injection (SQLi)** vulnerabilities using a simple web application.

## 📌 Overview

SQL Injection is a type of attack where malicious SQL code is inserted into input fields, allowing attackers to manipulate a database. SQL Injection

This lab demonstrates:

* Vulnerable login forms
* Authentication bypass
* Data manipulation via injection

> ⚠️ This project is for **educational purposes only**

---

## 🚀 Features

* Insecure login system
* Raw SQL queries (intentionally vulnerable)
* Example attack payloads
* Optional Docker setup

---

## 🛠️ Tech Stack

* Python / Flask (or Node.js)
* SQLite
* HTML/CSS

---

## 💻 How to Run

### Option 1: Local

```bash
pip install -r requirements.txt
python app/app.py
```

### Option 2: Docker

```bash
docker build -t sqli-demo .
docker run -p 8000:8000 sqli-demo
```

Then go to:

```
http://localhost:8000
```

---

## 🧪 Example SQL Injection Attacks

Try entering this in the username field:

```
' OR '1'='1
```

This works because the query becomes:

```sql
SELECT * FROM users WHERE username = '' OR '1'='1' AND password = '';
```

Which always evaluates to true. ([GitHub][1])

---

## 🔐 Why This Happens

SQL injection occurs when user input is directly inserted into queries without sanitization or parameterization. ([CMSC 334 Computer Security][2])

---

## 🛡️ How to Prevent It

* Use parameterized queries
* Use ORM frameworks
* Validate and sanitize input

---

## 📚 Learning Goals

* Understand how SQL injection works
* Practice exploiting vulnerabilities safely
* Learn secure coding practices

---

## ⚠️ Disclaimer

Do NOT use these techniques on real systems without permission.

[1]: https://github.com/cmspencer109/SQLInjectionDemo?utm_source=chatgpt.com "GitHub - cmspencer109/SQLInjectionDemo: A web app vulnerable to SQL injection, built as the final project for my Offensive Security class"
[2]: https://cmsc334-s24.github.io/labs/lab8-sql-injection.html?utm_source=chatgpt.com "Lab 8: SQL Injection · CMSC 334 Computer Security"
