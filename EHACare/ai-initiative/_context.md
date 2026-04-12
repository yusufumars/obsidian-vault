# EHACare Clinical AI Platform

**Status**: Phase 1 planning  
**Source**: [Design Document — Confluence](https://ehealthnigeria.atlassian.net/wiki/spaces/EHACARE/pages/263913478)  
**Author**: Adam Thompson + Claude  
**Last updated**: 2026-04-12

## Three-layer architecture
1. **KemiQA** (knowledge layer) — 14 knowledge bases, Databricks-first, Unity Catalog + Vector Search. Currently ~30-40% complete (Phase 1 of 5)
2. **@ehacare/health-ai** (orchestration layer) — shared workspace library wrapping Claude Agent SDK, routing all AI through Databricks AI Gateway for governance, tracing, cost control
3. **EHA Care EMR** (workflow integration layer) — AI embedded at specific touchpoints, no workflow redesigns

## 8 capability areas
| # | Capability | Phase |
|---|---|---|
| 1 | Quality App Modernisation | 1-5 |
| 2 | Clinical Notes Enhancement | 6 |
| 3 | Diagnostic Support | 7 |
| 4 | Pharmacy Safety | 8 |
| 5 | Lab & Imaging Intelligence | 9 |
| 6 | Leadership Analytics | 10 |
| 7 | Voice Capture | 11 |
| 8 | Population Surveillance | 9/10 |

## Key architectural decisions
- **Databricks AI Gateway** (not direct Anthropic API) — MLflow tracing, governance, cost visibility, multi-model routing
- **Claude Agent SDK** — tool execution loop, subagent support, MCP server integration
- **Human-in-the-loop is non-negotiable** — AI suggests, clinician decides
- **Models**: Claude Sonnet 4.6 default → Haiku after structured validation (95% agreement rate threshold)
- **NOT using** Anthropic's Claude for Healthcare offering — US-centric connectors, irrelevant to Nigeria

## Cost control (4 layers)
1. Model tiering (Sonnet → Haiku after validation)
2. Prompt caching (90% discount on repeated system prompts)
3. Message Batches API (50% discount for non-interactive tasks)
4. Application-level Redis caching (cache-aside, keyed on composition UID)

## Current phase status
- Phase 1 (Foundation): not started. Prereq: Databricks AI Gateway endpoint provisioned
- KemiQA: ~30-40% complete (Phase 1 of 5 — Terminology + Pharma KBs in progress)
- Lab Portal: 2 AI features already in production (AI lab interpretations + PDF extraction) — these validate the Databricks gateway pattern

## Key assumptions to validate
- Databricks AI Gateway can proxy Claude Agent SDK agentic loop traffic (tool calls, multi-turn)
- Clinician time available for Phase 4 model validation (200-chart blind review)
- Standards digitization project delivers content for Phase 4

## Reference docs
- [Full Design Document](https://ehealthnigeria.atlassian.net/wiki/spaces/EHACARE/pages/263913478)
- [Product Strategy Hub](https://ehealthnigeria.atlassian.net/wiki/spaces/EHACARE/pages/168525828)
