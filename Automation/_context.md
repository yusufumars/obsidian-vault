# Automation — Product Context

**Status**: Active  
**Last updated**: 2026-04-12

## What it is
- n8n-based automation workflows for EHA Clinics operations
- Banjee is the BA and domain owner
- Self-hosted n8n instance at n8n.ehealth.ink

## Active automations
- EHACare FAQ chatbot (Groq llama-3.3-70b-versatile model, knowledge base from eha-care-knowledge-base.md)
- Lab results delivery via WhatsApp and Google Sheets

## Hard data privacy rules (non-negotiable)
- Only Report IDs flow through WhatsApp and Google Sheets — NO PII
- No patient names, DOB, diagnosis, or any identifying information in automation outputs
- Dedicated read-only service account — not shared credentials
- These rules apply to ALL n8n automations touching patient data

## Deferred work
- GitHub Actions auto-update pipeline for knowledge base (deferred to George)

## Stakeholders who have production URL
- Victor (Director)
- Ogo (Head of Product)
