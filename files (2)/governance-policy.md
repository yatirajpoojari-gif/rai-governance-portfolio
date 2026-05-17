# AI Governance Policy — SynthMind AI Platform
**NovaSynth Biologics | Gen AI for Drug Discovery & Clinical Trial Matching**
**Policy Version:** 1.0 (Draft for adoption) | **Prepared by:** Yatiraj Poojari | **Status:** Pending Approval

---

## 1. Purpose and Scope

### 1.1 Purpose

This policy establishes the governance framework, accountability structure, and operating standards for the responsible deployment and use of the SynthMind AI platform at NovaSynth Biologics. It defines roles, responsibilities, controls, and oversight mechanisms to ensure SynthMind is used safely, ethically, and in compliance with applicable regulatory requirements.

This policy is a foundational document. It will be supplemented by operational procedures, user guidelines, and technical standards as NovaSynth's AI governance maturity develops.

### 1.2 Scope

This policy applies to:
- All users of the SynthMind AI platform (research scientists, clinical trial coordinators, bioinformatics team, and any future users)
- All staff involved in the development, deployment, maintenance, or oversight of SynthMind
- All AI systems deployed by NovaSynth Biologics — SynthMind is the first system governed under this policy; subsequent deployments will follow the same framework

### 1.3 Regulatory Context

This policy has been designed in alignment with:
- **EU AI Act** (Regulation 2024/1689) — High-Risk AI system obligations
- **FDA Software as a Medical Device (SaMD) Guidance** — applicable to the patient matching function
- **ICH E6 (R3) Good Clinical Practice** — applicable to all AI use in clinical trial operations
- **ISO 42001:2023** — AI Management System Standard
- **NIST AI Risk Management Framework** — GOVERN · MAP · MEASURE · MANAGE
- **GDPR** (EU) and **DPDP Act 2023** (India) — data protection obligations

---

## 2. Governance Structure

### 2.1 AI Governance Committee

**Purpose:** Provide strategic oversight, policy approval, and escalation resolution for all AI governance matters at NovaSynth Biologics.

**Membership:**

| Role | Member |
|------|--------|
| Chair | Chief Scientific Officer (CSO) |
| AI Accountability Owner | Head of Compliance (or designated AI Risk Lead) |
| R&D Representative | VP, Drug Discovery |
| Clinical Representative | Clinical Trial Lead |
| Data & Technology Representative | Bioinformatics Lead |
| Legal Representative | General Counsel |
| Ethics Representative | IRB/Ethics Committee Liaison |

**Meeting Cadence:** Quarterly (monthly during the first 12 months of this policy)

**Mandate:**
- Approve and review this policy annually
- Oversee the AI System Inventory and governance roadmap
- Resolve escalated AI risk and ethics issues
- Review AI incident reports
- Monitor regulatory developments relevant to NovaSynth's AI use

### 2.2 AI Accountability Owner

**Appointed Role:** Head of Compliance (interim) — dedicated AI Risk Lead to be recruited within 6 months

**Responsibilities:**
- Day-to-day governance of all AI systems at NovaSynth
- Maintain the AI System Inventory
- Ensure the risk register is reviewed monthly and escalated items are actioned
- Coordinate the RAI assessment process for new AI deployments
- Serve as the primary point of contact for regulatory enquiries related to AI
- Chair the AI Incident Response process
- Report to the AI Governance Committee at each quarterly meeting

### 2.3 AI System Owner (SynthMind)

**Appointed Role:** Bioinformatics Lead

**Responsibilities:**
- Day-to-day technical operation and maintenance of SynthMind
- RAG knowledge base change control — no updates without documented approval
- Maintain the SynthMind model card and technical documentation
- Implement monitoring, logging, and alert mechanisms
- Escalate technical incidents to the AI Accountability Owner within 24 hours
- Coordinate model updates and retraining with the AI Governance Committee

### 2.4 Intended Users — Responsibilities

All researchers and clinical trial coordinators using SynthMind are responsible for:
- Completing mandatory AI literacy training before using SynthMind
- Treating all SynthMind outputs as recommendations — not as authoritative scientific conclusions
- Applying critical professional judgement when evaluating outputs
- Following the human review and validation protocol for patient matching (see Section 5)
- Reporting concerning outputs, near-misses, or suspected errors to the AI System Owner immediately
- Not using SynthMind for purposes outside its defined scope (see Section 4)

---

## 3. RACI Matrix

