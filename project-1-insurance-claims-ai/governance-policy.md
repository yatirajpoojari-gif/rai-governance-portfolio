# AI Governance Policy — ClaimSense ML System
**Meridian Insurance Ltd | Version 1.0 | May 2026**
**Policy Owner:** Chief Risk Officer | **Review Frequency:** Annual (or after material system change)

---

## 1. Purpose

This policy establishes the governance structure, accountability framework, and operating standards for **ClaimSense** — Meridian Insurance Ltd's AI-powered motor claims automation system. It is designed to ensure ClaimSense operates safely, fairly, transparently, and in alignment with regulatory expectations and the organisation's risk appetite.

---

## 2. Scope

This policy applies to:
- All decisions made by or with the assistance of ClaimSense
- All teams involved in the development, operation, monitoring, and oversight of ClaimSense
- All third-party vendors whose data or services are consumed by ClaimSense

---

## 3. Governing Principles

Meridian Insurance Ltd's use of AI in claims automation is governed by the following Responsible AI principles:

| Principle | What It Means for ClaimSense |
|-----------|------------------------------|
| **Fairness** | ClaimSense must not produce systematically different outcomes for policyholders based on age, geography, gender, or other protected characteristics |
| **Transparency** | Policyholders must be informed that AI assessed their claim and must be given a plain-language explanation of the decision |
| **Accountability** | A named individual (the AI Accountability Owner) is responsible for ClaimSense governance at all times |
| **Human Oversight** | A human must be able to review, override, and correct any ClaimSense decision |
| **Data Integrity** | Only data that is accurate, representative, and necessary for the decision is used by ClaimSense |
| **Safety** | ClaimSense must not cause harm to policyholders through wrongful rejection, discriminatory outcomes, or privacy violations |

---

## 4. Accountability Structure (RACI)

| Activity | AI Accountability Owner (CRO Delegate) | Data Science Lead | Claims Operations Head | Compliance Officer |
|----------|---------------------------------------|-------------------|----------------------|-------------------|
| Model performance monitoring | A | R | C | I |
| Fairness metrics review | A | R | I | C |
| Override protocol management | I | I | R | A |
| Incident response — activation | A | C | R | C |
| Regulatory reporting | I | I | I | R/A |
| Annual RAI reassessment | A | R | C | C |
| Training data governance | A | R | I | C |
| Policyholder transparency | C | I | I | R/A |
| Vendor data quality | I | C | R | A |

**R** = Responsible | **A** = Accountable | **C** = Consulted | **I** = Informed

---

## 5. Governance Operating Model

### 5.1 AI Accountability Owner
- Designated by the CRO from within the Risk or Compliance function
- Single point of accountability for all ClaimSense governance activities
- Chairs the monthly ClaimSense Governance Review
- Escalation point for all ClaimSense incidents and risk threshold breaches

### 5.2 Monthly Governance Review
Agenda:
1. Model performance metrics (accuracy, precision, recall — vs. prior month)
2. Fairness metrics (approval rates by demographic segment — vs. thresholds)
3. Drift monitoring status (PSI/KS results — any alerts triggered)
4. Override log review (volume, patterns, reason codes)
5. Open risk register items — status update
6. Any policyholder complaints related to AI decisions

Attendees: AI Accountability Owner, Data Science Lead, Claims Operations Head, Compliance Officer

### 5.3 Quarterly CRO Report
A summary governance report is presented to the CRO each quarter covering:
- Model health scorecard
- Fairness metrics trend
- Open risks and remediation status
- Override patterns and emerging concerns
- Regulatory developments relevant to ClaimSense

### 5.4 Annual RAI Reassessment
A full RAI assessment of ClaimSense is conducted annually, or following any material change to:
- The model (retraining, threshold changes, feature additions)
- The use case (new claim types, new geographies, changed decision authority)
- The regulatory environment (new IRDAI guidelines, AI governance regulations)

---

## 6. Human Oversight Protocol

