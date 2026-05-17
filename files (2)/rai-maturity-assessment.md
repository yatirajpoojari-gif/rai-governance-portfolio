# RAI Maturity Assessment — SynthMind AI Platform
**NovaSynth Biologics | Gen AI for Drug Discovery & Clinical Trial Matching**
**Assessment Type:** RAI Maturity Assessment | **Prepared by:** Yatiraj Poojari | **Framework:** IAPP AIGP · NIST AI RMF · ISO 42001:2023

---

## 1. System Profile

| Attribute | Details |
|-----------|---------|
| System Name | SynthMind v2.1 |
| System Type | Gen AI Platform — Fine-tuned LLM + Retrieval-Augmented Generation (RAG) |
| Primary Functions | (1) Molecule screening recommendations · (2) Clinical trial patient matching |
| Underlying Model | Fine-tuned open-source LLM (LLaMA-3 variant) + proprietary RAG pipeline |
| Knowledge Base | Internal research documents, published literature, clinical trial databases |
| Deployment Date | November 2025 |
| Assessment Date | May 2026 (6 months post-deployment) |
| Geography | Basel, Switzerland (R&D HQ) · Hyderabad, India (R&D Centre) |
| Decision Authority | Semi-autonomous — outputs are recommendations; final decisions rest with researchers |
| Volume | ~200 molecule screening queries/week · ~50 patient matching queries/week |
| Commissioned By | Chief Scientific Officer (CSO) + Head of Compliance |
| Trigger | Internal audit raised concerns about AI decision traceability ahead of EMA inspection |

---

## 2. Use Case Classification

### 2.1 Risk Tier Determination

**Classification: HIGH-RISK AI SYSTEM**

| Classification Lens | Assessment | Rationale |
|--------------------|------------|-----------|
| Nature of Decision | Consequential — influences drug development and patient selection | Molecule screening errors can misdirect R&D investment; patient matching errors pose direct safety risks |
| Affected Population | Clinical trial patients — potentially vulnerable, ill individuals | Incorrect matching can expose patients to unsuitable trials or exclude eligible patients from life-saving treatments |
| Reversibility | Low for patient matching — trial enrolment decisions are difficult to reverse | Molecule screening errors compound over time, wasting significant R&D resources |
| Human Oversight | Partial — researchers review outputs but no formal validation protocol exists | No structured human review process, audit trail, or override documentation |
| Regulatory Exposure | High — intersects FDA SaMD, EU AI Act High-Risk, ICH E6 GCP | Regulatory inspection readiness is a stated organisational concern |

### 2.2 Framework Classification

| Framework | Classification | Key Obligations |
|-----------|---------------|----------------|
| EU AI Act | High-Risk AI System — Annex III (medical/clinical context) | Conformity assessment, human oversight, transparency, technical documentation, post-market monitoring |
| FDA SaMD Guidance | Patient matching meets Software as a Medical Device (SaMD) definition | Clinical performance evidence, post-market surveillance, software change control |
| ICH E6 (R3) GCP | Clinical trial patient matching directly implicates Good Clinical Practice | Data integrity, subject protection, protocol compliance, investigator accountability |
| ISO 42001:2023 | High Risk AI Application | Documented AI management system, risk management, roles and responsibilities, continual improvement |
| NIST AI RMF | High Impact AI System | GOVERN, MAP, MEASURE, MANAGE controls required across full AI lifecycle |

### 2.3 Stakeholder Mapping

| Stakeholder Type | Who They Are | RAI Consideration |
|-----------------|--------------|-------------------|
| Intended Users | Research scientists, clinical trial coordinators, bioinformatics team | Must understand model limitations, hallucination risk, and retrieval quality; need formal validation protocol |
| Impacted Users — Primary | Clinical trial patients selected or excluded by SynthMind matching | Subject to consequential decisions; entitled to protection under GCP and informed consent obligations |
| Impacted Users — Secondary | Molecule developers, R&D investment decision-makers | Downstream resource allocation affected by screening recommendations |
| Oversight Stakeholders | CSO, Head of Compliance, EMA (external regulator), IRB/Ethics Committee | Accountable for regulatory compliance; require audit trail and performance evidence |
| Vendor / Technology | LLM provider, RAG infrastructure team | Model card, data usage terms, fine-tuning documentation required |

---

## 3. RAI Maturity Assessment Framework

### 3.1 Maturity Scale

