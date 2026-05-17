# Risk Register — SynthMind AI Platform
**NovaSynth Biologics | Gen AI for Drug Discovery & Clinical Trial Matching**
**Register Version:** 1.0 | **Owner:** AI Accountability Owner (TBA — appoint within 30 days) | **Review Frequency:** Monthly

---

## Scoring Methodology

| Score | Likelihood | Impact |
|-------|-----------|--------|
| 5 | Almost Certain — will very likely occur | Catastrophic — patient safety risk, regulatory enforcement, or major IP loss |
| 4 | Likely — high probability of occurring | Major — significant R&D disruption, regulatory finding, or reputational harm |
| 3 | Possible — may occur under certain conditions | Moderate — contained impact, manageable remediation |
| 2 | Unlikely — low probability | Minor — limited impact, recoverable |
| 1 | Rare — only in exceptional circumstances | Negligible — minimal impact |

**Risk Level = Likelihood × Impact**

| Risk Level | Score Range | Action Required |
|-----------|-------------|-----------------|
| 🔴 Critical | 20–25 | Immediate action — escalate to CSO within 24 hours |
| 🟠 High | 12–19 | Action within 90 days — assign owner and milestone |
| 🟡 Medium | 6–11 | Action within 180 days — include in governance roadmap |
| 🟢 Low | 1–5 | Monitor — review at quarterly governance meeting |

---

## Risk Summary Table

| ID | Risk | Category | Likelihood | Impact | Score | Level |
|----|------|----------|-----------|--------|-------|-------|
| R-01 | No RAI governance framework or accountability structure | Governance | 5 | 5 | 25 | 🔴 Critical |
| R-02 | LLM outputs used in clinical trial matching without human validation | Patient Safety | 5 | 5 | 25 | 🔴 Critical |
| R-03 | No explainability or audit trail for AI recommendations | Transparency | 5 | 4 | 20 | 🔴 Critical |
| R-04 | Training and retrieval data — IP and consent gaps | Data / Legal | 4 | 5 | 20 | 🔴 Critical |
| R-05 | LLM hallucination risk — undetected fabricated scientific claims | Model | 4 | 5 | 20 | 🟠 High |
| R-06 | No EU AI Act conformity assessment conducted | Regulatory | 5 | 4 | 20 | 🟠 High |
| R-07 | Patient matching function not assessed under FDA SaMD | Regulatory | 4 | 4 | 16 | 🟠 High |
| R-08 | Cross-border data flows (Basel ↔ Hyderabad) not GDPR/DPDP reviewed | Data / Privacy | 4 | 4 | 16 | 🟠 High |
| R-09 | No demographic fairness analysis of patient matching outputs | Ethics | 4 | 4 | 16 | 🟠 High |
| R-10 | RAG knowledge base updated without change control or impact assessment | Operational | 4 | 3 | 12 | 🟠 High |
| R-11 | No model performance monitoring or drift detection post-deployment | Operational | 4 | 3 | 12 | 🟠 High |
| R-12 | No AI incident response plan or escalation pathway | Operational | 3 | 4 | 12 | 🟠 High |
| R-13 | Dual-use risk — molecule screening outputs not assessed for harmful potential | Ethics | 2 | 4 | 8 | 🟡 Medium |
| R-14 | Researchers unaware of LLM limitations — over-reliance risk | Operational | 3 | 3 | 9 | 🟡 Medium |

---

## Individual Risk Cards

---

### R-01 — No RAI Governance Framework or Accountability Structure

| Field | Detail |
|-------|--------|
| **Risk ID** | R-01 |
| **Risk Description** | SynthMind was deployed without a formal RAI governance framework, accountability owner, or governance committee. No AI governance policy exists at NovaSynth. |
| **Risk Category** | Governance |
| **Risk Owner** | Chief Scientific Officer |
| **Likelihood** | 5 — Already occurred; ongoing state |
| **Impact** | 5 — Entire governance foundation is absent; all subsequent risks are amplified; EMA/FDA inspection finding if not remediated |
| **Risk Level** | 🔴 Critical (25) |
| **Current Controls** | None |
| **Primary Mitigation** | Appoint AI Accountability Owner within 30 days; establish AI Governance Committee; draft AI Governance Policy |
| **Secondary Mitigation** | Create AI System Inventory; mandate governance gate for all future AI deployments |
| **Target Date** | 30 days |
| **Residual Risk** | 🟡 Medium — once governance structure is in place and policy is adopted |
| **Status** | 🔴 Open |

