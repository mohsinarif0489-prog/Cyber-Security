

# 🔐 Cybersecurity Internship Task – Web Application Security Enhancement

##  Project Overview

This project focuses on identifying and mitigating common security vulnerabilities in a mock **User Management System** web application. The objective is to perform vulnerability assessments, implement security best practices, and document the process as part of the Cybersecurity Internship Program.

The project is divided into **three weeks**, covering security assessment, implementation of protective measures, and final reporting.

---

## 🛠️ Tech Stack

* **Node.js**
* **Express.js**
* **MongoDB (if applicable)**
* Security Libraries:

  * `validator`
  * `bcrypt`
  * `jsonwebtoken`
  * `helmet`
  * `winston`
* Security Tools:

  * OWASP ZAP
  * Nmap
  * Browser Developer Tools

---

# 📅 Week 1 – Security Assessment

## 1️⃣ Application Setup

1. Clone a mock web-based application from GitHub.
2. Install dependencies:

```bash
npm install
```

3. Start the application:

```bash
npm start
```

4. Access the application at:

```
http://localhost:3000
```

5. Test the following pages:

* Signup
* Login
* Profile

---

## 2️⃣ Basic Vulnerability Assessment

### 🔍 Tools Used

* **OWASP ZAP** – Automated vulnerability scanning
* **Browser Developer Tools** – Manual testing
* Manual SQL Injection Testing

### 🧪 Tests Performed

#### ✅ Cross-Site Scripting (XSS)

Tested input fields with:

```html
<script>alert('XSS');</script>
```

#### ✅ SQL Injection

Tested login with:

```
Username: admin' OR '1'='1
Password: admin' OR '1'='1
```

#### ✅ Checked For:

* XSS vulnerabilities
* Weak password storage (plain text passwords)
* Security misconfigurations
* Lack of input validation

---

## 3️⃣ Findings Documentation

Documented:

* Identified vulnerabilities
* Risk level
* Recommended fixes
* Areas for improvement

---

# 📅 Week 2 – Implementing Security Measures

## 1️⃣ Input Validation & Sanitization

Installed:

```bash
npm install validator
```

Example Implementation:

```javascript
const validator = require('validator');

if (!validator.isEmail(email)) {
    return res.status(400).send('Invalid email');
}
```

---

## 2️⃣ Password Hashing

Installed:

```bash
npm install bcrypt
```

Example Implementation:

```javascript
const bcrypt = require('bcrypt');

const hashedPassword = await bcrypt.hash(password, 10);
```

Passwords are now securely hashed before storing in the database.

---

## 3️⃣ Token-Based Authentication

Installed:

```bash
npm install jsonwebtoken
```

Example Implementation:

```javascript
const jwt = require('jsonwebtoken');

const token = jwt.sign({ id: user._id }, 'your-secret-key');
res.send({ token });
```

Implemented:

* JWT-based authentication
* Protected routes
* Token verification middleware

---

## 4️⃣ Secure HTTP Headers

Installed:

```bash
npm install helmet
```

Example Implementation:

```javascript
const helmet = require('helmet');
app.use(helmet());
```

Helmet enhances security by setting various HTTP headers.

---

# 📅 Week 3 – Advanced Security & Reporting

## 1️⃣ Basic Penetration Testing

Performed additional testing using:

* **Nmap**
* Manual browser-based attack simulation

Simulated:

* Port scanning
* Authentication bypass attempts
* Input manipulation

---

## 2️⃣ Logging & Monitoring

Installed:

```bash
npm install winston
```

Example Implementation:

```javascript
const winston = require('winston');

const logger = winston.createLogger({
  transports: [
    new winston.transports.Console(),
    new winston.transports.File({ filename: 'security.log' })
  ]
});

logger.info('Application started');
```

Implemented:

* Console logging
* Security log file (`security.log`)
* Error tracking

---

# ✅ Security Checklist

* [x] Validate all user inputs
* [x] Sanitize inputs
* [x] Hash and salt passwords
* [x] Implement JWT authentication
* [x] Use secure HTTP headers (Helmet)
* [x] Perform vulnerability assessment
* [x] Basic penetration testing
* [x] Implement logging
* [ ] Use HTTPS for secure data transmission (recommended for production)


---

#  Learning Outcomes

* Understanding common web vulnerabilities (XSS, SQL Injection)
* Implementing secure authentication mechanisms
* Applying password hashing and input validation
* Performing basic penetration testing
* Implementing logging and monitoring
* Applying secure development best practices

---

#  Author

Cybersecurity Internship Task Submission
Web Application Security Enhancement Project


