
🧱 Governance Guardrails (College / Entra ID-Centered)
The goal
Before we deploy anything, we define the “rules of the road”:

identity standards

minimum security controls

naming/tagging conventions

logging baseline

cost controls + cleanup discipline

Analogy
If the college is a city, guardrails are the building codes:
They prevent unsafe structures from being built, even if someone tries.

1) Identity guardrails (Entra ID)
Minimum requirements
MFA for privileged users (at minimum; ideally for all)

Conditional Access for risky sign-ins

Privileged Identity Management (PIM) for admin roles

Principle
No standing admin. Admin access should be temporary, approved, and audited.

flowchart LR
  User[Admin User] --> CA[Conditional Access + MFA]
  CA --> PIM[PIM Elevation Request]
  PIM --> Role[Time-bound Admin Role]
  Role --> Audit[Audit Logs]
2) Naming & tagging (inventory + destroy)
Tag keys (recommended)
owner: your handle (e.g., olumidetowoju)

env: dev | test | prod (labs mostly dev)

app: lab name (e.g., vault-basics)

costcenter: college-it

expires: YYYY-MM-DD (optional but powerful)

Rule
If it has cost potential, it must be taggable/labelable.

3) Logging baseline (what we expect later)
At minimum:

Identity logs (sign-ins, role changes)

Cloud audit logs (API calls)

Network/security logs (where possible)

4) Cost guardrails (free-tier safe)
Budgets + alerts enabled in each cloud

Prefer serverless/free-tier patterns

Avoid NAT gateways and always-on VMs unless necessary

Destroy after each lab

5) Cleanup discipline (mandatory)
Every module ends with:

“Destroy steps”

“Verification steps” (prove resources are gone)
