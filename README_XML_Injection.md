# XML / XXE Injection – Lab Project

## 📌 Overview
This project demonstrates XML and XXE Injection testing in a controlled lab environment to evaluate insecure XML parser configurations and their potential impact.

---

## ⚠️ Disclaimer
This project was performed **only in a lab environment** for **educational purposes**.  
Do not attempt these techniques on systems without **explicit permission**.

---

## 🛠 Tools & Environment
- **Target Application:** Vulnerable XXE demo app (Docker-based)
- **Attacker Machine:** Kali Linux
- **Tools:** Burp Suite, OWASP ZAP, Custom XXE Payloads

---

## 🔍 Vulnerability Description
- **XML Injection:** Occurs when unsanitized XML input is parsed directly, allowing entity manipulation.
- **XXE Injection:** Exploits external entity resolution, enabling file read, SSRF, or sensitive data disclosure.

---

## ⚙️ Steps to Exploit
1. Identified XML input fields in the application.
2. Injected XML entities manually to test parser behavior.
3. Sent malicious payloads (e.g., XXE) through Burp Suite Repeater.
4. Observed responses indicating successful file read / data disclosure.