| Activity | CSO | AI Accountability Owner | Bioinformatics Lead | Researchers | Legal / Compliance | IRB |
|----------|-----|------------------------|---------------------|-------------|-------------------|-----|
| Policy approval and annual review | A | R | C | I | C | I |
| AI System Inventory maintenance | I | A/R | C | I | I | — |
| New AI system deployment approval | A | R | C | I | C | I |
| Risk register review (monthly) | I | A | R | I | C | — |
| RAG knowledge base updates | I | A | R | I | — | — |
| Patient matching validation protocol | I | A | C | R | C | C |
| AI incident identification | I | I | I | R | I | — |
| AI incident response | I | A/R | R | C | C | C |
| Regulatory compliance assessment | I | A | C | I | R | I |
| AI literacy training delivery | I | A | R | I | C | — |
| Fairness and ethics review | A | R | C | I | C | R |
| Annual RAI reassessment | A | R | C | I | C | C |

**Key:** R = Responsible · A = Accountable · C = Consulted · I = Informed

---

## 4. Permitted and Prohibited Uses

### 4.1 Permitted Uses of SynthMind

SynthMind is approved for the following use cases only:

| Use Case | Permitted | Conditions |
|----------|-----------|-----------|
| Molecule screening — generating candidate compound recommendations for NovaSynth internal R&D | ✅ Yes | Outputs must be verified by a qualified research scientist before downstream use |
| Clinical trial patient matching — identifying potentially eligible patient profiles from internal databases | ✅ Yes | Mandatory human review and validation protocol must be completed for every output before any action is taken |
| Literature summarisation — summarising published scientific literature for internal research use | ✅ Yes | Source citations must be verified; summaries must not be used in regulatory submissions without independent verification |

### 4.2 Prohibited Uses of SynthMind

The following uses are explicitly prohibited:

| Prohibited Use | Reason |
|---------------|--------|
| Using patient matching outputs without completing the human review protocol | Patient safety; GCP compliance |
| Including SynthMind outputs in regulatory submissions (IND, NDA, EMA applications) without independent verification and disclosure | Regulatory integrity |
| Querying SynthMind with identifiable patient data | GDPR; data minimisation; patient privacy |
| Using SynthMind for compound synthesis planning without dual-use risk clearance | Biosecurity; IP |
| Sharing SynthMind outputs externally (to partners, vendors, or publications) without Compliance approval | IP; regulatory; confidentiality |
| Using SynthMind for any purpose not listed in the Permitted Uses table | Outside assessed scope |

---

## 5. Human Review and Validation Protocol — Patient Matching

Given the patient safety implications of clinical trial matching, the following mandatory protocol applies to every patient matching query processed by SynthMind.

### 5.1 Validation Steps

| Step | Action | Responsible |
|------|--------|-------------|
| 1 | Receive SynthMind patient matching recommendation | Clinical Trial Coordinator |
| 2 | Review source citations — confirm all cited sources are accessible and accurately represented | Clinical Trial Coordinator |
| 3 | Independently verify patient eligibility criteria against the trial protocol — do not rely solely on SynthMind output | Clinical Trial Coordinator |
| 4 | Obtain sign-off from Principal Investigator (PI) before any patient is contacted or enrolled | Principal Investigator |
| 5 | Document the AI output, the independent verification, and the PI sign-off in the trial master file | Clinical Trial Coordinator |
| 6 | If SynthMind output conflicts with independent assessment — do not use the AI output; escalate to AI System Owner | Clinical Trial Coordinator + AI System Owner |

### 5.2 Audit Requirements

Every patient matching interaction must be logged including:
- Query submitted
- SynthMind output received
- Verification steps completed
- PI sign-off confirmation
- Final enrolment decision and rationale

This log constitutes part of the trial master file and is subject to GCP audit requirements.

---

## 6. Risk Management

### 6.1 Risk Register

The SynthMind risk register is maintained by the AI System Owner and reviewed by the AI Accountability Owner monthly. The register documents all identified risks with likelihood × impact scoring, ownership, mitigation actions, and status.

Current risk register: [`risk-register.md`](./risk-register.md)

### 6.2 Risk Escalation Pathway

| Risk Level | Escalation | Timeframe |
|-----------|-----------|-----------|
| 🔴 Critical | Immediate escalation to AI Accountability Owner and CSO | Within 24 hours of identification |
| 🟠 High | Escalation to AI Accountability Owner | Within 5 business days |
| 🟡 Medium | Documented in risk register; reviewed at next monthly review | Within 30 days |
| 🟢 Low | Monitored; reviewed at quarterly governance meeting | Quarterly |

---

