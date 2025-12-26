# 📧 Email Forensics & Phishing Investigation (SOC Incident Report)

##  Project Overview
This project demonstrates a **SOC-style email forensics investigation** performed on a suspicious email impersonating Facebook. Using SMTP header analysis, authentication checks, and threat mapping, the email was confirmed to be a **phishing attempt** designed to harvest user credentials.

The workflow mirrors real-world **blue team / SOC analyst** processes.


## Objectives
- Analyze a suspicious email using full SMTP headers
- Identify the true source SMTP server and IP address
- Validate email authentication mechanisms (SPF, DKIM, DMARC)
- Extract Indicators of Compromise (IOCs)
- Map attacker behavior to the **MITRE ATT&CK framework**
- Produce a professional SOC Incident Report


##  Tools & Techniques
- SMTP Email Header Analysis  
- Manual Forensic Investigation  
- Email Authentication Validation (SPF / DKIM / DMARC)  
- IP Geolocation & WHOIS Lookup  
- MITRE ATT&CK Framework  


##  Key Findings
- Email was **spoofed** and not sent by Facebook
- Reply-To and Return-Path redirected to a malicious Gmail account
- SPF, DKIM, and DMARC checks failed
- Source SMTP server was unauthorized
- Origin IP geolocated to Germany (non-Facebook infrastructure)



## 🚨 Indicators of Compromise (IOCs)

| Type | Value |
|---|---|
| Source IP | `89.144.21.170` |
| Spoofed Sender | `support@facebook.com` |
| Reply-To | `secureinternationalalerts10@gmail.com` |
| Sending Domain | `ghostnet.de` |


##  MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|------|----------|----|
| Initial Access | Phishing | T1566 |
| Initial Access | Phishing via Email | T1566.001 |
| Defense Evasion | Masquerading (Spoofed Headers) | T1036 |
| Credential Access | Credential Harvesting | T1556 |