---

### R-02 — LLM Outputs Used in Clinical Trial Matching Without Human Validation Protocol

| Field | Detail |
|-------|--------|
| **Risk ID** | R-02 |
| **Risk Description** | SynthMind's patient matching recommendations are used by clinical trial coordinators without a structured human review and validation protocol. Incorrect matching could expose patients to unsuitable trials or exclude eligible patients from life-saving treatments. |
| **Risk Category** | Patient Safety |
| **Risk Owner** | Clinical Trial Lead |
| **Likelihood** | 5 — Occurring in every patient matching query processed |
| **Impact** | 5 — Direct patient safety risk; GCP violation; potential regulatory enforcement |
| **Risk Level** | 🔴 Critical (25) |
| **Current Controls** | Researchers informally review outputs — no structured protocol |
| **Primary Mitigation** | Suspend fully autonomous use of patient matching outputs; implement mandatory structured human review and sign-off protocol for every patient matching recommendation before any action is taken |
| **Secondary Mitigation** | Engage IRB/Ethics Committee; define validation criteria researchers must apply before accepting a matching recommendation |
| **Target Date** | Immediate — within 7 days |
| **Residual Risk** | 🟢 Low — once mandatory human review protocol is implemented and documented |
| **Status** | 🔴 Open |

---

### R-03 — No Explainability or Audit Trail for AI Recommendations

| Field | Detail |
|-------|--------|
| **Risk ID** | R-03 |
| **Risk Description** | SynthMind outputs do not include source citations, retrieval traces, or reasoning pathways. Researchers cannot verify how a recommendation was reached. No audit log of AI outputs or downstream decisions exists. |
| **Risk Category** | Transparency / Compliance |
| **Risk Owner** | Bioinformatics Lead |
| **Likelihood** | 5 — Every output is currently unexplained |
| **Impact** | 4 — Regulatory non-compliance (EU AI Act, ICH E6); inability to investigate adverse events; loss of scientific credibility |
| **Risk Level** | 🔴 Critical (20) |
| **Current Controls** | None |
| **Primary Mitigation** | Implement RAG source citation in all outputs; implement AI output audit log capturing query, output, timestamp, user, and downstream action |
| **Secondary Mitigation** | Add confidence scoring; produce model card; train researchers on output interpretation |
| **Target Date** | 60 days |
| **Residual Risk** | 🟡 Medium — until hallucination detection is also in place |
| **Status** | 🔴 Open |

---

### R-04 — Training and Retrieval Data — IP and Consent Gaps

| Field | Detail |
|-------|--------|
| **Risk ID** | R-04 |
| **Risk Description** | The RAG knowledge base was populated with unpublished internal research, licensed databases, and scraped scientific literature without a formal data provenance review. Consent and IP status of fine-tuning data is undocumented. |
| **Risk Category** | Data / Legal |
| **Risk Owner** | Legal Counsel + Data Management Lead |
| **Likelihood** | 4 — Highly likely that unlicensed or improperly consented data is present given no review was conducted |
| **Impact** | 5 — IP litigation risk; regulatory data integrity finding; potential retraction of AI-assisted research outputs |
| **Risk Level** | 🔴 Critical (20) |
| **Current Controls** | None |
| **Primary Mitigation** | Conduct full data provenance audit of the RAG knowledge base; document every source with IP status and usage rights |
| **Secondary Mitigation** | Review LLM fine-tuning dataset for patient data, third-party IP, or consent gaps; establish data ingestion governance for future knowledge base updates |
| **Target Date** | 60 days |
| **Residual Risk** | 🟡 Medium — residual risk of historical outputs already generated from non-compliant data |
| **Status** | 🔴 Open |

