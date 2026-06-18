# Log_Analysis

# QuickSilver Materials – Incident Response Report (SQL Injection Simulation)

This repository contains a simulated security incident investigation on a containerised web application environment (OWASP Juice Shop behind an nginx reverse proxy) using Wazuh SIEM, Docker logs, and network traffic analysis.

The scenario follows a multi-day attack pattern involving authentication probing, suspected SQL injection behaviour and broken access control leading to potential exposure of sensitive user and financial data.

## What this project covers

- Wazuh-based detection of suspicious web activity  
- nginx access and error log analysis  
- Docker containerised investigation environment  
- Reconstruction of attacker behaviour across multiple days  
- Assessment of SQL injection vs broken access control hypotheses  
- Evaluation of data exposure impact (user + financial data)  
- Incident response lifecycle (containment, eradication, recovery)  
- Security gaps in authentication, logging, and access control  
- Recommendations for SIEM and application hardening  

## Environment

- Wazuh (Manager, Indexer, Dashboard)  
- Docker (OWASP Juice Shop + nginx reverse proxy)  
- Linux log inspection and container shell access  
- Internal simulated network (172.18.0.0/16 range)

## Key findings

- Repeated login attempts and API probing from a single internal IP  
- Shift from failed authentication → successful sessions → sensitive data access  
- Access to user data, payment details, and admin-related endpoints  
- No direct SQL payload captured in logs due to logging limitations  
- Behaviour consistent with SQL injection or broken access control exploitation  

## Limitations

- No visibility into request bodies or SQL queries  
- Wazuh detection based mainly on HTTP 400/500 patterns  
- Heavy reliance on manual log correlation and behavioural inference  

## Outcome

The investigation indicates likely unauthorized access to sensitive data due to weak access control and insufficient backend validation. The case highlights gaps in logging depth, authentication hardening, and SIEM rule specificity.

## Note

This is a simulated cybersecurity lab exercise for incident response practice.
