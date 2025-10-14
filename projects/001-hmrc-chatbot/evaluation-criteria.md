# Vendor Evaluation Criteria: HMRC Tax Guidance ChatBot

**Document Type**: Vendor Evaluation Framework
**RFP ID**: HMRC-CHATBOT-2025-001
**Project ID**: 001-hmrc-chatbot
**Version**: 1.0
**Date**: 2025-10-14
**Evaluation Lead**: [HMRC Procurement Lead - TBD]
**Evaluation Committee**: [To be assigned before proposal deadline]

---

## 1. Evaluation Overview

### 1.1 Purpose

This document defines the criteria, scoring methodology, and process for evaluating vendor proposals for the **HMRC Tax Guidance ChatBot** project. The goal is to select the vendor that provides the best value considering technical capability, AI/ML expertise, UK Government experience, security compliance, cost, and cultural fit.

This evaluation framework implements the scoring criteria defined in the Statement of Work (SOW) Section 8 and ensures compliance with G-Cloud 14 procurement rules, HM Treasury value for money principles, and HMRC governance standards.

### 1.2 Evaluation Principles

- **Objective**: Criteria are measurable, documented, and consistently applied to all vendors
- **Transparent**: Vendors understand evaluation criteria from SOW publication (no hidden scoring)
- **Fair**: All vendors evaluated against same criteria; no favoritism or conflicts of interest
- **Documented**: All scores, rationale, and decisions captured for audit trail and potential appeals
- **Value-Based**: Best value for taxpayer money, not necessarily lowest cost (70% technical, 30% cost)
- **Compliance-Focused**: UK GDPR, WCAG 2.2 AA, NCSC Cloud Security Principles, GDS Service Standard are non-negotiable

### 1.3 Evaluation Team

| Name | Role | Department | Evaluation Focus | Voting |
|------|------|------------|------------------|--------|
| [TBD] | **Evaluation Lead** | HMRC Procurement | Process orchestration, compliance with procurement rules, final scoring coordination | Yes |
| [TBD] | **Technical Evaluator - Architecture** | HMRC Enterprise Architecture | Solution architecture, alignment with 17 architecture principles, technology choices | Yes |
| [TBD] | **Technical Evaluator - AI/ML** | HMRC Data Science / AI Lead | RAG architecture, LLM selection, bias mitigation, ATRS compliance, AI safety | Yes |
| [TBD] | **Technical Evaluator - Security** | HMRC CISO Office | Security design, NCSC Cloud Security Principles, Zero Trust, Cyber Essentials Plus, threat model | Yes |
| [TBD] | **Technical Evaluator - Accessibility** | HMRC Accessibility Specialist | WCAG 2.2 AA compliance, assistive technology testing, GOV.UK Design System, Welsh language | Yes |
| [TBD] | **Business Evaluator - Product** | HMRC Digital Services (Product Owner) | Requirements understanding, user needs, citizen satisfaction, helpline deflection goals | Yes |
| [TBD] | **Business Evaluator - Tax Policy** | HMRC Tax Policy | Tax domain accuracy, knowledge base quality, HMRC integration, escalation strategy | Yes |
| [TBD] | **Business Evaluator - Finance** | HMRC Finance | Cost evaluation, budget alignment, value for money, 3-year TCO, £75M savings realization | Yes |
| [TBD] | **Observer (Non-Voting)** | HMRC Legal | Contract terms review, IP rights, liability, termination clauses | No |
| [TBD] | **Observer (Non-Voting)** | HMRC Data Protection Officer | UK GDPR compliance, DPIA review, citizen consent, data subject rights | No |
| [TBD] | **Observer (Non-Voting)** | GDS Assessor | GDS Service Standard alignment (18 criteria), readiness for Live Assessment | No |

**Committee Size**: 8 voting members (quorum: 6 members minimum for consensus meeting)

**Scoring Approach**:
- Individual scoring by each voting member
- Consensus meeting to discuss and agree on final scores
- Outlier scores (>15 points difference from median) discussed and justified
- Final score = consensus score (not average of individual scores)

### 1.4 Conflict of Interest

All evaluators must disclose any conflicts of interest with vendors before evaluation begins.

**Conflict of Interest Declaration** (mandatory for all evaluators):
- [ ] Personal relationships with vendor employees (family, close friends)
- [ ] Financial interests in vendor companies (stock ownership, consulting fees, gifts >£50)
- [ ] Prior employment with vendor within past 2 years
- [ ] Concurrent consulting arrangements or side employment with vendor
- [ ] Participation in vendor-sponsored events or training (>£250 value)
- [ ] Other conflicts (describe): _______________

**Recusal Process**:
- Evaluators with conflicts MUST recuse themselves from evaluation of that specific vendor
- Recusal documented in evaluation records
- Replacement evaluator appointed if necessary to maintain quorum

**Penalties for Undisclosed Conflicts**:
- Disciplinary action per HMRC HR policy
- Entire evaluation may be invalidated and restarted
- Potential legal consequences if procurement rules violated

---

## 2. Evaluation Process

### 2.1 Process Flow

```
1. Proposals Received (Due Date: 2025-12-09, 5:00 PM GMT)
   “
2. Mandatory Qualifications Check (Pass/Fail) - 2 days
   “ (Qualified vendors only proceed)
3. Individual Technical Scoring (Blind to Cost) - 1 week
   “
4. Consensus Technical Scoring Meeting - 1 day
   “
5. Shortlist Top 3-5 Vendors (Technical Score e70/100) - 1 day
   “
6. Cost Proposals Opened (Shortlisted Vendors Only) - Same day
   “
7. Cost Scoring (Best Value Method) - 2 days
   “
8. Combined Technical + Cost Scoring (70% + 30%) - 1 day
   “
9. Vendor Presentations & Q&A (2 hours per vendor) - 1 week
   “
10. Reference Checks (3 references per vendor) - 1 week
   “
11. Final Scoring & Selection Decision - 2 days
   “
12. Selection Approval (HMRC SRO + CTO) - 1 day
   “
13. Vendor Notification (Selected + Non-Selected) - 1 day
   “
14. Contract Negotiation (Selected Vendor Only) - 2 weeks
```

### 2.2 Timeline

| Phase | Duration | Start Date | End Date | Responsible |
|-------|----------|------------|----------|-------------|
| **RFP Issued** | - | 2025-10-14 | - | HMRC Procurement |
| **Vendor Questions Due** | 2 weeks | 2025-10-14 | 2025-10-28 | Vendors |
| **Answers Published** | 1 week | 2025-10-28 | 2025-11-04 | HMRC Procurement |
| **Proposals Due** | 8 weeks | 2025-10-14 | 2025-12-09 (5pm GMT) | Vendors |
| **Mandatory Qualifications Check** | 2 days | 2025-12-09 | 2025-12-11 | Procurement + EA |
| **Individual Technical Scoring** | 1 week | 2025-12-11 | 2025-12-18 | All voting evaluators |
| **Consensus Scoring Meeting** | 1 day | 2025-12-19 | 2025-12-19 | Evaluation committee |
| **Shortlist Announcement** | 1 day | 2025-12-20 | 2025-12-20 | Evaluation lead |
| **Cost Proposals Opened** | - | 2025-12-20 | 2025-12-20 | Finance evaluator |
| **Cost Scoring** | 2 days | 2025-12-20 | 2025-12-23 | Finance evaluator |
| **Combined Scoring** | 1 day | 2025-12-23 | 2025-12-23 | Evaluation lead |
| **Vendor Presentations** | 1 week | 2026-01-06 | 2026-01-10 | Shortlisted vendors |
| **Reference Checks** | 1 week | 2026-01-13 | 2026-01-17 | Product/business evaluators |
| **Final Scoring & Decision** | 2 days | 2026-01-20 | 2026-01-20 | Evaluation committee |
| **Selection Approval** | 1 day | 2026-01-21 | 2026-01-21 | HMRC SRO + CTO |
| **Vendor Notification** | 1 day | 2026-01-22 | 2026-01-22 | HMRC Procurement |
| **Contract Negotiation** | 2 weeks | 2026-01-23 | 2026-02-06 | HMRC Legal + Procurement |
| **Contract Signing / Kickoff** | - | 2026-02-09 | 2026-02-09 | Week 1 |

---

## 3. Mandatory Qualifications (Pass/Fail)

Before scoring, vendors MUST meet ALL mandatory qualifications. **Failure on any item results in automatic disqualification** (no technical scoring). These align with SOW Section 6.1 (MQ-1 through MQ-7).

### 3.1 Mandatory Qualification Checklist

