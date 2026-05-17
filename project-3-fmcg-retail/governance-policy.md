# AI Ethics Governance Policy — LumeAI Personalisation Engine
**LumeCart India | D2C E-Commerce Consumer Personalisation**
**Policy Version:** 1.0 (Draft for adoption) | **Prepared by:** Yatiraj Poojari | **Status:** Pending Approval

---

## 1. Purpose and Scope

### 1.1 Purpose

This policy establishes the AI ethics governance framework, accountability structure, and operating standards for the responsible development and deployment of LumeAI and all future AI systems at LumeCart India. It defines roles, responsibilities, ethical guardrails, and oversight mechanisms to ensure LumeCart's AI systems are fair, transparent, privacy-respecting, and compliant with applicable laws.

This policy is adopted in response to findings from the May 2026 RAI ethics assessment and is a foundational document for LumeCart's response to the active DPDP Act 2023 regulatory complaint.

### 1.2 Scope

This policy applies to:
- All AI and algorithmic systems deployed by LumeCart India, including LumeAI (recommendations, dynamic pricing, nudge engine)
- All staff involved in designing, building, deploying, or operating AI systems
- All third-party vendors and SDK providers whose tools feed data into or receive data from LumeCart AI systems

### 1.3 Regulatory Context

This policy is designed in alignment with:
- **DPDP Act 2023** — India's Digital Personal Data Protection Act
- **Consumer Protection Act 2019** — including prohibition on unfair trade practices and dark patterns
- **BIS IS 17880** — India's national AI ethics standard
- **EU AI Act** (reference standard) — transparency and bias obligations
- **NIST AI Risk Management Framework** — GOVERN · MAP · MEASURE · MANAGE

---

## 2. AI Ethics Principles

LumeCart commits to the following AI ethics principles for all AI systems:

| Principle | Commitment |
|-----------|-----------|
| **Fairness** | LumeCart AI systems will not discriminate against users based on geography, income proxy, device type, age, or gender. Pricing and recommendation systems will be tested for demographic bias before deployment and monitored continuously. |
| **Transparency** | Users will be clearly informed when AI is influencing their experience. Personalised prices and recommendations will be explained. Users will have meaningful opt-out controls. |
| **Privacy** | Personal data will be collected only for stated purposes, with explicit consent. Data will be minimised, retained only as long as necessary, and never used beyond the scope of user consent. |
| **Honesty** | All urgency signals, social proof indicators, stock counts, and promotional claims must be accurate. Fabricated or algorithmically inflated signals are prohibited. |
| **Accountability** | Every AI system will have a named owner. AI decisions affecting users will be auditable. Users will have access to human review for disputed AI decisions. |
| **Consumer Protection** | LumeCart will not deploy dark patterns, drip pricing, confirmshaming, or any design intended to exploit cognitive biases to override informed user choice. |

---

## 3. Governance Structure

### 3.1 AI Ethics Committee

**Purpose:** Provide strategic oversight and policy approval for all AI ethics matters at LumeCart India.

**Membership:**

| Role | Member |
|------|--------|
| Chair | Chief Product Officer (CPO) |
| AI Ethics Lead | Designated AI Ethics Lead (to be appointed) |
| Data Protection Officer | DPO |
| Legal Representative | General Counsel |
| Engineering Representative | VP Engineering |
| Consumer Experience Representative | Head of Customer Experience |

**Meeting Cadence:** Monthly (weekly during first 90 days of this policy)

**Mandate:**
- Approve and review this policy annually
- Review all new AI feature proposals at the ethics gate
- Oversee the AI System Inventory and risk register
- Review consumer complaints related to AI behaviour
- Monitor regulatory developments (DPDP Act, Consumer Protection Act, BIS standards)

### 3.2 AI Ethics Lead

**Responsibilities:**
- Day-to-day management of AI ethics governance
- Maintain AI System Inventory and risk register
- Chair ethics review gate for all new AI and nudge features
- Coordinate bias audits and fairness monitoring
- Liaise with DPO on DPDP Act compliance
- Report to AI Ethics Committee monthly
- Manage the Algorithmic Accountability Report

