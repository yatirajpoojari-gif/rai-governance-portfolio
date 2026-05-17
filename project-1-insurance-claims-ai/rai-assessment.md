# RAI Assessment — ClaimSense ML System
**Meridian Insurance Ltd | Motor Claims Automation**
**Assessment Type:** Full Lifecycle | **Prepared by:** Yatiraj Poojari | **Framework:** IAPP AIGP

---

## 1. System Profile

| Attribute | Details |
|-----------|---------|
| System Name | ClaimSense v1.2 |
| System Type | Supervised ML Classification (XGBoost) |
| Purpose | Automated approve/reject for motor claims < ₹2 lakhs |
| Training Data | 2.4M records — 3 years historical claims data |
| Deployment Date | January 2026 |
| Assessment Date | May 2026 (4 months post-deployment) |
| Geography | India & UAE |
| Decision Authority | Fully autonomous below ₹2L; human review above ₹2L |
| Volume Processed | ~60% of total incoming claims (~5,000–6,000/month) |

---

## 2. Use Case Classification

### 2.1 Risk Tier Determination

**Classification: HIGH-RISK AI SYSTEM**

| Classification Lens | Assessment | Rationale |
|--------------------|------------|-----------|
| Nature of Decision | Consequential — Autonomous financial decision | Approve/reject directly impacts policyholder's financial recovery |
| Affected Population | Broad, non-technical, potentially vulnerable | Accident victims, elderly policyholders, Tier-3 city residents |
| Reversibility | Low — decisions are communicated before any review | Rejected claims cause immediate financial harm |
| Human Oversight | None for sub-₹2L claims | No review, no override protocol, no monitoring |

### 2.2 Framework Classification

| Framework | Classification | Key Obligations |
|-----------|---------------|-----------------|
| NIST AI RMF | High Impact AI System | GOVERN, MAP, MEASURE, MANAGE controls required |
| ISO 42001:2023 | High Risk AI Application | Risk management, human oversight, auditability |
| EU AI Act (reference) | High Risk — Financial Services AI | Conformity assessment, transparency, human oversight |
| IRDAI Guidelines | Regulated Automated Decision System | Explainability, appeal mechanism, audit trail |

### 2.3 Stakeholder Mapping

| Stakeholder Type | Who They Are | RAI Consideration |
|-----------------|--------------|-------------------|
| Intended Users | Claims operations team, data science team, compliance officers | Must understand model limitations and be able to override |
| Impacted Users — Primary | Motor insurance policyholders | Affected by automated decisions; need transparency and appeal rights |
| Impacted Users — Secondary | Vehicle repair vendors, third-party claimants | Indirectly affected by approval/rejection timelines |
| Oversight Stakeholders | CRO, Compliance team, IRDAI | Accountable for governance; need audit trail and performance data |

---

## 3. Pre-Implementation Risk Assessment (Retrospective)

> These risks were present at system design and deployment. No pre-deployment RAI assessment was conducted — this section reconstructs what should have been assessed before go-live.

### 3.1 Governance Assessment

**Finding:** ClaimSense was deployed without a formal RAI assessment, governance sign-off, or accountability structure. The data science team performed model accuracy testing (F1 score, precision, recall) but did not assess:
- Fairness across demographic groups
- Societal impact of automated rejection at scale
- Regulatory alignment for automated financial decisions
- Policyholder rights and transparency obligations

**Gap:** No RAI governance framework existed at Meridian Insurance at the time of deployment.

**Risk Level:** 🔴 Critical

---

### 3.2 Training Data Assessment

**Finding:** The model was trained on 3 years of historical motor insurance claims data (2.4M records). Key concerns:

- **Representativeness:** Distribution of training data across demographic groups (age, geography, vehicle type) was not documented
- **Historical bias:** Human adjudicators who produced the historical approval/rejection decisions likely carried unconscious biases — particularly around Tier-3 city claimants and elderly policyholders
- **Data quality:** No data quality audit was performed before training. Missing values, outliers, and data entry inconsistencies were handled by the data science team without formal governance oversight
- **Temporal relevance:** Claims patterns from 2021–2023 may not reflect post-COVID vehicle usage and claim behaviour in 2026

**Gap:** No bias audit, no data quality documentation, no representativeness analysis.

**Risk Level:** 🔴 Critical

---

### 3.3 Model Design Assessment

**Finding:** The XGBoost model produces a binary output (approve/reject) with a confidence score. Key design gaps:

- No explainability layer — the model cannot generate reasons for its decisions
- Fixed confidence threshold (0.72) set on balanced test data — not validated against live distribution
- No fairness constraints applied during model training
- No adversarial testing or edge case analysis documented

**Gap:** Model was optimised for accuracy on a test set, not for fairness, explainability, or robustness in live deployment.

**Risk Level:** 🔴 Critical

---

## 4. In-Production Risk Assessment

### 4.1 Data Risks

#### R-04 — Data Drift
**Finding:** No mechanism exists to detect whether incoming claims data is drifting from the training distribution. Four months of live operation without monitoring means potential degradation in model performance is invisible to the team.

**Evidence of concern:** Post-COVID shifts in vehicle usage patterns, fraud behaviour, and claim frequency have been documented across the industry. ClaimSense's training data predates these shifts.

**Metrics to monitor:**
- Population Stability Index (PSI) on key input features
- Kolmogorov-Smirnov (KS) test on score distribution
- Feature drift on top 10 model input variables

**Risk Level:** 🟠 High

---

#### R-05 — Excess PII in Model Inputs
**Finding:** ClaimSense ingests the following PII fields that may not be necessary for the approval/rejection decision:
- Full policyholder name and address
- Vehicle registration number (full)
- Medical report details in injury claims
- Contact details of repair vendors