| Level | Label | Description |
|-------|-------|-------------|
| 0 | Non-existent | No awareness, process, or control exists |
| 1 | Ad Hoc | Informal, reactive — depends on individual judgment; no documentation |
| 2 | Developing | Some awareness and partial controls; inconsistent application |
| 3 | Defined | Documented policies and processes; consistently applied across the organisation |
| 4 | Managed | Quantitative monitoring; metrics-driven governance; continuous improvement |
| 5 | Optimised | Industry-leading practice; proactive governance; embedded in culture and operations |

### 3.2 Domain Maturity Scores

| # | Domain | Current Level | Target (12 months) | Gap |
|---|--------|--------------|-------------------|-----|
| 1 | AI Governance & Accountability | 1 — Ad Hoc | 3 — Defined | 2 levels |
| 2 | Risk Management | 1 — Ad Hoc | 3 — Defined | 2 levels |
| 3 | Data Governance | 2 — Developing | 4 — Managed | 2 levels |
| 4 | Model Transparency & Explainability | 0 — Non-existent | 3 — Defined | 3 levels |
| 5 | Ethics & Fairness | 0 — Non-existent | 3 — Defined | 3 levels |
| 6 | Regulatory Compliance | 1 — Ad Hoc | 3 — Defined | 2 levels |
| 7 | Incident Response & Monitoring | 1 — Ad Hoc | 3 — Defined | 2 levels |

**Overall Current Maturity: Level 1.0 (Ad Hoc)**
**Overall Target Maturity: Level 3.1 (Defined)**

---

## 4. Domain-by-Domain Assessment

---

### Domain 1 — AI Governance & Accountability

**Current Level: 1 — Ad Hoc**

#### Findings

NovaSynth has no formal AI governance structure. SynthMind was initiated by the bioinformatics team and approved informally by the CSO without a governance committee review, accountability assignment, or RAI assessment.

- No AI Accountability Owner has been appointed
- No AI governance policy, committee, or operating model exists
- No documented roles and responsibilities for AI oversight
- Procurement and deployment of AI tools is not subject to a governance gate
- The bioinformatics team informally "owns" SynthMind but has no documented accountability

#### Gap Analysis

| Required (Level 3) | Current State | Gap |
|-------------------|---------------|-----|
| Documented AI governance policy | None | ❌ Missing |
| AI Accountability Owner appointed | None | ❌ Missing |
| AI governance committee with defined mandate | None | ❌ Missing |
| All AI systems registered in an AI inventory | Not done | ❌ Missing |
| Governance gate for new AI deployments | Not done | ❌ Missing |

#### Recommendations

1. Appoint an **AI Accountability Owner** (recommended: Head of Compliance or a newly designated AI Risk Lead) within 30 days
2. Establish an **AI Governance Committee** with representation from Compliance, Legal, R&D, Data Science, and the CSO office
3. Draft and adopt an **AI Governance Policy** covering deployment approval, accountability, monitoring, and incident response
4. Create an **AI System Inventory** — register SynthMind and any other AI tools in use across NovaSynth
5. Mandate a governance gate (RAI assessment + sign-off) for all future AI deployments

**Risk Level:** 🔴 Critical

---

### Domain 2 — Risk Management

**Current Level: 1 — Ad Hoc**

#### Findings

No formal risk management process was applied to SynthMind before or after deployment. The internal audit that triggered this assessment was the first structured risk review ever conducted on the platform.

- No pre-deployment risk assessment conducted
- No risk register exists for SynthMind or any other AI system
- Risk is managed informally by researchers who flag concerns verbally to the bioinformatics team
- No risk escalation pathway or risk ownership exists
- No assessment of the molecule screening or patient matching functions against EU AI Act or FDA SaMD risk tiers

#### Gap Analysis

| Required (Level 3) | Current State | Gap |
|-------------------|---------------|-----|
| Pre-deployment RAI risk assessment | Not conducted | ❌ Missing |
| Live risk register with ownership | None | ❌ Missing |
| Formal risk escalation pathway | None | ❌ Missing |
| Regulatory risk tier classification | Not done | ❌ Missing |

#### Recommendations

1. Conduct and document a **retrospective pre-deployment risk assessment** (this document serves as the foundation)
2. Implement the **risk register** developed in this engagement (see `risk-register.md`)
3. Classify SynthMind's patient matching function formally under **FDA SaMD** and **EU AI Act** Annex III
4. Define a risk escalation pathway: bioinformatics team → AI Accountability Owner → CSO → Board Risk Committee

**Risk Level:** 🔴 Critical

