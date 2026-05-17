# RAI Assessment Master Template
**Prepared by:** Yatiraj Poojari | IAPP AI Governance Professional (AIGP)
**Template Version:** 1.0 | **Framework:** IAPP AIGP · NIST AI RMF · ISO 42001:2023

> **How to use this template:** Fill in each section for the AI system you are assessing. Sections marked ⚠️ are mandatory for any High-Risk AI system. Use the scoring guide in Section 5 to rate each risk.

---

## SECTION 1 — System Profile

| Attribute | Details |
|-----------|---------|
| System Name | |
| System Type | (e.g., ML Classification, LLM, RPA, Recommendation Engine) |
| Business Purpose | |
| Decision Type | (Autonomous / Human-assisted / Advisory) |
| Training Data | |
| Deployment Date | |
| Assessment Date | |
| Geography / Markets | |
| Primary Business Owner | |
| Technical Owner | |
| Volume / Scale | |

---

## SECTION 2 — Use Case Classification ⚠️

### 2.1 Risk Tier Determination

Answer each question to determine the risk tier:

| Question | Response | Risk Signal |
|----------|----------|-------------|
| Does the system make autonomous decisions without human review? | Yes / No | Yes → High Risk indicator |
| Do decisions directly impact individuals' financial, health, legal, or safety outcomes? | Yes / No | Yes → High Risk indicator |
| Is the affected population broad and non-technical? | Yes / No | Yes → High Risk indicator |
| Can individuals contest or appeal automated decisions? | Yes / No | No → High Risk indicator |
| Is the system deployed in a regulated industry? | Yes / No | Yes → High Risk indicator |
| Does the system use personal or sensitive data? | Yes / No | Yes → High Risk indicator |

**Preliminary Classification:** ☐ Minimal Risk | ☐ Limited Risk | ☐ High Risk | ☐ Unacceptable Risk

### 2.2 Framework Alignment

| Framework | Classification | Key Obligations |
|-----------|---------------|-----------------|
| NIST AI RMF | | |
| ISO 42001:2023 | | |
| EU AI Act (if applicable) | | |
| Sector-specific regulation | | |

### 2.3 Stakeholder Mapping

| Stakeholder Type | Who They Are | Key RAI Consideration |
|-----------------|--------------|----------------------|
| Intended Users | | |
| Impacted Users — Primary | | |
| Impacted Users — Secondary | | |
| Oversight Stakeholders | | |
| Third-Party Vendors | | |

---

## SECTION 3 — Pre-Implementation Assessment ⚠️

### 3.1 Governance Readiness

| Checkpoint | Status | Notes |
|-----------|--------|-------|
| RAI assessment conducted before deployment | ☐ Yes ☐ No | |
| AI Accountability Owner designated | ☐ Yes ☐ No | |
| Governance policy in place | ☐ Yes ☐ No | |
| Regulatory compliance reviewed | ☐ Yes ☐ No | |
| Stakeholder mapping completed | ☐ Yes ☐ No | |

### 3.2 Training Data Assessment

| Dimension | Assessment | Gap Identified |
|-----------|-----------|----------------|
| Data provenance — source documented | ☐ Yes ☐ No ☐ Partial | |
| Demographic distribution analysed | ☐ Yes ☐ No ☐ Partial | |
| Historical bias audit conducted | ☐ Yes ☐ No ☐ Partial | |
| Data quality standards defined | ☐ Yes ☐ No ☐ Partial | |
| Consent / legal basis for data use confirmed | ☐ Yes ☐ No ☐ Partial | |
| Data minimisation applied | ☐ Yes ☐ No ☐ Partial | |

### 3.3 Model Design Assessment

| Dimension | Assessment | Gap Identified |
|-----------|-----------|----------------|
| Explainability mechanism in place | ☐ Yes ☐ No ☐ Partial | |
| Fairness constraints applied during training | ☐ Yes ☐ No ☐ Partial | |
| Adversarial / edge case testing conducted | ☐ Yes ☐ No ☐ Partial | |
| Model card / technical documentation created | ☐ Yes ☐ No ☐ Partial | |
| Threshold calibration validated on production distribution | ☐ Yes ☐ No ☐ Partial | |

