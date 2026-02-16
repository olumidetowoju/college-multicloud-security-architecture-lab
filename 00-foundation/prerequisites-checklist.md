
✅ Module 00 — Prerequisites Checklist (Entra ID Center)
Local workstation (WSL Ubuntu 24.04)
 Ubuntu 24.04 running in WSL2

 Git installed + configured

 Basic packages installed: curl, wget, unzip, jq

 You can reach the internet from WSL (DNS works)

Install essentials
sudo apt update
sudo apt install -y git curl wget unzip jq ca-certificates gnupg lsb-release
git config --global user.name "Olumide"
git config --global user.email "YOUR_EMAIL_HERE"
Accounts (do NOT commit IDs/tokens)
 Azure tenant with Entra ID admin access (or lab admin)

 AWS account access (free-tier capable)

 GCP billing/project access (free-tier capable)

Tools we will use
 Azure CLI (az)

 AWS CLI (aws)

 Google Cloud CLI (gcloud)

 HashiCorp Vault (vault) for labs

 Terraform (optional but recommended)

Baseline security you must enable (college-grade)
 MFA enforced for privileged roles (at minimum)

 “No standing admin”: plan to use PIM/JIT for admin elevation

 Break-glass accounts (documented and monitored)

 Central logging strategy chosen (later modules implement)

Cost guardrails (mandatory)
 Budgets + alerts enabled (Azure + AWS + GCP)

 Tagging/labels strategy decided (owner, env, costcenter)

 Each lab ends with destroy steps

Verification quick checks
wsl.exe --status 2>/dev/null || true
lsb_release -a
git --version