---

### R-05 — LLM Hallucination Risk — Undetected Fabricated Scientific Claims

| Field | Detail |
|-------|--------|
| **Risk ID** | R-05 |
| **Risk Description** | SynthMind's LLM component can generate plausible but factually incorrect scientific claims. No hallucination detection mechanism exists. Researchers may act on fabricated molecule properties or patient eligibility criteria. |
| **Risk Category** | Model |
| **Risk Owner** | Bioinformatics Lead |
| **Likelihood** | 4 — LLM hallucination is a known and expected failure mode; no detection mitigates this |
| **Impact** | 5 — Misdirected R&D investment; patient safety risk if hallucinated eligibility criteria are applied |
| **Risk Level** | 🟠 High (20) |
| **Current Controls** | Researchers informally cross-check outputs — no systematic process |
| **Primary Mitigation** | Deploy hallucination detection layer — cross-check factual claims against knowledge base before surfacing to users; flag low-confidence or unsupported claims |
| **Secondary Mitigation** | Implement mandatory researcher verification for all molecule screening recommendations before downstream use; add output disclaimer on every SynthMind response |
| **Target Date** | 90 days |
| **Residual Risk** | 🟡 Medium — hallucination cannot be fully eliminated in current LLM generation |
| **Status** | 🔴 Open |

---

### R-06 — No EU AI Act Conformity Assessment Conducted

| Field | Detail |
|-------|--------|
| **Risk ID** | R-06 |
| **Risk Description** | SynthMind has not been assessed against EU AI Act obligations. As a High-Risk AI system operating in the EU (Basel HQ), NovaSynth faces significant regulatory exposure if inspected before conformity is established. |
| **Risk Category** | Regulatory |
| **Risk Owner** | Head of Compliance |
| **Likelihood** | 5 — No assessment has been started |
| **Impact** | 4 — Regulatory enforcement, fines, mandatory suspension of AI use |
| **Risk Level** | 🟠 High (20) |
| **Current Controls** | None |
| **Primary Mitigation** | Commission EU AI Act conformity assessment; engage external AI regulatory counsel if needed |
| **Secondary Mitigation** | Begin preparation of Article 11 technical documentation; assign compliance lead for EU AI Act implementation |
| **Target Date** | 90 days for assessment; documentation ongoing to 180 days |
| **Residual Risk** | 🟡 Medium — conformity is a multi-step process; full compliance will take 12+ months |
| **Status** | 🔴 Open |

---

### R-07 — Patient Matching Function Not Assessed Under FDA SaMD

| Field | Detail |
|-------|--------|
| **Risk ID** | R-07 |
| **Risk Description** | SynthMind's patient matching function likely meets the FDA's Software as a Medical Device (SaMD) definition. No regulatory assessment has been conducted. If NovaSynth's clinical trials include US sites or US regulatory submissions, this creates material regulatory risk. |
| **Risk Category** | Regulatory |
| **Risk Owner** | Regulatory Affairs Lead |
| **Likelihood** | 4 — Likely that patient matching meets SaMD definition based on its clinical decision support function |
| **Impact** | 4 — FDA enforcement; requirement to cease use pending SaMD compliance; impact on US trial regulatory submissions |
| **Risk Level** | 🟠 High (16) |
| **Current Controls** | None |
| **Primary Mitigation** | Engage Regulatory Affairs to conduct SaMD classification assessment; obtain external regulatory opinion if needed |
| **Secondary Mitigation** | Document findings and develop a regulatory strategy if SaMD classification is confirmed |
| **Target Date** | 120 days |
| **Residual Risk** | 🟡 Medium — regulatory strategy and compliance timeline may extend beyond 12 months |
| **Status** | 🔴 Open |

---

### R-08 — Cross-Border Data Flows Not GDPR/DPDP Reviewed