| ID | Qualification | Evidence Required | Pass/Fail | Evaluator | Notes |
|----|---------------|-------------------|-----------|-----------|-------|
| **MQ-1** | **Experience**: Minimum 5 years delivering AI/ML systems for UK Government or equivalent public sector | Company profile with project list (dates, clients, scope). At least 2 AI chatbot projects in production. | [ ] Pass<br>[ ] Fail | EA + Procurement | Must demonstrate RAG architecture experience. |
| **MQ-2** | **Security Clearance**: Key personnel eligible for Security Check (SC) clearance. Company eligible for UK Gov contracts. | NDA and DPA signed. Key personnel citizenship/residency declarations. | [ ] Pass<br>[ ] Fail | CISO + Procurement | SC clearance not required at proposal stage but eligibility confirmed. |
| **MQ-3** | **Reference Projects**: Minimum 3 reference projects in past 3 years demonstrating AI/ML, cloud (AWS/Azure), UK Gov authentication integration. | Reference project descriptions with client name, contact, scope, technologies, outcomes. | [ ] Pass<br>[ ] Fail | Product + EA | At least 1 reference must be UK Gov/public sector. |
| **MQ-4** | **Certifications - Company**: Cyber Essentials Plus (current, not expired). G-Cloud 14 listing or eligibility. | Certificate copies with expiration dates. G-Cloud 14 supplier ID or application proof. | [ ] Pass<br>[ ] Fail | CISO + Procurement | Cyber Essentials Plus is NON-NEGOTIABLE for HMG contracts. |
| **MQ-5** | **Certifications - Key Personnel**: AWS Certified Solutions Architect Professional (or equivalent), CISSP/CEH (Security Architect), AWS ML Specialty (AI/ML Lead), WCAG 2.2 AA certification (Accessibility Specialist). | Certificate copies for named key personnel in proposal. | [ ] Pass<br>[ ] Fail | EA + CISO | Must match CVs of key personnel provided. |
| **MQ-6** | **Financial Stability**: Minimum £5M annual revenue (past 2 years). Professional liability insurance £5M, cyber liability £2M. | 2 years audited financial statements. Insurance certificates (current, not expired). | [ ] Pass<br>[ ] Fail | Finance + Procurement | Vendor must be financially stable to deliver 12-month project. |
| **MQ-7** | **UK Presence**: UK office or registered UK subsidiary. Minimum 50% onshore team allocation. | UK company registration (Companies House number). Team allocation plan showing e50% UK-based staff. | [ ] Pass<br>[ ] Fail | Procurement + EA | On-site presence in London required for design workshops and GDS assessments. |
| **MQ-8** | **Accessibility Expertise**: At least 1 dedicated accessibility specialist with WCAG 2.2 AA certification and experience delivering compliant public sector services. | Accessibility specialist CV with IAAP CPACC or WAS certification. Reference projects with WCAG 2.2 AA audits. | [ ] Pass<br>[ ] Fail | Accessibility Specialist | WCAG 2.2 AA is legal requirement (Public Sector Bodies Accessibility Regulations 2018). |
| **MQ-9** | **Proposal Compliance - Timeliness**: Proposal submitted by 2025-12-09 at 5:00 PM GMT. | Email timestamp. | [ ] Pass<br>[ ] Fail | Procurement | Late proposals NOT accepted (no exceptions). |
| **MQ-10** | **Proposal Compliance - Format**: Technical proposal and cost proposal in separate PDF files. All required sections completed (Executive Summary, Company Overview, Technical Solution, Project Approach, Team, Experience, Assumptions). Page limits adhered to. | Visual inspection of PDFs. | [ ] Pass<br>[ ] Fail | Procurement | Proposals exceeding page limits penalized (5-point deduction per 10 pages over limit). |
| **MQ-11** | **Proposal Compliance - Key Personnel CVs**: CVs provided for Solution Architect, AI/ML Lead, Technical Lead, Security Architect. | CVs attached as separate PDF or in proposal appendix. | [ ] Pass<br>[ ] Fail | EA + CISO | CVs must include: Name, years of experience, relevant certifications, project references. |
| **MQ-12** | **Proposal Compliance - Evidence of Qualifications**: Cyber Essentials Plus certificate, G-Cloud 14 listing, financial statements, insurance certificates, key personnel certifications provided. | Separate PDF with all evidence documents. | [ ] Pass<br>[ ] Fail | Procurement | Missing evidence = automatic disqualification (cannot score without proof). |

### 3.2 Disqualification Procedure

1. **Initial Review** (2 days): Procurement Lead + Enterprise Architect review all proposals for mandatory qualifications
2. **Disqualification Identified**: If any MQ fails, document specific failure reason
3. **Evaluation Lead Confirmation**: Procurement Lead confirms failure with second reviewer (no single-person disqualification decision)
4. **Vendor Notification** (within 48 hours): Email vendor with specific MQ failure reason
5. **Vendor Clarification Period** (48 hours): Vendor may provide clarification if failure due to misunderstanding or missing evidence (e.g., "We have Cyber Essentials Plus but forgot to attach certificate - here it is")
6. **Final Determination**: Evaluation Lead makes final decision based on clarification
   - If clarification resolves issue (e.g., missing evidence now provided): Vendor proceeds to technical scoring
   - If clarification does not resolve issue (e.g., vendor does not have Cyber Essentials Plus): Vendor disqualified, no technical scoring

**Disqualified Vendors**:
- Notified within 5 business days of disqualification
- Provided written rationale for disqualification
- May request debrief call to understand gaps for future proposals

---

## 4. Technical Evaluation Criteria (100 Points)

Technical proposals are scored **blind to cost** to ensure unbiased evaluation. Cost proposals remain sealed until after technical evaluation and shortlisting.

### 4.1 Criteria Summary

Technical evaluation aligned with SOW Section 8.2. Total: **100 points** across 5 categories.

| Category | Weight | Max Points | Primary Evaluator(s) |
|----------|--------|------------|----------------------|
| **1. Technical Approach and Solution Design** | 35% | 35 | EA (Architecture) + EA (AI/ML) + CISO (Security) + Accessibility Specialist |
| **2. Project Approach and Methodology** | 20% | 20 | Product Owner + EA (Architecture) + Finance |
| **3. Team Qualifications and Experience** | 25% | 25 | EA (Architecture) + EA (AI/ML) + CISO + Product Owner |
| **4. Relevant Experience and References** | 15% | 15 | Product Owner + Tax Policy + Finance |
| **5. Understanding of Requirements and Problem Domain** | 5% | 5 | All evaluators (consensus) |
| **TOTAL** | **100%** | **100** | |

**Minimum Technical Score to Proceed**: 70/100 (vendors scoring <70 not shortlisted for cost evaluation, even if lowest cost)

---

### 4.2 Category 1: Technical Approach and Solution Design (35 points)

**Purpose**: Evaluate the proposed technical solution's quality, feasibility, alignment with HMRC requirements, and compliance with 17 architecture principles.

**Primary Evaluators**: EA (Architecture), EA (AI/ML), CISO (Security), Accessibility Specialist

#### Subcriteria

| Subcriterion | Points | Key Evaluation Questions |
|--------------|--------|-------------------------|
| **1.1 RAG Architecture Quality** | 10 | " Is RAG pipeline well-designed (embedding ’ vector search ’ LLM generation ’ validation ’ source citation)?<br>" Are embedding model and vector database choices appropriate (AWS Titan Embeddings, OpenSearch k-NN)?<br>" Is knowledge base ingestion pipeline automated and scalable (100,000+ HMRC documents)?<br>" Is 100% source citation implemented with links to GOV.UK?<br>" Is confidence scoring implemented with human escalation threshold (<70%)?<br>**Aligns with Principle #12 (RAG for AI Accuracy), FR-2, FR-3, FR-4** |
| **1.2 AI Safety and Responsible AI** | 8 | " Is bias mitigation strategy comprehensive (quarterly testing across 9 protected characteristics)?<br>" Are guardrails robust (hallucination detection, prompt injection defense, toxic content filtering)?<br>" Is ATRS creation plan clear (Tier 1 + Tier 2, publication on GOV.UK)?<br>" Is explainability strategy sound (100% source citation, "Why did ChatBot say this?" feature)?<br>" Is human-in-the-loop implemented (escalation for complex queries, appeals, disputes)?<br>**Aligns with Principle #5 (Responsible AI and ATRS), NFR-SEC-6, BR-6** |
| **1.3 Security and Compliance Architecture** | 7 | " Is Zero Trust security model implemented (no network-based trust, continuous verification)?<br>" Are all 14 NCSC Cloud Security Principles addressed with specific controls?<br>" Is UK GDPR compliance strategy clear (DPIA, data minimization, citizen consent, data subject rights)?<br>" Is encryption comprehensive (TLS 1.3 in transit, AES-256 at rest)?<br>" Is secrets management via AWS Secrets Manager (no hardcoded credentials)?<br>" Is Cyber Essentials Plus compliance approach documented?<br>**Aligns with Principle #3 (Security by Design - Zero Trust), #7 (Data Sovereignty), NFR-SEC-1 to NFR-SEC-5** |
| **1.4 Architecture Quality and Scalability** | 6 | " Is high-level architecture clear (C4 Context, Container, Component diagrams)?<br>" Are microservices boundaries well-defined (Citizen Identity, Conversational AI, Knowledge Management, HMRC Integration, Audit & Compliance)?<br>" Is technology stack aligned with approved stack or well-justified alternatives (Python, Node.js, React, AWS Bedrock, PostgreSQL, OpenSearch)?<br>" Is scalability strategy credible (ECS Fargate auto-scaling, RDS read replicas, ElastiCache)?<br>" Does solution meet performance targets (<2s p95 latency, 500 req/s throughput)?<br>**Aligns with Principle #1 (Cloud-First), #9 (Approved Tech Stack), #11 (Microservices), NFR-P-1, NFR-P-2, NFR-S-1** |
| **1.5 Accessibility and Welsh Language** | 4 | " Is WCAG 2.2 Level AA compliance strategy comprehensive (automated + manual testing, assistive technologies)?<br>" Is GOV.UK Design System integrated (gov.uk-frontend components)?<br>" Is Welsh language support architecture sound (bilingual UI toggle, Welsh AI responses, Welsh knowledge base)?<br>" Is Plain English content design approach clear (reading age 9, GOV.UK style guide)?<br>**Aligns with Principle #4 (Accessibility-First Design), NFR-U-2, NFR-U-3, FR-9, FR-10, BR-5** |

#### Scoring Rubric (Apply to Each Subcriterion)

| Score Range | Description | Criteria |
|-------------|-------------|----------|
| **90-100%** (Excellent) | Exceeds expectations; innovative; demonstrates deep expertise; minimal risks; fully aligned with all architecture principles | " All requirements met + innovative approach<br>" Clear evidence of best practices<br>" No gaps or concerns<br>" Strong alignment with principles |
| **75-89%** (Good) | Meets all expectations; sound approach; minor concerns or areas for clarification; aligned with principles | " All requirements met<br>" Credible approach<br>" Minor gaps addressable in Q&A<br>" Good alignment with principles |
| **60-74%** (Adequate) | Meets most expectations; workable approach; some concerns or gaps requiring discussion | " Most requirements met<br>" Some gaps or ambiguities<br>" Concerns addressable with vendor clarifications<br>" Partial alignment with principles |
| **40-59%** (Weak) | Meets minimum expectations; significant concerns; substantial gaps or risks | " Minimum requirements met<br>" Significant gaps or risks<br>" Substantial clarification needed<br>" Weak alignment with principles |
| **0-39%** (Unacceptable) | Does not meet expectations; major flaws; unworkable approach; principles violated | " Requirements not met<br>" Fundamental design flaws<br>" Unworkable approach<br>" Non-negotiable principles violated |

#### Scoring Template (per vendor)

**Vendor Name**: _______________

