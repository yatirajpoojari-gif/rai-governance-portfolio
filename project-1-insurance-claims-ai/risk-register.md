# Risk Register — ClaimSense ML System
**Meridian Insurance Ltd | Motor Claims Automation**
**Register Version:** 1.0 | **Owner:** AI Accountability Owner (TBA) | **Review Frequency:** Monthly

---

## Scoring Methodology

| Score | Likelihood | Impact |
|-------|-----------|--------|
| 5 | Almost Certain — will very likely occur | Catastrophic — severe regulatory, financial, or reputational harm |
| 4 | Likely — has a high probability of occurring | Major — significant operational disruption or policyholder harm |
| 3 | Possible — may occur under certain conditions | Moderate — contained impact, manageable remediation |
| 2 | Unlikely — low probability | Minor — limited impact, easy to recover |
| 1 | Rare — would only occur in exceptional circumstances | Negligible — minimal impact |

**Risk Level = Likelihood × Impact**

| Risk Level | Score Range | Action Required |
|-----------|-------------|-----------------|
| 🔴 Critical | 20–25 | Immediate action — escalate to CRO within 24 hours |
| 🟠 High | 12–19 | Action within 90 days — assign owner and milestone |
| 🟡 Medium | 6–11 | Action within 180 days — include in governance roadmap |
| 🟢 Low | 1–5 | Monitor — review at quarterly governance meeting |

---

## Risk Register

### R-01 — No Pre-Deployment RAI Assessment

| Field | Detail |
|-------|--------|
| **Risk ID** | R-01 |
| **Risk Description** | ClaimSense was deployed without a formal RAI assessment, governance sign-off, or accountability structure |
| **Risk Category** | Governance |
| **Risk Owner** | Chief Risk Officer |
| **Likelihood** | 5 — Already occurred |
| **Impact** | 5 — Entire governance foundation is missing; all subsequent risks are amplified |
| **Risk Level** | 🔴 Critical (25) |
| **Current Controls** | None |
| **Primary Mitigation** | Conduct retrospective RAI assessment immediately (this document); mandate governance sign-off for all future AI deployments |
| **Secondary Mitigation** | Draft and adopt an AI Governance Policy that requires RAI assessment before any AI system goes live |
| **Target Date** | Immediate — within 30 days |
| **Residual Risk** | 🟡 Medium — once retrospective assessment is complete and policy is adopted |
| **Status** | 🔴 Open |

---

### R-02 — Training Data Bias — Unaudited Historical Data

| Field | Detail |
|-------|--------|
| **Risk ID** | R-02 |
| **Risk Description** | Model trained on historical claims data carrying unaudited human adjudicator biases; no bias audit conducted pre-training |
| **Risk Category** | Data |
| **Risk Owner** | Data Science Lead |
| **Likelihood** | 5 — Bias confirmed in live output analysis (see R-06) |
| **Impact** | 5 — Systemic unfair decisions at scale; regulatory and legal exposure |
| **Risk Level** | 🔴 Critical (25) |
| **Current Controls** | None |
| **Primary Mitigation** | Commission independent bias audit of 2.4M record training dataset; document demographic distribution |
| **Secondary Mitigation** | Retrain model with curated, balanced dataset; apply fairness constraints during training |
| **Target Date** | Bias audit: 30 days | Retraining: 90–120 days |
| **Residual Risk** | 🟡 Medium — post retraining, residual model risk remains; ongoing monitoring required |
| **Status** | 🔴 Open |

---

### R-03 — No Explainability for Rejected Claims

| Field | Detail |
|-------|--------|
| **Risk ID** | R-03 |
| **Risk Description** | ClaimSense produces binary approve/reject output with no explanation — policyholders and operations team cannot understand rejection basis |
| **Risk Category** | Model |
| **Risk Owner** | Data Science Lead |
| **Likelihood** | 5 — Confirmed absent in current system |
| **Impact** | 5 — Policyholders cannot contest; regulatory non-compliance; reputational risk |
| **Risk Level** | 🔴 Critical (25) |
| **Current Controls** | None |
| **Primary Mitigation** | Implement SHAP or LIME post-hoc explainability module on ClaimSense inference pipeline |
| **Secondary Mitigation** | Generate plain-language rejection reason (top 3 contributing factors) stored in audit trail and communicated to policyholder |
| **Target Date** | 30–60 days |
| **Residual Risk** | 🟢 Low — post-hoc explanations well-established for XGBoost; implementation is straightforward |
| **Status** | 🔴 Open |

---

### R-04 — Data Drift — No Detection Mechanism

