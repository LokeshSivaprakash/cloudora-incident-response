# Cloudora Incident Response — Executive Account Takeover Investigation

> **Simulated client engagement | MyFirstHack training project**

A SOC / incident-response investigation of a simulated Cloudora account-takeover incident involving password spraying, valid-account access, MFA persistence, and business-email-compromise (BEC) staging.

## Executive overview

Between 8–10 August 2026, an external actor conducted a low-and-slow password-spraying campaign against 26 Cloudora accounts from three Lagos IP addresses.

The attacker successfully compromised:
- `daniel.reeve@cloudora.io` — CEO
- `priya.nair@cloudora.io`

On the CEO account, the attacker obtained valid credentials, registered an unauthorized authenticator device (`Pixel 6`), accessed Outlook Web and Azure Portal, and created the `RSS Subscriptions` inbox rule to hide finance/invoice messages. This created a risk of business-email-compromise / invoice fraud.

The incident was contained and eradicated, and 24 additional targeted-but-not-breached accounts were identified for precautionary resets.

## Investigation highlights

| Area | Result |
|---|---|
| Spray infrastructure | 3 Lagos IPs in `102.89.x.x` |
| Failed sign-ins | 114 |
| Accounts targeted | 26 |
| Confirmed compromises | 2 |
| Targeted but not breached | 24 |
| Persistence | Unauthorized MFA registration |
| BEC staging | Finance/invoice-hiding inbox rule |
| Second victim | Priya Nair |
| False positive | Omar Farah — legitimate Dubai travel |

## MITRE ATT&CK mapping

- **T1110.003 — Brute Force: Password Spraying**
- **T1078 — Valid Accounts**
- **T1098.005 — Account Manipulation: Device Registration**
- **T1564.008 — Hide Artifacts: Email Hiding Rules**

## Detection engineering

The `detection-engineering/` directory contains KQL for password-spray detection and identification of targeted-but-unbreached accounts.

## Skills demonstrated

- SOC investigation
- Incident response
- Threat hunting
- Identity and authentication log analysis
- Password-spray detection
- Account takeover analysis
- MFA persistence investigation
- Business email compromise analysis
- IOC identification
- MITRE ATT&CK mapping
- KQL detection engineering
- False-positive analysis
- Incident documentation and executive reporting

## Repository structure

```text
cloudora-incident-response/
├── README.md
├── incident-report/
│   ├── Cloudora_CLD-IR-0001_Incident_Report.pdf
│   └── Cloudora_CLD-IR-0001_Incident_Report.docx
├── detection-engineering/
│   ├── password-spray-detection.kql
│   └── near-miss-accounts.kql
├── investigation/
│   ├── findings.md
│   ├── timeline.md
│   ├── iocs.md
│   ├── scope.md
│   └── response-actions.md
├── data/
│   ├── cloudora_signin_logs.csv
│   └── cloudora_audit_logs.csv
└── screenshots/
```

## Recommended resume project entry

**Cloudora Incident Response — Executive Account Takeover Investigation | MyFirstHack**

- Investigated a simulated enterprise account takeover by correlating Entra ID sign-in and audit activity, identifying a three-night password spray that targeted 26 accounts and compromised two users.
- Detected attacker persistence through unauthorized MFA registration and a finance/invoice-hiding mailbox rule, mapped activity to MITRE ATT&CK, and developed KQL detections for password spraying and targeted-but-unbreached accounts.
- Scoped the incident, validated a legitimate-travel false positive, documented containment/eradication actions, and produced an executive-ready incident report.

## Disclaimer

This repository contains simulated training data and a simulated client engagement. Cloudora is fictional. No real customer, employee, credential, or production security data is represented here.
