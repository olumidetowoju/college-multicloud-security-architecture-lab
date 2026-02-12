# 🏫 College Multi-Cloud Security Architecture Lab (Vault + AWS + Azure + GCP)

**Owner:** @olumidetowoju  
**Goal:** Design and implement a secure, real-world **college/university** cloud architecture across AWS, Azure, and GCP using **HashiCorp Vault** as a cross-cloud secrets & identity control plane.

> Tutor style: I will explain each concept with analogies, diagrams, and step-by-step labs you can run on Ubuntu 24.04 (WSL).

---

## 🧭 What we are building

A college has **very different zones** with different risk levels:

- **Student Systems** (portals, LMS, email access)
- **Faculty/Staff Systems** (HR, finance, payroll)
- **Research Systems** (high compute, sensitive datasets)
- **Public Services** (websites, admissions pages)
- **Third-Party Vendors** (limited access, audited)

This repo builds **governance + identity + network segmentation + data protection + detection/response**
and then implements it with hands-on labs.

---

## ✅ Start Here

1) 👉 [00-Foundation](./00-foundation/README.md)  
2) 👉 [01-Requirements & Threat Model](./01-requirements-and-threat-model/README.md)  
3) 👉 [02-Reference Architecture](./02-reference-architecture/README.md)  

---

## 🏗️ Build Modules (Hands-On)

4) 👉 [03-HashiCorp Vault Platform](./03-hashicorp-vault-platform/README.md)  
5) 👉 [04-AWS Landing Zone Security](./04-aws-landing-zone-security/README.md)  
6) 👉 [05-Azure Landing Zone Security](./05-azure-landing-zone-security/README.md)  
7) 👉 [06-GCP Landing Zone Security](./06-gcp-landing-zone-security/README.md)  
8) 👉 [07-Cross-Cloud Zero Trust Integration](./07-cross-cloud-zero-trust-integration/README.md)  
9) 👉 [08-Capstone College Scenarios](./08-capstone-college-scenarios/README.md)  

---

## 💸 Cost & Cleanup (Mandatory)

10) 👉 [99-Cleanup & Cost Controls](./99-cleanup-and-cost-controls/README.md)

**Rule:** Every lab ends with a destroy runbook. If it can’t be destroyed safely, we don’t build it.

---

## 🧠 Simple analogy for the whole architecture

Think of the college like a **city**:

- **Identity** = passports and badges  
- **Network segmentation** = neighborhoods with gates  
- **Vault** = the central “key office” issuing time-limited keys  
- **KMS** = the vault inside each cloud’s bank  
- **Logging/SIEM** = security cameras + incident dispatch

---

## 📊 Architecture flowchart (high level)

```mermaid
flowchart LR
  Users[Students / Faculty / Staff / Vendors] --> IdP[Central Identity (SSO/MFA)]
  IdP --> ZTNA[Zero Trust Access Layer]
  ZTNA --> Clouds[AWS / Azure / GCP Workloads]
  Vault[HashiCorp Vault] --> Clouds
  Clouds --> Logs[Central Logging + SIEM]
  Logs --> IR[Incident Response Runbooks]

---

# ✅ “Think deep” checklist before we start (college architecture readiness)
Use this as `00-foundation/prerequisites-checklist.md`:

### Governance & design
- [ ] Define the **college zones**: Student / Staff / Research / Public / Vendor
- [ ] Define **data classification**: Public / Internal / Confidential / Regulated
- [ ] Define **risk owners** (who approves access?): IT, Security, Registrar, Finance, Research Office
- [ ] Choose **identity source of truth** (Entra ID / Google Workspace / hybrid)
- [ ] Decide: **central SIEM** (Microsoft Sentinel / Splunk / Chronicle / other)

### Identity & access
- [ ] MFA enforced for all users (students included, with exceptions documented)
- [ ] Privileged access model: Admin roles via **PIM/JIT** (no standing admin)
- [ ] Break-glass accounts protected + monitored
- [ ] Vendor access pattern defined (time-bound, least privilege, audited)

### Network & segmentation
- [ ] Separate environments: dev/test/prod
- [ ] Separate zones: student vs admin vs research
- [ ] Private connectivity patterns documented (VPN / PrivateLink / Private Endpoint / PSC)
- [ ] Egress control strategy (firewall, DNS control, web proxy)

### Secrets & keys
- [ ] Vault scope: secrets engine selection, auth method selection, HA approach
- [ ] Cloud KMS approach per cloud + key rotation
- [ ] No long-lived keys in code (policy + CI checks)

### Logging & detection
- [ ] Log sources required (IAM, network, DNS, workload logs)
- [ ] Retention policy + immutable storage for critical logs
- [ ] Alerting to an on-call route + playbooks

### Cost guardrails (free tier safe)
- [ ] Budgets + alerts enabled in each cloud
- [ ] Tagging/labels enforced for all resources
- [ ] Destroy scripts/runbooks required per module

---


