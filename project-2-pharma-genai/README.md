# Project 2 — RAI Maturity Assessment for Gen AI in Drug Discovery
### Industry: Pharma / Life Sciences | Company: NovaSynth Biologics | System: SynthMind AI Platform

---

## Project Overview

NovaSynth Biologics, a mid-size European pharmaceutical company, deployed **SynthMind** — a Gen AI platform combining a fine-tuned LLM with a retrieval-augmented generation (RAG) pipeline — to accelerate two core R&D workflows: **molecule screening** and **clinical trial patient matching**.

The platform had been operational for 6 months across two research sites (Basel, Switzerland and Hyderabad, India) when this RAI maturity assessment was commissioned by the Chief Scientific Officer (CSO) and Head of Compliance, following concerns raised during an internal audit about AI decision traceability and regulatory readiness ahead of an EMA inspection.

This project delivers a **full RAI maturity assessment**, a risk register, a governance policy, and a **12-month roadmap** to move NovaSynth from its current maturity level to a governed, audit-ready RAI posture.

---

## Key Findings at a Glance

| Metric | Value |
|--------|-------|
| Overall RAI Maturity Level | **Level 1 — Ad Hoc** (out of 5) |
| Target Maturity (12 months) | **Level 3 — Defined** |
| Total Risks Identified | **14** |
| Critical Risks | **4** — Immediate action required |
| High Risks | **6** — Action within 90 days |
| Medium Risks | **4** — Action within 180 days |
| Regulatory Exposure | FDA SaMD · EU AI Act · ICH E6 · ISO 42001:2023 |
| AIGP Domains Covered | **All 6** |

---

## RAI Maturity Summary

| Domain | Current Level | Target Level (12 months) |
|--------|--------------|--------------------------|
| AI Governance & Accountability | Level 1 | Level 3 |
| Risk Management | Level 1 | Level 3 |
| Data Governance | Level 2 | Level 4 |
| Model Transparency & Explainability | Level 0 | Level 3 |
| Ethics & Fairness | Level 0 | Level 3 |
| Regulatory Compliance | Level 1 | Level 3 |
| Incident Response & Monitoring | Level 1 | Level 3 |

> **Level 0** = Non-existent · **Level 1** = Ad Hoc · **Level 2** = Developing · **Level 3** = Defined · **Level 4** = Managed · **Level 5** = Optimised

---

## Critical Risks Summary

| ID | Risk | Level |
|----|------|-------|
| R-01 | No RAI governance framework or accountability structure exists | 🔴 Critical (25/25) |
| R-02 | LLM outputs used in clinical trial matching without human validation protocol | 🔴 Critical (25/25) |
| R-03 | No explainability or audit trail for molecule screening recommendations | 🔴 Critical (20/25) |
| R-04 | Training and retrieval data contains unpublished proprietary research — IP and consent gaps | 🔴 Critical (20/25) |

---

## Deliverables in This Project

| File | Description |
|------|-------------|
| [`rai-maturity-assessment.md`](./rai-maturity-assessment.md) | Full RAI maturity assessment — 7 domains, maturity scoring, gap analysis, roadmap |
| [`risk-register.md`](./risk-register.md) | 14-risk register with likelihood × impact scoring and mitigations |
| [`governance-policy.md`](./governance-policy.md) | AI governance policy, accountability structure, RACI, and operating model |
| Case Study — Full Document | DOCX | [📝 Download DOCX](YOUR_GOOGLE_DRIVE_LINK_P2_DOCX) |
| Presentation Deck | PPTX | [📊 Download PPTX](YOUR_GOOGLE_DRIVE_LINK_P2_PPTX) |

---

## Regulatory Framework Alignment

| Framework | Relevance to NovaSynth | Key Obligations |
|-----------|----------------------|-----------------|
| EU AI Act | SynthMind classified as High-Risk AI in medical/clinical context | Conformity assessment, human oversight, transparency, audit trail |
| FDA SaMD Guidance | Patient matching function meets Software as a Medical Device definition | Performance evidence, post-market surveillance, change control |
| ICH E6 (R3) GCP | Clinical trial patient matching directly implicates Good Clinical Practice | Data integrity, subject protection, investigator accountability |
| ISO 42001:2023 | Organisational AI management system standard | Risk management, roles, continual improvement |
| NIST AI RMF | Operational governance framework | GOVERN · MAP · MEASURE · MANAGE controls across lifecycle |

---

## AIGP Framework Alignment

| AIGP Domain | How It Applies Here |
|-------------|-------------------|
| 1. Foundations of AI & Governance | Gen AI (LLM + RAG) architecture assessment in a regulated research context |
| 2. AI Risk Management | 14 risks identified across data, model, operational, ethical, and regulatory dimensions |
| 3. AI Ethics & Responsible AI | Patient safety, clinical trial fairness, informed consent, IP ethics |
| 4. AI Governance Frameworks & Standards | EU AI Act, FDA SaMD, ICH E6, ISO 42001:2023, NIST AI RMF |
| 5. AI Lifecycle Governance | In-production maturity assessment with pre-deployment retrospective |
| 6. Stakeholder Engagement | CSO, Head of Compliance, EMA readiness framing, patient impact mapping |

---

## 12-Month Governance Roadmap Summary

| Horizon | Timeframe | Focus |
|---------|-----------|-------|
| Foundation | 0–90 Days | Establish AI governance committee · appoint AI Accountability Owner · freeze clinical trial matching pending human review protocol |
| Build | 90–180 Days | Deploy explainability layer · data provenance audit · IP and consent review · draft AI governance policy |
| Operate | 180–270 Days | Implement drift monitoring · fairness metrics · incident response plan · SaMD classification assessment |
| Sustain | 270–365 Days | First annual RAI review · EMA readiness assessment · publish internal AI transparency report · target Level 3 maturity |

---

*Scenario and company are fictional. Methodology reflects IAPP AIGP framework and globally recognised RAI standards: NIST AI RMF · ISO 42001:2023 · EU AI Act · FDA SaMD · ICH E6.*
