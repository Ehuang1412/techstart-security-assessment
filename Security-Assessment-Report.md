# TechStart Inc. — Security Assessment Report

###### Prepared by: Emily
###### Date: 0ctober 7, 2026
###### Classification: Internal Use Only
###### Assessment Period: 1 Week

## 1. Executive Summary

TechStart Inc. is a 50-person startup operating a cloud-based web application on AWS, supported by employee laptops and remote/flexible work arrangements. This assessment reviewed the company's current security posture and identified **five major risks** that threaten the confidentiality, integrity, and availability of company and customer data.

The findings reveal that TechStart's most significant vulnerabilities stem not from sophisticated threats, but from basic security hygiene failures — shared credentials, absent backups, unsecured communication channels, and a lack of security awareness. These are low-cost, high-impact issues that can be remediated within 90 days.

Key Finding: TechStart is currently operating at a security maturity level of 1 out of 5 (ad hoc/undefined). A single compromised credential or stolen laptop could result in complete system compromise, permanent data loss, regulatory penalties, and irreparable reputational damage.

#### Recommended Immediate Actions:

1. Eliminate shared admin passwords (Week 1)
2. Implement automated backups (Weeks 2–3)
3. Deploy company email and VPN (Weeks 2–4)
4. Launch security awareness training (Month 2)
5. Establish patch management policy (Month 2)  
  **Estimated Total First-Year Cost:** $8,000–$15,000    
  **Estimated Risk Reduction:** ~80% of identified critical risk

## 2. Scope & Methodology

#### In Scope:

* AWS cloud infrastructure
* Public-facing web application
* Employee laptop fleet (50 devices)
* Identity and access management practices
* Employee communication and data handling
* Backup and recovery capabilities

#### Methodology:

* Review of current practices against NIST Cybersecurity Framework (Identify, Protect, Detect, Respond, Recover)
* Risk rating using likelihood × impact matrix
* Alignment with OWASP Top 10 for web application risks
* Cost/benefit analysis for each recommendation

## 3. Risk Assessment — Five Major Risks

### RISK 1: Shared Admin Passwords Stored in Plain Text

Severity:	🔴 HIGH
Likelihood:	High
Impact:	Critical

#### Description:
Administrative credentials for AWS, the web application, and internal systems are stored in a shared text file accessible to multiple employees. There is no individual accountability, no password rotation, and no audit trail.

#### Potential Impact:

* Complete system compromise — anyone with the file has full admin access
* No way to trace who performed an action (no accountability)
* If the file is leaked (email, USB, cloud sync), attackers gain instant privileged access
* A single disgruntled employee could delete infrastructure or exfiltrate customer data
* Potential GDPR/CCPA violations if customer data is breached
* Estimated breach cost for a startup: $50,000–$150,000+
  
#### Recommended Solution:

1. Deploy a password manager (e.g., Bitwarden Teams or 1Password Business)
2. Create unique, strong credentials for every admin account
3. Enable Multi-Factor Authentication (MFA) on all admin accounts
4. Implement role-based access control (RBAC) — no shared accounts
5. Rotate all existing passwords immediately
6. Enable audit logging on all privileged accounts

Timeline: 1 week 
Cost: $50–$200/month (password manager) + staff time 
Priority: 🔥 IMMEDIATE — Week 1 
