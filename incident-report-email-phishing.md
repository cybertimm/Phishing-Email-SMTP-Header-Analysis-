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


##  Screenshots
Screenshots included in this project show:
- Full raw email headers
- SMTP mail flow (`Received` headers)
- Authentication failures (SPF/DKIM/DMARC)
- IP geolocation results

  ## Legitimacy Assessment

The email is **not legitimate** and was confirmed to be **spoofed**. Although the message appears to originate from `support@facebook.com`, analysis of the email headers shows that replies are redirected to `secureinternationalalerts10@gmail.com`. This mismatch between the **From** address and the **Reply-To/Return-Path** is a clear indicator of email spoofing and phishing activity.

  <img width="1270" height="406" alt="image" src="https://github.com/user-attachments/assets/62f17357-5cbe-4b97-81d6-fc5cd883ac4c" />

## Source SMTP Server Identification

The originating SMTP server was identified through analysis of the bottom-most `Received` header. The source IP address of the sending server is:

- **Source IP:** `89.144.21.170`


  <img width="1255" height="244" alt="image" src="https://github.com/user-attachments/assets/7466dde6-e38f-4700-8756-2030d9b6690a" />
  
## Source IP Geolocation

Geolocation analysis of the source SMTP server IP (`89.144.21.170`) indicates that the email originated from **Germany**.  
It is important to note that IP geolocation results may change over time due to IP reallocation or ISP ownership changes; therefore, the identified location reflects the most accurate information available at the time of analysis.


  <img width="943" height="625" alt="image" src="https://github.com/user-attachments/assets/00636354-8490-4c4d-932d-1cf7325de91b" />





##  Outcome
The email was confirmed as **phishing**.  
No user interaction occurred, and no account compromise was detected.

Mitigation actions included:
- Blocking the sender IP and domain
- Updating email security filters
- User awareness and guidance


##  Skills Demonstrated
- Email Forensics
- Phishing Detection & Analysis
- SOC Incident Reporting
- Threat Intelligence & IOC Analysis
- MITRE ATT&CK Mapping
- Blue Team Investigation Workflow



##  Author
**Oluwadamilola Timothy Ayeni**  
Cybersecurity Analyst | SOC | Digital Forensics  