## 7. AI Incident Response

### 7.1 AI Incident Categories

| Category | Description | Examples |
|----------|-------------|---------|
| Patient Safety | AI output contributes to or could contribute to patient harm | Incorrect patient matching used in enrolment; hallucinated eligibility criteria acted upon |
| Data Breach | Unauthorised access to or disclosure of AI inputs or outputs | Query log accessed by unauthorised party; proprietary compound data exposed |
| Regulatory Trigger | AI use creates regulatory compliance exposure | External audit discovers non-compliant AI use; regulatory enquiry received |
| Output Quality Failure | Systematic degradation in SynthMind output quality | Hallucinations increasing; retrieval accuracy declining |
| Ethics / Fairness | Discriminatory or unfair outcomes detected | Demographic bias found in patient matching outputs |

### 7.2 Incident Response Steps

1. **Identify** — any user who identifies a suspected AI incident must report to the AI System Owner immediately
2. **Contain** — AI System Owner assesses severity; suspends the relevant SynthMind function if patient safety or data breach is suspected
3. **Escalate** — AI Accountability Owner notified within 24 hours; CSO and Legal notified for Critical and High incidents
4. **Investigate** — AI System Owner leads technical investigation; Legal leads regulatory and data breach aspects
5. **Remediate** — implement technical and operational fixes; document all actions taken
6. **Review** — post-incident review within 30 days; update risk register and monitoring processes
7. **Report** — regulatory notification if required (GDPR 72-hour breach notification; EMA/FDA if patient safety affected); internal report to AI Governance Committee

### 7.3 Near-Miss Reporting

Users are encouraged to report near-misses — situations where a concerning AI output was identified before any harmful action was taken. Near-miss reports should be submitted to the AI System Owner and are treated as learning opportunities, not disciplinary matters.

---

## 8. Monitoring and Oversight

### 8.1 Model Performance Monitoring

The AI System Owner is responsible for maintaining a model monitoring dashboard that tracks:
- Output quality metrics (user feedback, retrieval relevance scores)
- Query volume and usage patterns
- Alert triggers for performance degradation

### 8.2 RAG Knowledge Base Change Control

All updates to the SynthMind RAG knowledge base require:
1. Documented change request (source of new content, reason for addition)
2. IP and data quality review by the Data Management Lead
3. Approval from the AI Accountability Owner
4. Version logging with timestamp and change rationale
5. Post-update output quality check before resuming normal operations

### 8.3 Scheduled Reviews

| Review | Frequency | Owner |
|--------|-----------|-------|
| Risk register review | Monthly | AI Accountability Owner |
| AI Governance Committee meeting | Quarterly (monthly in Year 1) | CSO |
| Model performance review | Quarterly | AI System Owner |
| Full RAI reassessment | Annual | AI Accountability Owner |
| Policy review | Annual | Head of Compliance |
| EMA/regulatory readiness review | Annual | Head of Compliance |

---

## 9. Training and Awareness

### 9.1 Mandatory Training

| Training | Audience | Frequency |
|----------|----------|-----------|
| AI Literacy — LLM limitations, hallucination risk, appropriate reliance | All SynthMind users | Before first use; annual refresher |
| Patient Matching Validation Protocol | Clinical trial coordinators, PIs | Before using patient matching; annual refresher |
| AI Incident Reporting | All SynthMind users | At onboarding; annual refresher |
| AI Governance Policy | All staff involved in AI oversight | At policy adoption; on material update |

### 9.2 Training Records

Completion of mandatory training must be recorded and is subject to audit.

---

## 10. Policy Governance

| Attribute | Detail |
|-----------|--------|
| Policy Owner | Head of Compliance (AI Accountability Owner) |
| Approved By | Chief Scientific Officer |
| Approval Date | [To be completed on adoption] |
| Version | 1.0 |
| Review Frequency | Annual |
| Next Review Date | May 2027 |
| Distribution | All NovaSynth staff; available on internal policy portal |

### 10.1 Policy Exceptions

Requests for exceptions to this policy must be submitted in writing to the AI Accountability Owner with a documented business justification and proposed risk mitigation. Exceptions require CSO approval and must be time-limited. All granted exceptions are logged and reviewed at the next AI Governance Committee meeting.

---

*This policy covers a fictional AI governance scenario designed to demonstrate RAI governance methodology. All frameworks and obligations referenced reflect globally recognised standards: EU AI Act · FDA SaMD · ICH E6 (R3) · ISO 42001:2023 · NIST AI RMF · GDPR · DPDP Act 2023.*