| Field | Detail |
|-------|--------|
| **Risk ID** | R-04 |
| **Risk Description** | No mechanism to detect distributional drift in incoming claims data vs. training data; model performance degradation is invisible |
| **Risk Category** | Data |
| **Risk Owner** | Data Science Lead |
| **Likelihood** | 4 — Post-COVID claims pattern shifts are documented across industry |
| **Impact** | 4 — Silent model degradation leads to systematic errors before detection |
| **Risk Level** | 🟠 High (16) |
| **Current Controls** | None |
| **Primary Mitigation** | Deploy automated weekly drift monitoring using PSI and KS tests on top input features |
| **Secondary Mitigation** | Set alert thresholds that trigger governance review when PSI > 0.2 or KS statistic exceeds tolerance |
| **Target Date** | 30–60 days |
| **Residual Risk** | 🟢 Low — automated monitoring addresses root cause |
| **Status** | 🔴 Open |

---

### R-05 — Excess PII in Model Inputs

| Field | Detail |
|-------|--------|
| **Risk ID** | R-05 |
| **Risk Description** | ClaimSense ingests more PII than necessary for its decision function — violating data minimisation principles |
| **Risk Category** | Data |
| **Risk Owner** | Compliance Officer |
| **Likelihood** | 3 — Confirmed by data pipeline review |
| **Impact** | 4 — Regulatory exposure under data protection laws; breach risk |
| **Risk Level** | 🟠 High (12) |
| **Current Controls** | None |
| **Primary Mitigation** | Conduct data necessity audit — document which fields are strictly required for approve/reject decision |
| **Secondary Mitigation** | Mask or exclude unnecessary PII fields (full address, medical details) from model inputs |
| **Target Date** | 45–60 days |
| **Residual Risk** | 🟢 Low — technical implementation is straightforward |
| **Status** | 🔴 Open |

---

### R-06 — Demographic Bias in Live Outputs

| Field | Detail |
|-------|--------|
| **Risk ID** | R-06 |
| **Risk Description** | Live output analysis shows statistically significant lower approval rates for Tier-3 city claimants (−13pp) and policyholders over 60 (−18pp) |
| **Risk Category** | Model |
| **Risk Owner** | Chief Risk Officer |
| **Likelihood** | 5 — Confirmed in 4-month output data |
| **Impact** | 4 — Active discriminatory harm to policyholders; regulatory investigation risk |
| **Risk Level** | 🔴 Critical (20) |
| **Current Controls** | None |
| **Primary Mitigation** | Immediately suspend fully automated rejection for identified segments; route to human review |
| **Secondary Mitigation** | Implement fairness metrics monitoring (Equalized Odds, Demographic Parity) as ongoing control |
| **Target Date** | Immediate suspension: within 7 days | Fairness metrics: 90 days |
| **Residual Risk** | 🟡 Medium — until retraining with debiased data is complete |
| **Status** | 🔴 Open — Escalated to CRO |

---

### R-07 — Confidence Threshold Miscalibration

| Field | Detail |
|-------|--------|
| **Risk ID** | R-07 |
| **Risk Description** | Fixed 0.72 threshold calibrated on balanced test data does not reflect live claims distribution (68% approvable); estimated 200–300 incorrect rejections/month |
| **Risk Category** | Model |
| **Risk Owner** | Data Science Lead |
| **Likelihood** | 3 — Confirmed by distribution analysis |
| **Impact** | 4 — Ongoing wrongful rejections causing policyholder harm |
| **Risk Level** | 🟠 High (12) |
| **Current Controls** | None |
| **Primary Mitigation** | Recalibrate confidence threshold using live claims distribution data |
| **Secondary Mitigation** | Implement dynamic threshold review on a quarterly basis as distribution evolves |
| **Target Date** | 30–45 days |
| **Residual Risk** | 🟢 Low — recalibration is a standard model maintenance activity |
| **Status** | 🔴 Open |

---

### R-08 — No Human Override Protocol

| Field | Detail |
|-------|--------|
| **Risk ID** | R-08 |
| **Risk Description** | No formal, tracked, or reported process for claims operations to override a ClaimSense decision; override patterns are invisible to governance |
| **Risk Category** | Operational |
| **Risk Owner** | Claims Operations Head |
| **Likelihood** | 4 — Override capability exists but is entirely ungoverned |
| **Impact** | 4 — No feedback loop; no visibility into model-human disagreements; governance blind spot |
| **Risk Level** | 🟠 High (16) |
| **Current Controls** | Ad hoc overrides (untracked) |
| **Primary Mitigation** | Define, document, and communicate formal override protocol with authorisation levels and logging requirements |
| **Secondary Mitigation** | Build override dashboard in claims management system; include override rate in monthly governance reporting |
| **Target Date** | Protocol: 30 days | Dashboard: 60 days |
| **Residual Risk** | 🟢 Low |
| **Status** | 🔴 Open |