| Subcriterion | Max Points | Score | Justification (specific references to proposal sections, requirement IDs, principle alignment) |
|--------------|------------|-------|-----------------------------------------------------------------------------------------------|
| 1.1 RAG Architecture Quality | 10 | ___ | Example: "Excellent RAG design with AWS Titan Embeddings, OpenSearch k-NN, and LangChain orchestration (Section 4.2.1). 100% source citation with GOV.UK links (Section 4.2.3). Confidence scoring with 70% escalation threshold (Section 4.2.4). Fully aligns with Principle #12 and FR-2, FR-3, FR-4. Score: 9/10 (minor: no mention of retrieval quality metrics like precision@k)." |
| 1.2 AI Safety and Responsible AI | 8 | ___ | |
| 1.3 Security and Compliance | 7 | ___ | |
| 1.4 Architecture Quality & Scalability | 6 | ___ | |
| 1.5 Accessibility & Welsh Language | 4 | ___ | |
| **Category 1 Total** | **35** | **___** | |

---

### 4.3 Category 2: Project Approach and Methodology (20 points)

**Purpose**: Evaluate the vendor's approach to delivering the project, managing risks, ensuring quality, and adhering to the 12-month timeline.

**Primary Evaluators**: Product Owner, EA (Architecture), Finance

#### Subcriteria

| Subcriterion | Points | Key Evaluation Questions |
|--------------|--------|-------------------------|
| **2.1 Agile Delivery and Timeline Realism** | 8 | " Is Agile methodology appropriate (Scrum, Kanban)?<br>" Is 12-month timeline realistic with 6 milestones (M0 through M6)?<br>" Are phases logically sequenced (Design Weeks 1-8, Development Weeks 9-32, Testing Weeks 33-40, Beta Weeks 41-48, Production Weeks 49-52)?<br>" Is critical path identified with dependencies?<br>" Is there buffer for risks/unknowns?<br>**Aligns with SOW Section 5 (Timeline), Principle #14 (CI/CD)** |
| **2.2 Risk Management** | 6 | " Are top 10+ risks identified proactively (LLM API cost overruns, Government Gateway integration delays, DPIA approval delays, GDS assessment failure)?<br>" Are mitigation strategies credible and actionable?<br>" Is risk monitoring process defined (risk register, monthly reviews)?<br>" Does vendor show awareness of UK Gov project risks (approvals, GDS assessments, security compliance)?<br>**Aligns with SOW Section 9.12 (Change Management)** |
| **2.3 Quality Assurance and Testing** | 6 | " Is testing strategy comprehensive (unit e80% coverage, integration, E2E, performance, security, accessibility, AI accuracy >95%, bias <5% disparity)?<br>" Are QA resources adequate (QA Lead, 2 QA Engineers)?<br>" Is test automation planned (CI/CD quality gates)?<br>" Are acceptance criteria for deliverables clear and measurable?<br>**Aligns with Principle #15 (Testing Strategy), NFR-P-1, NFR-SEC-4, NFR-U-2** |

#### Scoring Template

**Vendor Name**: _______________

| Subcriterion | Max Points | Score | Justification |
|--------------|------------|-------|---------------|
| 2.1 Agile Delivery & Timeline Realism | 8 | ___ | |
| 2.2 Risk Management | 6 | ___ | |
| 2.3 Quality Assurance & Testing | 6 | ___ | |
| **Category 2 Total** | **20** | **___** | |

---

### 4.4 Category 3: Team Qualifications and Experience (25 points)

**Purpose**: Evaluate the vendor's team expertise, certifications, experience, and ability to deliver.

**Primary Evaluators**: EA (Architecture), EA (AI/ML), CISO, Product Owner

#### Subcriteria

| Subcriterion | Points | Key Evaluation Questions |
|--------------|--------|-------------------------|
| **3.1 Key Personnel Qualifications** | 12 | " **Solution Architect**: 10+ years experience, AWS Certified Solutions Architect Professional, UK Gov experience?<br>" **AI/ML Lead**: 8+ years, AWS ML Specialty, RAG architecture experience?<br>" **Technical Lead**: 8+ years, team leadership experience, Agile delivery?<br>" **Security Architect**: 8+ years, CISSP/CEH, NCSC Cloud Security Principles expertise?<br>" **Accessibility Specialist**: WCAG 2.2 AA certified (IAAP CPACC or WAS), UK public sector experience?<br>" Do CVs demonstrate depth in required technologies (AWS, Python, React, LLMs, GOV.UK Design System)?<br>**Aligns with SOW Section 6.4 (Team Requirements), MQ-5** |
| **3.2 Team Composition and Allocation** | 5 | " Is team size adequate (20-25 FTE over 12 months)?<br>" Are key personnel dedicated (e50% allocation for Solution Architect, e75% for AI/ML Lead and Technical Lead)?<br>" Is onshore/offshore mix compliant (e50% UK-based)?<br>" Are backup resources identified (no single point of failure)?<br>**Aligns with SOW Section 6.4, MQ-7** |
| **3.3 UK Government and Tax Domain Expertise** | 5 | " Does team have UK Gov/public sector experience (HMRC, GDS, NHS, MOD, DVLA, DWP)?<br>" Do they understand UK tax system (Self Assessment, PAYE, VAT, National Insurance)?<br>" Have they integrated with Government Gateway or HMRC systems?<br>" Is GDS Service Standard experience demonstrated (Discovery, Alpha, Beta, Live phases)?<br>**Aligns with SOW Section 6.2 (Preferred Qualifications PQ-1, PQ-2)** |
| **3.4 AI/ML and Chatbot Expertise** | 3 | " Does team have production AI chatbot experience (not just PoCs)?<br>" Have they implemented RAG architecture with LLMs (OpenAI, Anthropic, AWS Bedrock)?<br>" Is bias testing and fairness audit experience demonstrated?<br>" Have they published ATRS records for previous AI projects?<br>**Aligns with SOW Section 6.2 (Preferred Qualifications PQ-4)** |

#### Scoring Template

**Vendor Name**: _______________

| Subcriterion | Max Points | Score | Justification |
|--------------|------------|-------|---------------|
| 3.1 Key Personnel Qualifications | 12 | ___ | |
| 3.2 Team Composition & Allocation | 5 | ___ | |
| 3.3 UK Gov & Tax Domain Expertise | 5 | ___ | |
| 3.4 AI/ML & Chatbot Expertise | 3 | ___ | |
| **Category 3 Total** | **25** | **___** | |

---

### 4.5 Category 4: Relevant Experience and References (15 points)

**Purpose**: Evaluate vendor's track record delivering similar projects successfully.

**Primary Evaluators**: Product Owner, Tax Policy, Finance

#### Subcriteria

| Subcriterion | Points | Key Evaluation Questions |
|--------------|--------|-------------------------|
| **4.1 Reference Project Relevance** | 9 | " Are 3+ reference projects similar in scope and complexity (AI chatbot, RAG, UK Gov/public sector)?<br>" Do references demonstrate required capabilities (LLM, Government Gateway integration, WCAG 2.2 AA, Welsh language)?<br>" Were projects successful (on time, on budget, quality)?<br>" Are client names, contacts, and detailed outcomes provided?<br>" **Reference Check Results** (conducted in Phase 10): Do reference clients give positive feedback?<br>**Aligns with SOW Section 7.1 (Proposal Format - Section 7: Experience and References), MQ-3** |
| **4.2 UK Government and GDS Experience** | 4 | " Has vendor delivered services that passed GDS Service Standard Live Assessment (18 criteria)?<br>" Do they have experience with GDS phases (Discovery, Alpha, Beta, Live)?<br>" Are they familiar with GDS Design System and GOV.UK style guide?<br>" Have they navigated UK Gov governance (Architecture Review Boards, DPIAs, security assessments)?<br>**Aligns with SOW Section 6.2 (PQ-2), BR-4** |
| **4.3 Financial and Organizational Stability** | 2 | " Are financial statements sound (£5M+ revenue, profitable or path to profitability)?<br>" Is company stable (years in business, client retention, no recent layoffs/restructuring)?<br>" Are insurance requirements met (£5M professional liability, £2M cyber liability)?<br>**Aligns with MQ-6** |

#### Reference Project Evaluation (Per Reference)

For each of 3 reference projects, evaluate:

| Reference | Client Name & Contact | Similarity (High/Med/Low) | Technologies Used | On Time? | On Budget? | Quality? | Reference Check Result | Notes |
|-----------|-----------------------|---------------------------|-------------------|----------|------------|----------|------------------------|-------|
| Ref 1 | | | | | | | | |
| Ref 2 | | | | | | | | |
| Ref 3 | | | | | | | | |

**Similarity Scoring**:
- **High Similarity** (3 points): AI chatbot for UK Gov/public sector, RAG architecture, Government Gateway integration, WCAG 2.2 AA, production use
- **Medium Similarity** (2 points): AI chatbot or conversational AI, public sector (not UK), some accessibility compliance
- **Low Similarity** (1 point): Tangentially related (e.g., general AI/ML project, not chatbot)

#### Scoring Template

**Vendor Name**: _______________

| Subcriterion | Max Points | Score | Justification |
|--------------|------------|-------|---------------|
| 4.1 Reference Project Relevance | 9 | ___ | |
| 4.2 UK Government & GDS Experience | 4 | ___ | |
| 4.3 Financial & Organizational Stability | 2 | ___ | |
| **Category 4 Total** | **15** | **___** | |

---

### 4.6 Category 5: Understanding of Requirements and Problem Domain (5 points)

**Purpose**: Evaluate how well vendor understands the HMRC ChatBot problem, requirements, and business drivers.

**Primary Evaluators**: All evaluators (consensus)

#### Subcriteria

| Subcriterion | Points | Key Evaluation Questions |
|--------------|--------|-------------------------|
| **5.1 Problem and Business Context Understanding** | 2 | " Does vendor demonstrate understanding of HMRC's business drivers (£75M savings target, 30% helpline deflection by Year 3, citizen satisfaction >70% NPS)?<br>" Do they articulate WHY HMRC needs AI ChatBot (not just WHAT)?<br>" Do they show empathy for UK citizens' tax guidance needs (accessibility, Plain English, Welsh language)?<br>**Aligns with SOW Section 1.2 (Background), BR-1, BR-2, BR-3** |
| **5.2 Requirements Comprehension** | 2 | " Are all key requirements addressed in proposal (7 BR, 11 FR, 21 NFR, 5 INT)?<br>" Are requirements interpreted correctly (no major misunderstandings)?<br>" Are gaps, ambiguities, or risks in requirements identified proactively?<br>**Aligns with SOW Section 3 (Requirements)** |
| **5.3 UK Tax Domain Knowledge** | 1 | " Does vendor demonstrate understanding of UK tax system (Self Assessment, PAYE, VAT, National Insurance)?<br>" Do they understand HMRC's role and responsibilities?<br>" Are tax-specific risks identified (e.g., accuracy of tax advice, citizen liability if ChatBot gives wrong guidance)?<br>**Aligns with SOW Section 1.2, Tax Policy evaluation** |