### 3.3 Data Protection Officer (DPO)

**Responsibilities:**
- Manage DPDP Act 2023 compliance for all AI data processing
- Own consent architecture design and implementation
- Manage Data Principal rights portal
- Lead response to Data Protection Board complaint
- Conduct data minimisation and retention audits

### 3.4 RACI Matrix

| Activity | CPO | AI Ethics Lead | DPO | Legal | Engineering | Customer Experience |
|----------|-----|---------------|-----|-------|-------------|-------------------|
| Policy approval | A | R | C | C | I | I |
| AI System Inventory | I | A/R | C | I | C | I |
| Ethics gate review | A | R | C | C | C | I |
| Bias audit | A | R | C | I | C | I |
| Consent architecture | I | C | A/R | C | C | I |
| Data Principal rights | I | C | A/R | C | C | I |
| Dark pattern review | A | R | I | C | C | C |
| Consumer complaint (AI) | I | R | C | C | I | A |
| Regulatory response | A | C | R | R | I | I |
| Accountability report | A | R | C | C | I | I |

**Key:** R = Responsible · A = Accountable · C = Consulted · I = Informed

---

## 4. Permitted and Prohibited AI Practices

### 4.1 Permitted Personalisation Practices

| Practice | Permitted | Conditions |
|----------|-----------|-----------|
| Product recommendations based on purchase history | ✅ Yes | Must be disclosed as AI-driven; opt-out must be available |
| Personalised promotions and discounts | ✅ Yes | Must not result in demographic price discrimination; must disclose personalisation |
| Search result ranking personalisation | ✅ Yes | Must disclose AI ranking; option to view non-personalised results |
| Dynamic pricing based on supply/demand | ✅ Yes | Must be disclosed; must not discriminate by demographic proxy; full price shown upfront |
| Urgency signals based on real inventory | ✅ Yes | Must reflect actual stock levels accurately |
| Countdown timers for real promotions | ✅ Yes | Timer must reflect a real, fixed deadline that does not reset |

### 4.2 Prohibited AI Practices

| Prohibited Practice | Reason |
|-------------------|--------|
| Fabricated scarcity signals (stock count lower than actual inventory) | Consumer Protection Act 2019 — misleading claim |
| Fake countdown timers that reset on refresh | Consumer Protection Act 2019 — misleading claim |
| Inflated social proof figures (viewer counts, purchase counts) | Consumer Protection Act 2019 — misleading claim |
| Dynamic pricing that systematically charges higher prices to lower-income demographic proxies | Consumer Protection Act 2019 — unfair trade practice |
| Using data beyond the scope of user consent for personalisation | DPDP Act 2023 — purpose limitation |
| Collecting cross-app data without explicit disclosure and consent | DPDP Act 2023 — consent obligation |
| Processing personal data of users under 18 without verifiable parental consent | DPDP Act 2023 Section 9 |
| Confirmshaming opt-out language | Consumer Protection Act 2019 — dark pattern |
| Drip pricing — progressive disclosure of fees in checkout | Consumer Protection Act 2019 — dark pattern |
| Deploying AI features without ethics gate approval | Internal policy |

---

## 5. Ethics Review Gate

All new AI features, personalisation changes, nudge designs, and pricing algorithm updates must pass an ethics gate review before deployment.

### 5.1 Gate Criteria

The AI Ethics Lead assesses each proposal against the following criteria:

| Criterion | Question |
|-----------|---------|
| Fairness | Could this feature discriminate against any demographic group? Has bias testing been conducted? |
| Privacy | Does this feature require new data collection or new data use? Is it within consent scope? |
| Honesty | Does this feature present any signals, claims, or figures to users? Are they accurate? |
| Transparency | Will users know this feature is AI-driven? Is there an opt-out? |
| Manipulation | Does this feature exploit cognitive biases or emotional states to override informed user choice? |
| Legal | Does this feature comply with DPDP Act 2023 and Consumer Protection Act 2019? |

### 5.2 Gate Outcomes

