# Hope Children Hospital — Go-Live Context

**Status**: In planning — June 2026 target  
**Source**: [PRD — Referral Lab Workflow](https://ehealthnigeria.atlassian.net/wiki/spaces/EHACARE/pages/245628929)  
**Last updated**: 2026-04-12

## What this is
- First external EHACare client (replaces CareOne Digital Hospital in pipeline)
- Go-live target: June 2026
- Key net-new capability required: referral lab workflow

## Referral lab workflow
- Problem: Hope Hospital needs to refer patients to EHA Clinics lab for tests
- Preferred solution: expand existing EHA Clinics Lab Portal (not cross-tenant EMR routing flags)
- This decision is pending Adam discussion — do not build until confirmed
- n8n automation for results delivery: Report IDs only via WhatsApp/Google Sheets — NO PII
- Dedicated read-only service account for all n8n automations

## Data privacy constraints (hard rules)
- Only Report IDs flow through WhatsApp and Google Sheets
- No patient names, DOB, diagnosis, or any PII in automation outputs
- Dedicated read-only service account — not shared credentials

## Key decisions pending
- [ ] [[../../People/adam|Adam]] discussion: Lab Portal expansion vs cross-tenant routing
- [ ] Lab Portal scope and timeline with [[../../People/george|George]]

## Reference docs
- [PRD — Referral Lab Workflow](https://ehealthnigeria.atlassian.net/wiki/spaces/EHACARE/pages/245628929)
- [Referral Feature Audit](https://ehealthnigeria.atlassian.net/wiki/spaces/EHACARE/pages/243990532)
- [Lab Order & Patient Creation Audit](https://ehealthnigeria.atlassian.net/wiki/spaces/EHACARE/pages/247627777)
