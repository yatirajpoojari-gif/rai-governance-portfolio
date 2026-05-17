# Risk Register — LumeAI Personalisation Engine
**LumeCart India | D2C E-Commerce Consumer Personalisation**
**Register Version:** 1.0 | **Owner:** AI Ethics Lead (to be appointed) | **Review Frequency:** Monthly

---

## Scoring Methodology

| Score | Likelihood | Impact |
|-------|-----------|--------|
| 5 | Almost Certain — will very likely occur | Catastrophic — regulatory enforcement, mass consumer harm, or major reputational damage |
| 4 | Likely — high probability of occurring | Major — significant regulatory finding, consumer harm, or reputational harm |
| 3 | Possible — may occur under certain conditions | Moderate — contained impact, manageable remediation |
| 2 | Unlikely — low probability | Minor — limited impact, recoverable |
| 1 | Rare — only in exceptional circumstances | Negligible — minimal impact |

**Risk Level = Likelihood × Impact**

| Risk Level | Score Range | Action Required |
|-----------|-------------|-----------------|
| 🔴 Critical | 20–25 | Immediate action — escalate to CPO and CEO within 24 hours |
| 🟠 High | 12–19 | Action within 90 days — assign owner and milestone |
| 🟡 Medium | 6–11 | Action within 180 days — include in governance roadmap |
| 🟢 Low | 1–5 | Monitor — review at quarterly governance meeting |

---

## Risk Summary Table

| ID | Risk | Category | L | I | Score | Level |
|----|------|----------|---|---|-------|-------|
| R-01 | Training data used beyond original consent scope | Privacy | 5 | 5 | 25 | 🔴 Critical |
| R-02 | Dynamic pricing discriminates against lower-income user segments | Bias / Fairness | 5 | 5 | 25 | 🔴 Critical |
| R-03 | Fabricated urgency signals and fake countdown timers | Dark Patterns | 5 | 4 | 20 | 🔴 Critical |
| R-04 | No AI transparency — users unaware of personalised pricing and recommendations | Transparency | 5 | 4 | 20 | 🔴 Critical |
| R-05 | DPDP Act 2023 complaint — active regulatory investigation | Regulatory | 5 | 4 | 20 | 🟠 High |
| R-06 | Cross-app data collection via undisclosed third-party SDKs | Privacy | 4 | 5 | 20 | 🟠 High |
| R-07 | Children's data processed without parental consent | Privacy / Legal | 4 | 5 | 20 | 🟠 High |
| R-08 | Data retention exceeded — 4-year backlog outside stated policy | Privacy | 5 | 3 | 15 | 🟠 High |
| R-09 | No Data Principal rights mechanism (access, correction, erasure) | Privacy / Legal | 5 | 3 | 15 | 🟠 High |
| R-10 | Inflated social proof signals — "847 people viewing this" | Dark Patterns | 5 | 3 | 15 | 🟠 High |
| R-11 | Drip pricing — fees not disclosed upfront | Dark Patterns | 4 | 3 | 12 | 🟠 High |
| R-12 | No AI ethics governance structure or oversight | Governance | 5 | 4 | 20 | 🟠 High |
| R-13 | Confirmshaming opt-out language — Consumer Protection Act exposure | Dark Patterns | 3 | 3 | 9 | 🟡 Medium |
| R-14 | No human review pathway for AI-driven decisions | Transparency | 3 | 3 | 9 | 🟡 Medium |
| R-15 | Recommendation engine amplifies socioeconomic stratification | Bias / Fairness | 3 | 3 | 9 | 🟡 Medium |

---

## Individual Risk Cards

---

### R-01 — Training Data Used Beyond Original Consent Scope

| Field | Detail |
|-------|--------|
| **Risk ID** | R-01 |
| **Risk Description** | LumeAI's personalisation model uses data collected for order fulfilment (delivery address, payment method, purchase history) to infer income level and price sensitivity — a materially different purpose not covered by original user consent |
| **Risk Category** | Privacy |
| **Risk Owner** | Data Protection Officer |
| **Likelihood** | 5 — Already occurring across all 8 million user profiles |
| **Impact** | 5 — DPDP Act 2023 enforcement action; potential Data Protection Board penalty; user trust collapse |
| **Risk Level** | 🔴 Critical (25) |
| **Current Controls** | None — no purpose limitation controls exist |
| **Primary Mitigation** | Rebuild consent architecture — implement granular, purpose-specific consent; obtain fresh consent for AI personalisation use cases |
| **Secondary Mitigation** | Conduct data minimisation audit; delete or anonymise data used outside consent scope |
| **Target Date** | Immediate — consent architecture rebuild within 60 days |
| **Residual Risk** | 🟡 Medium — historical consent breach cannot be fully remediated; legal exposure remains for past processing |
| **Status** | 🔴 Open |