### 6.1 Override Authorisation
| Override Scenario | Authorised By | Required Documentation |
|------------------|---------------|----------------------|
| Individual claim override — low value | Senior Claims Officer | Override reason code in claims system |
| Segment-level pause (e.g., suspend auto-reject for a demographic) | AI Accountability Owner | Written approval + governance log entry |
| Full system pause — all automated decisions | CRO | Incident declaration + governance log |

### 6.2 Override Logging
All overrides must be logged in the ClaimSense Override Register with:
- Claim ID and decision being overridden
- Reason code (bias concern / data quality / customer complaint / other)
- Override decision and outcome
- Name and role of person authorising the override

Override data is reviewed monthly in the Governance Review and used as a feedback signal for model improvement.

---

## 7. Policyholder Rights

### 7.1 AI Disclosure
All claim outcome communications must include the following statement:

> *"Your claim was assessed using an automated AI system as part of our claims processing. The AI evaluated [key factors including vehicle data, incident details, and claim history]. If you have questions about this decision or would like it reviewed by a human assessor, please contact us at [contact details]."*

### 7.2 Right to Human Review
Any policyholder who receives an automated claim decision has the right to request a human review within **30 days** of receiving the decision. Human review requests must be:
- Acknowledged within 2 business days
- Completed within 10 business days
- Communicated to the policyholder with a plain-language explanation of the human review outcome

### 7.3 Complaint Mechanism
Policyholders who believe an AI decision was unfair or incorrect can raise a formal complaint through Meridian's existing complaints process. AI-related complaints are tagged and reviewed monthly by the Compliance Officer for systemic patterns.

---

## 8. Model Risk Management Standards

### 8.1 Fairness Thresholds
The following fairness metrics are monitored monthly. If any metric breaches the defined threshold, the AI Accountability Owner must be notified within 24 hours:

| Metric | Calculation | Alert Threshold |
|--------|-------------|-----------------|
| Demographic Parity | Approval rate difference between demographic groups | > 10 percentage points |
| Equalized Odds | Difference in True Positive Rate across groups | > 8 percentage points |
| Predictive Parity | Difference in Positive Predictive Value across groups | > 8 percentage points |

### 8.2 Data Drift Thresholds
| Metric | Alert Threshold | Action |
|--------|----------------|--------|
| Population Stability Index (PSI) | > 0.2 on any key feature | Governance review within 5 days |
| KS Statistic — score distribution | Significant shift (p < 0.05) | Model performance audit within 10 days |

### 8.3 Model Retraining Standards
ClaimSense must be retrained when any of the following occur:
- Bias audit identifies systemic demographic disparities
- Data drift alerts persist for more than 4 consecutive weeks
- Model accuracy falls more than 5 percentage points below baseline
- A material change in claims patterns is identified

All retraining must include:
- Documented training data provenance and demographic distribution
- Pre-deployment bias audit of training data
- Fairness metrics validation on the new model before deployment
- Sign-off from the AI Accountability Owner

---

## 9. Incident Response Summary

| Incident Level | Definition | Response Time | Escalation |
|---------------|------------|---------------|------------|
| Level 1 — Minor | Individual claim anomaly | 24 hours | Claims Operations Head |
| Level 2 — Significant | Batch of incorrect decisions (< 1% of volume) | 4 hours | AI Accountability Owner |
| Level 3 — Critical | Systematic failure or confirmed bias pattern | 1 hour | CRO + Compliance Officer |
| Level 4 — Crisis | Regulatory breach or media attention | Immediate | CRO + Legal + CEO |

Full incident response procedures are documented in the ClaimSense AI Incident Response Plan (separate document).

---

## 10. Policy Compliance

Non-compliance with this policy — including failure to log overrides, failure to disclose AI involvement to policyholders, or failure to escalate threshold breaches — must be reported to the Compliance Officer and will be treated as a governance incident requiring formal remediation.

---

## 11. Document Control

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | May 2026 | Yatiraj Poojari | Initial policy established following RAI assessment |

---

*Prepared by Yatiraj Poojari | IAPP AI Governance Professional (AIGP) | Portfolio Case Study*
*This policy is a fictional governance document created for portfolio demonstration purposes.*
