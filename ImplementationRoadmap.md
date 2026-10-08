# TechStart Inc. — 90-Day Security Implementation Roadmap

### Phase Overview

Week 1 |Weeks 2-4|Month 2|Month 3+
--- |---|---|---
PHASE 1|PHASE 2 |PHASE 3|PHASE 4
 STOP BLEEDING|SECURE CORE | TRAIN & PROCESS | SUSTAIN  & AUDIT 

### PHASE 1: Stop the Bleeding (Week 1)
**Goal:** Eliminate the two most critical, exploitable risks immediately.

Action |	Owner	| Timeline |	Cost	| Milestone
--- | --- | --- | --- | ---
Rotate all admin passwords	| IT Lead	| Day 1–2 |	$0	| All shared creds invalidated
Deploy password manager (Bitwarden Teams)|	IT Lead	|Day 2–3|	$50/mo	|Team vault live
Enable MFA on all admin accounts|	IT Lead|	Day 3–4	|$0	|100% admin MFA coverage
Revoke access for all ex-employees|	HR + IT	|Day 1|	$0	|Zero orphaned accounts
Enable AWS Backup on critical resources|	DevOps|	Day 4–5|	$100/mo|	Daily backups running

**Phase 1 Milestone:** ✅ Critical access risks closed; backups initiated  
**Phase 1 Cost:** ~$150/month  

### PHASE 2: Secure the Core (Weeks 2–4)

**Goal:** Establish controlled communication and network security.

Action |	Owner	| Timeline |	Cost	| Milestone
--- | --- | --- | --- | ---
Provision company email (Google Workspace)|	IT Lead|	Week 2|	$300/mo	|All staff on company email
Migrate active work from personal email|	All staff|	Week 2–3	|$0	|Zero work on personal email
Deploy company VPN (Tailscale/NordLayer)|	IT Lead|	Week 2–3	|$250/mo|	VPN required on public WiFi
Enable full-disk encryption on all laptops	|IT Lead	|Week 3	|$0	|100% encrypted devices
Configure backup retention + test restore	|DevOps	|Week 3–4|	$0	|Successful restore test
Implement RBAC on AWS and app|	DevOps	|Week 4	|$0	| No shared accounts

**Phase 2 Milestone:** ✅ All data in company-controlled channels; network traffic encrypted
**Phase 2 Cost:** ~$550/month