#### Scoring Template

**Vendor Name**: _______________

| Subcriterion | Max Points | Score | Justification |
|--------------|------------|-------|---------------|
| 5.1 Problem & Business Context | 2 | ___ | |
| 5.2 Requirements Comprehension | 2 | ___ | |
| 5.3 UK Tax Domain Knowledge | 1 | ___ | |
| **Category 5 Total** | **5** | **___** | |

---

### 4.7 Technical Scoring Summary

**Vendor Name**: _______________
**Evaluator**: _______________
**Date**: _______________

| Category | Max Points | Score | Percentage |
|----------|------------|-------|------------|
| 1. Technical Approach & Solution Design | 35 | ___ | ___% |
| 2. Project Approach & Methodology | 20 | ___ | ___% |
| 3. Team Qualifications & Experience | 25 | ___ | ___% |
| 4. Relevant Experience & References | 15 | ___ | ___% |
| 5. Understanding of Requirements | 5 | ___ | ___% |
| **TOTAL TECHNICAL SCORE** | **100** | **___** | **___%** |

**Overall Assessment**:
- [ ] **Excellent (85-100)**: Strong candidate, few concerns, recommend shortlist
- [ ] **Good (70-84)**: Solid candidate, some minor concerns, recommend shortlist
- [ ] **Adequate (60-69)**: Marginal candidate, significant concerns, consider shortlist only if few alternatives
- [ ] **Weak (40-59)**: Weak candidate, substantial gaps, do not shortlist
- [ ] **Unacceptable (0-39)**: Unacceptable, major flaws, do not shortlist

**Key Strengths** (top 3):
1. _______________
2. _______________
3. _______________

**Key Weaknesses / Concerns** (top 3):
1. _______________
2. _______________
3. _______________

**Recommendation**:
- [ ] **Shortlist for Cost Evaluation**: Technical score e70/100, meets all mandatory qualifications, acceptable risk level
- [ ] **Do Not Shortlist**: Technical score <70/100 OR significant concerns OR unacceptable risks

---

## 5. Cost Evaluation (For Shortlisted Vendors Only)

Cost proposals are opened **only for shortlisted vendors** (technical score e70/100) after technical evaluation and consensus meeting are complete.

### 5.1 Cost Scoring Methodology

**Method**: **Best Value Approach** (not lowest price wins)

**Formula**:
- **Technical Score**: 70% weight (from Phase 4 technical evaluation)
- **Cost Score**: 30% weight (calculated below using lowest-price scaling)
- **Final Score** = (Technical Score × 0.7) + (Cost Score × 0.3)