---

## SECTION 4 — In-Production Assessment ⚠️

### 4.1 Data Risks

| Risk Area | Finding | Risk Level |
|-----------|---------|-----------|
| Data drift — detection mechanism | | |
| PII handling and data minimisation | | |
| Third-party data quality and SLA | | |
| Data lineage and traceability | | |

### 4.2 Model Risks

| Risk Area | Finding | Risk Level |
|-----------|---------|-----------|
| Bias in live output distribution | | |
| Model accuracy vs. baseline | | |
| Confidence / threshold calibration | | |
| Distributional shift from training | | |
| Adversarial input vulnerability | | |

### 4.3 Operational Risks

| Risk Area | Finding | Risk Level |
|-----------|---------|-----------|
| Human override protocol | | |
| Incident response plan | | |
| Audit trail and logging | | |
| Model version control | | |
| Disaster recovery / rollback capability | | |

### 4.4 Ethical Risks

| Risk Area | Finding | Risk Level |
|-----------|---------|-----------|
| Transparency to affected individuals | | |
| Right to contest / appeal mechanism | | |
| Accountability clarity | | |
| Vulnerable population protections | | |
| Environmental / societal impact | | |

---

## SECTION 5 — Risk Scoring ⚠️

### Scoring Guide

| Score | Likelihood | Impact |
|-------|-----------|--------|
| 5 | Almost Certain | Catastrophic |
| 4 | Likely | Major |
| 3 | Possible | Moderate |
| 2 | Unlikely | Minor |
| 1 | Rare | Negligible |

**Risk Level = Likelihood × Impact**
- 🔴 Critical: 20–25 | 🟠 High: 12–19 | 🟡 Medium: 6–11 | 🟢 Low: 1–5

### Risk Summary Table

| Risk ID | Risk Description | Category | Likelihood | Impact | Level | Owner | Target Date |
|---------|-----------------|----------|-----------|--------|-------|-------|------------|
| R-01 | | | | | | | |
| R-02 | | | | | | | |
| R-03 | | | | | | | |
| R-04 | | | | | | | |
| R-05 | | | | | | | |

---

## SECTION 6 — Post-Deployment Monitoring Assessment

| Monitoring Dimension | Current Maturity (0–4) | Target Maturity | Gap |
|--------------------|----------------------|-----------------|-----|
| Model performance tracking | | | |
| Data drift detection | | | |
| Bias / fairness monitoring | | | |
| Human override tracking | | | |
| Incident detection and response | | | |
| Periodic model reassessment | | | |
| Policyholder / user feedback loop | | | |

**Maturity Scale:** 0 = None | 1 = Ad Hoc | 2 = Defined | 3 = Proactive | 4 = Optimised

---

## SECTION 7 — AIGP Domain Coverage

| AIGP Domain | Addressed in This Assessment | Evidence |
|-------------|---------------------------|---------|
| 1. Foundations of AI & Governance | ☐ Yes ☐ Partial ☐ No | |
| 2. AI Risk Management | ☐ Yes ☐ Partial ☐ No | |
| 3. AI Ethics & Responsible AI | ☐ Yes ☐ Partial ☐ No | |
| 4. AI Governance Frameworks | ☐ Yes ☐ Partial ☐ No | |
| 5. AI Lifecycle Governance | ☐ Yes ☐ Partial ☐ No | |
| 6. Stakeholder Engagement | ☐ Yes ☐ Partial ☐ No | |

---

## SECTION 8 — Assessment Sign-Off

| Role | Name | Date | Signature |
|------|------|------|-----------|
| RAI Assessor | | | |
| AI Accountability Owner | | | |
| Compliance Officer | | | |
| Business Owner | | | |

---

*Template by Yatiraj Poojari | IAPP AI Governance Professional (AIGP)*
*Based on NIST AI RMF, ISO 42001:2023, and IAPP AIGP framework. Adapt for your organisation's context.*
