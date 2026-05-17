# AI Governance Playbook — AskVantage LLM Customer Service Chatbot
**VantageOne Financial Services | Contact Centre AI Governance**
**Playbook Version:** 1.0 (Draft for adoption) | **Prepared by:** Yatiraj Poojari | **Status:** Pending Approval

---

## 1. Purpose and Scope

### 1.1 Purpose

This playbook establishes the AI governance framework, accountability structure, vendor oversight model, incident response capability, and human oversight architecture for the AskVantage LLM chatbot and all future AI systems deployed at VantageOne Financial Services. It is designed to bring VantageOne into alignment with FCA Consumer Duty obligations, NIST AI RMF controls, and EU AI Act requirements.

This playbook is adopted in response to findings from the May 2026 RAI assessment and is VantageOne's primary response to the governance gaps identified following three confirmed AskVantage hallucination incidents.

### 1.2 Scope

This playbook applies to:
- AskVantage LLM chatbot across all channels (web, mobile, telephone)
- All future AI systems deployed by VantageOne Financial Services
- All staff involved in operating, managing, or overseeing AI systems
- The LLM provider and all third-party AI vendors

### 1.3 Regulatory Context

| Framework | Obligation |
|-----------|-----------|
| FCA Consumer Duty (PS22/9) | Good outcomes · Fair value · Consumer understanding · Vulnerable customer support |
| FCA PRIN 12 | Act in customer best interests — AI must not cause foreseeable harm |
| EU AI Act | High-Risk AI obligations — transparency, human oversight, accuracy, robustness |
| NIST AI RMF | GOVERN · MAP · MEASURE · MANAGE controls |
| ISO 42001:2023 | AI management system — risk, accountability, continual improvement |
| UK GDPR | Data protection obligations for customer data processed by AI |

---

## 2. Governance Structure

### 2.1 AI Governance Committee

**Membership:**

| Role | Member |
|------|--------|
| Chair | Chief Risk Officer (CRO) |
| AI Accountability Owner | Designated AI Risk Lead (to be appointed) |
| Compliance Representative | Head of Compliance |
| Legal Representative | General Counsel |
| Technology Representative | Head of Digital |
| Contact Centre Representative | Head of Contact Centre |
| Customer Experience Representative | Customer Experience Director |

**Meeting Cadence:** Monthly (weekly during first 90 days)

**Mandate:**
- Approve this playbook and review annually
- Oversee AI System Inventory and risk register
- Review all AI incident reports
- Approve new AI system deployments
- Monitor FCA, EU AI Act, and NIST AI RMF regulatory developments

### 2.2 AI Accountability Owner

**Responsibilities:**
- Day-to-day AI governance management
- Maintain AI System Inventory and risk register
- Coordinate NIST AI RMF implementation
- Lead vendor governance framework
- Chair AI Incident Response process
- Report to AI Governance Committee monthly
- Manage FCA Consumer Duty AI alignment

### 2.3 RACI Matrix

| Activity | CRO | AI Accountability Owner | Compliance | Legal | Head of Digital | Head of Contact Centre |
|----------|-----|------------------------|-----------|-------|-----------------|----------------------|
| Playbook approval | A | R | C | C | I | I |
| New AI deployment approval | A | R | C | C | C | I |
| Risk register review | I | A/R | C | I | C | I |
| Vendor due diligence | I | A | C | R | C | I |
| Incident response (Severity 1/2) | A | R | R | C | C | C |
| Human escalation protocol | I | A | C | I | C | R |
| FCA notification assessment | A | C | R | R | I | I |
| Customer remediation | A | C | R | C | I | C |
| Staff AI training | I | A | C | I | C | R |
| Annual AI review | A | R | C | C | C | I |

**Key:** R = Responsible · A = Accountable · C = Consulted · I = Informed

---

## 3. AskVantage Operating Boundaries

### 3.1 Permitted Use Cases

| Use Case | Permitted | Conditions |
|----------|-----------|-----------|
| General account balance and transaction queries | ✅ Yes | Must be grounded in real-time verified account data; not LLM-generated |
| Product information — general descriptions | ✅ Yes | Must be grounded in verified, current product knowledge base |
| FAQs — non-financial, non-regulated topics | ✅ Yes | Low-risk information delivery |
| Appointment booking and callback requests | ✅ Yes | Administrative function — low AI risk |
| Directing customers to appropriate resources or teams | ✅ Yes | Signposting — not financial advice |

### 3.2 Prohibited Use Cases (pending RAG validation layer)

