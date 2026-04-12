# EHACare — Architecture Notes

**Last updated**: 2026-04-12

## Stack
- Platform: OpenEHR / BetterCare
- Frontend: Next.js (React)
- Multi-tenant SaaS
- ERP integration: Odoo (billing, HMO claims, inventory)
- Automation: n8n (self-hosted at n8n.ehealth.ink)

## Key apps in monorepo
- `apps/ehacare/` — main EMR
- `apps/labportal/` — lab portal (separate app, 2 AI features in production)
- `libs/bettercare-sdk/` — SDK wrapping BetterCare REST/AQL API
- `libs/erp-adapter/` — Odoo integration layer (version-agnostic, supports v16-v20)

## Data flow
- Clinical data: OpenEHR compositions in BetterCare EHR
- Analytics: BetterCare ETL → Cloud SQL → Databricks → Tableau (being replaced in AI Phase 3)
- Billing/HMO: Odoo ERP
- Automation outputs: n8n → WhatsApp/Google Sheets (Report IDs only, no PII)

## BetterCare proxy
- All EHR calls go through `/api/bettercare/[...path]` proxy
- SDK handles AQL construction, response typing, Zod validation
