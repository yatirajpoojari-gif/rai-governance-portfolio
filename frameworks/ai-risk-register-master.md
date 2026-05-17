# AI Risk Register — Master Template
**Prepared by:** Yatiraj Poojari | IAPP AI Governance Professional (AIGP)
**Template Version:** 1.0

> **How to use:** Copy this template for each AI system you are governing. Add risks using the individual risk card format below. Update the summary table and review log at each governance review.

---

## Scoring Methodology

| Score | Likelihood | Impact |
|-------|-----------|--------|
| 5 | Almost Certain | Catastrophic — regulatory breach, major financial/reputational harm |
| 4 | Likely | Major — significant operational disruption or user harm |
| 3 | Possible | Moderate — contained impact, manageable remediation |
| 2 | Unlikely | Minor — limited impact, easy to recover |
| 1 | Rare | Negligible — minimal impact |

**Risk Level = Likelihood × Impact Score**

| Level | Score | Action Requirement |
|-------|-------|--------------------|
| 🔴 Critical | 20–25 | Escalate to senior leadership within 24 hours; immediate action plan |
| 🟠 High | 12–19 | Action within 90 days; assign named owner and milestone |
| 🟡 Medium | 6–11 | Action within 180 days; include in governance roadmap |
| 🟢 Low | 1–5 | Monitor; review at quarterly governance meeting |

---

## Risk Categories

Use one of the following categories for each risk:

| Category | Description |
|----------|-------------|
| **Governance** | Accountability gaps, policy absence, oversight failures |
| **Data** | Training data quality, bias, drift, PII, provenance |
| **Model** | Bias in outputs, explainability, threshold calibration, robustness |
| **Operational** | Override protocols, incident response, vendor dependencies, logging |
| **Ethics** | Transparency, fairness, user rights, vulnerable population impacts |
| **Regulatory** | Compliance with applicable AI laws and sector regulations |

---

## Individual Risk Card Template

Copy and fill for each risk identified:

```
### R-[XX] — [Risk Name]

| Field | Detail |
|-------|--------|
| **Risk ID** | R-[XX] |
| **Risk Description** | [Clear description of what the risk is] |
| **Risk Category** | [Governance / Data / Model / Operational / Ethics / Regulatory] |
| **Risk Owner** | [Named individual or role] |
| **Likelihood** | [1–5] — [Rationale] |
| **Impact** | [1–5] — [Rationale] |
| **Risk Level** | [🔴 Critical / 🟠 High / 🟡 Medium / 🟢 Low] ([Score]) |
| **Current Controls** | [What controls exist today — or "None"] |
| **Primary Mitigation** | [The main action to reduce this risk] |
| **Secondary Mitigation** | [Supporting action or ongoing control] |
| **Target Date** | [When mitigation will be complete] |
| **Residual Risk** | [Expected risk level after mitigation] |
| **Status** | [🔴 Open / 🟡 In Progress / 🟢 Closed] |
```

---

## Risk Summary Table

Update this table at each governance review:

| Risk ID | Risk Description | Category | L | I | Level | Owner | Target Date | Status |
|---------|-----------------|----------|---|---|-------|-------|------------|--------|
| R-01 | | | | | | | | |
| R-02 | | | | | | | | |
| R-03 | | | | | | | | |
| R-04 | | | | | | | | |
| R-05 | | | | | | | | |

**L** = Likelihood (1–5) | **I** = Impact (1–5)

---

## Risk Heat Map

Plot risks by Likelihood (Y-axis) and Impact (X-axis):

```
  5 |  |  |  |  |  |
  4 |  |  |  |  |  |
  3 |  |  |  |  |  |
  2 |  |  |  |  |  |
  1 |  |  |  |  |  |
     1  2  3  4  5
     ←  Impact  →

Fill in Risk IDs at their coordinates.
🟢 Bottom-left = Low | 🟡 Middle = Medium | 🟠 Upper-middle = High | 🔴 Top-right = Critical
```

---

## Risk Appetite Statement

Define your organisation's risk appetite before completing the register:

> *"[Organisation name] has a [Low / Medium / High] appetite for AI-related risk. We will not accept any AI system deployment where Critical risks have not been identified and a remediation plan approved. We accept Medium risks as part of normal AI operations, provided they are monitored and have a defined remediation timeline."*

---

## Register Governance

| Governance Activity | Frequency | Owner |
|--------------------|-----------|-------|
| Risk register review and update | Monthly | AI Accountability Owner |
| Risk level re-scoring | Quarterly | AI Accountability Owner + Risk Team |
| New risk identification | Ongoing (at each governance review) | All governance stakeholders |
| Full register audit | Annual | Compliance Officer |
| Closed risk archival | As closed | AI Accountability Owner |

---

## Review Log

| Review Date | Reviewer | Risks Added | Risks Closed | Material Changes |
|-------------|----------|-------------|--------------|-----------------|
| | | | | |

---

*Template by Yatiraj Poojari | IAPP AI Governance Professional (AIGP)*
*Adapt for your organisation. This template is informed by NIST AI RMF, ISO 42001:2023, and IAPP AIGP framework.*
