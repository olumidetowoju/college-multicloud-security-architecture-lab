
🧰 WSL Ubuntu Tooling Setup (Azure-first, Entra ID Center)
Goal
Install and verify the core CLIs on Ubuntu 24.04 (WSL):

Azure CLI (az)

AWS CLI (aws)

Google Cloud CLI (gcloud)

Vault (vault)

Tutor tip: Treat CLIs like “remote controls” for each cloud. If the remote can’t pair, you can’t operate the environment.

1) Azure CLI
Follow Microsoft’s repo-based install for Ubuntu 24.04.

Verify:

az version
az login
az account show
2) AWS CLI v2
Recommended install (official AWS CLI v2 installer).

Verify:

aws --version
aws sts get-caller-identity
3) Google Cloud CLI
Install gcloud then authenticate.

Verify:

gcloud version
gcloud auth login
gcloud auth list
gcloud config list
4) HashiCorp Vault (for labs)
We’ll start with dev-mode for learning, then discuss production patterns later.

Verify:

vault version
5) Optional: Terraform
Terraform helps you build/destroy cleanly, which is perfect for cost controls.

Verify:

terraform version
“Definition of done”
You can run:

az account show

aws sts get-caller-identity

gcloud config list

vault version

…and all commands succeed without errors.
