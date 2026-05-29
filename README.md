# AP Platform — AI-Native Accounts Payable

> Interactive prototype for an AI-assisted invoice processing platform at Aker BP.  
> 28 iterations. 17 screens. 5 specialized AI agents. Built to replace manual AP workflows with confidence-scored, human-in-the-loop automation.
**[→ Live demo](https://helgetorsoy.github.io/ap-platform/)**
---

## What This Is

A fully interactive prototype for a next-generation accounts payable platform designed for Aker BP's finance department. The platform replaces fragmented SAP GUI workflows with a unified, AI-native cockpit where five specialized agents handle invoice coding, PO matching, exception triage, and vendor communication — with humans entering the loop only when AI confidence falls below configurable thresholds.

This is a prototype. Every screen is functional — invoices can be opened, coded, matched, approved, and posted. The AI agents respond to user actions. The confidence model updates in real time. The vendor portal has its own login flow and dashboard.

## My Role

I designed and built this prototype end-to-end as a Senior Digital Finance Analyst at Aker BP, in collaboration with our in-house SAP team

- **Problem framing** — current solution is a monolithic SAP + Readsoft add-on solution. Difficult to scale, no modern ML. Heavy manual coding and routing. Exception handling is slow and costly. Heavily reliant on specific technical resources.
- **Solution design** — designed the multi-agent model (Coding, Matching, Exception, Communication), the confidence scoring system, and the human-in-the-loop escalation logic
- **Domain modeling** — mapped every SAP data object (GL accounts, WBS elements, tax codes, PO structures, Service Entry Sheets) into the prototype's data model using real Aker BP naming conventions
- **UX/interaction design** — designed all 17 screens across the full procure-to-pay lifecycle, including the vendor self-service portal
- **Business case** — built the pitch narrative, phased delivery roadmap, and ROI model embedded in the prototype's Story pages
- **28 iterations** — each iteration incorporated feedback from AP specialists, finance managers, and SAP architects

## Architecture

The platform is designed as **cloud-agnostic, container-native, and decoupled from SAP**:

Key design decisions:
- **Multi-agent over monolithic** — five purpose-built agents collaborating through a shared event bus, each learning independently
- **Confidence-first** — every AI prediction carries a confidence score; only predictions above the threshold auto-post
- **Shadow mode** — agents run in parallel with human decisions before going autonomous, building trust through measurable accuracy
- **SAP-decoupled** — reads/writes to SAP via OData APIs, but the platform's logic lives outside the ERP

## The Five Agents

| Agent | Purpose | Key Behavior |
|-------|---------|-------------|
| **Coding Agent** | Predicts GL account, cost center (WBS), and tax code | Learns from every approver correction via vector memory |
| **Matching Agent** | 2-way and 3-way matching against POs, GRs, and SES | Fuzzy line matching with unit-of-measure normalization |
| **Exception Agent** | Triages mismatches and recommends resolution paths | Gathers historic evidence so AP doesn't start from a blank page |
| **Communication Agent** | Drafts buyer and vendor emails | Bilingual templates (EN/NO) with one-click send |
| **Risk & Fraud Agent** | Catches what tired humans miss | Hunts duplicate invoices, bank-account changes, amount anomalies, and new-vendor fraud patterns| 

## Screens

The prototype includes 17 interactive screens:

**Story pages** (context and pitch):
- Overview — architecture, agent model, phased delivery status
- The Pitch — autoplay live demo that drives the real app
- Business Case — goals, outcomes, combined value proposition
- Roadmap — 7-phase delivery plan from Foundation to Continuous Audit

**Application pages** (working screens):
- Cockpit — KPI dashboard with configurable metrics and AI assistant
- Invoices — unified queue with natural-language filtering, bulk actions
- OCR — document intelligence with extraction confidence
- Inbox — AI-drafted communications, bilingual templates
- Risk — fraud detection and anomaly flagging
- Cash-flow — payment timing optimization
- P2P Timeline — full procure-to-pay lifecycle view per invoice
- Vendor Portal — external self-service with login, dashboard, clarification flows
- AI Agents — agent status, accuracy metrics, learning history
- Analytics — spend analytics grouped by vendor, status, period
- Ask AI — natural-language Copilot for AP queries
- Learning — onboarding and documentation
- Customizing — thresholds, templates, rules, automation settings

## Confidence Model

The prototype implements a working confidence scoring system:

- **High confidence (≥95%)**: Auto-post to SAP, no human review
- **Medium confidence (71–94%)**: Route to AP specialist for review
- **Low confidence (<71%)**: Flag for manual coding with AI suggestion as starting point

Confidence thresholds are configurable per vendor based on historical accuracy:
- High-volume vendors with stable patterns → lower threshold (e.g., 92%)
- Vendors with historic coding inconsistencies → higher threshold (e.g., 98%)

## Technology & Context

- Built as a single-file interactive HTML/CSS/JS application
- Data model mirrors real SAP S/4HANA structures (GL accounts, WBS elements per NCS project naming, tax codes, PO/GR/SES matching)
- Vendor data uses realistic Norwegian E&P industry suppliers (Halliburton, Schlumberger, Aibel, DNV, Subsea 7)
- Contract integration shows SAP Outline Agreements and Ivalua CLM sync
- All data is synthetic — no proprietary information

## Delivery Approach

The prototype embeds a phased delivery model:

1. **Foundation** (Weeks 1–8) — Core platform, data model, SAP connectivity ✓
2. **Coding Agent** (Weeks 9–16) — GL/CC/tax prediction with confidence scoring ✓
3. **Shadow Mode** (Weeks 17–24) — Parallel run, accuracy validation ← current
4. **Autonomous** (Week 25+) — Auto-posting above threshold
5. **Vendor Portal** — Self-service for suppliers
6. **Predictive Analytics** — Cash-flow forecasting, accrual prediction
7. **Continuous Audit** — Real-time compliance monitoring

## Related Work

This prototype is part of a broader portfolio of finance digitalization at Aker BP:

- **Driver-Based Forecast (D&W)** — Wizard-based forecasting for Drilling & Wells (13 iterations, currently in SAP Fiori development)
- **Close Cockpit** — Financial close management dashboard (5 iterations, SAP Fiori target)
- **Data Product Standard for Finance** — Ordering framework for finance data products in Microsoft Fabric
- **SAP Project Delivery Methodology** — New process for running SAP projects, demonstrated to PM, SCM, and AI Champions

---

*Built by Helge Torsøy · Senior Digital Finance Analyst · Aker BP*