| Prohibited Use | Reason |
|---------------|--------|
| Providing specific interest rates, APRs, or product pricing | High hallucination risk — confirmed in INC-001 |
| Assessing or advising on loan eligibility | High hallucination risk — confirmed in INC-002; potential regulated advice |
| Providing regulatory information (FSCS limits, FCA rights, complaint rights) | High hallucination risk — confirmed in INC-003; regulatory accuracy required |
| Handling formal complaints end-to-end | FCA complaints handling rules require human involvement |
| Providing financial planning or investment guidance | Regulated activity — must not be delivered by AI without human oversight |
| Providing information to a customer who has indicated financial distress | FCA Consumer Duty vulnerable customer obligation |

### 3.3 Restoration of Prohibited Use Cases

Prohibited use cases may be restored following successful implementation of:
- RAG-based output validation layer grounded in verified product data
- Confidence scoring with low-confidence escalation trigger
- Hallucination monitoring dashboard with defined thresholds
- FCA Consumer Duty alignment assessment
- AI Governance Committee approval

---

## 4. Human Escalation Protocol

### 4.1 Mandatory Escalation Triggers

The following signals must trigger immediate escalation to a human agent:

| Trigger | Signal | Action |
|---------|--------|--------|
| Financial distress | Keywords: "can't afford", "struggling", "behind on payments", "debt", "bankruptcy" | Immediate escalation — trained vulnerability agent |
| Complaint | Keywords: "complain", "unhappy", "wrong", "error", "problem with my account" | Immediate escalation — complaints-trained agent |
| Regulatory query | Keywords: "FCA", "ombudsman", "FSCS", "legal rights", "compensation" | Immediate escalation — compliance-aware agent |
| Formal financial decision | Loan application, insurance claim, account closure, large transfer | Immediate escalation — specialist agent |
| Low confidence | AskVantage confidence score below defined threshold | Escalation with context handoff |
| Repeat contact | 3+ contacts on same issue within 30 days | Escalation with contact history |
| Human request | "Speak to a human", "real person", "agent" | Immediate — always honoured within 60 seconds |
| Silence or distress signals | Prolonged silence, incomplete responses, repeated short messages | Proactive escalation with welfare check |

### 4.2 Escalation Process

1. AskVantage detects escalation trigger
2. AskVantage informs customer: "I'm connecting you with one of our team members who can help you further"
3. Full conversation transcript passed to receiving agent
4. Agent reviews transcript before engaging customer
5. Escalation logged in contact management system
6. Escalation reason and outcome recorded for monitoring

### 4.3 Override Capability

Contact centre agents must have:
- Real-time dashboard showing active AskVantage conversations flagged for review
- One-click takeover capability for any AskVantage conversation
- Ability to flag and submit a correction report for any AskVantage response
- Access to AskVantage interaction history for any customer they are supporting

---

## 5. Vendor Governance Framework

### 5.1 LLM Provider Assessment (immediate)

VantageOne must complete the following assessments for the current LLM provider within 60 days:

| Assessment | Requirement |
|------------|------------|
| Model card review | Understand training data, known limitations, failure modes, intended use |
| AI governance maturity | Assess vendor's AI governance policy, bias testing, incident response capability |
| Data processing review | Confirm data processing locations, sub-processor arrangements, UK GDPR compliance |
| FCA fit assessment | Assess whether vendor AI meets FCA Consumer Duty and regulatory information accuracy standards |
| AI-specific contractual gaps | Identify gaps between current contract and required AI governance obligations |

### 5.2 Mandatory Contract Addendum

VantageOne's legal team must negotiate and execute an AI-specific addendum to the LLM provider contract covering:

| Requirement | Obligation |
|-------------|-----------|
| Model update notification | 14 days advance written notice before any model update that could affect output quality or behaviour |
| AI incident notification | Notification within 24 hours of any AI incident, outage, or quality degradation |
| Performance SLA | Defined maximum hallucination rate, minimum response accuracy, availability SLA |
| Right to audit | VantageOne right to audit vendor AI systems on 30 days' notice |
| AI-specific DPA | Data processing agreement covering model training data use, customer data access, sub-processor disclosure |
| Termination for AI cause | Right to terminate without standard notice periods for AI-specific failures (confirmed hallucination incidents, regulatory non-compliance, SLA breach) |
| Indemnification | Vendor indemnification for AI-caused customer harm arising from model failures |

### 5.3 Ongoing Vendor Monitoring

| Review | Frequency | Owner |
|--------|-----------|-------|
| Vendor AI performance review | Quarterly | AI Accountability Owner |
| Vendor SLA compliance review | Monthly | Head of Digital |
| Vendor AI governance reassessment | Annual | Legal + Compliance |
| Model update impact assessment | On each update | Engineering + AI Accountability Owner |

---

## 6. AI Incident Response Playbook

### 6.1 Incident Classification