**Data minimisation principle** requires that only data strictly necessary for the intended purpose is processed. No data minimisation review was conducted.

**Risk Level:** 🟠 High

---

### 4.2 Model Risks

#### R-06 — Demographic Bias in Live Outputs
**Finding:** Analysis of 4-month output data (January–April 2026) reveals:

| Segment | Approval Rate | vs. Metro Average |
|---------|--------------|-------------------|
| Metro cities (Mumbai, Delhi, Bengaluru) | 74% | Baseline |
| Tier-2 cities | 68% | -6 percentage points |
| Tier-3 cities | 61% | **-13 percentage points** |
| Policyholders under 40 | 76% | Baseline |
| Policyholders over 60 | 58% | **-18 percentage points** |

These differentials are statistically significant and consistent with historical adjudicator bias patterns in the training data.

**Risk Level:** 🔴 Critical

---

#### R-07 — Confidence Threshold Miscalibration
**Finding:** The 0.72 confidence threshold was calibrated on a balanced test dataset (50/50 approve/reject). In live deployment, the natural distribution of claims is approximately 68% approvable / 32% rejectable. This mismatch causes over-rejection at the decision boundary.

**Estimated impact:** Approximately 200–300 claims per month may be incorrectly rejected due to threshold miscalibration.

**Risk Level:** 🟠 High

---

### 4.3 Operational Risks

#### R-08 — No Human Override Protocol
**Finding:** There is no documented, tracked, or reported mechanism for the claims operations team to override a ClaimSense decision. While technically possible in the system, overrides are:
- Not tracked in any governance log
- Not reported to compliance or CRO
- Not used as feedback to improve model performance
- Not subject to any authorisation or review process

This means the organisation has no visibility into how often human judgement contradicts the model.

**Risk Level:** 🟠 High

---

#### R-09 — No Incident Response Plan
**Finding:** No documented AI Incident Response Plan exists for ClaimSense. There are no defined:
- Trigger conditions for a ClaimSense incident
- Detection mechanisms for systematic errors
- Escalation paths or notification protocols
- Containment steps or rollback procedures
- Post-incident review process

If ClaimSense produces a batch of systematically wrong decisions, the team would respond reactively without a defined process.

**Risk Level:** 🟠 High

---

#### R-10 — Third-Party Data Dependency
**Finding:** ClaimSense ingests vehicle damage assessment data from a third-party inspection vendor. No formal data quality SLA has been established. The vendor's data completeness, accuracy, and latency standards are undocumented.

**Risk:** Inaccurate or incomplete third-party data directly influences model outputs without any validation gate.

**Risk Level:** 🟡 Medium

---

### 4.4 Ethical Risks

#### R-11 — No Policyholder Transparency
**Finding:** Policyholders are not informed that:
- Their claim is being assessed by an automated AI system
- What data was used in the assessment
- How the decision was reached
- That they have the right to request human review

Rejection notices currently state only that the claim has been assessed and the outcome — with no AI disclosure and no appeal pathway communicated.

**Risk Level:** 🟠 High

---

#### R-12 — Diffuse Accountability
**Finding:** Accountability for ClaimSense decisions is spread across three teams with no clear ownership:
- Data science team owns the model
- Claims operations team owns the outputs
- Compliance team has no formal oversight mandate

There is no designated AI Accountability Owner and no RACI matrix for ClaimSense governance.

**Risk Level:** 🟡 Medium

---

## 5. Post-Deployment Monitoring Assessment

| Monitoring Dimension | Current State | Target State |
|---------------------|---------------|--------------|
| Model performance tracking | None | Weekly accuracy and fairness metrics dashboard |
| Data drift detection | None | Automated PSI/KS alerts on weekly data batches |
| Bias monitoring | None | Monthly fairness metrics (Equalized Odds, Demographic Parity) |
| Override tracking | Informal, unlogged | Formal override log reviewed monthly by CRO |
| Incident detection | Reactive only | Automated alert thresholds with defined escalation path |
| Periodic reassessment | None scheduled | Annual full RAI reassessment |

**Overall post-deployment monitoring maturity: Level 0 (None)**
**Target: Level 3 (Proactive) within 180 days**

---

## 6. Assessment Summary

| Risk ID | Risk Description | Category | Likelihood | Impact | Level |
|---------|-----------------|----------|-----------|--------|-------|
| R-01 | No pre-deployment RAI assessment | Governance | 5 | 5 | 🔴 Critical |
| R-02 | Training data bias — unaudited | Data | 5 | 5 | 🔴 Critical |
| R-03 | No explainability for rejections | Model | 5 | 5 | 🔴 Critical |
| R-04 | Data drift — no detection | Data | 4 | 4 | 🟠 High |
| R-05 | Excess PII in model inputs | Data | 3 | 4 | 🟠 High |
| R-06 | Demographic bias in live outputs | Model | 5 | 4 | 🔴 Critical |
| R-07 | Confidence threshold miscalibration | Model | 3 | 4 | 🟠 High |
| R-08 | No human override protocol | Operational | 4 | 4 | 🟠 High |
| R-09 | No incident response plan | Operational | 3 | 5 | 🟠 High |
| R-10 | Third-party data dependency | Operational | 3 | 3 | 🟡 Medium |
| R-11 | No policyholder AI transparency | Ethics | 4 | 4 | 🟠 High |
| R-12 | Diffuse accountability — no AI owner | Governance | 3 | 3 | 🟡 Medium |

---

*Prepared by Yatiraj Poojari | IAPP AI Governance Professional (AIGP) | Portfolio Case Study*
*Scenario and company are fictional. Methodology reflects globally recognised RAI standards.*