| Field | Detail |
|-------|--------|
| **Risk ID** | R-08 |
| **Risk Description** | Research queries containing proprietary compound data and potentially personal data flow between Basel (EU) and Hyderabad (India). These cross-border flows have not been assessed under GDPR or India's Digital Personal Data Protection (DPDP) Act 2023. |
| **Risk Category** | Data / Privacy |
| **Risk Owner** | Legal Counsel |
| **Likelihood** | 4 — Cross-border flows are ongoing with no legal basis documented |
| **Impact** | 4 — GDPR enforcement; DPDP Act penalties; reputational harm |
| **Risk Level** | 🟠 High (16) |
| **Current Controls** | Standard corporate data transfer agreements exist for operational data — AI-specific flows not covered |
| **Primary Mitigation** | Conduct GDPR transfer impact assessment for Basel → Hyderabad AI query flows; confirm appropriate transfer mechanism (SCCs or adequacy) |
| **Secondary Mitigation** | Review DPDP Act obligations for India operations; update data processing agreements to cover AI system data flows |
| **Target Date** | 90 days |
| **Residual Risk** | 🟢 Low — once legal basis for transfers is documented |
| **Status** | 🔴 Open |

---

### R-09 — No Demographic Fairness Analysis of Patient Matching Outputs

| Field | Detail |
|-------|--------|
| **Risk ID** | R-09 |
| **Risk Description** | Patient matching outputs have not been tested for demographic bias. Bias in training data or retrieval weighting could systematically exclude or over-include certain patient groups (by age, gender, ethnicity, or geography) from clinical trial selection. |
| **Risk Category** | Ethics / Fairness |
| **Risk Owner** | Data Science Lead + Head of Compliance |
| **Likelihood** | 4 — Demographic bias is common in clinical data; no testing has been done |
| **Impact** | 4 — Patient harm through exclusion from treatment; GCP violation; reputational harm if bias is discovered externally |
| **Risk Level** | 🟠 High (16) |
| **Current Controls** | None |
| **Primary Mitigation** | Conduct demographic fairness analysis of historical patient matching outputs — test for systematic patterns across protected characteristics |
| **Secondary Mitigation** | Define fairness metrics and thresholds; integrate fairness monitoring into the model monitoring dashboard |
| **Target Date** | 180 days |
| **Residual Risk** | 🟡 Medium — continuous monitoring required; fairness is not a one-time assessment |
| **Status** | 🔴 Open |

---

### R-10 — RAG Knowledge Base Updated Without Change Control

| Field | Detail |
|-------|--------|
| **Risk ID** | R-10 |
| **Risk Description** | The RAG knowledge base has been updated 3 times since deployment without a formal change control or impact assessment process. New content could introduce incorrect information, IP violations, or shift model output behaviour without detection. |
| **Risk Category** | Operational |
| **Risk Owner** | Bioinformatics Lead |
| **Likelihood** | 4 — Informal update practice is ongoing |
| **Impact** | 3 — Output quality degradation; IP risk; audit trail gap |
| **Risk Level** | 🟠 High (12) |
| **Current Controls** | None |
| **Primary Mitigation** | Implement RAG knowledge base change control — every update must be logged, reviewed for content quality and IP, and approved before deployment |
| **Secondary Mitigation** | Version the knowledge base; maintain a rollback capability |
| **Target Date** | 60 days |
| **Residual Risk** | 🟢 Low — once change control is implemented |
| **Status** | 🔴 Open |

---

### R-11 — No Model Performance Monitoring or Drift Detection

| Field | Detail |
|-------|--------|
| **Risk ID** | R-11 |
| **Risk Description** | No monitoring of SynthMind's output quality or behavioural drift has been implemented since deployment. Output degradation or distribution shift would go undetected until a researcher notices a problem. |
| **Risk Category** | Operational |
| **Risk Owner** | Bioinformatics Lead |
| **Likelihood** | 4 — Drift is occurring with no mechanism to detect it |
| **Impact** | 3 — Silent degradation of output quality; delayed detection of safety-critical failure |
| **Risk Level** | 🟠 High (12) |
| **Current Controls** | None |
| **Primary Mitigation** | Implement model monitoring dashboard — track output quality metrics, user feedback, query volume, and retrieval relevance scores |
| **Secondary Mitigation** | Define performance thresholds and alert triggers; establish escalation pathway for performance degradation |
| **Target Date** | 180 days |
| **Residual Risk** | 🟢 Low — once monitoring is in place |
| **Status** | 🔴 Open |

