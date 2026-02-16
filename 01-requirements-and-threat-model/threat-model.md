
🎯 Threat Model (College / Entra ID Center)
Top threats for colleges
Phishing / credential theft

Ransomware

Privilege escalation

Data exfiltration (student records, HR/finance, research)

Vendor compromise

Misconfiguration (public buckets, overly-permissive IAM)

Attack paths (simple)
flowchart LR
  Phish[Phishing] --> Creds[Stolen Credentials]
  Creds --> SignIn[Cloud Sign-in]
  SignIn --> PrivEsc[Privilege Escalation]
  PrivEsc --> Data[Access Sensitive Data]
  Data --> Exfil[Exfiltration]
  PrivEsc --> Ransom[Ransomware Impact]
Security controls we will implement in later modules
Entra: MFA + Conditional Access + PIM (reduce credential abuse impact)

Vault: dynamic credentials + rotation (reduce long-lived secrets)

Cloud guardrails: policy/organization controls

Logging + detection: central visibility + alerting

Segmentation: isolate blast radius (student vs admin vs research)

Definition of done
We can explain:

what we protect

who the adversaries are

where the biggest risks are

what controls reduce those risks
