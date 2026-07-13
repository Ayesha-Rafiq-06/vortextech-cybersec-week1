# OWASP Top 10 (2025) — Research & Documentation
**Vortex Tech Internship Program 2026 — Cyber Security Track — Week 1**

**Name:** Ayesha
**Track:** Cyber Security Internship

---

## Introduction

This document covers 5 vulnerabilities from the OWASP Top 10 (2025) list, which is the industry-standard reference that security professionals use to understand the most common risks in web applications. Understanding these risks is the first step toward learning how to prevent them.

---

## 1. Broken Access Control

### What it is
Broken Access Control happens when a website or application does not properly check what a user is allowed to see or do. In simple words, it means the "rules" about who can access what are not enforced correctly, so people can end up viewing or changing things they should not have permission to touch.

### How an attacker could exploit it
Imagine a website where each user has a profile page at a URL like `website.com/user/123`. If the system does not check whether the logged-in user actually owns profile 123, an attacker could simply change the number in the URL to `website.com/user/124` and view someone else's private data, even though they are not supposed to.

### Real-world example
In 2019, a large breach at Capital One occurred when a former employee of a cloud provider exploited a misconfigured firewall to access over 100 million customer records, because access controls were not properly restricting what parts of the system could be reached.

### Prevention
Developers should enforce "least privilege" — meaning every user or system should only have access to exactly what they need, nothing more. Every request to view or edit data should be checked on the server side to confirm the user actually has permission for that specific piece of data.

---

## 2. Injection

### What it is
Injection happens when an application takes user input (like text typed into a search box or login form) and uses it directly inside a command or database query without checking it first. This lets an attacker "inject" their own malicious instructions into the system.

### How an attacker could exploit it
A classic example is SQL Injection. If a login form takes the username and puts it directly into a database query without proper checks, an attacker could type something like `' OR '1'='1` into the username field. This can trick the database into thinking the condition is always true, letting the attacker log in without knowing a real password.

### Real-world example
The 2017 Equifax breach, which exposed the personal data of about 147 million people, happened because attackers exploited an unpatched vulnerability that allowed them to send malicious input to a web application and execute commands on the server.

### Prevention
Developers should use parameterized queries (also called prepared statements) instead of directly combining user input with database commands. This way, user input is always treated as data, never as executable code.

---

## 3. Cryptographic Failures

### What it is
Cryptographic Failures happen when sensitive data  like passwords, credit card numbers, or personal information is not properly protected using encryption, or is protected using weak/outdated encryption methods. This makes it easier for attackers to read the data if they manage to steal it.

### How an attacker could exploit it
If a company stores user passwords as plain text or uses a weak hashing method, an attacker who breaks into the database can instantly read everyone's real password, instead of having to spend time and resources cracking strong encryption.

### Real-world example
In the 2013 Adobe breach, attackers stole data for about 150 million user accounts. The passwords were encrypted using a weak, outdated method instead of proper modern hashing, which made it much easier for attackers to figure out the original passwords.

### Prevention
Developers should always use strong, modern encryption standards (such as AES-256 for stored data and TLS for data in transit), and never store passwords in plain text — passwords should always be hashed using a strong algorithm designed for that purpose (like bcrypt).

---

## 4. Authentication Failures

### What it is
Authentication Failures happen when the process of verifying "who a user really is" (like logging in) is weak or poorly designed. This can let attackers pretend to be someone else, or break into accounts more easily than they should be able to.

### How an attacker could exploit it
If a website allows unlimited login attempts without any lockout or delay, an attacker can use automated software to try thousands of password combinations very quickly (called a "brute force attack") until they guess the correct one.

### Real-world example
In the 2012 LinkedIn breach, around 117 million user passwords were exposed. Weak password protection and authentication practices made it easier for attackers to crack a large number of the stolen passwords afterward.

### Prevention
Developers should implement Multi-Factor Authentication (MFA), so even if a password is stolen, the attacker still needs a second verification step. Systems should also limit the number of login attempts and enforce strong password requirements.

---

## 5. Security Misconfiguration

### What it is
Security Misconfiguration happens when a system, server, or application is not set up securely — for example, using default settings, leaving unnecessary features turned on, or not properly restricting access to important files and settings.

### How an attacker could exploit it
Many systems come with default usernames and passwords (like "admin/admin") for easy initial setup. If a company forgets to change these before going live, an attacker can simply look up the default credentials online and log straight in.

### Real-world example
In 2017, a misconfigured Amazon S3 storage bucket exposed the personal data of over 198 million American voters, because the storage was left publicly accessible when it should have required proper authentication.

### Prevention
Developers and system administrators should always change default credentials immediately, disable any features or services that are not actually being used, and regularly review configuration settings to make sure nothing is left exposed by mistake.

---

## Personal Reflection

Out of all five, Security Misconfiguration surprised me the most, because it often happens not due to complex hacking skills, but simply due to human mistakes like forgetting to change a default password or leaving something publicly accessible. It shows that even small oversights can lead to massive breaches affecting millions of people. This made me realize that cybersecurity is not only about writing secure code, but also about careful, consistent system management and double-checking every setting before going live.

---

## References
- OWASP Top 10:2025 — https://owasp.org/Top10/2025/
-  Youtube : https://www.youtube.com/watch?v=Jzr0Jdnq_EI&t=507s