---

### R-09 — No Incident Response Plan

| Field | Detail |
|-------|--------|
| **Risk ID** | R-09 |
| **Risk Description** | No documented AI Incident Response Plan for ClaimSense — no defined triggers, escalation path, containment steps, or rollback procedure |
| **Risk Category** | Operational |
| **Risk Owner** | Chief Risk Officer |
| **Likelihood** | 3 — Incidents are inevitable at scale; current response would be reactive and uncoordinated |
| **Impact** | 5 — A systematic failure without a response plan could affect thousands of claims before detection |
| **Risk Level** | 🟠 High (15) |
| **Current Controls** | None |
| **Primary Mitigation** | Develop documented AI Incident Response Plan covering: triggers, detection, escalation, containment, rollback, and post-incident review |
| **Secondary Mitigation** | Conduct annual incident simulation exercise to test response readiness |
| **Target Date** | 45–60 days |
| **Residual Risk** | 🟡 Medium — plan reduces impact; residual risk from execution quality |
| **Status** | 🔴 Open |

---

### R-10 — Third-Party Data Dependency

| Field | Detail |
|-------|--------|
| **Risk ID** | R-10 |
| **Risk Description** | ClaimSense ingests vehicle damage data from a third-party inspection vendor with no data quality SLA or validation at ingestion |
| **Risk Category** | Operational |
| **Risk Owner** | Claims Operations Head |
| **Likelihood** | 3 |
| **Impact** | 3 — Inaccurate vendor data directly influences model outputs |
| **Risk Level** | 🟡 Medium (9) |
| **Current Controls** | None |
| **Primary Mitigation** | Establish formal data quality SLA with vendor covering completeness, accuracy, and latency standards |
| **Secondary Mitigation** | Implement automated data validation at ingestion point; reject or flag non-compliant feeds before reaching model |
| **Target Date** | 60–90 days |
| **Residual Risk** | 🟢 Low |
| **Status** | 🔴 Open |

---

### R-11 — No Policyholder AI Transparency

| Field | Detail |
|-------|--------|
| **Risk ID** | R-11 |
| **Risk Description** | Policyholders are not informed that AI assessed their claim, what data was used, or that they can request human review |
| **Risk Category** | Ethics |
| **Risk Owner** | Compliance Officer |
| **Likelihood** | 4 — Confirmed absent in all current claim communications |
| **Impact** | 4 — Regulatory non-compliance; policyholder rights violation; reputational risk |
| **Risk Level** | 🟠 High (16) |
| **Current Controls** | None |
| **Primary Mitigation** | Draft and publish AI Decision Notice in all claim outcome communications |
| **Secondary Mitigation** | Update policy T&Cs to include right-to-human-review clause; establish complaint mechanism |
| **Target Date** | Notice draft: 30 days | Published: 45 days |
| **Residual Risk** | 🟢 Low — standard transparency measure |
| **Status** | 🔴 Open |

---

### R-12 — Diffuse Accountability — No AI Owner

| Field | Detail |
|-------|--------|
| **Risk ID** | R-12 |
| **Risk Description** | Accountability for ClaimSense governance is spread across data science, claims operations, and compliance with no designated AI Accountability Owner |
| **Risk Category** | Governance |
| **Risk Owner** | Chief Risk Officer |
| **Likelihood** | 3 |
| **Impact** | 3 — Governance decisions are delayed; no single point of escalation; audit readiness is low |
| **Risk Level** | 🟡 Medium (9) |
| **Current Controls** | None |
| **Primary Mitigation** | Appoint designated AI Accountability Owner for ClaimSense |
| **Secondary Mitigation** | Define RACI matrix covering model ownership, monitoring, escalation, and regulatory reporting |
| **Target Date** | 30 days |
| **Residual Risk** | 🟢 Low |
| **Status** | 🔴 Open |

---

## Register Summary

| Level | Count | Risk IDs |
|-------|-------|----------|
| 🔴 Critical | 4 | R-01, R-02, R-03, R-06 |
| 🟠 High | 5 | R-04, R-05, R-07, R-08, R-09, R-11 |
| 🟡 Medium | 2 | R-10, R-12 |
| 🟢 Low | 0 | — |
| **Total** | **12** | |

---

## Review Log

| Review Date | Reviewer | Changes Made |
|-------------|----------|-------------|
| May 2026 | Yatiraj Poojari | Initial register created — baseline assessment |
| (Next) | AI Accountability Owner | 30-day progress review |

---

*Prepared by Yatiraj Poojari | IAPP AI Governance Professional (AIGP) | Portfolio Case Study*
*This register should be reviewed monthly by the designated AI Accountability Owner and presented to the CRO quarterly.*