| Outcome | Meaning |
|---------|---------|
| ✅ Approved | Feature may proceed to deployment |
| ⚠️ Approved with conditions | Feature may proceed subject to specific modifications or monitoring |
| 🔴 Rejected | Feature may not be deployed; must be redesigned and resubmitted |

### 5.3 Emergency Deployment

In urgent cases, a feature may deploy with temporary approval from the AI Ethics Lead, with full gate review completed within 5 business days. Emergency deployments are logged and reported to the AI Ethics Committee.

---

## 6. Consumer Rights Framework

### 6.1 AI Transparency Rights

Every LumeCart user has the right to:
- Know when an AI system is influencing their product recommendations, prices, or nudges
- Receive a plain-language explanation of why they are seeing a particular price or recommendation
- Opt out of AI-driven personalisation, dynamic pricing, and behavioural nudges
- Browse LumeCart in a non-personalised mode

### 6.2 Data Rights (DPDP Act 2023)

Every LumeCart user has the right to:
- Access the personal data LumeCart holds about them (within 72 hours of request)
- Correct inaccurate personal data
- Erase their personal data (subject to legal retention requirements)
- Withdraw consent for any specific purpose of data processing
- Nominate a representative to exercise their rights on their behalf

### 6.3 Human Review Right

Users who believe they have been treated unfairly by a LumeAI-driven decision have the right to:
- Request human review of that decision
- Receive a response within 10 business days
- Escalate to the AI Ethics Lead if unsatisfied with the initial response

### 6.4 Redress Mechanism

LumeCart will establish a consumer redress mechanism for users who have suffered demonstrable financial harm as a result of LumeAI's pricing bias. The scope and implementation of this mechanism will be defined in consultation with Legal and the AI Ethics Lead within 180 days of this policy adoption.

---

## 7. Fairness Monitoring

### 7.1 Bias Audit Schedule

| Audit | Frequency | Owner |
|-------|-----------|-------|
| Dynamic pricing demographic bias audit | Quarterly | AI Ethics Lead + Data Science |
| Recommendation engine socioeconomic bias test | Quarterly | AI Ethics Lead + Data Science |
| Nudge engine accuracy audit (stock counts, timers, social proof) | Monthly | Engineering + AI Ethics Lead |
| Full fairness assessment | Annual | AI Ethics Lead |

### 7.2 Fairness Thresholds

The following thresholds define acceptable performance. Breaches trigger escalation to the AI Ethics Committee:

| Metric | Maximum Acceptable Variance | Escalation Trigger |
|--------|----------------------------|-------------------|
| Price disparity by geography (Tier-1 vs Tier-2/3) | ≤ 5% for identical products | > 5% triggers immediate investigation |
| Price disparity by device type | ≤ 3% for identical products | > 3% triggers bias audit |
| Discount offer rate disparity by income proxy | ≤ 10% | > 10% triggers algorithm review |
| Stock count accuracy | ≥ 98% | < 98% triggers nudge engine audit |

---

## 8. Algorithmic Accountability Report

LumeCart will publish an annual **Algorithmic Accountability Report** covering:
- A plain-language description of how LumeAI works
- What data LumeAI uses and how consent is managed
- Fairness audit results and any bias findings
- Actions taken to remediate bias or privacy issues
- Consumer complaint statistics related to AI behaviour
- Changes made to LumeAI in the reporting period

The first report will be published within 12 months of this policy adoption.

---

## 9. Policy Governance

| Attribute | Detail |
|-----------|--------|
| Policy Owner | AI Ethics Lead |
| Approved By | Chief Product Officer |
| Approval Date | [To be completed on adoption] |
| Version | 1.0 |
| Review Frequency | Annual (six-monthly in Year 1) |
| Next Review Date | November 2026 |
| Distribution | All LumeCart staff; published on company intranet |

---

*This policy covers a fictional AI governance scenario designed to demonstrate RAI governance methodology. All frameworks and obligations referenced reflect globally recognised standards: DPDP Act 2023 · Consumer Protection Act 2019 · BIS IS 17880 · EU AI Act · NIST AI RMF.*