---

### Domain 3 — Data Governance

**Current Level: 2 — Developing**

#### Findings

NovaSynth has stronger data governance than most domains — driven by existing GxP data integrity requirements for clinical operations. However, AI-specific data governance for SynthMind's training data and RAG knowledge base is materially weaker.

**Strengths:**
- Clinical trial data is managed under GCP/GxP data integrity controls
- A Data Management team exists with defined data stewardship roles
- Basic data classification policy is in place for clinical data

**Gaps specific to SynthMind:**
- The RAG knowledge base was populated without a formal data provenance review — sources include unpublished internal research, licensed databases, and scraped scientific literature
- Consent and IP status of training data used to fine-tune the LLM has not been documented
- No data quality assessment was performed before populating the knowledge base
- Data retention, versioning, and audit trail for the RAG knowledge base are not defined
- Cross-border data flow (Basel ↔ Hyderabad) for model queries containing proprietary compound data has not been reviewed under GDPR or Indian DPDP Act

#### Gap Analysis

| Required (Level 4) | Current State | Gap |
|-------------------|---------------|-----|
| Training data provenance documented | Not done | ❌ Missing |
| IP and consent status of all data sources confirmed | Not done | ❌ Missing |
| RAG knowledge base data quality assessed | Not done | ❌ Missing |
| Cross-border data flow GDPR/DPDP review | Not done | ❌ Missing |
| Data versioning and audit trail for AI inputs | Not done | ❌ Missing |

#### Recommendations

1. Conduct a **data provenance audit** of the RAG knowledge base — document every source, confirm IP rights and consent status
2. Review the LLM fine-tuning dataset — confirm no patient data, unpublished third-party research, or licensed content was used without authorisation
3. Perform a **GDPR and Indian DPDP Act review** of cross-border data flows involving proprietary compound data
4. Implement **data versioning** for the RAG knowledge base — every update should be logged with a timestamp and change rationale
5. Define data retention and deletion policies specific to AI system inputs and outputs

**Risk Level:** 🟠 High

---

### Domain 4 — Model Transparency & Explainability

**Current Level: 0 — Non-existent**

#### Findings

SynthMind produces molecule screening recommendations and patient matching outputs with no explanation of how conclusions were reached. Researchers receive outputs as narrative text generated by the LLM — there is no source citation, confidence scoring, retrieval trace, or reasoning pathway visible to the user.

- No explainability layer or output attribution exists
- Researchers cannot identify which documents in the RAG knowledge base drove a specific recommendation
- No model card has been produced for SynthMind
- LLM hallucination risk is unmitigated — outputs may contain plausible but fabricated scientific claims
- No confidence or uncertainty indicator is surfaced to users
- Audit trail for AI outputs used in clinical trial matching decisions does not exist

#### Gap Analysis

| Required (Level 3) | Current State | Gap |
|-------------------|---------------|-----|
| Source citations in RAG outputs | Not implemented | ❌ Missing |
| Confidence / uncertainty scoring | Not implemented | ❌ Missing |
| Hallucination detection mechanism | Not implemented | ❌ Missing |
| Model card published internally | Not done | ❌ Missing |
| Audit trail for AI outputs used in decisions | Not done | ❌ Missing |

#### Recommendations

1. Implement **RAG source citation** in all SynthMind outputs — every claim should reference the source document and passage
2. Add a **confidence indicator** to all outputs — surfacing retrieval similarity scores helps researchers calibrate reliance
3. Deploy a **hallucination detection layer** — cross-check factual claims in outputs against the knowledge base before surfacing to users
4. Produce a **model card** for SynthMind — document intended use, limitations, training approach, known failure modes
5. Implement an **AI output audit log** — every query, output, and downstream action taken must be logged for regulatory review

**Risk Level:** 🔴 Critical

---

### Domain 5 — Ethics & Fairness

**Current Level: 0 — Non-existent**

#### Findings

No ethics review or fairness analysis has been conducted for SynthMind. This is particularly acute for the patient matching function, where demographic bias in training data or retrieval could systematically exclude or include patient groups in clinical trials.

- No ethics review was conducted before deployment
- No fairness analysis of patient matching outputs across demographic groups (age, gender, ethnicity, geography)
- No process for researchers to flag ethically concerning AI outputs
- No engagement with IRB/Ethics Committee regarding AI-assisted trial matching
- The molecule screening function has not been assessed for potential dual-use risks (outputs could inadvertently assist identification of harmful compounds)

