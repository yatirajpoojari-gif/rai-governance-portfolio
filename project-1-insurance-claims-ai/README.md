# Project 1 — RAI Governance Framework for AI-Powered Claims Automation
### Industry: Insurance & BFSI | Company: Meridian Insurance Ltd | System: ClaimSense ML

---

## Project Overview

Meridian Insurance Ltd deployed **ClaimSense**, an in-house XGBoost ML model, to auto-approve or reject motor insurance claims below ₹2 lakhs — without human review. The system had been live for 4 months, processing ~60% of total claims volume when this RAI assessment was commissioned by the Chief Risk Officer (CRO).

This project delivers a **comprehensive RAI governance framework** covering risk classification, full-lifecycle risk assessment, a detailed risk register, mitigation recommendations, and a 180-day governance roadmap.

---

## Key Findings at a Glance

| Metric | Value |
|--------|-------|
| Risk Classification | **HIGH-RISK AI System** |
| Total Risks Identified | **12** |
| Critical Risks | **3** — Immediate action required |
| High Risks | **5** — Action within 90 days |
| Medium Risks | **4** — Action within 180 days |
| AIGP Domains Covered | **All 6** |

---

## Critical Risks Summary

| ID | Risk | Status |
|----|------|--------|
| R-01 | No pre-deployment RAI assessment conducted | 🔴 Critical |
| R-02 | Training data bias — unaudited historical claims data | 🔴 Critical |
| R-03 | No explainability mechanism for rejected claims | 🔴 Critical |
| R-06 | Demographic bias identified in live output data | 🔴 Critical |

---

## Deliverables in This Project

| File | Description |
|------|-------------|
| [`rai-assessment.md`](./rai-assessment.md) | Full RAI assessment — pre-implementation, in-production, post-deployment |
| [`risk-register.md`](./risk-register.md) | 12-risk register with likelihood × impact scoring and mitigations |
| [`governance-policy.md`](./governance-policy.md) | AI governance policy, accountability structure, and RACI |
| `case-study.pdf` | Full formatted case study document (8-12 pages) |

---

## AIGP Framework Alignment

| AIGP Domain | How It Applies Here |
|-------------|-------------------|
| 1. Foundations of AI & Governance | ClaimSense system architecture and deployment context assessment |
| 2. AI Risk Management | 12 risks identified and scored across 4 dimensions |
| 3. AI Ethics & Responsible AI | Fairness analysis, bias detection, policyholder rights assessment |
| 4. AI Governance Frameworks | Mapped to NIST AI RMF, ISO 42001:2023, EU AI Act, IRDAI |
| 5. AI Lifecycle Governance | Pre-implementation (retrospective), in-production, post-deployment |
| 6. Stakeholder Engagement | CRO-facing recommendations, intended vs impacted user mapping |

---

## Governance Roadmap Summary

| Horizon | Timeframe | Focus |
|---------|-----------|-------|
| Immediate | 0–30 Days | Suspend auto-rejection for flagged segments, bias audit, explainability |
| Short-Term | 30–90 Days | Drift monitoring, PII minimisation, override protocol, incident plan |
| Strategic | 90–180 Days | Retraining, fairness metrics, vendor SLA, formal RACI, annual reassessment |

---

## Use Case Classification

> **ClaimSense is classified as a HIGH-RISK AI system** under NIST AI RMF, ISO 42001:2023, and EU AI Act principles — because it makes fully autonomous, consequential financial decisions affecting a broad population of policyholders without human oversight, explainability, or an appeal mechanism.

---

*Scenario and company are fictional. Methodology reflects IAPP AIGP framework and globally recognised RAI standards.*
