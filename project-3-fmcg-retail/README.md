# Project 3 — AI Ethics & Risk Assessment for Consumer Personalisation Engine
### Industry: FMCG / Retail (D2C E-Commerce) | Company: LumeCart India | System: LumeAI Personalisation Engine

---

## Project Overview

LumeCart India is a fast-growing direct-to-consumer (D2C) e-commerce platform serving 8 million users across Tier-1, Tier-2, and Tier-3 cities. In 2024, LumeCart deployed **LumeAI** — an AI personalisation engine combining collaborative filtering, dynamic pricing algorithms, and behavioural nudge systems — to drive product discovery, increase average order value, and reduce cart abandonment.

By May 2026, LumeAI was influencing approximately **73% of all purchase decisions** on the platform through personalised recommendations, surge pricing, urgency triggers, and targeted discount offers.

This RAI assessment was commissioned by the Chief Product Officer (CPO) and Data Protection Officer (DPO) following a consumer rights complaint filed with India's Data Protection Board under the **Digital Personal Data Protection (DPDP) Act 2023**, alleging that LumeAI was using personal data beyond the scope of user consent to manipulate purchasing behaviour.

This project delivers a **comprehensive RAI ethics and risk assessment** covering algorithmic bias, consumer data privacy, dark pattern design, and AI transparency — with a full risk register, governance policy, and 12-month remediation roadmap.

---

## Key Findings at a Glance

| Metric | Value |
|--------|-------|
| RAI Risk Classification | **HIGH-RISK AI System** |
| Total Risks Identified | **15** |
| Critical Risks | **4** — Immediate action required |
| High Risks | **7** — Action within 90 days |
| Medium Risks | **4** — Action within 180 days |
| Users Affected | **8 million** across India |
| Regulatory Exposure | DPDP Act 2023 · EU AI Act · Consumer Protection Act 2019 · BIS AI Standards |
| AIGP Domains Covered | **All 6** |

---

## Critical Risks Summary

| ID | Risk | Level |
|----|------|-------|
| R-01 | LumeAI trained on data collected beyond original consent scope | 🔴 Critical (25/25) |
| R-02 | Dynamic pricing algorithm charges higher prices to lower-income user segments | 🔴 Critical (25/25) |
| R-03 | Urgency and scarcity nudges use fabricated signals — dark pattern manipulation | 🔴 Critical (20/25) |
| R-04 | No algorithmic transparency — users cannot understand why they see specific prices or recommendations | 🔴 Critical (20/25) |

---

## Deliverables in This Project

| File | Description |
|------|-------------|
| [`rai-assessment.md`](./rai-assessment.md) | Full RAI ethics assessment — bias, privacy, dark patterns, transparency |
| [`risk-register.md`](./risk-register.md) | 15-risk register with Likelihood × Impact scoring and mitigations |
| [`governance-policy.md`](./governance-policy.md) | AI ethics governance policy, RACI, consumer rights framework |
| Case Study — Full Document | DOCX | [📝 Download DOCX](YOUR_GOOGLE_DRIVE_LINK_P3_DOCX) |
| Presentation Deck | PPTX | [📊 Download PPTX](YOUR_GOOGLE_DRIVE_LINK_P3_PPTX) |

---

## Ethics Themes Covered

| Theme | Key Findings |
|-------|-------------|
| Algorithmic Bias & Fairness | Dynamic pricing systematically disadvantages Tier-2/3 city users and lower-income segments · Recommendation engine amplifies premium product bias |
| Consumer Data Privacy | Data used beyond original consent scope · Cross-app data sharing undisclosed · DPDP Act 2023 obligations unmet |
| Dark Patterns & Manipulation | Fabricated urgency signals ("Only 2 left!") · Fake countdown timers · Personalised fear-of-missing-out (FOMO) triggers |
| Transparency & Explainability | No explanation for personalised prices · No opt-out for AI-driven recommendations · No AI disclosure to users |

---

## Regulatory Framework Alignment

| Framework | Relevance | Key Obligations |
|-----------|-----------|----------------|
| DPDP Act 2023 (India) | Primary — complaint already filed | Consent management, data minimisation, purpose limitation, user rights |
| Consumer Protection Act 2019 | Unfair trade practices, misleading claims | Dark pattern prohibition, price transparency, right to fair treatment |
| EU AI Act (reference) | High-Risk / General Purpose AI | Transparency obligations, bias monitoring, user rights |
| BIS AI Ethics Standard IS 17880 | India national AI standard | Fairness, accountability, transparency for AI systems |
| NIST AI RMF | Operational governance | GOVERN · MAP · MEASURE · MANAGE |

---

## AIGP Framework Alignment

| AIGP Domain | How It Applies Here |
|-------------|-------------------|
| 1. Foundations of AI & Governance | Recommender system + dynamic pricing + nudge engine architecture assessment |
| 2. AI Risk Management | 15 risks across bias, privacy, manipulation, transparency, and operational dimensions |
| 3. AI Ethics & Responsible AI | Consumer fairness, manipulation ethics, privacy rights, vulnerable user protection |
| 4. AI Governance Frameworks & Standards | DPDP Act 2023, Consumer Protection Act, EU AI Act, BIS IS 17880, NIST AI RMF |
| 5. AI Lifecycle Governance | In-production assessment with pre-deployment retrospective gap analysis |
| 6. Stakeholder Engagement | CPO, DPO, consumer rights mapping, Data Protection Board response framing |

---

## Governance Roadmap Summary

| Horizon | Timeframe | Focus |
|---------|-----------|-------|
| Immediate | 0–30 Days | Disable fabricated urgency signals · Suspend cross-app data sharing · Appoint AI Ethics Lead |
| Short-Term | 30–90 Days | Bias audit of dynamic pricing · Consent architecture rebuild · Transparency notices |
| Strategic | 90–180 Days | Fairness metrics dashboard · Algorithmic accountability report · DPDP compliance posture |
| Sustain | 180–365 Days | Annual ethics review · Consumer redress mechanism · AI disclosure framework |

---

*Scenario and company are fictional. Methodology reflects IAPP AIGP framework and globally recognised RAI standards: NIST AI RMF · EU AI Act · DPDP Act 2023 · Consumer Protection Act 2019 · BIS IS 17880.*