| Severity | Description | Response Time | Escalation |
|----------|-------------|--------------|-----------|
| 1 — Critical | AI caused or has caused direct customer harm | Within 1 hour | CRO + Compliance immediately |
| 2 — High | Materially incorrect output; customer harm possible | Within 4 hours | AI Accountability Owner + Compliance |
| 3 — Medium | Quality degradation; no confirmed harm | Within 24 hours | AI Accountability Owner |
| 4 — Low | Minor quality issue; no customer impact | Within 5 business days | Head of Digital |

### 6.2 Incident Response Steps

| Step | Action | Owner |
|------|--------|-------|
| 1. Detect | Alert from monitoring dashboard, customer complaint, agent flag, or vendor notification | All staff |
| 2. Classify | Assign severity level; log in incident register | AI Accountability Owner |
| 3. Contain | Severity 1/2: restrict AskVantage scope immediately; route all consequential queries to humans | Head of Digital + Head of Contact Centre |
| 4. Investigate | Root cause analysis within 48 hours; identify affected customers and interactions | AI Accountability Owner + Engineering |
| 5. FCA Assessment | Assess FCA notification obligation — Consumer Duty breach? Significant Operational Incident? | Compliance + Legal |
| 6. Remediate | Fix root cause; update knowledge base; retrain or reconfigure as required | Engineering + Data Science |
| 7. Customer Notification | Proactively contact customers who received incorrect information | Customer Experience + Compliance |
| 8. Post-Incident Review | Update incident register; revise monitoring; report to AI Governance Committee | AI Accountability Owner |

### 6.3 FCA Notification Decision Framework

For every Severity 1 or 2 incident, Compliance must assess:

| Question | If Yes → |
|----------|---------|
| Was a customer given incorrect regulated information? | Assess FCA Consumer Duty breach |
| Did the incorrect information influence a financial decision? | Likely Consumer Duty breach — notify FCA |
| Was a vulnerable customer involved? | Consumer Duty breach — notify FCA; assess customer remediation |
| Does this meet Significant Operational Incident threshold? | Notify FCA within 4 hours under operational resilience obligations |

### 6.4 Historical Incident Review (INC-001, INC-002, INC-003)

All three confirmed incidents must be assessed against the FCA Notification Decision Framework within 30 days. Legal and Compliance must jointly determine:
- Whether FCA notification is required for each incident
- Whether affected customers are entitled to remediation
- What remediation is appropriate (correction letter, financial redress, apology)

---

## 7. NIST AI RMF Implementation Roadmap

| Function | Control | Target Date | Owner |
|----------|---------|------------|-------|
| GOVERN | AI Governance Policy | 60 days | AI Accountability Owner |
| GOVERN | AI Accountability Owner appointed | 30 days | CRO |
| GOVERN | AI Governance Committee established | 45 days | CRO |
| GOVERN | AI System Inventory created | 45 days | AI Accountability Owner |
| GOVERN | Vendor Governance Framework | 60 days | Legal + AI Accountability Owner |
| GOVERN | Staff AI literacy training | 60 days | AI Accountability Owner + L&D |
| MAP | AskVantage risk tier classification | Complete (this document) | AI Accountability Owner |
| MAP | FCA Consumer Duty mapping | 90 days | Compliance |
| MAP | Vulnerable customer impact assessment | 60 days | Compliance + Customer Experience |
| MEASURE | Hallucination monitoring dashboard | 60 days | Engineering |
| MEASURE | Escalation rate tracking | 60 days | Head of Contact Centre |
| MEASURE | Customer outcome metrics | 90 days | Customer Experience |
| MEASURE | Vendor SLA definition and tracking | 90 days | Legal + Head of Digital |
| MANAGE | AI Incident Response Playbook | 60 days | AI Accountability Owner |
| MANAGE | Human escalation protocol | 30 days | Head of Contact Centre |
| MANAGE | Override capability | 45 days | Engineering |
| MANAGE | RAG output validation layer | 90 days | Engineering + Data Science |
| MANAGE | Vulnerable customer detection | 90 days | Engineering |

---

## 8. Policy Governance

| Attribute | Detail |
|-----------|--------|
| Playbook Owner | AI Accountability Owner |
| Approved By | Chief Risk Officer |
| Approval Date | [To be completed on adoption] |
| Version | 1.0 |
| Review Frequency | Annual (six-monthly in Year 1) |
| Next Review Date | November 2026 |

---

*This playbook covers a fictional AI governance scenario designed to demonstrate RAI governance methodology. All frameworks and obligations referenced reflect globally recognised standards: NIST AI RMF · FCA Consumer Duty · FCA PRIN 12 · EU AI Act · ISO 42001:2023 · UK GDPR.*
