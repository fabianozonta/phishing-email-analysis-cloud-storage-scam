# Phishing Email Analysis – Fake Cloud Storage Deletion Alert

## 📌 Overview

This repository documents the analysis of a phishing email impersonating a cloud storage service.  
The message attempts to create urgency by warning the recipient that files will be permanently deleted unless action is taken.

The objective of this analysis is to identify Indicators of Compromise (IOCs), evaluate authentication failures, and classify the threat.

---

## 📨 Email Summary

- **Subject:** Final Warning: Files Will Be Deleted
- **Displayed Sender Name:** Cloud Storage
- **Actual From Address:** QFA7ZA1X@ZO37SPNDTBEY06012GDDJ4W5G4YY.com
- **Return-Path:** <>
- **Spam Confidence Level (SCL):** 9 (High Confidence Spam)

---

## 🔎 Header Analysis

### 1️⃣ Source Server


Received: from uphy.bobikrit.it (20.170.17.87)


- Sending domain unrelated to legitimate cloud providers
- IP address does not belong to Google or Microsoft infrastructure

---

### 2️⃣ Authentication Failures


spf=none
dkim=none
dmarc=none
compauth=fail


- No SPF validation
- No DKIM signature
- No DMARC policy alignment
- Microsoft Composite Authentication: FAILED

This confirms sender identity could not be verified.

---

### 3️⃣ Microsoft Spam Classification


X-MS-Exchange-Organization-SCL: 9


SCL 9 indicates High Confidence Spam.

---

## 🔗 Malicious URL Analysis

Button redirects to:


https://kyempapu.org/?act=cl&
...


Tracking pixel detected:


https://kyempapu.org/track/?act=op
...


Findings:
- Domain unrelated to legitimate cloud providers
- Tracking mechanism suggests campaign monitoring
- Likely credential harvesting or payment fraud page

---

## 🧠 Social Engineering Techniques Identified

- Urgency ("Final Warning")
- Threat of permanent deletion
- Time pressure
- Emotional trigger language
- Professional layout design

---

## 🚨 Indicators of Compromise (IOCs)

| Type | Value |
|------|-------|
| IP Address | 20.170.17.87 |
| Sending Domain | uphy.bobikrit.it |
| Malicious Domain | kyempapu.org |
| Fake Sender Domain | ZO37SPNDTBEY06012GDDJ4W5G4YY.com |

---

## 🎯 Threat Classification

**Type:** Phishing  
**Objective:** Credential harvesting or payment scam  
**Risk Level:** High  

---

## 🛡️ Recommended Mitigation Actions

- Block malicious domains and IP
- User awareness training
- Enforce SPF/DKIM/DMARC validation
- Monitor similar campaigns in SIEM

---

## 📌 Conclusion

This email was confirmed as phishing based on:

- Authentication failures
- Domain spoofing
- Malicious redirection
- High spam confidence classification

No legitimate cloud provider was involved.

---

## 👨‍💻 Author

SOC Analyst – Email Threat Investigation Project  