#### Gap Analysis

| Required (Level 3) | Current State | Gap |
|-------------------|---------------|-----|
| Pre-deployment ethics review | Not conducted | ❌ Missing |
| Fairness analysis of patient matching outputs | Not done | ❌ Missing |
| IRB/Ethics Committee engagement | Not done | ❌ Missing |
| Researcher ethics escalation pathway | None | ❌ Missing |
| Dual-use risk assessment | Not done | ❌ Missing |

#### Recommendations

1. Conduct a **retrospective ethics review** of SynthMind — engage the IRB/Ethics Committee on AI-assisted patient matching
2. Perform a **demographic fairness analysis** of patient matching outputs — test for systematic exclusion or inclusion patterns across age, gender, ethnicity, and geography
3. Establish an **ethics escalation pathway** — researchers must have a named contact to raise concerns about AI outputs
4. Assess molecule screening outputs for **dual-use risk** — confirm no outputs could assist identification of toxic or harmful compounds
5. Engage Legal and Compliance on **informed consent obligations** — are patients aware AI was used in their trial selection?

**Risk Level:** 🔴 Critical

---

### Domain 6 — Regulatory Compliance

**Current Level: 1 — Ad Hoc**

#### Findings

NovaSynth operates in a heavily regulated environment — but AI-specific regulatory compliance has not been addressed. The organisation's existing GxP and GCP compliance infrastructure is strong for clinical operations, but does not extend to AI system governance.

- SynthMind has not been assessed under EU AI Act obligations
- The patient matching function has not been evaluated against FDA SaMD classification criteria
- ICH E6 (R3) GCP obligations relevant to AI-assisted trial matching have not been reviewed
- No technical documentation (as required by EU AI Act Article 11) has been prepared
- No regulatory change monitoring process exists for evolving AI regulation

#### Gap Analysis

| Required (Level 3) | Current State | Gap |
|-------------------|---------------|-----|
| EU AI Act conformity assessment | Not started | ❌ Missing |
| FDA SaMD classification determination | Not done | ❌ Missing |
| ICH E6 (R3) GCP alignment review | Not done | ❌ Missing |
| EU AI Act technical documentation (Article 11) | Not prepared | ❌ Missing |
| Regulatory change monitoring for AI law | Not in place | ❌ Missing |

#### Recommendations

1. Commission a **EU AI Act conformity assessment** for SynthMind — confirm High-Risk classification and begin conformity process
2. Engage regulatory affairs to determine **FDA SaMD classification** for the patient matching function — if classified as SaMD, a regulatory strategy is required before continued use in US-connected trials
3. Review **ICH E6 (R3) GCP** obligations for AI-assisted patient matching — document findings and any required protocol amendments
4. Begin preparation of **EU AI Act Article 11 technical documentation** — system description, training data, validation methodology, performance metrics
5. Establish a **regulatory horizon scanning** process — assign responsibility for monitoring EU AI Act implementation timelines, FDA AI/ML guidance updates, and ICH AI guidance developments

**Risk Level:** 🟠 High

---

### Domain 7 — Incident Response & Monitoring

**Current Level: 1 — Ad Hoc**

#### Findings

No formal monitoring or incident response capability exists for SynthMind. Researchers informally flag issues to the bioinformatics team via email or in team meetings. There is no structured process for identifying, escalating, investigating, or remediating AI-related incidents.

- No model performance monitoring is in place post-deployment
- No drift detection mechanism exists — the knowledge base has been updated 3 times since deployment without impact assessment
- No incident classification framework or response playbook exists for AI-related events
- No near-miss or adverse event reporting process for AI outputs that led to poor decisions
- No post-deployment review has been conducted since go-live

#### Gap Analysis

| Required (Level 3) | Current State | Gap |
|-------------------|---------------|-----|
| Model performance monitoring dashboard | Not in place | ❌ Missing |
| RAG knowledge base change control | Not in place | ❌ Missing |
| AI incident response playbook | Not in place | ❌ Missing |
| Adverse event / near-miss reporting for AI | Not in place | ❌ Missing |
| Scheduled post-deployment reviews | Not in place | ❌ Missing |

#### Recommendations

1. Implement a **model monitoring dashboard** — track output quality metrics, user feedback signals, and query volume trends
2. Establish **RAG knowledge base change control** — every update must be logged, assessed for impact, and approved before deployment
3. Develop an **AI incident response playbook** — define incident categories (hallucination, bias, data breach, regulatory trigger) and response steps for each
4. Create an **AI near-miss reporting mechanism** — researchers should be able to flag concerning outputs without fear of blame
5. Schedule **quarterly post-deployment reviews** — assess performance, risks, and any required governance updates

