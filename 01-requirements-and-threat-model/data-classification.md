
🧾 Data Classification (College)
Why classify data?
Because security controls must match data risk.
Analogy: You don’t store exam answers on a public bulletin board.

Simple 4-tier model
Public: public website content, brochures

Internal: internal memos, general operational docs

Confidential: student records, staff records, internal finance

Regulated/Restricted: highly sensitive research data, compliance-bound data

Control mapping (examples)
Confidential/Regulated data should have:

encryption at rest (KMS/Key Vault/Cloud KMS)

encryption in transit (TLS)

access logging + alerts

least privilege + time-bound access