---

### R-02 — Dynamic Pricing Discriminates Against Lower-Income User Segments

| Field | Detail |
|-------|--------|
| **Risk ID** | R-02 |
| **Risk Description** | LumeAI's dynamic pricing algorithm charges Tier-2/3 city users 8–23% more than Tier-1 users for identical products. Users on low-cost Android devices receive fewer discount offers. High purchase intent users are shown higher prices than first-time viewers. |
| **Risk Category** | Algorithmic Bias / Fairness |
| **Risk Owner** | AI Ethics Lead (once appointed) + Chief Product Officer |
| **Likelihood** | 5 — Confirmed through internal data analysis; occurring on every transaction |
| **Impact** | 5 — Consumer Protection Act 2019 violation; mass consumer harm; regulatory and reputational consequences |
| **Risk Level** | 🔴 Critical (25) |
| **Current Controls** | None — no fairness monitoring exists |
| **Primary Mitigation** | Conduct immediate demographic bias audit; implement fairness constraints in pricing model; define maximum acceptable price variance thresholds |
| **Secondary Mitigation** | Assess consumer redress for users systematically overcharged; publish pricing fairness commitment |
| **Target Date** | Bias audit within 60 days; fairness constraints implemented within 120 days |
| **Residual Risk** | 🟡 Medium — some personalisation revenue impact from fairness constraints; ongoing monitoring required |
| **Status** | 🔴 Open |

---

### R-03 — Fabricated Urgency Signals and Fake Countdown Timers

| Field | Detail |
|-------|--------|
| **Risk ID** | R-03 |
| **Risk Description** | The nudge engine generates "Only X left in stock!" signals independently of actual inventory in 34% of cases. Countdown timers reset on page refresh. Both signals are personalised to exploit high-intent users. |
| **Risk Category** | Dark Patterns / Consumer Manipulation |
| **Risk Owner** | Chief Product Officer + Legal Counsel |
| **Likelihood** | 5 — Deployed in production and active on all high-intent user sessions |
| **Impact** | 4 — Consumer Protection Act 2019 violation (misleading claims); regulatory fine; reputational harm |
| **Risk Level** | 🔴 Critical (20) |
| **Current Controls** | None — nudge engine operates without accuracy checks |
| **Primary Mitigation** | Immediately disable all fabricated urgency signals and fake countdown timers; replace with accuracy-only signals tied to real inventory and real deadlines |
| **Secondary Mitigation** | Implement ethics review gate for all nudge features before deployment |
| **Target Date** | Immediate — within 7 days |
| **Residual Risk** | 🟢 Low — once fabricated signals are removed and accuracy controls are in place |
| **Status** | 🔴 Open |

---

### R-04 — No AI Transparency — Users Unaware of Personalised Pricing and Recommendations

| Field | Detail |
|-------|--------|
| **Risk ID** | R-04 |
| **Risk Description** | LumeCart does not disclose that an AI system is influencing product recommendations, prices, and nudges. Users have no way to understand why they see the prices or recommendations they do, and no mechanism to opt out. |
| **Risk Category** | Transparency / Explainability |
| **Risk Owner** | Chief Product Officer + DPO |
| **Likelihood** | 5 — Absence of disclosure affects all 8 million users on every session |
| **Impact** | 4 — DPDP Act transparency obligations breached; EU AI Act reference standard; consumer trust risk |
| **Risk Level** | 🔴 Critical (20) |
| **Current Controls** | None |
| **Primary Mitigation** | Implement AI disclosure notices across all LumeAI-driven features; provide personalised price explanation; implement AI opt-out controls |
| **Secondary Mitigation** | Publish Algorithmic Accountability Report annually; implement human review pathway |
| **Target Date** | AI disclosure notices within 60 days; opt-out controls within 120 days |
| **Residual Risk** | 🟢 Low — once disclosure and opt-out controls are implemented |
| **Status** | 🔴 Open |

---

### R-05 — DPDP Act 2023 Complaint — Active Regulatory Investigation

| Field | Detail |
|-------|--------|
| **Risk ID** | R-05 |
| **Risk Description** | A consumer rights complaint has been filed with India's Data Protection Board under DPDP Act 2023, alleging data use beyond consent scope. The investigation is pending. Multiple DPDP Act obligations are currently unmet. |
| **Risk Category** | Regulatory |
| **Risk Owner** | Data Protection Officer + Legal Counsel |
| **Likelihood** | 5 — Complaint is already filed; investigation is active |
| **Impact** | 4 — DPDP Act penalties up to ₹250 crore per violation; mandatory remediation orders; reputational harm |
| **Risk Level** | 🟠 High (20) |
| **Current Controls** | Legal team engaged — no substantive remediation in place |
| **Primary Mitigation** | Engage specialist privacy counsel; develop DPDP Act compliance roadmap; proactively remediate consent architecture before Board ruling |
| **Secondary Mitigation** | Prepare regulatory response demonstrating good-faith remediation steps; appoint DPO with appropriate authority |
| **Target Date** | Regulatory response within 30 days; compliance roadmap within 45 days |
| **Residual Risk** | 🟡 Medium — historical non-compliance creates residual penalty risk regardless of remediation |
| **Status** | 🔴 Open |