---

### R-12 — No AI Incident Response Plan or Escalation Pathway

| Field | Detail |
|-------|--------|
| **Risk ID** | R-12 |
| **Risk Description** | No incident response playbook or escalation pathway exists for AI-related events — including hallucinated outputs acted upon, patient matching errors, data breaches involving AI inputs, or regulatory triggers. |
| **Risk Category** | Operational |
| **Risk Owner** | AI Accountability Owner (once appointed) |
| **Likelihood** | 3 — Incidents may already have occurred without being formally identified |
| **Impact** | 4 — Unmanaged incidents could escalate to patient harm, regulatory breach, or reputational crisis |
| **Risk Level** | 🟠 High (12) |
| **Current Controls** | General IT incident process exists — does not cover AI-specific event types |
| **Primary Mitigation** | Develop AI incident response playbook — define incident categories, severity levels, response steps, and communication protocols |
| **Secondary Mitigation** | Conduct tabletop exercise to test the playbook; train relevant teams on AI incident identification |
| **Target Date** | 180 days |
| **Residual Risk** | 🟢 Low — once playbook is in place and teams are trained |
| **Status** | 🔴 Open |

---

### R-13 — Dual-Use Risk — Molecule Screening Not Assessed for Harmful Potential

| Field | Detail |
|-------|--------|
| **Risk ID** | R-13 |
| **Risk Description** | SynthMind's molecule screening function could inadvertently provide information useful for synthesising harmful compounds. No dual-use risk assessment has been conducted. |
| **Risk Category** | Ethics |
| **Risk Owner** | Head of Compliance + Chief Scientific Officer |
| **Likelihood** | 2 — Low probability given closed-system deployment; access is limited to credentialed researchers |
| **Impact** | 4 — Biosecurity risk; regulatory and reputational harm if misused |
| **Risk Level** | 🟡 Medium (8) |
| **Current Controls** | Access is restricted to NovaSynth employees via corporate authentication |
| **Primary Mitigation** | Conduct dual-use risk assessment of molecule screening outputs; engage biosecurity expert if needed |
| **Secondary Mitigation** | Implement output filtering for high-risk compound categories; review access controls |
| **Target Date** | 180 days |
| **Residual Risk** | 🟢 Low — access controls provide significant mitigation; assessment will confirm |
| **Status** | 🟡 In Review |

---

### R-14 — Researcher Over-Reliance on LLM Outputs

| Field | Detail |
|-------|--------|
| **Risk ID** | R-14 |
| **Risk Description** | Researchers may place excessive trust in SynthMind outputs due to automation bias — particularly given the system's confident, fluent narrative style. No training on LLM limitations or appropriate use has been provided. |
| **Risk Category** | Operational / Human Factors |
| **Risk Owner** | Bioinformatics Lead + R&D Training Lead |
| **Likelihood** | 3 — Automation bias is a well-documented human factors risk |
| **Impact** | 3 — Poor R&D decisions; patient matching errors; erosion of scientific rigour |
| **Risk Level** | 🟡 Medium (9) |
| **Current Controls** | None |
| **Primary Mitigation** | Deliver mandatory AI literacy training for all SynthMind users — covering LLM limitations, hallucination risk, and the requirement to critically evaluate outputs |
| **Secondary Mitigation** | Add prominent output disclaimers; implement structured verification checklist for patient matching decisions |
| **Target Date** | 90 days |
| **Residual Risk** | 🟢 Low — once training and disclaimer controls are in place |
| **Status** | 🔴 Open |

---

## Governance Log

| Review Date | Reviewer | Changes Made | Next Review |
|-------------|----------|--------------|-------------|
| May 2026 | Yatiraj Poojari | Initial register created | June 2026 |

---

*Scenario and company are fictional. Methodology reflects IAPP AIGP framework and globally recognised RAI standards.*
