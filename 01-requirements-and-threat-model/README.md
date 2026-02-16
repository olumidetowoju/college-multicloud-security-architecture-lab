
🛡️ Module 01 — College Requirements & Threat Model (Entra ID Center)
This module defines what a college must protect, why it matters, and what we’re building toward.

Clickable path
✅ College Use Cases

✅ Data Classification

✅ Threat Model

Why this matters (analogy)
A threat model is like a campus security plan:

You don’t secure every door the same way.

The lab must reflect real risk differences between:
student portals vs payroll vs research data.

Architecture intent (high-level)
flowchart LR
  Users[Students/Faculty/Staff/Vendors] --> Entra[Entra ID]
  Entra --> ZT[Zero Trust Access]
  ZT --> Clouds[AWS + Azure + GCP]
  Clouds --> Logs[Central Logging / SIEM]
  Logs --> IR[Incident Response]
Next module
👉 02 — Reference Architecture
