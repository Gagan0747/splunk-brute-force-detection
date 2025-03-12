# Brute-Force Detection and Monitoring in Splunk

## 🔐 Project Overview
A practical Security Information and Event Management (SIEM) implementation demonstrating brute-force attack detection using Splunk. This project showcases fundamental SOC analyst skills including log analysis, alert configuration, and incident response capabilities.

![Initial Splunk Dashboard](./Splunk%20Screenshot%206.PNG)
*Initial Splunk environment showing the search interface and key monitoring panels*

## 🎯 Key Features
- **Real-Time Detection Engine**: Custom-configured queries to identify suspicious login patterns
- **SOC Dashboard**: Purpose-built visualization for security monitoring
- **Alert System**: Automated notification system for potential threats
- **MITRE ATT&CK Integration**: Aligned with T1110.001 (Password Guessing)

## 🛠 Technical Implementation

### Detection Logic
```splunk
index=_audit action="login attempt" info="failed"
| stats count by user, src
| where count > 1