---

### R-06 — Cross-App Data Collection via Undisclosed Third-Party SDKs

| Field | Detail |
|-------|--------|
| **Risk ID** | R-06 |
| **Risk Description** | LumeCart's mobile app contains 14 third-party SDKs that collect behavioural data from other apps on the user's device. This data feeds LumeAI's personalisation model. Users were never informed of this data collection. |
| **Risk Category** | Privacy |
| **Risk Owner** | Data Protection Officer + Engineering Lead |
| **Likelihood** | 4 — Ongoing; occurs on every app session for all users |
| **Impact** | 5 — DPDP Act consent violation; potential class action; severe reputational harm if publicised |
| **Risk Level** | 🟠 High (20) |
| **Current Controls** | None |
| **Primary Mitigation** | Immediately suspend cross-app data collection; audit all 14 SDKs for data collection scope; terminate SDKs that exceed necessity |
| **Secondary Mitigation** | Disclose third-party data sharing in privacy policy; obtain explicit consent for any resumed cross-app data collection |
| **Target Date** | Suspension within 7 days; audit within 30 days |
| **Residual Risk** | 🟡 Medium — data already collected from cross-app sources creates historical exposure |
| **Status** | 🔴 Open |

---

### R-07 — Children's Data Processed Without Parental Consent

| Field | Detail |
|-------|--------|
| **Risk ID** | R-07 |
| **Risk Description** | LumeCart has no age verification mechanism. The DPDP Act 2023 requires verifiable parental consent for processing personal data of users under 18. LumeCart likely holds data on underage users processed without such consent. |
| **Risk Category** | Privacy / Legal |
| **Risk Owner** | Data Protection Officer + Legal Counsel |
| **Likelihood** | 4 — High probability given no age verification exists across 8 million users |
| **Impact** | 5 — DPDP Act Section 9 violation; severe regulatory penalty; reputational harm |
| **Risk Level** | 🟠 High (20) |
| **Current Controls** | None |
| **Primary Mitigation** | Implement age verification mechanism; identify and isolate data of users under 18; obtain verifiable parental consent or delete underage user data |
| **Secondary Mitigation** | Restrict LumeAI personalisation features for users under 18 pending parental consent |
| **Target Date** | Age verification implementation within 90 days |
| **Residual Risk** | 🟡 Medium — historical data of underage users without consent creates residual exposure |
| **Status** | 🔴 Open |

---

### R-08 to R-15 — Summary Cards

| ID | Risk | Mitigation Summary | Target | Status |
|----|------|--------------------|--------|--------|
| R-08 | Data retention exceeded — 4-year backlog | Implement automated deletion at policy retention limits; purge backlog outside 12-month window | 90 days | 🔴 Open |
| R-09 | No Data Principal rights portal | Build functional access, correction, erasure portal per DPDP Act timelines | 60 days | 🔴 Open |
| R-10 | Inflated social proof signals | Replace with accurate real-time viewer counts; implement accuracy audit for all social proof signals | 30 days | 🔴 Open |
| R-11 | Drip pricing — fees not disclosed upfront | Display full price including all fees on product page before checkout | 30 days | 🔴 Open |
| R-12 | No AI ethics governance structure | Appoint AI Ethics Lead; establish AI Ethics Committee; mandate ethics review gate for all AI features | 30 days | 🔴 Open |
| R-13 | Confirmshaming opt-out language | Audit all consent and opt-out UI; replace with neutral, respectful language | 45 days | 🟠 In Progress |
| R-14 | No human review pathway | Establish consumer dispute pathway for AI-driven decisions; define SLA for human review | 120 days | 🔴 Open |
| R-15 | Recommendation engine amplifies socioeconomic stratification | Apply diversity constraints to recommendation model; test for socioeconomic bias in outputs | 180 days | 🔴 Open |

---

## Governance Log

| Review Date | Reviewer | Changes Made | Next Review |
|-------------|----------|--------------|-------------|
| May 2026 | Yatiraj Poojari | Initial register created | June 2026 |

---

*Scenario and company are fictional. Methodology reflects IAPP AIGP framework and globally recognised RAI standards.*