**Cost Score Calculation** (30 points max):
- Vendor with **lowest 3-year TCO** receives **30 points**
- Other vendors scored proportionally: **Cost Score = (Lowest TCO / Vendor's TCO) × 30 points**

**Example**:
- Vendor A: 3-Year TCO = £18M ’ Cost Score = (£16M / £18M) × 30 = **26.67 points**
- Vendor B: 3-Year TCO = £16M ’ Cost Score = (£16M / £16M) × 30 = **30.00 points** (lowest)
- Vendor C: 3-Year TCO = £20M ’ Cost Score = (£16M / £20M) × 30 = **24.00 points**

**Rationale for 70/30 Split**:
- **70% Technical**: Technical quality, AI accuracy, security, and compliance are critical for citizen-facing tax guidance system. Poor technical solution creates unacceptable risk (inaccurate tax advice, data breaches, accessibility failures).
- **30% Cost**: Cost is important for taxpayer value for money, but not the sole driver. A lower-cost vendor with weak technical approach creates greater long-term cost (rework, security incidents, GDS assessment failures, reputational damage).

### 5.2 Cost Evaluation Criteria

**Primary Evaluator**: Finance (with input from Product Owner and EA for value assessment)

| Criterion | Evaluation Questions | Red Flags |
|-----------|---------------------|-----------|
| **3-Year Total Cost of Ownership (TCO)** | " What is total 3-year TCO (capex + opex)?<br>" Design/development capex: £4.5M-£5.5M budget (within range?)<br>" Annual opex (AWS, LLM API, support): £4M-£5M budget (within range?)<br>" 3-Year TCO: £16.5M-£20.5M budget (within range?) | " Cost significantly above budget (>£22M) indicates vendor doesn't understand scope or padding estimates<br>" Cost significantly below budget (<£14M) indicates vendor underestimating scope or planning to cut corners |
| **Cost Breakdown Transparency** | " Is cost breakdown detailed (labor by role, AWS infrastructure, LLM API, third-party services)?<br>" Are hourly/daily rates reasonable for UK market?<br>" Is labor allocation justified (FTE × months)?<br>" Are infrastructure costs realistic (not underestimated)? | " Vague cost categories (e.g., "Development: £3M" with no detail)<br>" Unrealistic labor rates (£50/day for Senior Architect indicates offshore with hidden risks)<br>" Infrastructure costs too low (£100K/year for AWS when realistic is £500K+) |
| **LLM API Cost Realism** | " Are LLM API costs estimated realistically based on token usage projections?<br>" Target: <£0.50 per conversation (see ATRS record)<br>" Are caching and optimization strategies to reduce token usage described? | " No LLM API costs included (major risk - could be £1M+/year)<br>" Unrealistic token estimates (e.g., 1M tokens/year when realistic is 100M+ tokens/year) |
| **Value for Money** | " Considering technical quality (technical score), is cost reasonable?<br>" Cost per technical point: £X TCO / Y technical score = £Z/point<br>" How does £Z/point compare across vendors?<br>" Does vendor provide value-added services (e.g., free knowledge transfer, extended warranty, performance guarantees)? | " High cost per technical point (e.g., £250K/point vs. £200K/point for others) indicates poor value<br>" Fixed-price vendor with aggressive padding (30% contingency) vs. T&M vendor with realistic buffer (10%) |
| **Payment Terms and Milestones** | " Are payment milestones aligned with SOW Section 9.2 (10% signing, 15% design, 20% dev, 20% testing, 10% private beta, 20% production, 5% warranty)?<br>" Is 5% retainage held until warranty completion?<br>" Are payment terms Net 30 days? | " Payment terms front-loaded (e.g., 50% upfront) indicating vendor cash flow issues or lack of confidence in delivery<br>" No retainage (removes incentive for warranty support) |
| **Assumptions and Exclusions** | " Are cost assumptions clearly stated and reasonable?<br>" Are exclusions appropriate (e.g., HMRC pays AWS bills directly, HMRC provides subject matter experts)?<br>" Are there hidden costs (e.g., travel, tools, licenses) not included? | " Unrealistic assumptions (e.g., "HMRC provides 100% of testing effort")<br>" Excessive exclusions (e.g., "Security testing not included" when SOW requires it)<br>" Hidden costs discovered in fine print |

### 5.3 Cost Analysis Template

**Completed by**: Finance Evaluator
**Date**: _______________

#### 5.3.1 Cost Summary Comparison

| Vendor | Design/Dev Capex (£M) | Annual Opex (£M) | Year 1 Total | Year 2 Opex | Year 3 Opex | **3-Year TCO (£M)** | Cost Score (30 pts max) | Rank by Cost |
|--------|-----------------------|------------------|--------------|-------------|-------------|---------------------|-------------------------|--------------|
| Vendor A | £___ | £___ | £___ | £___ | £___ | **£___** | ___ | ___ |
| Vendor B | £___ | £___ | £___ | £___ | £___ | **£___** | ___ | ___ |
| Vendor C | £___ | £___ | £___ | £___ | £___ | **£___** | ___ | ___ |
| **HMRC Budget** | **£4.5-£5.5M** | **£4-£5M** | **£8.5-£10.5M** | **£4-£5M** | **£4-£5M** | **£16.5-£20.5M** | - | - |

#### 5.3.2 Cost Breakdown Comparison

| Cost Category | Vendor A | Vendor B | Vendor C | HMRC Notes |
|---------------|----------|----------|----------|------------|
| **Capex: Design/Development (Months 1-12)** |
| Labor (by role/phase) | £___ | £___ | £___ | |
| AWS Infrastructure (Year 1) | £___ | £___ | £___ | |
| LLM API Costs (AWS Bedrock, Year 1) | £___ | £___ | £___ | |
| Third-Party Tools (Monitoring, Security, CI/CD) | £___ | £___ | £___ | |
| **Subtotal Capex (Year 1)** | **£___** | **£___** | **£___** | |
| **Opex: Ongoing Support (Year 2)** |
| Annual Support & Maintenance | £___ | £___ | £___ | |
| AWS Infrastructure (Year 2) | £___ | £___ | £___ | |
| LLM API Costs (Year 2) | £___ | £___ | £___ | |
| Third-Party Tools (Year 2) | £___ | £___ | £___ | |
| **Subtotal Opex (Year 2)** | **£___** | **£___** | **£___** | |
| **Opex: Ongoing Support (Year 3)** |
| Annual Support & Maintenance | £___ | £___ | £___ | |
| AWS Infrastructure (Year 3) | £___ | £___ | £___ | |
| LLM API Costs (Year 3) | £___ | £___ | £___ | |
| Third-Party Tools (Year 3) | £___ | £___ | £___ | |
| **Subtotal Opex (Year 3)** | **£___** | **£___** | **£___** | |
| **3-YEAR TCO** | **£___** | **£___** | **£___** | |

#### 5.3.3 Value Analysis

| Vendor | 3-Year TCO (£M) | Technical Score (100 pts) | **Cost per Technical Point** (£TCO / Tech Score) | Value Rank | Notes |
|--------|-----------------|---------------------------|--------------------------------------------------|------------|-------|
| Vendor A | £___ | ___ | £___/point | ___ | |
| Vendor B | £___ | ___ | £___/point | ___ | |
| Vendor C | £___ | ___ | £___/point | ___ | |

**Best Value Analysis**:
- Vendor with lowest £/point = best value (combines technical quality and cost)
- Example: Vendor B (£16M TCO, 82 technical score) = £195K/point vs. Vendor A (£18M TCO, 76 technical score) = £237K/point ’ Vendor B is better value

#### 5.3.4 Cost Evaluation Summary

**Finance Evaluator Assessment**:

| Vendor | Cost Score (30 pts) | Cost Breakdown Transparency | Value for Money | Payment Terms | Assumptions Reasonable? | **Overall Cost Rating** |
|--------|---------------------|-----------------------------|--------------------|---------------|-------------------------|-------------------------|
| Vendor A | ___ | Good/Adequate/Weak | Good/Adequate/Weak | Favorable/Acceptable/Unfavorable | Yes/No/Concerns | Excellent/Good/Adequate/Weak |
| Vendor B | ___ | Good/Adequate/Weak | Good/Adequate/Weak | Favorable/Acceptable/Unfavorable | Yes/No/Concerns | Excellent/Good/Adequate/Weak |
| Vendor C | ___ | Good/Adequate/Weak | Good/Adequate/Weak | Favorable/Acceptable/Unfavorable | Yes/No/Concerns | Excellent/Good/Adequate/Weak |

**Cost Concerns** (if any):
- Vendor A: _______________
- Vendor B: _______________
- Vendor C: _______________

---

## 6. Combined Scoring

### 6.1 Final Scoring Formula

**Final Score = (Technical Score × 0.7) + (Cost Score × 0.3)**

Where:
- **Technical Score**: 0-100 points from Phase 4 technical evaluation (consensus score from evaluation committee)
- **Cost Score**: 0-30 points from Phase 5 cost evaluation (lowest TCO = 30 points, others scaled proportionally)

### 6.2 Combined Scoring Summary

**Completed by**: Evaluation Lead
**Date**: _______________

| Vendor | Technical Score (100 pts) | Technical Weighted (70%) | Cost Score (30 pts) | Cost Weighted (30%) | **Final Score (100 pts)** | Rank |
|--------|---------------------------|--------------------------|---------------------|---------------------|---------------------------|------|
| Vendor A | ___ | ___ × 0.7 = ___ | ___ | ___ × 1.0 = ___ | **___** | ___ |
| Vendor B | ___ | ___ × 0.7 = ___ | ___ | ___ × 1.0 = ___ | **___** | ___ |
| Vendor C | ___ | ___ × 0.7 = ___ | ___ | ___ × 1.0 = ___ | **___** | ___ |

**Example Calculation**:
- **Vendor B**: Technical = 82/100, Cost = 30/30 (lowest TCO)
  - Technical Weighted = 82 × 0.7 = 57.4
  - Cost Weighted = 30 × 1.0 = 30.0
  - **Final Score = 57.4 + 30.0 = 87.4** (highest, recommended)

- **Vendor A**: Technical = 76/100, Cost = 26.67/30
  - Technical Weighted = 76 × 0.7 = 53.2
  - Cost Weighted = 26.67 × 1.0 = 26.67
  - **Final Score = 53.2 + 26.67 = 79.87** (second)

**Visual Scoring Matrix**:

```
Final Score = Technical (70%) + Cost (30%)

100 $                      Vendor B (87.4)
    
 90 $      Vendor A (79.87)
    
 80 $           Vendor C (75.2)
    
 70 $  [Minimum threshold = 70]
    
 60 $
    
 50 $
    
 40 $
    
 30 $
    
 20 $
    
 10 $
    
  0 4                                    
     Technical  Cost  Combined
```

---

## 7. Vendor Presentations (For Shortlisted Vendors Only)

Shortlisted vendors (top 3-5 from Phase 4+5) present their proposals to the HMRC evaluation committee.

### 7.1 Presentation Format

**Date**: 2026-01-06 to 2026-01-10 (Week of presentations, vendors scheduled individually)
**Duration**: **2 hours per vendor**
- Vendor presentation: **60 minutes** (strictly enforced with time warnings at 45 min, 55 min)
- Q&A with evaluation committee: **60 minutes**

**Location**: HMRC offices, 10 South Colonnade, London E14 4PU (or virtual if required)

**Attendees** (HMRC side):
- **Voting Members**: All 8 evaluation committee members (EA Architecture, EA AI/ML, CISO, Accessibility Specialist, Product Owner, Tax Policy, Finance, Procurement Lead)
- **Observers (Non-Voting)**: Legal, Data Protection Officer, GDS Assessor
- **Additional Stakeholders**: HMRC SRO (if available), Technical Leads, Domain Architects
- **Note-Taker**: Non-voting administrative staff to document Q&A

**Attendees** (Vendor side):
- **Maximum 5 vendor attendees**:
  - Solution Architect (mandatory)
  - AI/ML Lead (mandatory)
  - Technical Lead (mandatory)
  - Security Architect (recommended)
  - Additional attendee (e.g., Project Manager, Accessibility Specialist, or Executive Sponsor)

**Presentation Content** (suggested structure):
1. **Company Overview** (5 min): Brief intro, financial stability, UK Gov experience
2. **Team Introductions** (5 min): Key personnel introduce themselves (name, role, relevant experience)
3. **Solution Overview** (10 min): High-level architecture, key design decisions
4. **Technical Deep-Dive** (30 min):
   - RAG architecture demo (live or mock)
   - C4 diagrams walkthrough (Context, Container, Component)
   - AI safety and bias mitigation strategy
   - Security design (Zero Trust, NCSC principles)
   - Accessibility strategy (WCAG 2.2 AA, GOV.UK Design System)
   - Welsh language support
5. **Project Delivery Approach** (10 min): Timeline, milestones, risk management, Agile methodology
6. **Q&A** (60 min): Open discussion with evaluation committee

**Presentation Rules**:
- Vendor may use slides (PowerPoint/PDF), live demos (mockups acceptable), or architecture diagrams
- No video recordings by vendor (HMRC may record for internal use only)
- Questions may interrupt presentation (not held until end) - be flexible
- Follow-up materials (e.g., additional diagrams, clarifications) may be submitted within 48 hours of presentation

### 7.2 Presentation Evaluation

**Scoring Impact**: Presentations do NOT add new points, but may **adjust existing technical scores** (+/- up to 10 points per category) based on:

**Positive Adjustments** (increase scores):
- **Clarifications that resolve concerns**: E.g., vendor explains RAG architecture ambiguity from proposal, demonstrates understanding ’ increase Category 1.1 score by 2 points
- **Strong demo or proof-of-concept**: Vendor shows working RAG prototype with HMRC-like knowledge base ’ increase Category 1.1 score by 3 points
- **Team chemistry and competence**: Key personnel demonstrate deep expertise, answer technical questions confidently ’ increase Category 3.1 score by 2 points
- **Proactive risk identification**: Vendor identifies risks we missed and proposes mitigations ’ increase Category 2.2 score by 1 point

**Negative Adjustments** (decrease scores):
- **Red flags or concerning answers**: E.g., vendor cannot explain how they'll meet <2s latency target ’ decrease Category 1.4 score by 3 points
- **Weak team expertise**: Key personnel struggle to answer technical questions, lack depth ’ decrease Category 3.1 score by 5 points
- **Overconfidence or unrealistic claims**: E.g., "We can deliver in 6 months" when SOW requires 12 months ’ decrease Category 2.1 score by 2 points
- **Poor communication or unprofessionalism**: Vendor is defensive, dismissive of concerns, or unprepared ’ decrease Category 5 (Understanding) score by 1 point

**Post-Presentation Process**:
1. **Immediate Debrief** (30 min after each vendor presentation): Evaluation committee discusses observations, concerns, and whether scores should be adjusted
2. **Score Adjustments Documented**: Any score changes documented with rationale in evaluation records
3. **Updated Scores Finalized**: Updated technical scores feed into final combined scoring (Technical 70% + Cost 30%)

### 7.3 Presentation Evaluation Template

**Vendor Name**: _______________
**Presentation Date**: _______________
**Attendees**: _______________

| Evaluation Dimension | Rating (1-5) | Notes |
|----------------------|--------------|-------|
| **Clarity of Presentation** | 1 2 3 4 5 | Was presentation clear, well-structured, easy to follow? |
| **Technical Depth** | 1 2 3 4 5 | Did vendor demonstrate deep technical expertise? |
| **Q&A Responsiveness** | 1 2 3 4 5 | Did vendor answer questions thoughtfully and directly? |
| **Team Competence** | 1 2 3 4 5 | Do key personnel inspire confidence in delivery? |
| **Cultural Fit** | 1 2 3 4 5 | Do we feel comfortable working with this team for 12 months? |

**Key Insights from Presentation**:
1. _______________
2. _______________
3. _______________

**Concerns Raised or Unresolved**:
1. _______________
2. _______________
3. _______________

**Score Adjustments Recommended**:
- Category ___ (___): Adjust from ___ to ___ (± ___ points) - Rationale: _______________
- Category ___ (___): Adjust from ___ to ___ (± ___ points) - Rationale: _______________

**Overall Presentation Assessment**:
- [ ] **Excellent**: Significantly strengthened confidence in vendor, recommend selection
- [ ] **Good**: Solid presentation, maintained or slightly improved confidence
- [ ] **Adequate**: Acceptable but no improvement in confidence, some concerns remain
- [ ] **Weak**: Raised significant concerns, lowered confidence in vendor
- [ ] **Unacceptable**: Major red flags, recommend removing from shortlist

---

## 8. Reference Checks

### 8.1 Reference Check Process

For each shortlisted vendor, contact **all provided references** (minimum 3 per SOW requirement).

**Assigned To**: Product Owner + Business Evaluator (Tax Policy or Finance)
**Timeline**: 1 week (2026-01-13 to 2026-01-17)
**Method**: Phone call (30-45 min per reference), followed by written summary

**Reference Check Template**:

**Reference Information**:
- Vendor Name: _______________
- Client Organization: _______________
- Contact Name: _______________
- Contact Role/Title: _______________
- Contact Email/Phone: _______________
- Project Name: _______________
- Project Timeframe: _______________
- Project Scope (brief): _______________
- Technologies Used: _______________

**Questions**:

1. **Project Scope**: Can you describe the project [Vendor] delivered for you?
   - **Notes**: _______________

2. **On-Time Delivery**: Was the project delivered on schedule? If not, what caused delays?
   - [ ] On time
   - [ ] Minor delays (<10% over timeline)
   - [ ] Significant delays (>10% over timeline)
   - **Notes**: _______________

3. **On-Budget Delivery**: Was the project delivered within budget? Were there change orders or cost overruns?
   - [ ] On budget (no overruns)
   - [ ] Minor overruns (<10% over budget)
   - [ ] Significant overruns (>10% over budget)
   - **Notes**: _______________

4. **Quality**: Was the quality of deliverables high? Did it meet your expectations?
   - [ ] Exceeded expectations (outstanding quality, few bugs)
   - [ ] Met expectations (acceptable quality, normal bug rate)
   - [ ] Below expectations (quality issues, many bugs, rework required)
   - **Notes**: _______________

5. **Team Effectiveness**: How effective was the vendor's team? Communication? Responsiveness? Professionalism?
   - [ ] Excellent (proactive, responsive, professional)
   - [ ] Good (solid communication, responsive to issues)
   - [ ] Adequate (acceptable but some communication gaps)
   - [ ] Poor (unresponsive, unprofessional, difficult to work with)
   - **Notes**: _______________

6. **Issue Resolution**: How did the vendor handle problems, bugs, or conflicts?
   - [ ] Very well (proactive problem-solving, owned issues, resolved quickly)
   - [ ] Adequately (resolved issues with some follow-up needed)
   - [ ] Poorly (slow to respond, blamed others, issues lingered)
   - **Notes**: _______________

7. **Technical Expertise**: Did the team demonstrate strong technical skills in [specific technologies relevant to HMRC ChatBot]?
   - [ ] Excellent (deep expertise, solved complex technical challenges)
   - [ ] Good (solid technical skills)
   - [ ] Adequate (basic technical skills, needed guidance)
   - [ ] Lacking (technical skills inadequate for project)
   - **Notes**: _______________

8. **AI/ML and Chatbot Specific** (if applicable): Did the AI chatbot perform well? Accuracy? User satisfaction?
   - [ ] Excellent (high accuracy, positive user feedback)
   - [ ] Good (acceptable accuracy, generally positive feedback)
   - [ ] Adequate (some accuracy issues, mixed feedback)
   - [ ] Poor (significant accuracy issues, negative feedback)
   - [ ] N/A (project was not AI chatbot)
   - **Notes**: _______________

9. **Post-Go-Live Support**: How was support during warranty/maintenance phase? Responsiveness to bugs and issues?
   - [ ] Excellent (very responsive, fixed issues quickly)
   - [ ] Good (responsive, resolved issues within SLA)
   - [ ] Adequate (acceptable but slow at times)
   - [ ] Poor (unresponsive, left issues unresolved)
   - [ ] N/A (project too recent, no warranty period yet)
   - **Notes**: _______________

10. **Would You Hire Again?**: Would you engage this vendor for another project? Why or why not?
    - [ ] Definitely (no hesitation, would seek them out)
    - [ ] Probably (positive experience, would consider)
    - [ ] Maybe (mixed experience, would consider with reservations)
    - [ ] No (would not rehire due to issues)
    - **Notes**: _______________

11. **Anything Else**: Is there anything else we should know about working with this vendor? Strengths? Weaknesses? Surprises?
    - **Notes**: _______________

**Reference Check Summary**:
- [ ] **Highly Positive** (enthusiastic, would definitely rehire, exceeded expectations in multiple areas)
- [ ] **Positive** (satisfied, met expectations, would consider hiring again)
- [ ] **Mixed** (some concerns, met most expectations but issues in some areas, might rehire with reservations)
- [ ] **Negative** (not satisfied, below expectations, would not rehire)

### 8.2 Reference Check Impact on Scoring

Reference checks do NOT add points but may **disqualify** or **lower scores**:

**Disqualification Criteria**:
- **Multiple negative references** (2+ out of 3 references rate "Negative" overall)
- **Single highly negative reference with severe issues** (e.g., "Project was a disaster, vendor abandoned us, do not hire under any circumstances")
- **Reference fraud** (fake references, reference contacts don't exist or deny knowledge of project)

**Score Adjustment Criteria** (lower scores by 10-20% in relevant categories):
- **Consistent pattern of delays**: Lower Category 2.1 (Timeline Realism) score by 10-15%
- **Consistent pattern of cost overruns**: Lower Category 2.2 (Risk Management) score by 10-15%, flag cost concerns to Finance
- **Quality issues or rework required**: Lower Category 2.4 (Quality Assurance) score by 10-20%
- **Team effectiveness concerns**: Lower Category 3.1 (Key Personnel) or 3.2 (Team Composition) score by 10-15%
- **Post-go-live support issues**: Flag as risk for warranty period (SOW Section 9.4)

**Example Score Adjustment**:
- Original Technical Score: 82/100
- Reference checks reveal 2 out of 3 references report "significant delays (>10%)" and "minor cost overruns"
- Adjust Category 2.1 (Timeline Realism) from 7/8 to 6/8 (-1 point)
- Adjust Category 2.2 (Risk Management) from 5/6 to 4.5/6 (-0.5 points)
- New Technical Score: 82 - 1.5 = 80.5/100

### 8.3 Reference Check Summary Report

**Vendor Name**: _______________
**Reference Checks Completed By**: _______________
**Date**: _______________

| Reference | Client & Contact | Project Similarity | On Time? | On Budget? | Quality | Would Rehire? | Overall Rating |
|-----------|------------------|--------------------|----------|------------|---------|---------------|----------------|
| Ref 1 | | High/Med/Low | Yes/No | Yes/No | Excellent/Good/Adequate/Poor | Definitely/Probably/Maybe/No | Highly Positive / Positive / Mixed / Negative |
| Ref 2 | | High/Med/Low | Yes/No | Yes/No | Excellent/Good/Adequate/Poor | Definitely/Probably/Maybe/No | Highly Positive / Positive / Mixed / Negative |
| Ref 3 | | High/Med/Low | Yes/No | Yes/No | Excellent/Good/Adequate/Poor | Definitely/Probably/Maybe/No | Highly Positive / Positive / Mixed / Negative |

**Key Findings** (across all references):
- **Strengths**: _______________
- **Concerns**: _______________
- **Patterns** (e.g., always on time but sometimes over budget): _______________

**Score Adjustment Recommendations**:
- Category ___ (___): Adjust from ___ to ___ (decrease by ___%) - Rationale: _______________
- Category ___ (___): Adjust from ___ to ___ (decrease by ___%) - Rationale: _______________

**Recommendation**:
- [ ] **No Concerns**: References positive, proceed with selection if highest score
- [ ] **Minor Concerns**: Some issues but manageable, address in contract negotiation (e.g., tighter milestone definitions, penalty clauses)
- [ ] **Significant Concerns**: Multiple issues raised, reconsider selection even if highest score, or require mitigation plan
- [ ] **Disqualify**: Negative references or fraud, remove from consideration

---

## 9. Final Selection Decision

### 9.1 Decision Factors

The vendor with the **highest combined score** (Technical 70% + Cost 30%) is typically selected, but the final decision may also consider qualitative factors.

**Quantitative (Objective) Factors**:
- **Final Combined Score** (highest score wins, assuming e70 minimum)
- **Cost relative to budget** (within £16.5M-£20.5M 3-year TCO)
- **Technical score threshold**: Minimum 70/100 technical required (non-negotiable)

**Qualitative (Subjective) Factors**:
- **Cultural Fit**: Communication style, alignment with HMRC values (citizen-centric, inclusive, transparent), Agile culture
- **Confidence in Delivery**: Based on presentations, references, and team expertise, do we believe vendor can deliver on time, on budget, with high quality?
- **Strategic Partnership Potential**: Is this a vendor we want long-term relationship with for future AI/ML projects?
- **Risk Tolerance**: Prefer known vendor with solid references (lower risk) vs. innovative newcomer with cutting-edge approach (higher risk but potentially higher reward)
- **GDS Assessment Risk**: Which vendor has best track record passing GDS Service Standard Live Assessment?

### 9.2 Decision Matrix

**Completed by**: Evaluation Lead + Evaluation Committee (consensus)
**Date**: _______________

| Vendor | Final Score (100 pts) | Technical (100 pts) | Cost (3-Yr TCO £M) | Reference Check | Cultural Fit | Confidence in Delivery | Risk Level | GDS Pass Likelihood | **Recommendation** |
|--------|----------------------|---------------------|--------------------|-----------------|--------------|-----------------------|------------|---------------------|-------------------|
| Vendor A | ___ | ___ | £___ | Positive/Mixed/Negative | Excellent/Good/Adequate | High/Medium/Low | Low/Medium/High | High/Medium/Low | [ ] **Select**<br>[ ] Consider<br>[ ] Do Not Select |
| Vendor B | ___ | ___ | £___ | Positive/Mixed/Negative | Excellent/Good/Adequate | High/Medium/Low | Low/Medium/High | High/Medium/Low | [ ] **Select**<br>[ ] Consider<br>[ ] Do Not Select |
| Vendor C | ___ | ___ | £___ | Positive/Mixed/Negative | Excellent/Good/Adequate | High/Medium/Low | Low/Medium/High | High/Medium/Low | [ ] **Select**<br>[ ] Consider<br>[ ] Do Not Select |

**Scenario Analysis**:

**Scenario 1: Clear Winner** (e.g., Vendor B: Final Score 87.4, positive references, excellent cultural fit)
- **Decision**: Select Vendor B
- **Rationale**: Highest combined score, strong technical approach, best value for money, positive references, low risk

**Scenario 2: Close Scores** (e.g., Vendor A: 85.2, Vendor B: 84.8)
- **Tie-Breaker Factors**: Reference checks, cultural fit, GDS assessment likelihood, risk level
- **Decision**: Select vendor with stronger references, better cultural fit, or lower risk
- **Rationale**: With scores within 1-2 points, qualitative factors become more important

**Scenario 3: Highest Score BUT Concerns** (e.g., Vendor C: Highest score 88.0 but mixed reference checks, "probably would not rehire")
- **Risk Assessment**: Is highest score worth the risk given reference concerns?
- **Options**:
  - **Select with Mitigations**: Choose Vendor C but add contract protections (tighter milestones, penalty clauses, shorter payment holdbacks)
  - **Select Runner-Up**: Choose Vendor B (score 87.4) with positive references, accepting slightly lower score for lower risk
- **Decision**: Evaluation committee consensus required (vote if necessary)

### 9.3 Selection Approval

**Decision Authority**: HMRC Senior Responsible Officer (SRO) + HMRC Chief Technology Officer (CTO)

**Approval Process**:
1. **Evaluation Summary Presented**: Procurement Lead + EA Architecture present evaluation summary to SRO and CTO
2. **Recommended Vendor**: Evaluation committee's recommended vendor with rationale
3. **Risks and Mitigations**: Key risks identified and proposed mitigation strategies
4. **Budget Confirmation**: Finance confirms budget availability for selected vendor's cost
5. **Approval Decision**: SRO and CTO approve or request further evaluation
6. **Approval Signatures**: Formal sign-off on selection decision

**Approval Form**:

---

**HMRC CHATBOT VENDOR SELECTION - APPROVAL FORM**

**Recommended Vendor**: _______________

**Final Combined Score**: ___ / 100 (Technical ___ × 0.7 + Cost ___ × 1.0)

**3-Year Total Cost of Ownership**: £___ M (within budget: £16.5M-£20.5M)

**Selection Rationale**:
[2-3 paragraphs summarizing why this vendor was selected over others. Include: technical strengths, cost competitiveness, reference check results, cultural fit, confidence in delivery.]

**Example**:
"Vendor B scored highest with 87.4/100 combined score (82/100 technical, 30/30 cost). Their RAG architecture design is excellent with AWS Bedrock Claude 3.5 Sonnet, comprehensive bias mitigation, and strong security design aligned with NCSC principles. The team has deep UK Gov experience (3 GDS Service Standard passes) and demonstrated AI chatbot expertise. Reference checks were highly positive with all 3 clients stating they would 'definitely hire again.' Cost is competitive at £16.2M 3-year TCO (within budget), providing best value at £197K per technical point. We have high confidence Vendor B will deliver on time, on budget, and pass GDS Live Assessment."

**Key Strengths**:
1. [Strength 1 - e.g., "Excellent RAG architecture with 100% source citation and human escalation"]
2. [Strength 2 - e.g., "Strong UK Gov experience with 3 GDS Service Standard passes"]
3. [Strength 3 - e.g., "Best value at £197K per technical point, lowest 3-year TCO"]

**Risks and Mitigations**:
1. **Risk**: [Risk 1 - e.g., "LLM API costs could exceed estimates if token usage is higher than projected"]
   - **Mitigation**: [Mitigation strategy - e.g., "Contract includes quarterly LLM cost reviews with optimization strategies; vendor will implement caching to reduce token usage by 30%"]

2. **Risk**: [Risk 2 - e.g., "Government Gateway integration delays could impact timeline"]
   - **Mitigation**: [Mitigation strategy - e.g., "Early engagement with Government Gateway team in Week 1; sandbox environment access confirmed; fallback to guest mode if delays occur"]

3. **Risk**: [Risk 3 - e.g., "DPIA approval delays could push Private Beta launch"]
   - **Mitigation**: [Mitigation strategy - e.g., "DPO engaged early in design phase (Week 4); DPIA template pre-approved; contingency buffer in timeline (2 weeks)"]

**Budget Confirmation**:
- **Capex (Year 1)**: £___ M (Budget: £4.5-£5.5M) - [ ] Within Budget
- **Opex (Year 2)**: £___ M (Budget: £4-£5M) - [ ] Within Budget
- **Opex (Year 3)**: £___ M (Budget: £4-£5M) - [ ] Within Budget
- **3-Year TCO**: £___ M (Budget: £16.5-£20.5M) - [ ] Within Budget
- **Budget Authority Confirmed**: [ ] Yes (Finance approval attached)

**Approvals**:

| Role | Name | Signature | Date |
|------|------|-----------|------|
| **Evaluation Lead** | [Procurement Lead] | _________ | [DATE] |
| **Enterprise Architect** | [EA Lead] | _________ | [DATE] |
| **HMRC CISO** | [Security Lead] | _________ | [DATE] |
| **Finance Director** | [Finance] | _________ | [DATE] |
| **Senior Responsible Officer (SRO)** | [HMRC Director Digital Services] | _________ | [DATE] |
| **HMRC Chief Technology Officer (CTO)** | [CTO] | _________ | [DATE] |

**Decision**: [ ] **APPROVED** - Proceed to contract negotiation with selected vendor

**Date of Approval**: _______________

---

## 10. Vendor Notification

### 10.1 Award Notification (Selected Vendor)

**Timeline**: Notify within **1 business day** of approval decision (2026-01-22)

**Notification Method**: Phone call from Procurement Lead followed by formal email

**Email Content** (template):

---

**Subject**: HMRC ChatBot RFP Selection - You Have Been Selected

Dear [Vendor Contact],

Congratulations! HMRC is pleased to inform you that your proposal for the HMRC Tax Guidance ChatBot project (RFP ID: HMRC-CHATBOT-2025-001) has been selected.

**Selection Summary**:
- Your final score: ___ / 100 (highest among all vendors evaluated)
- Key strengths that led to your selection:
  1. [Strength 1]
  2. [Strength 2]
  3. [Strength 3]

**Next Steps**:
1. **Contract Negotiation Kickoff**: [Date, 2026-01-23]
   - Location: HMRC offices, 10 South Colonnade, London
   - Attendees: HMRC Legal, Procurement, your contract lead
   - Duration: 2 weeks (target contract signing 2026-02-09)

2. **Pre-Kickoff Preparation**: Please prepare:
   - Contract negotiation team and authority to sign
   - NDA and DPA signatures (if not already signed)
   - Key personnel availability confirmation for 2026-02-09 kickoff
   - Initial onboarding logistics (AWS access requests, HMRC system access)

3. **Project Kickoff**: Week 1 (2026-02-09)
   - Kickoff meeting with HMRC project team
   - Begin Milestone M0 (Initiation Phase, Weeks 1-2)

We are excited to partner with you on this important initiative and look forward to a successful delivery.

If you have any questions, please contact:
- **Procurement Lead**: [Name, Email, Phone]
- **Enterprise Architect**: [Name, Email]

Best regards,

[HMRC Procurement Lead]
HMRC Digital Services

---

### 10.2 Non-Selected Vendor Notification

**Timeline**: Notify within **2 business days** of selection decision (2026-01-22)

**Notification Method**: Email from Procurement Lead (phone call optional if vendor requests)

**Email Content** (template):

---

**Subject**: HMRC ChatBot RFP Selection Outcome

Dear [Vendor Contact],

Thank you for submitting a proposal for the HMRC Tax Guidance ChatBot project (RFP ID: HMRC-CHATBOT-2025-001). We appreciate the time and effort your team invested in responding to our RFP.

After a thorough evaluation process, we have selected another vendor whose proposal best met our requirements and provided the best overall value for HMRC.

**Your Evaluation Summary** (high-level feedback):
- Technical Score: ___ / 100
- Overall Ranking: ___ of ___ qualified vendors
- Key strengths in your proposal:
  1. [Strength 1]
  2. [Strength 2]

We value your interest in working with HMRC and encourage you to participate in future opportunities.

**Optional Debrief**: If you would like more detailed feedback on your proposal, we are happy to schedule a debrief call within the next 2 weeks. Please contact [Procurement Lead Email] to request a debrief.

**Debrief Guidelines**:
- We will provide constructive feedback on your proposal's strengths and areas for improvement
- We will NOT disclose other vendors' scores, proposals, or costs
- We will NOT disclose the identity of the selected vendor until contract is signed (publicly announced)
- Debrief duration: 30 minutes

Thank you again for your participation.

Best regards,

[HMRC Procurement Lead]
HMRC Digital Services

---

### 10.3 Debrief Guidelines (for Non-Selected Vendors)

**Purpose**: Provide constructive feedback to help vendors improve future proposals

**Debrief Attendees** (HMRC side):
- Procurement Lead (mandatory)
- Enterprise Architect (optional, for technical feedback)
- Finance (optional, for cost feedback)

**Debrief Duration**: 30 minutes

**Debrief Content** (what to share):
- Vendor's technical score and ranking (e.g., "You scored 76/100, ranked 3rd out of 5 qualified vendors")
- Specific strengths in proposal (e.g., "Your security design was excellent, scored 6.5/7 in Category 1.3")
- Specific areas for improvement (e.g., "Your RAG architecture lacked detail on confidence scoring and human escalation, scored 7/10 in Category 1.1 - adding these details would have strengthened your proposal")
- General advice for future RFPs (e.g., "Provide more detailed CVs for key personnel with specific project examples")

**Debrief Content** (what NOT to share):
- Other vendors' scores, proposals, or identities
- Selected vendor's cost or detailed proposal contents
- Evaluation committee discussions or individual evaluator scores
- Internal HMRC budget or cost expectations

**Debrief Recording**: HMRC may take notes for records; vendor may take notes but no audio/video recording

---

## 11. Appeals Process

Vendors may appeal the selection decision if they believe the evaluation process was unfair or procedurally flawed.

### 11.1 Grounds for Appeal

Appeals are **accepted ONLY for**:
- [ ] **Evaluation process not followed**: Vendor can demonstrate that HMRC did not follow the process documented in this evaluation criteria or the SOW (e.g., mandatory qualification disqualification without notification, no opportunity for clarification)
- [ ] **Scoring errors or mathematical mistakes**: Vendor identifies clear mathematical errors in score calculation (e.g., "You stated our technical score was 76/100 but subcategory scores add to 78/100")
- [ ] **Evaluator conflict of interest**: Vendor can demonstrate undisclosed conflict of interest that affected evaluation (e.g., "Evaluator X used to work for selected vendor and did not recuse themselves")
- [ ] **Vendor information misrepresented**: HMRC evaluation materials misrepresent vendor's proposal (e.g., "Evaluation summary states we don't have Cyber Essentials Plus, but we provided certificate on page 45 of evidence document")

Appeals are **NOT accepted for**:
- [ ] **Disagreement with evaluation criteria**: Vendor doesn't like the 70/30 technical/cost split (criteria were published in SOW, vendors could raise concerns during Q&A period)
- [ ] **Disagreement with scores or subjective judgments**: Vendor believes their RAG architecture deserves 9/10 instead of 7/10 (evaluation committee's professional judgment)
- [ ] **Cost-based arguments**: "We should have won because we're cheaper" (best value approach, not lowest price, was published in SOW)
- [ ] **New information not in proposal**: "We actually have GDS experience but forgot to mention it in our proposal" (too late, cannot revise proposals after submission)

### 11.2 Appeal Process

1. **Vendor Submits Written Appeal** (within **5 business days** of notification, 2026-01-29 deadline):
   - Email to [Procurement Lead Email] with subject line: "HMRC ChatBot RFP Appeal - [Vendor Name]"
   - Appeal must include:
     - Specific grounds for appeal (from Section 11.1)
     - Evidence supporting appeal (e.g., pages from proposal showing information HMRC allegedly misrepresented)
     - Requested remedy (e.g., "Re-evaluate our proposal with correct information" or "Disqualify selected vendor due to evaluator conflict")

2. **Impartial Review** (within **10 business days**, by 2026-02-12):
   - Appeal reviewed by impartial party not involved in original evaluation: HMRC Internal Audit or HMRC Legal
   - Reviewer examines:
     - Vendor's appeal and evidence
     - Original evaluation records (scoring sheets, consensus meeting notes, reference check notes)
     - Evaluation process compliance with this document and SOW
   - Reviewer determines:
     - Is appeal based on valid grounds (Section 11.1)?
     - If valid grounds, did the alleged issue materially affect the selection decision?

3. **Review Decision** (communicated to vendor by 2026-02-12):
   - **Appeal Upheld**: Issue found, material impact on decision
     - **Remedy Options**:
       - **Re-evaluation**: Vendor's proposal re-evaluated with corrected information, scores recalculated, selection decision reconsidered
       - **Process Restart**: If evaluator conflict or major process flaw, restart evaluation with new evaluation committee
       - **Disqualification of Selected Vendor**: If selected vendor had undisclosed conflict, disqualify and award to runner-up
   - **Appeal Denied**: No valid grounds or no material impact
     - Selection decision stands
     - Vendor notified with explanation of why appeal denied

4. **Final Decision**:
   - Procurement Lead's decision (or Internal Audit/Legal reviewer's decision) is **FINAL**
   - No further appeals within HMRC
   - Vendor may pursue external legal remedies if they believe HMRC violated UK procurement law (Public Contracts Regulations 2015), but this is outside scope of this process

**Appeal Fee**: No fee for appeal (HMRC does not charge vendors for appeal reviews)

**Contract Award on Hold**: If appeal is filed, contract signing with selected vendor is paused until appeal resolved (typically 10 business days delay)

---

## 12. Documentation and Records

### 12.1 Required Documentation

All evaluation materials must be retained for **7 years** (HMG records management standard) to support audit trail, appeals, and potential legal challenges.

**Documents to Retain**:
- [ ] RFP/SOW document (published version with Q&A)
- [ ] All vendor proposals (technical and cost, as submitted)
- [ ] Mandatory qualifications checklists (for all vendors, including disqualified)
- [ ] Individual scoring sheets (all evaluators, all vendors)
- [ ] Consensus scoring sheets (final agreed scores)
- [ ] Presentation notes and score adjustments (for shortlisted vendors)
- [ ] Reference check notes (for shortlisted vendors)
- [ ] Cost analysis spreadsheets (for shortlisted vendors)
- [ ] Final combined scoring summary
- [ ] Selection decision memo with rationale
- [ ] Selection approval form with signatures (SRO, CTO, Finance, EA, CISO, Procurement)
- [ ] Vendor notification emails (selected and non-selected)
- [ ] Debrief meeting notes (if debriefs requested)
- [ ] Appeal submissions and review decisions (if any)

**Storage Location**:
- Electronic documents: HMRC SharePoint (restricted access, evaluation committee + Legal + Internal Audit only)
- Physical documents (signatures): HMRC Procurement office secure filing cabinet

**Access Control**:
- Evaluation records are **OFFICIAL-SENSITIVE** (contain vendor proprietary information, scoring details)
- Access restricted to: Evaluation committee, HMRC SRO, HMRC Legal, HMRC Internal Audit, and authorized personnel for audit purposes
- Vendor proposals are **CONFIDENTIAL** - not shared outside evaluation committee except with vendor's written consent

### 12.2 Confidentiality

**Non-Disclosure Agreement (NDA)**:
- All evaluators sign NDA before accessing vendor proposals
- NDA terms: Confidential information not disclosed to third parties, proposals not used for purposes other than evaluation, proposals returned/destroyed after contract signed

**Confidentiality Requirements**:
- Evaluators do NOT disclose:
  - Vendor proposals, costs, or technical details to anyone outside evaluation committee
  - Individual or consensus scores to vendors (except in debrief: high-level score and ranking only)
  - Evaluation committee discussions, disagreements, or internal deliberations
  - Comparison of vendors (e.g., "Vendor A is better than Vendor B because...") to anyone outside committee
- Evaluators MAY disclose:
  - Evaluation process and criteria (already public in SOW)
  - Selected vendor name and contract value (after contract signed, public information)
  - High-level feedback to non-selected vendors in debrief (constructive feedback only, no competitor details)

**Penalties for Confidentiality Breach**:
- Disciplinary action per HMRC HR policy (up to termination)
- Potential legal liability if breach causes harm to vendor (e.g., disclosure of proprietary information)
- Entire procurement may be invalidated and restarted if breach materially affects fairness

---

## 13. Appendices

### Appendix A: Individual Evaluator Scorecard (Template)

**Evaluator Name**: _______________
**Vendor Name**: _______________
**Date**: _______________

[Complete scoring template with all categories and subcriteria from Sections 4.2-4.6, to be filled out independently by each evaluator before consensus meeting]

### Appendix B: Consensus Scoring Worksheet (Template)

**Evaluation Committee Consensus Meeting**
**Date**: _______________
**Attendees**: _______________

[Template for facilitated consensus scoring meeting, capturing discussion points, score rationale, and final agreed scores for each vendor]

### Appendix C: Evaluation Committee Charter

**Purpose**: Define roles, responsibilities, decision-making process, and code of conduct for evaluation committee members.

**Roles and Responsibilities**:
- **Evaluation Lead (Procurement)**: Process orchestration, ensure fairness, final scoring coordination, vendor communication
- **Technical Evaluators**: Score technical categories, provide expertise in architecture, AI/ML, security, accessibility
- **Business Evaluators**: Score business categories, validate requirements understanding, assess value for money
- **Observers (Non-Voting)**: Provide input on legal, data protection, GDS compliance; do not vote on scores

**Decision-Making**:
- **Individual Scoring**: Each voting evaluator scores vendors independently (blind to others' scores)
- **Consensus Scoring**: Committee discusses outlier scores (>15 points difference) and agrees on final consensus score
- **Consensus Method**: Discussion until agreement; if no agreement after 30 min discussion, take average of scores (excluding extreme outliers)
- **Final Selection**: Committee recommends vendor; SRO and CTO have final approval authority

**Code of Conduct**:
- Objectivity: Score based on evidence in proposals, not personal biases
- Confidentiality: Do not disclose proposals, scores, or discussions outside committee
- Conflicts of Interest: Disclose any conflicts; recuse if necessary
- Fairness: Apply same criteria consistently to all vendors
- Professionalism: Treat vendors respectfully; provide constructive feedback

### Appendix D: Conflict of Interest Declaration Form

**Evaluation Committee - Conflict of Interest Declaration**

**Evaluator Name**: _______________
**Role**: _______________
**Date**: _______________

I hereby declare the following potential conflicts of interest with vendors responding to HMRC ChatBot RFP (HMRC-CHATBOT-2025-001):

**For each vendor, check all that apply**:

| Vendor Name | Personal Relationship | Financial Interest | Prior Employment | Concurrent Work | Vendor-Sponsored Events | Other Conflict | **Recusal Required?** |
|-------------|----------------------|-------------------|------------------|----------------|-------------------------|----------------|-----------------------|
| Vendor A | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] No |
| Vendor B | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] No |
| Vendor C | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] No |