**Risk Level:** 🟠 High

---

## 5. 12-Month Governance Roadmap

### Phase 1 — Foundation (0–90 Days)

| Action | Owner | Priority |
|--------|-------|----------|
| Appoint AI Accountability Owner | CSO | 🔴 Critical |
| Establish AI Governance Committee | Head of Compliance | 🔴 Critical |
| Pause clinical trial patient matching pending human review protocol | CSO + Clinical Lead | 🔴 Critical |
| Conduct retrospective RAI assessment (this document) | AI Accountability Owner | 🔴 Critical |
| Register SynthMind in AI System Inventory | Bioinformatics Lead | 🟠 High |
| Commission data provenance audit of RAG knowledge base | Data Management Lead | 🟠 High |
| Implement RAG source citations in all outputs | Bioinformatics Team | 🟠 High |
| Engage IRB/Ethics Committee on AI-assisted trial matching | Head of Compliance | 🟠 High |

### Phase 2 — Build (90–180 Days)

| Action | Owner | Priority |
|--------|-------|----------|
| Draft and adopt AI Governance Policy | Head of Compliance | 🟠 High |
| Deploy confidence scoring and hallucination detection layer | Bioinformatics Team | 🟠 High |
| Complete IP and consent review of training data | Legal + Data Management | 🟠 High |
| Complete GDPR / DPDP cross-border data flow review | Legal | 🟠 High |
| Publish SynthMind model card (internal) | Bioinformatics Lead | 🟡 Medium |
| Define and implement AI output audit log | Bioinformatics Team | 🟠 High |
| Conduct EU AI Act conformity assessment | Head of Compliance + External Counsel | 🟠 High |
| Begin EU AI Act Article 11 technical documentation | Bioinformatics Lead + Compliance | 🟠 High |

### Phase 3 — Operate (180–270 Days)

| Action | Owner | Priority |
|--------|-------|----------|
| Deploy model monitoring dashboard | Bioinformatics Team | 🟠 High |
| Implement RAG knowledge base change control process | Bioinformatics Lead | 🟠 High |
| Develop AI incident response playbook | AI Accountability Owner | 🟠 High |
| Conduct demographic fairness analysis of patient matching | Data Science + Compliance | 🟠 High |
| Determine FDA SaMD classification and regulatory strategy | Regulatory Affairs | 🟡 Medium |
| Establish researcher ethics escalation pathway | Head of Compliance | 🟡 Medium |
| Launch AI near-miss reporting mechanism | AI Accountability Owner | 🟡 Medium |

### Phase 4 — Sustain (270–365 Days)

| Action | Owner | Priority |
|--------|-------|----------|
| Conduct first annual RAI review against this assessment | AI Accountability Owner | 🟠 High |
| EMA inspection readiness assessment for AI governance | Head of Compliance | 🟠 High |
| Publish internal AI transparency report | AI Accountability Owner | 🟡 Medium |
| Assess maturity against Level 3 target — identify gaps for Level 4 roadmap | AI Governance Committee | 🟡 Medium |
| Establish regulatory horizon scanning process | Compliance + Legal | 🟡 Medium |

---

## 6. Current State vs Target State

| Dimension | Current State | Target State (12 months) |
|-----------|--------------|--------------------------|
| Governance | No structure, no accountability | AI Governance Committee · AI Accountability Owner · documented policy |
| Risk Management | No risk register · no escalation pathway | Live risk register · formal escalation · quarterly reviews |
| Data | Unaudited RAG knowledge base · IP gaps | Fully provenance-documented knowledge base · GDPR/DPDP compliant |
| Explainability | No citations · no confidence scores · no audit trail | Source citations · confidence indicators · full output audit log |
| Ethics & Fairness | No ethics review · no fairness analysis | IRB-engaged · demographic fairness tested · escalation pathway live |
| Regulatory | No formal compliance posture | EU AI Act conformity in progress · SaMD determination made · GCP aligned |
| Monitoring | No monitoring · no incident process | Performance dashboard · change control · incident playbook · near-miss reporting |

---

*Scenario and company are fictional. Methodology reflects IAPP AIGP framework and globally recognised RAI standards: NIST AI RMF · ISO 42001:2023 · EU AI Act · FDA SaMD · ICH E6 (R3).*
