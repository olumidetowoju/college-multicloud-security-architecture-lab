# ✅ Prerequisites Checklist (College Lab)

## Local Setup (WSL Ubuntu 24.04)

Install essentials:

```bash
sudo apt update
sudo apt install -y git curl wget unzip jq
Cloud Accounts Needed
Azure tenant with Entra ID

AWS Free Tier account

GCP Free Tier project

Required Tools
Azure CLI (az)

AWS CLI (aws)

Google CLI (gcloud)

HashiCorp Vault (vault)

Cost Safety Rule
Every lab must end with:

Destroy steps

Billing verification


4. Click **Commit changes**

---

## 1.2 Add `00-foundation/tooling-wsl-ubuntu.md`

Create new file:

00-foundation/tooling-wsl-ubuntu.md


Paste:

```markdown
# 🧰 Tooling Setup (WSL Ubuntu)

Verify your CLI access before starting labs.

---

## Azure

```bash
az login
az account show
AWS
aws sts get-caller-identity
GCP
gcloud auth login
gcloud config list
Vault
vault version
✅ If all commands work, you are ready.


Commit changes.

---

## 1.3 Add `00-foundation/governance-guardrails.md`

Create:

00-foundation/governance-guardrails.md


Paste:

```markdown
# 🧱 Governance Guardrails (College Security)

Before building anything, enforce these baseline rules.

---

## Identity Rules (Entra ID)

- MFA required
- Conditional Access policies enabled
- No permanent admin access
- Use PIM (Just-in-Time elevation)

---

## Tagging Rules

Every resource must include:

- owner
- env
- app
- costcenter

---

## Cleanup Discipline

Every module ends with:

- Destroy commands
- Verification that resources are deleted
