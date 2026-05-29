# AP Platform — AI-Native Accounts Payable

> Interactive prototype for an AI-assisted invoice processing platform at Aker BP.  
> 28 iterations. 17 screens. Specialized AI agents. Built to replace manual AP workflows with confidence-scored, human-in-the-loop automation.
**[→ Live demo](https://helgetorsoy.github.io/ap-platform/)**
---

## What This Is

A fully interactive prototype for a next-generation accounts payable platform designed for Aker BP's finance department. The platform replaces fragmented SAP GUI workflows with a unified, AI-native cockpit where four specialized agents handle invoice coding, PO matching, exception triage, and vendor communication — with humans entering the loop only when AI confidence falls below configurable thresholds.

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
