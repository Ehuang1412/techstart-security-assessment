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

**Severity:**	🔴 HIGH  
**Likelihood:**	High  
**Impact:**	Critical  

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

**Timeline:** 1 week  
**Cost:** $50–$200/month (password manager) + staff time  
**Priority:** 🔥 IMMEDIATE — Week 1  

### RISK 2: No Backup System

**Severity:**	🔴 HIGH  
**Likelihood:**	High  
**Impact:**	Critical 

#### Description:
TechStart has no automated backup system for its AWS infrastructure, databases, or employee files. Data exists in a single location with no redundancy or recovery capability.

#### Potential Impact:

* Permanent, irrecoverable data loss from accidental deletion, ransomware, or hardware failure
* Business operations halt indefinitely — no recovery path
* Customer data loss leads to legal liability and churn
* Ransomware operators specifically target companies without backups
* Average cost of downtime for a small business: $8,000–$25,000 per day
* 60% of small companies that suffer a major data loss close within 6 months
#### Recommended Solution:

1. Enable AWS Backup for all RDS databases, S3 buckets, and EC2 instances
2. Configure automated daily backups with 30-day retention
3. Implement the 3-2-1 rule: 3 copies, 2 media types, 1 offsite
4. Store an immutable/offline copy to protect against ransomware
5. Test restoration quarterly — an untested backup is not a backup
6. Document recovery procedures (RTO/RPO targets)
**Timeline:** 2–3 weeks  
**Cost:** $100–$400/month (AWS Backup storage) + setup time  
**Priority:** 🔥 IMMEDIATE — Weeks 2–3

### RISK 3: Employees Use Personal Email for Work

**Severity:**	🟠 MEDIUM-HIGH    
**Likelihood:**	High    
**Impact:**	High  

#### Description:
Employees conduct company business — including sharing documents, credentials, and customer information — through personal email accounts (Gmail, Yahoo, etc.). The company has no visibility or control over this data.

#### Potential Impact:

* No data governance — company data lives on personal accounts the company can't control or recover
* Ex-employees retain access to company communications and files indefinitely
* No audit trail for compliance or legal discovery
* Increased phishing risk — personal accounts lack enterprise protections
* Data leakage if personal accounts are breached
* Violates most compliance frameworks (SOC 2, ISO 27001, GDPR)
  
#### Recommended Solution:

1. Provision company email (e.g., Google Workspace or Microsoft 365)
2. Migrate active work communications to company accounts
3. Enforce company email via acceptable use policy
4. Enable MFA and advanced phishing protection on company email
5. Set up email retention and eDiscovery policies
6. Offboard ex-employees immediately (see Risk 5)
   
**Timeline:** 2–4 weeks
**Cost:** $6–$12/user/month (~$300–$600/month for 50 users)
**Priority:** ⚡ HIGH — Weeks 2–4

### RISK 4: Public WiFi Used for Work Without VPN

**Severity:**	🟠 MEDIUM-HIGH    
**Likelihood:**	Medium-High    
**Impact:**	High  

#### Description:
Employees work from coffee shops, airports, and hotels using unsecured public WiFi without a VPN. All traffic — including credentials and customer data — is transmitted over untrusted networks.

#### Potential Impact:

* Man-in-the-middle (MITM) attacks — attackers intercept credentials and session tokens
* Evil twin attacks — fake hotspots mimic legitimate ones
* Session hijacking leads to account takeover
* Customer data intercepted in transit = breach + regulatory liability
* Packet sniffing can expose unencrypted internal communications
* One compromised session on public WiFi can lead to full network access
#### Recommended Solution:

1. Deploy a company VPN (e.g., Tailscale, NordLayer, or AWS Client VPN)
2. Require VPN use on all public/untrusted networks (enforce via policy + MDM)
3. Enable full-disk encryption on all laptops (BitLocker/FileVault)
4. Enforce HTTPS everywhere; deploy DNS filtering
5. Consider Zero Trust Network Access (ZTNA) as a modern alternative
6. Train employees on public WiFi risks

**Timeline:** 2–3 weeks  
**Cost:** $5–$10/user/month (~$250–$500/month) + MDM if not already deployed  
**Priority:** ⚡ HIGH — Weeks 2–4  


