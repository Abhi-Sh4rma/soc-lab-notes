# Windows Event ID 4625 – Failed Logon (SOC Basics)

## What is it?
**Event ID 4625** is generated when a login attempt **fails** on a Windows system.

This is one of the most important events for SOC analysts because it can indicate:
- wrong password attempts
- brute force attacks
- password spraying
- unauthorized access attempts

---

## Where to find it?
On Windows:
- **Event Viewer**
- Windows Logs → **Security**
- Look for: **Event ID 4625**

---

## Why this matters in SOC?
Failed logons help answer:
- Who is trying to access the system?
- From where is the login attempt coming?
- Is this normal behavior or suspicious?

---

## Common attack patterns using 4625
### 1) Brute Force
Many failed attempts on the same account in a short time.

### 2) Password Spraying
One/few attempts across many accounts using common passwords.

### 3) Enumeration
Attacker checks if usernames exist by observing different failure behavior.

---

## What I would check as a SOC analyst
- **Account Name** (who is being targeted)
- **Failure Reason**
- **Source IP / Workstation Name**
- **Frequency** (how many attempts per minute)
- **Time window** (is it happening at odd hours?)

---

## My observation (Day 2)
Today I learned that Windows keeps track of failed logins using Event ID 4625.
This event is a strong starting point for detecting brute force and unauthorized access attempts.