**Details of Conflicts** (if any):
_______________

**Recusal Commitment**:
I commit to recuse myself from evaluation of any vendor where I have disclosed a conflict of interest, as indicated above.

**Signature**: _______________ **Date**: _______________

**Evaluation Lead Approval**: _______________ **Date**: _______________

---

## Document Control

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | 2025-10-07 | HMRC Enterprise Architecture Team | Initial draft based on SOW Section 8 |
| 0.2 | 2025-10-10 | HMRC Procurement + EA | Stakeholder feedback incorporated; scoring rubrics refined |
| 1.0 | 2025-10-14 | HMRC Procurement Lead | **Finalized and approved for use with RFP** |

## Approvals

| Role | Name | Signature | Date |
|------|------|-----------|------|
| **Procurement Lead** | [TBD] | _________ | [PENDING] |
| **Enterprise Architect** | [TBD] | _________ | [PENDING] |
| **HMRC CISO** | [TBD] | _________ | [PENDING] |
| **Finance Director** | [TBD] | _________ | [PENDING] |
| **HMRC SRO** | [TBD] | _________ | [PENDING] |

---

**END OF VENDOR EVALUATION CRITERIA**

---

**IMPORTANT NOTES FOR EVALUATION COMMITTEE**:

1. **Read SOW First**: This evaluation criteria is based on SOW Section 8. Evaluators must read full SOW and requirements before scoring.

2. **Mandatory Qualifications Are Pass/Fail**: Any vendor failing MQ-1 through MQ-12 is disqualified (no technical scoring).

3. **Technical Scoring Blind to Cost**: Do not open cost proposals until after technical evaluation and shortlisting.

4. **Minimum Technical Score = 70/100**: Vendors scoring <70 are not shortlisted, even if lowest cost.

5. **Reference Checks Are Critical**: Reference checks can lower scores or disqualify vendors. Contact all references for shortlisted vendors.

6. **Final Score = 70% Technical + 30% Cost**: Best value approach, not lowest price.

7. **Presentations May Adjust Scores**: Use presentations to clarify concerns; adjust scores (+/- up to 10 points per category) based on new information.

8. **Document Everything**: All scores, rationale, and decisions must be documented for audit trail and potential appeals.

9. **Confidentiality**: Evaluators sign NDA and must not disclose proposals, scores, or discussions outside committee.

10. **Conflicts of Interest**: Disclose conflicts on Appendix D form; recuse if conflict exists.

Good luck with the evaluation! <¯
