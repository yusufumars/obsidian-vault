# EHACare — Product Context

**Status**: Pre-PMF, Solution Validated  
**Source**: [Product Strategy — Confluence](https://ehealthnigeria.atlassian.net/wiki/spaces/EHACARE/pages/168525828)  
**Last updated**: 2026-04-12

## What it is
- Multi-tenant SaaS EMR built on OpenEHR/BetterCare platform
- Configurable clinical workflows per tenant (rooms, stages, transitions, triage)
- Targets private hospitals, clinics, and health networks in Nigeria/Africa

## Primary differentiator
- **Workflow engine** — configurable rooms, stages, transitions, triage per tenant
- Helium Health (main competitor) lacks robust per-tenant workflow configuration
- This is the genuine moat — not just an EMR, but a configurable clinical OS

## Commercial model
- BetterCare charges EHA ~€0.25/patient/year (400,000 pre-purchased slots = ~€100K/year)
- EHACare charges tenants $1/patient/year
- **Billing gap**: no native billing in EMR — active sales objection. Odoo ERP is integration layer
- HMO claims live in Odoo ERP, not the EMR

## Key clarifications
- GetCare and HealthMate are EHA Clinics-specific — NOT tenant features
- GetCare and HealthMate do NOT ship to external clients
- Lab Portal: separate app (apps/labportal/) — already has 2 AI features in production

## First external client
- **Hope Children Hospital** — go-live June 2026
- Referral lab workflow is the key net-new capability needed

## Team
- PM/TPM: Yusuf
- Tech Lead: George
- BA (Mobile): Halima
- BA (GetCare/Automation): Banjee
- Head of Product: Ogo
- CTO: Adam

## Jira epics (7 capability domains)
1. Patient Registration & Records
2. Clinical Encounters & Referrals
3. Diagnostics & Pharmacy
4. Scheduling & Patient Flow
5. Billing & Finance
6. Reporting & Quality
7. Tenant & Clinic Administration

## Reference docs
- [Product Strategy](https://ehealthnigeria.atlassian.net/wiki/spaces/EHACARE/pages/168525828)
- [Product Roadmap](https://ehealthnigeria.atlassian.net/wiki/spaces/EHACARE/pages/93257729)
- [PRD Hub](https://ehealthnigeria.atlassian.net/wiki/spaces/EHACARE/pages/168689665)
- [Continuous Product Discovery](https://ehealthnigeria.atlassian.net/wiki/spaces/EHACARE/pages/256442370)
