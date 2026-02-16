# 🏗️ Module 00 — Foundation (Entra ID-Centered College Baseline)

This module prepares your workstation and establishes **college-grade guardrails** across AWS, Azure, and GCP — with **Microsoft Entra ID** as the central identity plane.

## Why this matters (tutor analogy)
Think of a college like a **city**:
- **Entra ID** = the city’s passport office (identity)
- **MFA + Conditional Access** = the security gate rules
- **PIM** = “temporary police badges” (no permanent admins)
- **Vault** = the key-issuing office for systems (short-lived secrets)
- **Cloud landing zones** = neighborhoods with zoning laws (policy/guardrails)

## Outcomes
By the end of Module 00, you will have:
- A safe local lab setup (Ubuntu 24.04 on WSL)
- A “no-surprises” cost posture (budgets/alerts + cleanup discipline)
- Naming/tagging standards (so you can inventory and destroy)
- A logging baseline mindset (before any workload goes live)
- Repo hygiene so you don’t leak identifiers or secrets

## Start here (clickable)
1) ✅ [Prerequisites Checklist](./prerequisites-checklist.md)  
2) ✅ [WSL Ubuntu Tooling Setup](./tooling-wsl-ubuntu.md)  
3) ✅ [Governance Guardrails](./governance-guardrails.md)

## High-level flow (how labs should run)
```mermaid
flowchart LR
  Plan[Plan + Guardrails] --> Build[Build Resources]
  Build --> Verify[Verify Security Controls]
  Verify --> Document[Document Decisions + Evidence]
  Document --> Destroy[Destroy Resources]
  Destroy --> Confirm[Confirm Zero Drift]
Next module
👉 01 — Requirements & Threat Model
