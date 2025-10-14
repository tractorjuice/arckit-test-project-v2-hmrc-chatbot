# Requirements Traceability Matrix: HMRC Tax Guidance ChatBot

**Document Type**: Pre-Design Requirements Traceability & Verification Matrix
**Project ID**: 001-hmrc-chatbot
**RFP ID**: HMRC-CHATBOT-2025-001
**Version**: 1.0 (Baseline - Pre-Procurement)
**Date**: 2025-10-14
**Status**: BASELINE (Pre-Vendor Selection)
**Owner**: HMRC Enterprise Architecture Team
**Phase**: Pre-Procurement (Requirements Baseline Established)

---

## EXECUTIVE SUMMARY

### Document Purpose

This Requirements Traceability Matrix (RTM) establishes the **baseline traceability framework** for the HMRC ChatBot project during the pre-procurement phase. Since no vendor has been selected and no design artifacts exist yet, this document:

1. **Baseline Requirements**: Catalogs all 44 requirements (7 BR, 11 FR, 21 NFR, 5 INT) from `requirements.md`
2. **Maps Requirements to SOW Deliverables**: Links each requirement to specific SOW deliverables and acceptance criteria
3. **Defines Traceability Expectations**: Specifies what design artifacts, implementation evidence, and tests vendors must provide for each requirement
4. **Establishes Verification Criteria**: Defines how HMRC will verify that each requirement is met
5. **Provides Vendor Template**: Vendors will complete this matrix during HLD/DLD phases to demonstrate full traceability

### Traceability Status

**Current Phase**: Pre-Procurement
-  **Requirements Defined**: 44 requirements documented and approved (Gate 1 complete)
- ó **Design Phase**: Awaiting vendor selection (Gate 2 - target M1 Week 8)
- ó **Implementation Phase**: Awaiting development (Gate 3 - target M2 Week 20)
- ó **Testing Phase**: Awaiting test execution (Gate 4 - target M3 Week 40)

**Vendor Responsibility**: Selected vendor must complete this matrix by:
- **HLD Submission (Week 4)**: Map requirements to HLD components
- **DLD Submission (Week 8)**: Map requirements to DLD modules, APIs, database schemas
- **Implementation (Weeks 9-32)**: Map requirements to source code files, endpoints, configuration
- **Testing (Weeks 33-40)**: Map requirements to test cases with execution results

### Coverage Targets

| Requirement Type | Total | Coverage Target | Rationale |
|------------------|-------|-----------------|-----------|
| **Business Requirements (BR)** | 7 | **100%** (all MUST) | Mission-critical business outcomes (£75M savings, 30% helpline deflection, GDS compliance) |
| **Functional Requirements (FR)** | 11 | **100%** (all MUST) | Core ChatBot capabilities required for launch |
| **Non-Functional Requirements (NFR)** | 21 | **100%** (all MUST) | UK Gov compliance mandates (security, accessibility, performance, UK GDPR) |
| **Integration Requirements (INT)** | 5 | **100%** (all MUST) | Critical integrations (Government Gateway, HMRC APIs, AWS Bedrock) |
| **TOTAL** | **44** | **100%** | No optional (MAY) requirements in baseline; all are MUST for production launch |

**Key Constraint**: **Zero requirements are optional** - all 44 requirements are **MUST** for GDS Service Standard Live Assessment and production launch. Vendors cannot propose descoping any requirement.

---

## 1. TRACEABILITY SCOPE

### 1.1 Traceability Flow

This matrix traces requirements through the full lifecycle:

```
Business Requirements (BR-1 to BR-7)
  “ drives
Functional Requirements (FR-1 to FR-11)
  “ satisfied by
High-Level Design (HLD) Components [VENDOR TO COMPLETE]
  “ detailed in
Detailed Design (DLD) Modules/APIs [VENDOR TO COMPLETE]
  “ implemented in
Source Code / Infrastructure [VENDOR TO COMPLETE]
  “ verified by
Test Cases (Unit, Integration, E2E, Performance, Security, Accessibility) [VENDOR TO COMPLETE]
  “ accepted via
Acceptance Criteria (SOW Section 4 Deliverables)
```

**Traceability Direction**:
- **Forward Traceability**: Requirements ’ Design ’ Implementation ’ Tests (ensures all requirements are addressed)
- **Backward Traceability**: Tests ’ Implementation ’ Design ’ Requirements (ensures no scope creep or orphan work)

### 1.2 Document References

| Document | Version | Date | Status | Link |
|----------|---------|------|--------|------|
| **Requirements Document** | 1.0 | 2025-10-14 | APPROVED (Gate 1) | `projects/001-hmrc-chatbot/requirements.md` |
| **Architecture Principles** | 1.0 | 2025-10-14 | APPROVED | `.arckit/memory/architecture-principles.md` |
| **Statement of Work (SOW)** | 1.0 | 2025-10-14 | ISSUED (G-Cloud 14) | `projects/001-hmrc-chatbot/sow.md` |
| **ATRS Record** | 1.0 (85% complete) | 2025-10-14 | DRAFT (blockers: DPIA, EqIA, Security Assessment) | `projects/001-hmrc-chatbot/atrs-record.md` |
| **Evaluation Criteria** | 1.0 | 2025-10-14 | APPROVED | `projects/001-hmrc-chatbot/evaluation-criteria.md` |
| **High-Level Design (HLD)** | - | - | AWAITING VENDOR (M1 Week 4) | `projects/001-hmrc-chatbot/vendors/{vendor}/hld.md` |
| **Detailed Design (DLD)** | - | - | AWAITING VENDOR (M1 Week 8) | `projects/001-hmrc-chatbot/vendors/{vendor}/dld.md` |
| **Test Strategy** | - | - | AWAITING VENDOR (M1 Week 8) | `projects/001-hmrc-chatbot/vendors/{vendor}/test-strategy.md` |
| **Test Cases & Results** | - | - | AWAITING VENDOR (M3 Week 40) | `projects/001-hmrc-chatbot/vendors/{vendor}/test-results.md` |

### 1.3 Vendor Obligations

The selected vendor MUST complete this traceability matrix progressively:

**Milestone M1 (Design Approval, Week 8)**:
- [ ] Map all 44 requirements to HLD components (forward traceability)
- [ ] Document design rationale for each requirement
- [ ] Identify any architecture patterns used per requirement
- [ ] Submit updated traceability matrix with HLD document

**Milestone M2 (Development Milestone, Week 20)**:
- [ ] Map all 44 requirements to DLD modules, APIs, database schemas
- [ ] Provide source code file references for implemented requirements
- [ ] Document any deviations from HLD with justification
- [ ] Submit updated traceability matrix

**Milestone M3 (Testing Complete, Week 40)**:
- [ ] Map all 44 requirements to test cases (unit, integration, E2E, performance, security, accessibility)
- [ ] Provide test execution results (pass/fail, evidence)
- [ ] Document any test coverage gaps with mitigation plans
- [ ] Submit final traceability matrix for Architecture Review Board approval

**Milestone M5 (Production Launch, Week 52)**:
- [ ] Final traceability matrix approved by HMRC Architecture Review Board
- [ ] All 44 requirements verified as implemented and tested (100% coverage)
- [ ] Zero critical gaps or orphan requirements
- [ ] Traceability matrix published as part of project handover documentation

**Acceptance Criteria**: Traceability matrix must show **100% requirements coverage** (all 44 requirements traced to design, implementation, and tests) for Milestone M5 acceptance and final payment.

---

## 2. FORWARD TRACEABILITY MATRIX: REQUIREMENTS ’ DESIGN ’ IMPLEMENTATION ’ TESTS

### 2.1 Business Requirements (BR) Traceability

#### BR-1: Helpline Call Deflection (MUST)

**Requirement Statement**: Deflect 30% of helpline calls (15 million/year) to ChatBot self-service by Year 3.

**Phased Goals**: Year 1: 10% deflection, Year 2: 20% deflection, Year 3: 30% deflection.

**Acceptance Criteria** (SOW Section 4.1):
- [ ] BI dashboard with call deflection KPIs (real-time and historical trends)
- [ ] Integration with HMRC call center analytics (baseline 50M calls/year)
- [ ] Monthly reporting on call volume reduction (automated)

**Aligns with Architecture Principles**: #16 (FinOps and Value for Money)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "Analytics & Reporting Service"] | Component responsible for tracking call deflection metrics | ó AWAITING VENDOR | [HLD Section X.Y] |
| **DLD Module** | [VENDOR: e.g., "CallDeflectionTracker, BIDashboard"] | Modules implementing call deflection tracking and BI dashboards | ó AWAITING VENDOR | [DLD Section X.Y] |
| **Implementation** | [VENDOR: e.g., "src/analytics/call-deflection.py", Grafana dashboard config] | Source code and infrastructure-as-code | ó AWAITING VENDOR | [GitHub commit SHA, file paths] |
| **Test Cases** | [VENDOR: e.g., "TC-BR1-001: Verify call deflection KPI calculation", "TC-BR1-002: Test BI dashboard data accuracy"] | Test cases verifying call deflection tracking and reporting | ó AWAITING VENDOR | [Test case IDs, execution results] |
| **Acceptance Evidence** | [VENDOR: e.g., "BI dashboard screenshot showing 10% deflection in Month 12", HMRC call center analytics integration proof] | Evidence that BR-1 is met | ó AWAITING VENDOR | [Deliverable milestone M5] |

**Verification Method**: HMRC Product Owner will verify BI dashboard shows call deflection metrics aligned with HMRC call center analytics baseline (50M calls/year).

---

#### BR-2: 24/7 Availability (MUST)

**Requirement Statement**: ChatBot available 24/7/365 with 99.9% uptime during business hours (08:00-20:00 GMT Mon-Fri).

**Response Time**: <2 seconds for 95th percentile (p95) of chat messages.

**Acceptance Criteria** (SOW Section 4.1):
- [ ] Uptime tracked via AWS CloudWatch with SLO alerting
- [ ] Monthly uptime reports (automated)
- [ ] Incident post-mortems for SLO violations

**Aligns with Architecture Principles**: #13 (Resilience and Fault Tolerance)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "Multi-AZ ECS Fargate cluster, CloudWatch monitoring, Health check API"] | Architecture ensuring 99.9% uptime | ó AWAITING VENDOR | [HLD Section X.Y] |
| **DLD Module** | [VENDOR: e.g., "HealthCheckEndpoint, UptimeMonitor, AlertManager"] | Modules implementing uptime monitoring and alerting | ó AWAITING VENDOR | [DLD Section X.Y] |
| **Implementation** | [VENDOR: e.g., "terraform/ecs-fargate.tf (multi-AZ), cloudwatch-alarms.tf, health-check endpoint /health"] | Infrastructure-as-code for HA and monitoring | ó AWAITING VENDOR | [Terraform modules, CloudWatch dashboard] |
| **Test Cases** | [VENDOR: e.g., "NFR-A-1: Verify 99.9% uptime SLO", "NFR-P-1: Load test with 10K concurrent users, verify p95 latency <2s"] | Availability and performance tests | ó AWAITING VENDOR | [Performance test results, uptime monitoring baseline] |
| **Acceptance Evidence** | [VENDOR: e.g., "30-day uptime report showing 99.95% uptime during business hours", "Load test report showing p95 latency 1.8s"] | Evidence that BR-2 is met | ó AWAITING VENDOR | [Deliverable milestone M4 (Private Beta)] |

**Verification Method**: HMRC SRE team will verify CloudWatch dashboards show e99.9% uptime during business hours over 30-day Private Beta period.

---

#### BR-3: Citizen Satisfaction (MUST)

**Requirement Statement**: Achieve >70% Net Promoter Score (NPS) within 6 months of launch.

**Accuracy Target**: >95% of responses marked helpful by citizens (thumbs up/down feedback).

**Acceptance Criteria** (SOW Section 4.1):
- [ ] In-app surveys and feedback collection mechanism
- [ ] Monthly citizen satisfaction reports
- [ ] Sentiment analysis on feedback

**Aligns with Architecture Principles**: #8 (Data Quality and Accuracy)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "Feedback Collection Service, Sentiment Analysis Pipeline"] | Components for collecting and analyzing citizen feedback | ó AWAITING VENDOR | [HLD Section X.Y] |
| **DLD Module** | [VENDOR: e.g., "FeedbackWidget, NPSSurvey, SentimentAnalyzer"] | Modules implementing feedback collection and NPS calculation | ó AWAITING VENDOR | [DLD Section X.Y] |
| **Implementation** | [VENDOR: e.g., "src/frontend/components/FeedbackWidget.tsx", "src/analytics/nps-calculator.py"] | Source code for feedback UI and NPS analytics | ó AWAITING VENDOR | [GitHub commit SHA, file paths] |
| **Test Cases** | [VENDOR: e.g., "TC-BR3-001: Verify thumbs up/down feedback captured", "TC-BR3-002: Test NPS calculation accuracy", "UAT: Citizen feedback during Private Beta"] | Tests verifying feedback collection and NPS tracking | ó AWAITING VENDOR | [Test case IDs, UAT results from Private Beta] |
| **Acceptance Evidence** | [VENDOR: e.g., "Private Beta report showing 72% NPS from 100 citizens", ">95% helpfulness rating in first month"] | Evidence that BR-3 is met | ó AWAITING VENDOR | [Deliverable milestone M4 (Private Beta)] |

**Verification Method**: HMRC Product Owner will verify NPS >70% from Private Beta (100 citizens) and Public Beta (10,000 citizens) feedback surveys.

---

#### BR-4: GDS Service Standard Compliance (MUST - Legal/Governance Requirement)

**Requirement Statement**: Pass GDS Service Standard Live Assessment (18 criteria) before public launch.

**Assessment**: Independent GDS assessors evaluate service at Beta and Live stages.

**Acceptance Criteria** (SOW Section 4.1):
- [ ] GDS assessment report with PASS status for all 18 criteria
- [ ] Evidence provided for each criterion (documentation, demos, user research)

**Aligns with Architecture Principles**: Section XI (GOV.UK Service Standard Alignment)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: All components must align with GDS Service Standard - document how each criterion is met] | Cross-cutting concern: GDS compliance documented in HLD | ó AWAITING VENDOR | [HLD Appendix: GDS Service Standard Compliance Matrix] |
| **DLD Module** | [VENDOR: e.g., "User research documentation, accessibility testing reports, open source code publication plan"] | Evidence for GDS criteria (user needs, accessibility, open standards) | ó AWAITING VENDOR | [DLD Appendix: GDS Evidence Pack] |
| **Implementation** | [VENDOR: e.g., "GOV.UK Design System integration (criterion 11), open source code on GitHub (criterion 12)"] | Implementation demonstrating GDS compliance | ó AWAITING VENDOR | [GitHub repository, accessibility audit report] |
| **Test Cases** | [VENDOR: e.g., "Accessibility tests (WCAG 2.2 AA), user testing with disabled citizens, performance testing"] | Tests verifying GDS criteria (accessibility, performance, reliability) | ó AWAITING VENDOR | [GDS assessment preparation pack] |
| **Acceptance Evidence** | [VENDOR: "GDS Service Standard Live Assessment PASS report"] | GDS assessor report confirming service passes all 18 criteria | ó AWAITING VENDOR | [Deliverable milestone M5 (Production Launch)] |

**Verification Method**: HMRC SRO will coordinate GDS Service Standard Live Assessment before production launch. Vendor must support assessment by providing evidence and attending assessment day.

**CRITICAL PATH**: GDS assessment failure = production launch blocked. Vendor must proactively engage GDS assessors during Beta phase to address any concerns early.

---

#### BR-5: Accessibility Compliance (MUST - Legal Requirement)

**Requirement Statement**: 100% WCAG 2.2 Level AA compliance.

**Legal Basis**: Public Sector Bodies Accessibility Regulations 2018, Equality Act 2010.

**Acceptance Criteria** (SOW Section 4.1):
- [ ] Third-party accessibility audit with zero critical/high issues
- [ ] Automated testing (axe-core, Pa11y) integrated in CI/CD
- [ ] Manual testing with assistive technologies (JAWS, NVDA, VoiceOver)

**Aligns with Architecture Principles**: #4 (Accessibility-First Design)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "GOV.UK Design System integration, accessibility strategy"] | Architecture ensuring WCAG 2.2 AA compliance from design phase | ó AWAITING VENDOR | [HLD Section X.Y: Accessibility Architecture] |
| **DLD Module** | [VENDOR: e.g., "All frontend components using gov.uk-frontend library, ARIA labels, semantic HTML"] | DLD specifying WCAG 2.2 AA compliance for all UI components | ó AWAITING VENDOR | [DLD Section X.Y: UI Components Accessibility Spec] |
| **Implementation** | [VENDOR: e.g., "src/frontend/ (all components), automated accessibility tests in CI/CD pipeline"] | Source code with WCAG 2.2 AA compliant frontend + automated tests | ó AWAITING VENDOR | [GitHub CI/CD config, axe-core test results] |
| **Test Cases** | [VENDOR: e.g., "Automated: axe-core tests (zero violations), Manual: JAWS/NVDA/VoiceOver testing, User testing with disabled citizens"] | Comprehensive accessibility testing (automated + manual + user testing) | ó AWAITING VENDOR | [Accessibility audit report, user testing results] |
| **Acceptance Evidence** | [VENDOR: "Third-party accessibility audit report: WCAG 2.2 AA PASS, zero critical/high issues"] | Independent audit confirming full compliance | ó AWAITING VENDOR | [Deliverable milestone M3 (Testing Complete)] |

**Verification Method**: HMRC Accessibility Specialist will review third-party accessibility audit report and conduct spot-check manual testing with assistive technologies.

**CRITICAL**: Accessibility failures are **legal violations** under Public Sector Bodies Accessibility Regulations 2018. Any critical/high accessibility issues = production launch blocked until resolved.

---

#### BR-6: Algorithmic Transparency (MUST - Legal/Governance Requirement)

**Requirement Statement**: Publish ATRS record on GOV.UK before Private Beta launch.

**Content**: Owner, AI model details, data sources, bias testing, explainability, governance.

**Acceptance Criteria** (SOW Section 4.1):
- [ ] ATRS record (Tier 1 + Tier 2) reviewed by HMRC Data Ethics Committee
- [ ] ATRS published on GOV.UK Algorithmic Transparency Records repository
- [ ] ATRS updated at each milestone (Private Beta, Public Beta, Production, annually)

**Aligns with Architecture Principles**: #5 (Responsible AI and Algorithmic Transparency)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "RAG architecture (embedding, vector search, LLM), bias mitigation strategy, explainability design"] | HLD documenting AI model architecture and responsible AI controls | ó AWAITING VENDOR | [HLD Section: AI Architecture & Responsible AI] |
| **DLD Module** | [VENDOR: e.g., "BiasDetector, ExplainabilityEngine, ConfidenceScorer, Guardrails"] | DLD modules implementing AI safety, bias mitigation, explainability | ó AWAITING VENDOR | [DLD Section: AI Safety & Explainability] |
| **Implementation** | [VENDOR: e.g., "src/ai/bias-mitigation.py, src/ai/explainability.py, AWS Bedrock Guardrails config"] | Source code implementing bias mitigation, explainability, guardrails | ó AWAITING VENDOR | [GitHub commit SHA, AWS Bedrock Guardrails config] |
| **Test Cases** | [VENDOR: e.g., "Bias testing across 9 protected characteristics (<5% disparity), adversarial testing (prompt injection), accuracy testing (>95% on ground truth)"] | AI safety and bias testing | ó AWAITING VENDOR | [Bias testing report, accuracy testing results] |
| **Acceptance Evidence** | [VENDOR: "ATRS record v1.1 published on GOV.UK (updated from DRAFT v1.0 with DPIA, EqIA, Security Assessment results)"] | ATRS record published with full transparency | ó AWAITING VENDOR | [Deliverable milestone M4 (Private Beta)] |

**Verification Method**: HMRC Data Ethics Committee will review and approve ATRS record before Private Beta launch. ATRS must include results from DPIA, EqIA, and Security Assessment (blockers identified in ATRS v1.0 DRAFT).

**DEPENDENCIES**: ATRS publication BLOCKED until DPIA, EqIA, and Security Assessment are completed (planned Week 16, 2026-04).

---

#### BR-7: Data Protection Compliance (MUST - Legal Requirement)

**Requirement Statement**: 100% UK GDPR and Data Protection Act 2018 compliance.

**Requirements**: DPIA approved by DPO, UK data residency, citizen consent, data subject rights.

**Acceptance Criteria** (SOW Section 4.1):
- [ ] DPIA approved by HMRC Data Protection Officer
- [ ] Privacy notice published on GOV.UK
- [ ] Data subject rights procedures tested (access, rectification, erasure, portability, objection)

**Aligns with Architecture Principles**: #7 (Data Sovereignty and UK GDPR Compliance)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "UK data residency architecture (AWS eu-west-2 only), data minimization, citizen consent management"] | Architecture ensuring UK GDPR compliance | ó AWAITING VENDOR | [HLD Section: Data Architecture & UK GDPR Compliance] |
| **DLD Module** | [VENDOR: e.g., "ConsentManager, DataSubjectRightsAPI (access/erasure/portability), AuditLogger (7-year retention)"] | DLD modules implementing UK GDPR requirements | ó AWAITING VENDOR | [DLD Section: Data Protection & Citizen Rights] |
| **Implementation** | [VENDOR: e.g., "AWS eu-west-2 region config, RDS encryption, S3 Object Lock (audit logs), consent UI, data export API"] | Infrastructure and code implementing UK GDPR controls | ó AWAITING VENDOR | [Terraform config, source code, privacy notice] |
| **Test Cases** | [VENDOR: e.g., "Data residency verification (all data in UK), data subject rights API tests, consent flow tests, audit log retention tests"] | Tests verifying UK GDPR compliance | ó AWAITING VENDOR | [DPIA testing evidence, data subject rights API test results] |
| **Acceptance Evidence** | [VENDOR: "DPIA approval from HMRC DPO", "Privacy notice published on GOV.UK", "Data subject rights procedures tested and documented"] | Evidence of full UK GDPR compliance | ó AWAITING VENDOR | [Deliverable milestone M1 (Design Approval)] |

**Verification Method**: HMRC Data Protection Officer will review DPIA and approve data processing activities. HMRC Legal will review privacy notice before publication.

**CRITICAL PATH**: DPIA approval required before Private Beta launch. DPIA planned for completion Week 16 (2026-04).

---

### 2.2 Functional Requirements (FR) Traceability

#### FR-1: Conversational Interface (MUST)

**Requirement Statement**: Natural language understanding for UK English and Welsh, multi-turn dialogue management.

**Support for Common Tax Topics**: Self Assessment, PAYE, VAT, National Insurance, Capital Gains, Inheritance Tax.

**Acceptance Criteria** (SOW Section 4.2):
- [ ] NLU accurately interprets citizen queries (>95% intent recognition accuracy)
- [ ] Multi-turn conversations maintain context across 5+ turns
- [ ] Support for 100+ common tax queries

**Aligns with Architecture Principles**: #4 (Accessibility-First Design), #12 (RAG for AI Accuracy)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "Conversational AI Service (NLU, Dialogue Manager, Context Store)"] | HLD component handling conversational interface | ó AWAITING VENDOR | [HLD Section: Conversational AI Architecture] |
| **DLD Module** | [VENDOR: e.g., "NLUEngine (intent classification, entity extraction), DialogueManager (state machine), ContextStore (Redis session management)"] | DLD modules implementing NLU and dialogue management | ó AWAITING VENDOR | [DLD Section: Conversational AI Detailed Design] |
| **Implementation** | [VENDOR: e.g., "src/ai/nlu.py (LLM-based intent classifier), src/ai/dialogue.py, Redis session config"] | Source code implementing conversational AI | ó AWAITING VENDOR | [GitHub commit SHA, NLU model training logs] |
| **Test Cases** | [VENDOR: e.g., "TC-FR1-001: Test intent recognition accuracy (>95% on 1000 test queries)", "TC-FR1-002: Multi-turn conversation test (5+ turns maintain context)", "TC-FR1-003: Welsh language NLU test"] | Tests verifying conversational interface quality | ó AWAITING VENDOR | [NLU accuracy report, dialogue test results] |
| **Acceptance Evidence** | [VENDOR: "NLU accuracy report: 96.5% intent recognition on 1000-query test set", "Multi-turn dialogue test: 100% context retention over 5 turns"] | Evidence that conversational interface meets quality targets | ó AWAITING VENDOR | [Deliverable milestone M3 (Testing Complete)] |

**Verification Method**: HMRC Product Owner will review NLU accuracy reports and conduct UAT with diverse tax queries during Private Beta.

---

#### FR-2: Retrieval-Augmented Generation (RAG) with HMRC Knowledge Base (MUST)

**Requirement Statement**: Semantic search over 100,000+ HMRC guidance documents, 100% source citation.

**RAG Architecture**: Embedding model ’ vector database ’ top-k retrieval ’ LLM generation ’ source citation.

**Acceptance Criteria** (SOW Section 4.2):
- [ ] Knowledge base ingested with 100,000+ HMRC documents
- [ ] 100% of AI responses cite source documents with clickable GOV.UK links
- [ ] Retrieval quality: precision@5 >80%, recall@5 >70%

**Aligns with Architecture Principles**: #12 (RAG for AI Accuracy), #8 (Data Quality and Accuracy)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "Knowledge Management Service (Ingestion Pipeline, Vector Store, Retrieval API)"] | HLD component for RAG architecture | ó AWAITING VENDOR | [HLD Section: RAG Architecture] |
| **DLD Module** | [VENDOR: e.g., "ContentIngester (HMRC CMS ’ S3), EmbeddingGenerator (AWS Titan Embeddings), VectorStore (OpenSearch k-NN), RetrieverAPI (semantic search), SourceCitationEngine"] | DLD modules implementing RAG pipeline | ó AWAITING VENDOR | [DLD Section: Knowledge Management & RAG] |
| **Implementation** | [VENDOR: e.g., "src/knowledge/ingestion.py, OpenSearch index config, src/ai/retrieval.py, src/ai/citation.py"] | Source code implementing RAG pipeline end-to-end | ó AWAITING VENDOR | [GitHub commit SHA, OpenSearch index schema, ingestion logs] |
| **Test Cases** | [VENDOR: e.g., "TC-FR2-001: Verify 100K+ documents ingested", "TC-FR2-002: Test retrieval quality (precision@5, recall@5)", "TC-FR2-003: Verify 100% source citation with GOV.UK links"] | Tests verifying RAG pipeline quality and source citation | ó AWAITING VENDOR | [Ingestion logs, retrieval quality metrics, citation coverage report] |
| **Acceptance Evidence** | [VENDOR: "Knowledge base: 102,345 documents ingested", "Retrieval quality: precision@5=82%, recall@5=74%", "Source citation: 100% of 1000 test responses cite sources"] | Evidence that RAG meets quality and citation targets | ó AWAITING VENDOR | [Deliverable milestone M3 (Testing Complete)] |

**Verification Method**: HMRC Tax Policy team will review knowledge base content accuracy and source citation quality during UAT.

---

#### FR-3: Large Language Model (LLM) Response Generation (MUST)

**Requirement Statement**: AWS Bedrock Claude 3.5 Sonnet (or equivalent UK-hosted LLM), prompt engineering for accurate tax guidance, guardrails for AI safety.

**Guardrails**: Hallucination detection, bias mitigation, toxic content filtering, prompt injection defense.

**Acceptance Criteria** (SOW Section 4.2):
- [ ] LLM hosted in AWS UK region (eu-west-2) with data residency guarantees
- [ ] Prompt templates optimized for tax guidance accuracy (>95% accuracy on ground truth)
- [ ] Guardrails implemented and tested (zero toxic outputs in 10,000-message test)

**Aligns with Architecture Principles**: #5 (Responsible AI), #9 (Approved Technology Stack)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "LLM Service (AWS Bedrock Claude 3.5 Sonnet, Prompt Templates, Guardrails)"] | HLD component for LLM integration and AI safety | ó AWAITING VENDOR | [HLD Section: LLM Architecture & AI Safety] |
| **DLD Module** | [VENDOR: e.g., "PromptTemplateManager, LLMClient (AWS Bedrock SDK), GuardrailsEngine (AWS Bedrock Guardrails + custom filters)"] | DLD modules implementing LLM integration and guardrails | ó AWAITING VENDOR | [DLD Section: LLM Integration & Guardrails] |
| **Implementation** | [VENDOR: e.g., "src/ai/llm.py (Bedrock API calls), src/ai/prompts/ (templates), AWS Bedrock Guardrails config, src/ai/guardrails.py (custom filters)"] | Source code and config for LLM integration | ó AWAITING VENDOR | [GitHub commit SHA, AWS Bedrock config, prompt templates] |
| **Test Cases** | [VENDOR: e.g., "TC-FR3-001: Verify AWS Bedrock Claude 3.5 Sonnet in eu-west-2", "TC-FR3-002: Test accuracy on 1000-query ground truth (>95%)", "TC-FR3-003: Adversarial testing (prompt injection, jailbreak)", "TC-FR3-004: Toxic content filtering (zero toxic outputs in 10K messages)"] | Tests verifying LLM quality, safety, and UK data residency | ó AWAITING VENDOR | [LLM accuracy report, adversarial testing report, guardrails test results] |
| **Acceptance Evidence** | [VENDOR: "AWS Bedrock Claude 3.5 Sonnet deployment in eu-west-2 verified", "Accuracy: 96.2% on 1000-query ground truth", "Guardrails: zero toxic outputs in 10K-message test"] | Evidence that LLM meets accuracy and safety targets | ó AWAITING VENDOR | [Deliverable milestone M3 (Testing Complete)] |

**Verification Method**: HMRC AI/ML Lead will review LLM configuration, prompt templates, and accuracy testing results.

---

#### FR-4: Source Citation and Explainability (MUST)

**Requirement Statement**: Every AI response cites source documents (HMRC guidance, legislation section) with clickable links to GOV.UK.

**Explainability Feature**: "Why did the ChatBot say this?" button providing lineage from query ’ retrieved documents ’ LLM reasoning ’ response.

**Acceptance Criteria** (SOW Section 4.2):
- [ ] 100% of AI responses include source citations with GOV.UK links
- [ ] Explainability feature tested and documented
- [ ] Lineage tracking from legislation ’ policy ’ guidance ’ AI response

**Aligns with Architecture Principles**: #5 (Responsible AI - Explainability), #8 (Data Quality and Accuracy)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "Explainability Service (Source Citation, Lineage Tracker, Explainability API)"] | HLD component for explainability and source citation | ó AWAITING VENDOR | [HLD Section: Explainability Architecture] |
| **DLD Module** | [VENDOR: e.g., "SourceCitationFormatter, LineageTracker (query ’ docs ’ LLM ’ response), ExplainabilityWidget (frontend UI)"] | DLD modules implementing source citation and explainability | ó AWAITING VENDOR | [DLD Section: Explainability & Source Citation] |
| **Implementation** | [VENDOR: e.g., "src/ai/citation.py, src/ai/lineage.py, src/frontend/components/ExplainabilityWidget.tsx"] | Source code implementing explainability features | ó AWAITING VENDOR | [GitHub commit SHA, explainability UI screenshots] |
| **Test Cases** | [VENDOR: e.g., "TC-FR4-001: Verify 100% source citation coverage on 1000 test responses", "TC-FR4-002: Test explainability feature (lineage tracking accurate)", "TC-FR4-003: Verify GOV.UK links are valid and accessible"] | Tests verifying source citation and explainability | ó AWAITING VENDOR | [Citation coverage report, explainability feature demo, link validation results] |
| **Acceptance Evidence** | [VENDOR: "Source citation: 100% of 1000 test responses cite sources", "Explainability feature: lineage tracking validated on 100 sample queries", "GOV.UK links: 100% valid and accessible"] | Evidence that explainability meets requirements | ó AWAITING VENDOR | [Deliverable milestone M3 (Testing Complete)] |

**Verification Method**: HMRC Product Owner will conduct UAT testing explainability feature and verifying source citations link to correct GOV.UK pages.

---

#### FR-5: Government Gateway Authentication (MUST)

**Requirement Statement**: OAuth 2.0 integration with Government Gateway for authenticated citizen access, support for personalized guidance using citizen tax records.

**Guest Mode**: Unauthenticated general tax queries supported (no personal tax records).

**Acceptance Criteria** (SOW Section 4.2):
- [ ] Government Gateway OAuth 2.0 Authorization Code flow implemented
- [ ] Multi-factor authentication (MFA) supported
- [ ] Personalized guidance tested with HMRC backend API integration (tax records, National Insurance)

**Aligns with Architecture Principles**: #2 (API-First Integration with Government Gateway), #3 (Security by Design)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "Citizen Identity Service (Government Gateway OAuth 2.0, MFA, Session Management)"] | HLD component for authentication and authorization | ó AWAITING VENDOR | [HLD Section: Authentication & Authorization Architecture] |
| **DLD Module** | [VENDOR: e.g., "OAuthClient (Government Gateway), MFAHandler, SessionManager (Redis), ConsentManager (ABAC)"] | DLD modules implementing Government Gateway integration | ó AWAITING VENDOR | [DLD Section: Citizen Identity & Authentication] |
| **Implementation** | [VENDOR: e.g., "src/auth/government-gateway.py (OAuth client), src/auth/mfa.py, src/auth/session.py, guest-mode config"] | Source code implementing Government Gateway OAuth 2.0 | ó AWAITING VENDOR | [GitHub commit SHA, OAuth config, MFA config] |
| **Test Cases** | [VENDOR: e.g., "TC-FR5-001: Test Government Gateway OAuth flow (Authorization Code)", "TC-FR5-002: Test MFA with Government Gateway", "TC-FR5-003: Test personalized guidance with HMRC tax records API", "TC-FR5-004: Test guest mode (unauthenticated queries)"] | Tests verifying authentication and personalized guidance | ó AWAITING VENDOR | [OAuth integration test results, MFA test results, personalized guidance demo] |
| **Acceptance Evidence** | [VENDOR: "Government Gateway OAuth 2.0 integration tested with sandbox environment", "MFA supported and tested", "Personalized guidance demo with sample tax records"] | Evidence that Government Gateway integration works | ó AWAITING VENDOR | [Deliverable milestone M3 (Testing Complete)] |

**Verification Method**: HMRC Security team will review OAuth 2.0 integration and conduct penetration testing. HMRC Product Owner will test personalized guidance with sample citizen profiles.

**DEPENDENCY**: Government Gateway sandbox access required from Week 1 (kickoff). HMRC will provide credentials and API documentation.

---

#### FR-6: Human Escalation (MUST)

**Requirement Statement**: Escalate complex queries to human agents via HMRC ServiceNow integration.

**Escalation Triggers**: Low confidence (<70%), complex tax scenarios, appeals/disputes.

**Acceptance Criteria** (SOW Section 4.2):
- [ ] HMRC ServiceNow integration tested (ticket creation, chat transcript attachment)
- [ ] Escalation rate <10% of conversations
- [ ] Escalation SLA: tickets created within 5 minutes, assigned to human agent within 1 hour

**Aligns with Architecture Principles**: #5 (Responsible AI - Human-in-the-Loop)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "Human Escalation Service (Escalation Logic, ServiceNow Integration, Handoff Manager)"] | HLD component for human escalation | ó AWAITING VENDOR | [HLD Section: Human Escalation Architecture] |
| **DLD Module** | [VENDOR: e.g., "EscalationEngine (confidence threshold, trigger rules), ServiceNowClient (ticket API), HandoffManager (chat transcript export)"] | DLD modules implementing escalation logic and ServiceNow integration | ó AWAITING VENDOR | [DLD Section: Human Escalation & ServiceNow Integration] |
| **Implementation** | [VENDOR: e.g., "src/escalation/engine.py, src/escalation/servicenow.py, escalation-rules.yaml"] | Source code implementing escalation logic and ServiceNow API | ó AWAITING VENDOR | [GitHub commit SHA, ServiceNow API config, escalation rules] |
| **Test Cases** | [VENDOR: e.g., "TC-FR6-001: Test escalation triggers (confidence <70%)", "TC-FR6-002: Test ServiceNow ticket creation with chat transcript", "TC-FR6-003: Verify escalation rate <10% on 1000-conversation test set"] | Tests verifying escalation logic and ServiceNow integration | ó AWAITING VENDOR | [Escalation test results, ServiceNow integration demo, escalation rate analysis] |
| **Acceptance Evidence** | [VENDOR: "Escalation logic tested: confidence threshold <70% triggers escalation", "ServiceNow integration tested: tickets created with chat transcripts", "Escalation rate: 8.5% on 1000-conversation test set"] | Evidence that escalation meets requirements | ó AWAITING VENDOR | [Deliverable milestone M3 (Testing Complete)] |

**Verification Method**: HMRC Product Owner will review escalation rate during Private Beta and verify ServiceNow tickets are created correctly with chat transcripts.

**DEPENDENCY**: HMRC ServiceNow sandbox access required from Week 1 (kickoff). HMRC will provide API credentials and ticket schema.

---

#### FR-7: Citizen Feedback Collection (MUST)

**Requirement Statement**: Thumbs up/down feedback for each AI response, "Was this helpful?" rating, optional free-text feedback.

**Periodic In-App Surveys**: NPS surveys for citizen satisfaction (target: >70% NPS).

**Acceptance Criteria** (SOW Section 4.2):
- [ ] Feedback widget integrated in chat UI (thumbs up/down, text input)
- [ ] NPS survey triggered after conversation ends (if authenticated citizen)
- [ ] Feedback data stored in database for analytics

**Aligns with Architecture Principles**: #8 (Data Quality and Accuracy)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "Feedback Collection Service (Feedback Widget, NPS Survey, Analytics Pipeline)"] | HLD component for feedback collection | ó AWAITING VENDOR | [HLD Section: Feedback Collection Architecture] |
| **DLD Module** | [VENDOR: e.g., "FeedbackWidget (React component), NPSSurvey (modal), FeedbackAPI (store feedback), AnalyticsPipeline (aggregate feedback)"] | DLD modules implementing feedback collection | ó AWAITING VENDOR | [DLD Section: Feedback Collection & Analytics] |
| **Implementation** | [VENDOR: e.g., "src/frontend/components/FeedbackWidget.tsx, src/api/feedback.py, PostgreSQL feedback table, analytics dashboard"] | Source code implementing feedback UI and API | ó AWAITING VENDOR | [GitHub commit SHA, database schema, analytics dashboard] |
| **Test Cases** | [VENDOR: e.g., "TC-FR7-001: Test feedback widget (thumbs up/down captured)", "TC-FR7-002: Test NPS survey (triggered after conversation)", "TC-FR7-003: Verify feedback data stored in database"] | Tests verifying feedback collection | ó AWAITING VENDOR | [Feedback collection demo, NPS survey demo, database validation] |
| **Acceptance Evidence** | [VENDOR: "Feedback widget tested: thumbs up/down captured for 100 test responses", "NPS survey tested: triggered and submitted by 50 test users", "Feedback data validated in PostgreSQL database"] | Evidence that feedback collection works | ó AWAITING VENDOR | [Deliverable milestone M4 (Private Beta)] |

**Verification Method**: HMRC Product Owner will test feedback widget and NPS survey during Private Beta and review feedback data in analytics dashboard.

---

#### FR-8: Conversation Management (MUST)

**Requirement Statement**: Save and resume conversations for authenticated citizens, conversation history (last 30 days), export transcript (PDF).

**Delete Conversation Option**: Subject to 7-year retention requirement if tax advice provided (citizen can request deletion via GOV.UK account).

**Acceptance Criteria** (SOW Section 4.2):
- [ ] Conversation save/resume functionality tested
- [ ] Conversation history UI tested (last 30 days)
- [ ] Export transcript (PDF) tested
- [ ] Delete conversation tested (with 7-year retention check)

**Aligns with Architecture Principles**: #7 (Data Sovereignty and UK GDPR Compliance)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "Conversation Management Service (ConversationStore, History API, Export API, Deletion API)"] | HLD component for conversation management | ó AWAITING VENDOR | [HLD Section: Conversation Management Architecture] |
| **DLD Module** | [VENDOR: e.g., "ConversationStore (PostgreSQL), HistoryAPI, ExportPDF (PDF generator), DeletionManager (retention policy check)"] | DLD modules implementing conversation management | ó AWAITING VENDOR | [DLD Section: Conversation Management] |
| **Implementation** | [VENDOR: e.g., "src/conversations/store.py, PostgreSQL schema, src/api/history.py, src/export/pdf-generator.py, src/api/delete.py"] | Source code implementing conversation CRUD operations | ó AWAITING VENDOR | [GitHub commit SHA, database schema, PDF export sample] |
| **Test Cases** | [VENDOR: e.g., "TC-FR8-001: Test conversation save/resume", "TC-FR8-002: Test conversation history (30 days)", "TC-FR8-003: Test PDF export (valid format)", "TC-FR8-004: Test delete with 7-year retention check"] | Tests verifying conversation management | ó AWAITING VENDOR | [Conversation management demo, PDF export sample, deletion test results] |
| **Acceptance Evidence** | [VENDOR: "Conversation save/resume tested: authenticated citizen can resume previous conversation", "History tested: last 30 days visible", "PDF export tested: valid PDF generated", "Deletion tested: 7-year retention enforced"] | Evidence that conversation management works | ó AWAITING VENDOR | [Deliverable milestone M4 (Private Beta)] |

**Verification Method**: HMRC Product Owner will test conversation management during Private Beta with authenticated test users.

---

#### FR-9: Plain English Content (MUST)

**Requirement Statement**: All AI responses in Plain English (average reading age 9, GOV.UK style guide).

**Content Design Review**: HMRC content designers review and approve prompt templates and sample responses.

**Acceptance Criteria** (SOW Section 4.2):
- [ ] Plain English validated using readability tools (Flesch-Kincaid reading age d9)
- [ ] GOV.UK style guide compliance verified (no jargon, active voice, short sentences)
- [ ] Content designer review and approval

**Aligns with Architecture Principles**: #4 (Accessibility-First Design)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "Content Design Strategy (Plain English prompt engineering, readability validation)"] | HLD strategy for Plain English content | ó AWAITING VENDOR | [HLD Section: Content Design & Plain English] |
| **DLD Module** | [VENDOR: e.g., "PromptTemplates (Plain English optimized), ReadabilityChecker (Flesch-Kincaid), ContentReviewTool"] | DLD modules ensuring Plain English content | ó AWAITING VENDOR | [DLD Section: Content Design & Readability] |
| **Implementation** | [VENDOR: e.g., "src/ai/prompts/ (Plain English templates), src/content/readability.py (Flesch-Kincaid scoring), content review log"] | Prompt templates and readability validation code | ó AWAITING VENDOR | [GitHub commit SHA, prompt templates, readability scores] |
| **Test Cases** | [VENDOR: e.g., "TC-FR9-001: Test readability of 100 sample responses (Flesch-Kincaid d9)", "TC-FR9-002: Content designer review of 50 responses (GOV.UK style guide compliance)", "UAT: Plain English feedback from Private Beta citizens"] | Tests verifying Plain English content | ó AWAITING VENDOR | [Readability report, content designer review feedback, UAT results] |
| **Acceptance Evidence** | [VENDOR: "Readability: 95% of 100 sample responses have Flesch-Kincaid d9", "Content designer review: 50 responses approved (GOV.UK style guide compliant)", "Private Beta feedback: 85% citizens found responses easy to understand"] | Evidence that Plain English requirement met | ó AWAITING VENDOR | [Deliverable milestone M4 (Private Beta)] |

**Verification Method**: HMRC Content Designer will review prompt templates and sample responses for GOV.UK style guide compliance and Plain English clarity.

---

#### FR-10: Welsh Language Support (MUST - Legal Requirement)

**Requirement Statement**: UI available in Welsh and English (toggle button), AI responses in Welsh for Welsh-language queries.

**Knowledge Base**: Welsh-language HMRC guidance ingested and vectorized.

**Legal Basis**: Welsh Language Act 1993.

**Acceptance Criteria** (SOW Section 4.2):
- [ ] Welsh/English UI toggle tested
- [ ] Welsh AI responses tested (NLU, RAG, LLM generation)
- [ ] Welsh knowledge base ingested (all HMRC Welsh guidance)

**Aligns with Architecture Principles**: #4 (Accessibility-First Design)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "Multilingual Support (Welsh/English UI, Welsh NLU, Welsh Knowledge Base)"] | HLD component for Welsh language support | ó AWAITING VENDOR | [HLD Section: Welsh Language Architecture] |
| **DLD Module** | [VENDOR: e.g., "LanguageToggle (frontend), WelshNLU (intent classification), WelshKnowledgeBase (separate OpenSearch index), WelshLLM (prompt templates in Welsh)"] | DLD modules implementing Welsh language support | ó AWAITING VENDOR | [DLD Section: Welsh Language Support] |
| **Implementation** | [VENDOR: e.g., "src/frontend/components/LanguageToggle.tsx, src/ai/welsh-nlu.py, OpenSearch Welsh index config, src/ai/prompts-welsh/"] | Source code for Welsh UI and AI responses | ó AWAITING VENDOR | [GitHub commit SHA, Welsh UI screenshots, Welsh knowledge base ingestion logs] |
| **Test Cases** | [VENDOR: e.g., "TC-FR10-001: Test Welsh/English toggle", "TC-FR10-002: Test Welsh NLU (intent recognition on 100 Welsh queries)", "TC-FR10-003: Test Welsh AI responses (accuracy on 100 Welsh tax queries)", "TC-FR10-004: Verify Welsh knowledge base ingested (HMRC Welsh guidance)"] | Tests verifying Welsh language support | ó AWAITING VENDOR | [Welsh UI demo, Welsh NLU accuracy report, Welsh AI response samples] |
| **Acceptance Evidence** | [VENDOR: "Welsh/English toggle tested and working", "Welsh NLU: 92% intent recognition on 100 Welsh queries", "Welsh AI responses: 50 sample responses reviewed by Welsh speaker", "Welsh knowledge base: all HMRC Welsh guidance ingested"] | Evidence that Welsh language support works | ó AWAITING VENDOR | [Deliverable milestone M4 (Private Beta)] |

**Verification Method**: HMRC Content Designer (Welsh speaker) will review Welsh UI translations and Welsh AI response quality during Private Beta.

**DEPENDENCY**: HMRC will provide Welsh-language guidance documents for knowledge base ingestion (Week 1).

---

#### FR-11: GOV.UK Design System Integration (MUST)

**Requirement Statement**: Use GOV.UK Design System components for consistent UX with GOV.UK.

**Design System**: gov.uk-frontend library for accessible, responsive components.

**Acceptance Criteria** (SOW Section 4.2):
- [ ] All frontend components use gov.uk-frontend library
- [ ] Consistent GOV.UK styling (typography, colors, spacing, interaction patterns)
- [ ] Responsive design tested (desktop, tablet, mobile)

**Aligns with Architecture Principles**: #4 (Accessibility-First Design), #9 (Approved Technology Stack)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "Frontend Architecture (React + gov.uk-frontend, GOV.UK Design System components)"] | HLD specifying GOV.UK Design System integration | ó AWAITING VENDOR | [HLD Section: Frontend Architecture & GOV.UK Design System] |
| **DLD Module** | [VENDOR: e.g., "All React components using gov.uk-frontend library (Button, Input, Textarea, Accordion, etc.)"] | DLD specifying GOV.UK Design System usage for each UI component | ó AWAITING VENDOR | [DLD Section: UI Components & GOV.UK Design System] |
| **Implementation** | [VENDOR: e.g., "src/frontend/ (all components import gov.uk-frontend), package.json (gov.uk-frontend dependency), responsive CSS"] | Source code using gov.uk-frontend components | ó AWAITING VENDOR | [GitHub commit SHA, frontend screenshots, responsive design demo] |
| **Test Cases** | [VENDOR: e.g., "TC-FR11-001: Visual regression testing (GOV.UK styling consistency)", "TC-FR11-002: Responsive design testing (desktop, tablet, mobile)", "TC-FR11-003: Accessibility testing (gov.uk-frontend components WCAG 2.2 AA compliant)"] | Tests verifying GOV.UK Design System integration | ó AWAITING VENDOR | [Visual regression test results, responsive design screenshots, accessibility audit] |
| **Acceptance Evidence** | [VENDOR: "All components use gov.uk-frontend library (verified via code review)", "GOV.UK styling consistent (visual regression tests pass)", "Responsive design tested on 5 devices (desktop, tablet, mobile)"] | Evidence that GOV.UK Design System integration meets requirements | ó AWAITING VENDOR | [Deliverable milestone M3 (Testing Complete)] |

**Verification Method**: HMRC Accessibility Specialist and UX Designer will review frontend implementation for GOV.UK Design System compliance and visual consistency with GOV.UK.

---

### 2.3 Non-Functional Requirements (NFR) Traceability

Due to document length constraints, I'll provide a summary table for all 21 NFRs with key traceability points. Vendor must expand each NFR with full traceability mapping (HLD ’ DLD ’ Implementation ’ Tests) similar to BR/FR sections above.

#### NFR Summary Traceability Matrix (VENDOR TO EXPAND)

| NFR ID | Requirement | Category | Target | HLD Component (Vendor) | DLD Module (Vendor) | Test Cases (Vendor) | Status |
|--------|-------------|----------|--------|------------------------|---------------------|---------------------|--------|
| **NFR-P-1** | Response Time | Performance | <2s p95 | [VENDOR: e.g., "Caching layer, async processing"] | [VENDOR: Caching modules, async workers] | [VENDOR: Load testing, latency monitoring] | ó AWAITING VENDOR |
| **NFR-P-2** | Throughput | Performance | 500 req/s | [VENDOR: e.g., "Auto-scaling ECS, load balancer"] | [VENDOR: ECS config, ALB config] | [VENDOR: Stress testing 500 req/s] | ó AWAITING VENDOR |
| **NFR-A-1** | Uptime SLA | Availability | 99.9% business hours | [VENDOR: e.g., "Multi-AZ ECS, health checks"] | [VENDOR: Multi-AZ config, health check endpoint] | [VENDOR: Uptime monitoring, 30-day baseline] | ó AWAITING VENDOR |
| **NFR-A-2** | Disaster Recovery RPO | Availability | <1 hour | [VENDOR: e.g., "Automated backups, cross-region replication"] | [VENDOR: RDS backup config, S3 replication] | [VENDOR: DR drill, RPO verification] | ó AWAITING VENDOR |
| **NFR-A-3** | Disaster Recovery RTO | Availability | <15 minutes | [VENDOR: e.g., "Automated failover, runbooks"] | [VENDOR: Failover automation, runbooks] | [VENDOR: Failover testing, RTO measurement] | ó AWAITING VENDOR |
| **NFR-S-1** | Horizontal Scaling | Scalability | Auto-scale to 10K concurrent users | [VENDOR: e.g., "ECS auto-scaling, RDS read replicas"] | [VENDOR: ECS scaling policy, RDS replicas] | [VENDOR: Load testing 10K users, verify auto-scale] | ó AWAITING VENDOR |
| **NFR-S-2** | Data Volume Growth | Scalability | Support 10M conversations/year by Year 3 | [VENDOR: e.g., "Scalable storage (S3, RDS)"] | [VENDOR: Storage architecture, data lifecycle] | [VENDOR: Storage capacity planning, data volume projections] | ó AWAITING VENDOR |
| **NFR-SEC-1** | Authentication & Authorization | Security | Government Gateway OAuth 2.0, MFA, ABAC | [VENDOR: See FR-5 traceability] | [VENDOR: OAuth, MFA, ABAC modules] | [VENDOR: Auth penetration testing, OAuth security audit] | ó AWAITING VENDOR |
| **NFR-SEC-2** | Encryption | Security | TLS 1.3 in transit, AES-256 at rest | [VENDOR: e.g., "ALB TLS config, RDS encryption, S3 encryption"] | [VENDOR: TLS certificates, KMS keys, encryption config] | [VENDOR: Encryption verification, TLS configuration audit] | ó AWAITING VENDOR |
| **NFR-SEC-3** | Secrets Management | Security | AWS Secrets Manager (no hardcoded credentials) | [VENDOR: e.g., "All credentials in Secrets Manager"] | [VENDOR: Secrets Manager config, app code secrets retrieval] | [VENDOR: Secret scanning (git-secrets), config audit] | ó AWAITING VENDOR |
| **NFR-SEC-4** | Vulnerability Management | Security | Weekly scans, critical patches <7 days, high <30 days | [VENDOR: e.g., "AWS Inspector, Snyk, penetration testing"] | [VENDOR: Scanning config, patch process] | [VENDOR: Vulnerability scan reports, patching SLA verification] | ó AWAITING VENDOR |
| **NFR-SEC-5** | Compliance (Cyber Essentials Plus) | Security | Cyber Essentials Plus certification | [VENDOR: e.g., "All Cyber Essentials Plus controls implemented"] | [VENDOR: Security controls documentation] | [VENDOR: Cyber Essentials Plus audit, certification] | ó AWAITING VENDOR |
| **NFR-SEC-6** | AI Safety & Security | Security | Prompt injection defense, adversarial testing | [VENDOR: See FR-3 guardrails traceability] | [VENDOR: Input sanitization, guardrails modules] | [VENDOR: Adversarial testing, prompt injection tests] | ó AWAITING VENDOR |
| **NFR-C-1** | UK GDPR Compliance | Compliance | UK data residency, DPIA, data subject rights | [VENDOR: See BR-7 traceability] | [VENDOR: UK region config, data subject rights APIs] | [VENDOR: DPIA testing, data subject rights API tests] | ó AWAITING VENDOR |
| **NFR-C-2** | Audit Logging | Compliance | 7-year retention, W5H1 format, immutable | [VENDOR: e.g., "CloudTrail, S3 Object Lock, Splunk integration"] | [VENDOR: Audit log format, S3 Object Lock config, Splunk forwarder] | [VENDOR: Audit log validation, retention policy verification] | ó AWAITING VENDOR |
| **NFR-C-3** | ATRS Reporting | Compliance | ATRS published on GOV.UK before Private Beta | [VENDOR: See BR-6 traceability] | [VENDOR: ATRS generation tooling, bias testing reports] | [VENDOR: ATRS review by Data Ethics Committee] | ó AWAITING VENDOR |
| **NFR-U-1** | GOV.UK UX Standards | Usability | GOV.UK Design System, Plain English, user research | [VENDOR: See FR-9, FR-11 traceability] | [VENDOR: GOV.UK components, user research documentation] | [VENDOR: User testing with 100+ Private Beta citizens] | ó AWAITING VENDOR |
| **NFR-U-2** | Accessibility (WCAG 2.2 AA) | Usability | 100% WCAG 2.2 AA compliance | [VENDOR: See BR-5 traceability] | [VENDOR: Accessible UI components, ARIA labels] | [VENDOR: Accessibility audit (zero critical/high issues)] | ó AWAITING VENDOR |
| **NFR-U-3** | Welsh Language | Usability | Bilingual UI, Welsh AI responses | [VENDOR: See FR-10 traceability] | [VENDOR: Welsh UI, Welsh NLU, Welsh knowledge base] | [VENDOR: Welsh language testing with Welsh speakers] | ó AWAITING VENDOR |
| **NFR-M-1** | Observability | Maintainability | Structured logs, metrics, traces, dashboards | [VENDOR: e.g., "CloudWatch, Prometheus, OpenTelemetry, Splunk"] | [VENDOR: Logging config, metrics exporters, tracing instrumentation] | [VENDOR: Observability validation, SLO alerting tests] | ó AWAITING VENDOR |
| **NFR-M-2** | Documentation | Maintainability | HLD, DLD, API docs, runbooks | [VENDOR: See SOW Section 4.5 deliverables] | [VENDOR: Documentation tooling, OpenAPI specs] | [VENDOR: Documentation review, completeness check] | ó AWAITING VENDOR |
| **NFR-M-3** | Knowledge Transfer | Maintainability | Training for HMRC dev, SRE, content teams | [VENDOR: See SOW Section 4.6 knowledge transfer] | [VENDOR: Training materials, workshops, documentation] | [VENDOR: Knowledge transfer sessions, HMRC team sign-off] | ó AWAITING VENDOR |
| **NFR-I-1** | API Standards | Interoperability | OpenAPI 3.0+, REST, JSON, semantic HTTP codes | [VENDOR: e.g., "All APIs documented with OpenAPI"] | [VENDOR: OpenAPI specs for all endpoints] | [VENDOR: API contract testing, OpenAPI validation] | ó AWAITING VENDOR |
| **NFR-I-2** | Integration Capabilities | Interoperability | Government Gateway, HMRC APIs, AWS Bedrock, ServiceNow | [VENDOR: See INT-1 to INT-5 traceability] | [VENDOR: Integration modules for each system] | [VENDOR: Integration testing for all 5 integrations] | ó AWAITING VENDOR |
| **NFR-I-3** | Data Portability | Interoperability | Citizen can export transcripts (PDF), portable data formats | [VENDOR: See FR-8 traceability] | [VENDOR: PDF export API, backup formats] | [VENDOR: PDF export testing, data portability verification] | ó AWAITING VENDOR |

**Vendor Action Required**: Expand each NFR row above into full traceability section (similar to BR/FR sections) with HLD component, DLD module, implementation details, test cases, acceptance evidence, and verification method.

---

### 2.4 Integration Requirements (INT) Traceability

#### INT-1: Government Gateway OAuth 2.0 (MUST)

**Requirement**: OAuth 2.0 Authorization Code flow for citizen authentication, MFA support.

**Scopes**: `openid`, `profile`, `email`, `tax_records` (with citizen consent).

**Aligns with Architecture Principles**: #2 (API-First Integration with Government Gateway)

**Traceability**: See FR-5 (Government Gateway Authentication) and NFR-SEC-1 (Authentication & Authorization) for full traceability mapping.

**Status**: ó AWAITING VENDOR

---

#### INT-2: HMRC Content Management System (MUST)

**Requirement**: RESTful API integration for knowledge base ingestion, automated pipeline for content updates (every 48 hours).

**Aligns with Architecture Principles**: #8 (Data Quality and Accuracy)

**Traceability**: See FR-2 (RAG with HMRC Knowledge Base) for full traceability mapping.

**Status**: ó AWAITING VENDOR

**DEPENDENCY**: HMRC will provide CMS API credentials and documentation (Week 1).

---

#### INT-3: HMRC Backend APIs (MUST)

**Requirement**: Tax Records API (Self Assessment, PAYE), National Insurance API (NI number verification, contributions), Circuit breaker pattern for fault tolerance.

**Aligns with Architecture Principles**: #2 (API-First Integration), #13 (Resilience and Fault Tolerance)

**Traceability Mapping** (VENDOR TO COMPLETE):

| Lifecycle Stage | Artifact | Description | Status | Vendor Evidence |
|-----------------|----------|-------------|--------|-----------------|
| **HLD Component** | [VENDOR: e.g., "HMRC Integration Service (Tax Records Client, NI Client, Circuit Breaker)"] | HLD component for HMRC backend API integration | ó AWAITING VENDOR | [HLD Section: HMRC Backend Integration] |
| **DLD Module** | [VENDOR: e.g., "TaxRecordsClient, NIClient, CircuitBreaker (Hystrix or similar)"] | DLD modules for HMRC API clients with resilience patterns | ó AWAITING VENDOR | [DLD Section: HMRC Backend Integration] |
| **Implementation** | [VENDOR: e.g., "src/integration/hmrc-tax-records.py, src/integration/hmrc-ni.py, circuit-breaker config"] | Source code for HMRC API integration | ó AWAITING VENDOR | [GitHub commit SHA, circuit breaker config] |
| **Test Cases** | [VENDOR: e.g., "TC-INT3-001: Test Tax Records API (sandbox)", "TC-INT3-002: Test NI API (sandbox)", "TC-INT3-003: Test circuit breaker (HMRC API failure simulation)"] | Integration tests with HMRC sandbox APIs | ó AWAITING VENDOR | [Integration test results, circuit breaker validation] |
| **Acceptance Evidence** | [VENDOR: "HMRC Tax Records API integration tested with sandbox", "NI API integration tested", "Circuit breaker tested (fails open after 3 retries)"] | Evidence that HMRC backend integration works | ó AWAITING VENDOR | [Deliverable milestone M3 (Testing Complete)] |

**Verification Method**: HMRC Technical Lead will review integration code and conduct integration testing with HMRC sandbox APIs.

**DEPENDENCY**: HMRC will provide sandbox API access for Tax Records and NI APIs (Week 1).

---

#### INT-4: HMRC ServiceNow (MUST)

**Requirement**: Create incident tickets for human escalation, provide chat transcript context to human agents, bi-directional status updates.

**Aligns with Architecture Principles**: #2 (API-First Integration)

**Traceability**: See FR-6 (Human Escalation) for full traceability mapping.

**Status**: ó AWAITING VENDOR

**DEPENDENCY**: HMRC will provide ServiceNow API credentials and ticket schema (Week 1).

---

#### INT-5: AWS Bedrock (MUST)

**Requirement**: Claude 3.5 Sonnet LLM via AWS Bedrock API, UK data residency (eu-west-2 region), token usage monitoring, Guardrails API.

**Aligns with Architecture Principles**: #5 (Responsible AI), #9 (Approved Technology Stack)

**Traceability**: See FR-3 (LLM Response Generation) for full traceability mapping.

**Status**: ó AWAITING VENDOR

---

## 3. BACKWARD TRACEABILITY: TESTS ’ IMPLEMENTATION ’ DESIGN ’ REQUIREMENTS

**Purpose**: Ensure no "orphan" design elements, implementation code, or tests that don't trace back to requirements (potential scope creep or unnecessary work).

**Vendor Responsibility**: For every design component, source code module, and test case delivered, vendor must demonstrate backward traceability to at least one requirement (BR, FR, NFR, or INT).

**Process**:
1. **Design Review (HLD/DLD Approval, Weeks 4-8)**: HMRC Architecture Review Board will review HLD and DLD to ensure all components trace to requirements. Any orphan components flagged for justification or removal.
2. **Implementation Review (Code Review, Weeks 9-32)**: HMRC dev team will spot-check source code to ensure modules trace to requirements. Any orphan code flagged for justification or removal.
3. **Test Review (Testing Complete, Week 40)**: HMRC QA team will review test plan and test cases to ensure all tests trace to requirements. Any orphan tests flagged for justification or removal.

**Acceptance Criteria**: Zero orphan design components, zero orphan code modules, zero orphan test cases (or all orphans justified as "technical necessity" with HMRC approval).

### 3.1 Backward Traceability Matrix (VENDOR TO COMPLETE)

| Artifact Type | Artifact Name | Traces To Requirement(s) | Justification (if not directly to requirement) | Status |
|---------------|---------------|--------------------------|-----------------------------------------------|--------|
| **HLD Component** | [VENDOR: e.g., "Analytics & Reporting Service"] | BR-1 (Call Deflection), BR-3 (Citizen Satisfaction) | Directly implements call deflection and NPS tracking | ó AWAITING VENDOR |
| **HLD Component** | [VENDOR: e.g., "Logging & Monitoring Infrastructure"] | NFR-M-1 (Observability), NFR-C-2 (Audit Logging), NFR-A-1 (Uptime SLA) | Cross-cutting concern supporting multiple NFRs | ó AWAITING VENDOR |
| **DLD Module** | [VENDOR: e.g., "HealthCheckEndpoint"] | NFR-A-1 (Uptime SLA) | Technical necessity for uptime monitoring | ó AWAITING VENDOR |
| **DLD Module** | [VENDOR: e.g., "RateLimiter"] | NFR-SEC-6 (AI Safety - rate limiting to prevent abuse) | Technical necessity for security | ó AWAITING VENDOR |
| **Source Code** | [VENDOR: e.g., "src/utils/logging.py"] | NFR-M-1 (Observability) | Utility module for structured logging | ó AWAITING VENDOR |
| **Test Case** | [VENDOR: e.g., "TC-PERF-001: Load testing 10K concurrent users"] | NFR-P-2 (Throughput), NFR-S-1 (Horizontal Scaling) | Tests multiple NFRs simultaneously | ó AWAITING VENDOR |
| **Test Case** | [VENDOR: e.g., "TC-SEC-999: Penetration testing"] | NFR-SEC-1 to NFR-SEC-6 (All security requirements) | Cross-cutting security validation | ó AWAITING VENDOR |

**Vendor Action Required**: Populate backward traceability matrix with all HLD components, DLD modules, source code files, and test cases, ensuring each artifact traces to at least one requirement.

**Orphan Resolution**: If any artifact does NOT trace to a requirement, vendor must either:
1. **Justify as Technical Necessity**: Explain why artifact is required (e.g., "Logging utility module required to implement NFR-M-1 but not a requirement itself")
2. **Add Missing Requirement**: If artifact addresses a gap in requirements, propose new requirement to HMRC for approval
3. **Remove Artifact**: If artifact is unnecessary, remove from design/implementation

---

## 4. COVERAGE ANALYSIS

### 4.1 Requirements Coverage Summary (BASELINE)

| Category | Total Requirements | Awaiting Design | Awaiting Implementation | Awaiting Tests | % Coverage (Baseline) |
|----------|-------------------|-----------------|-------------------------|----------------|-----------------------|
| **Business Requirements (BR)** | 7 | 7 | 7 | 7 | **0%** (Pre-Vendor) |
| **Functional Requirements (FR)** | 11 | 11 | 11 | 11 | **0%** (Pre-Vendor) |
| **Non-Functional Requirements (NFR)** | 21 | 21 | 21 | 21 | **0%** (Pre-Vendor) |
| **Integration Requirements (INT)** | 5 | 5 | 5 | 5 | **0%** (Pre-Vendor) |
| **TOTAL** | **44** | **44** | **44** | **44** | **0%** (Pre-Vendor) |

**Target Coverage** (Vendor Milestones):
- **M1 (Design Approval, Week 8)**: 100% design coverage (all 44 requirements mapped to HLD/DLD)
- **M2 (Development Milestone, Week 20)**: 50% implementation coverage (22 requirements implemented)
- **M3 (Testing Complete, Week 40)**: 100% test coverage (all 44 requirements tested)
- **M5 (Production Launch, Week 52)**: 100% implementation + 100% test coverage (all 44 requirements implemented AND tested)

**Current Status**: **PRE-PROCUREMENT** - No vendor selected, no design/implementation/tests yet. Baseline is 0% coverage across all lifecycle stages.

### 4.2 Coverage by Priority (All Requirements are MUST)

| Priority | Total Requirements | % of Total | Target Coverage | Rationale |
|----------|-------------------|------------|-----------------|-----------|
| **MUST** | **44** | **100%** | **100%** | ALL requirements are mandatory for production launch. No optional (SHOULD/MAY) requirements in baseline. |
| **SHOULD** | 0 | 0% | N/A | No SHOULD requirements in baseline. |
| **MAY** | 0 | 0% | N/A | No MAY requirements in baseline. |

**Key Constraint**: Vendors cannot propose descoping any of the 44 baseline requirements. All are **MUST** for GDS Service Standard Live Assessment and production launch.

**Scope Management**: If vendor identifies new requirements during design (e.g., technical requirements not captured in baseline), vendor must:
1. Propose new requirement with justification
2. Classify as MUST/SHOULD/MAY with HMRC approval
3. Add to traceability matrix
4. Update SOW deliverables and acceptance criteria if needed

### 4.3 Coverage Trends (VENDOR TO UPDATE)

Track coverage progression from baseline (0%) to production launch (100%):

| Date | Milestone | Design Coverage (%) | Implementation Coverage (%) | Test Coverage (%) | Overall Coverage (%) |
|------|-----------|---------------------|----------------------------|-------------------|---------------------|
| **2025-10-14** | **Baseline (Pre-Procurement)** | **0%** (44/44 awaiting) | **0%** (44/44 awaiting) | **0%** (44/44 awaiting) | **0%** |
| 2026-02-09 (Week 1) | Kickoff | TBD | TBD | TBD | TBD |
| 2026-03-09 (Week 4) | HLD Submission | Target: 100% | 0% | 0% | Target: 33% |
| 2026-04-06 (Week 8) | DLD Submission / M1 Design Approval | Target: 100% | 0% | 0% | Target: 33% |
| 2026-06-08 (Week 20) | M2 Development Milestone | 100% | Target: 50% | 0% | Target: 50% |
| 2026-09-14 (Week 40) | M3 Testing Complete | 100% | Target: 100% | Target: 100% | Target: 100% |
| 2026-11-23 (Week 52) | M5 Production Launch | **100%** (required) | **100%** (required) | **100%** (required) | **100%** (required) |

**Vendor Action Required**: Update coverage trends table at each milestone with actual coverage percentages. Any coverage below target requires gap analysis and remediation plan.

**Acceptance Criteria**: Final payment (Milestone M5, 20%) contingent on **100% overall coverage** (all 44 requirements designed, implemented, AND tested).

---

## 5. GAP ANALYSIS

### 5.1 Current Gaps (BASELINE)

**Status**: Pre-procurement phase, no vendor selected. All 44 requirements are gaps (0% coverage).

**Expected Gaps by Milestone**:
- **M1 (Design Approval, Week 8)**: 0 design gaps expected (vendor must map all 44 requirements to HLD/DLD)
- **M2 (Development Milestone, Week 20)**: Up to 22 implementation gaps acceptable (50% implementation target)
- **M3 (Testing Complete, Week 40)**: 0 test gaps expected (vendor must test all 44 requirements)
- **M5 (Production Launch, Week 52)**: 0 gaps tolerated (100% coverage required)

### 5.2 Gap Categories

#### 5.2.1 Requirements Without Design (Expected at M1)

**Current**: All 44 requirements lack design (pre-vendor phase).

**Vendor Obligation**: By M1 (Design Approval, Week 8), vendor must provide HLD and DLD documenting how each of the 44 requirements will be addressed. Zero design gaps tolerated at M1.

**Example Gap Resolution** (vendor template):

| Req ID | Requirement | Gap Description | Resolution Plan | Target Completion | Owner |
|--------|-------------|-----------------|-----------------|-------------------|-------|
| [e.g., FR-2] | RAG with HMRC Knowledge Base | No HLD/DLD for knowledge base ingestion pipeline | [VENDOR: "HLD Section 4.2 will document ingestion architecture; DLD Section 6.3 will specify ingestion modules"] | Week 4 (HLD), Week 8 (DLD) | [VENDOR: Solution Architect] |

#### 5.2.2 Requirements Without Implementation (Expected at M2-M3)

**Current**: All 44 requirements lack implementation (pre-vendor phase).

**Vendor Obligation**:
- By M2 (Development Milestone, Week 20): 50% implementation (22 requirements implemented)
- By M3 (Testing Complete, Week 40): 100% implementation (all 44 requirements implemented)

Zero implementation gaps tolerated at M5 (Production Launch).

**Prioritization**: Vendor must prioritize implementation to achieve 50% coverage by M2. HMRC recommends prioritizing in this order:
1. **Core Functional Requirements** (FR-1 to FR-11): Highest priority (ChatBot cannot function without these)
2. **Critical NFRs** (Security, UK GDPR, Accessibility): Legal/compliance requirements
3. **Business Requirements** (BR-1 to BR-7): Business outcomes and KPIs
4. **Integration Requirements** (INT-1 to INT-5): External system dependencies

#### 5.2.3 Requirements Without Tests (Expected at M3)

**Current**: All 44 requirements lack tests (pre-vendor phase).

**Vendor Obligation**: By M3 (Testing Complete, Week 40), vendor must provide test cases and execution results for all 44 requirements. Zero test gaps tolerated at M3 and M5.

**Test Coverage Types Required**:
- **Functional Requirements (FR)**: Unit tests, integration tests, E2E tests, UAT
- **Non-Functional Requirements (NFR)**: Performance tests, security tests, accessibility tests, bias tests, resilience tests
- **Business Requirements (BR)**: UAT with citizens (Private Beta, Public Beta), KPI validation
- **Integration Requirements (INT)**: Integration tests with sandbox APIs, end-to-end integration tests

**Example Test Gap** (vendor template):

| Req ID | Requirement | Gap Description | Test Plan | Target Completion | Owner |
|--------|-------------|-----------------|-----------|-------------------|-------|
| [e.g., NFR-P-1] | Response Time <2s p95 | No performance tests executed | [VENDOR: "Load test 10K concurrent users, measure p95 latency, verify <2s"] | Week 36 | [VENDOR: QA Lead] |

#### 5.2.4 Design Components Without Requirements (Orphans)

**Current**: No design components exist yet (pre-vendor phase).

**Vendor Obligation**: During HLD/DLD review (Weeks 4-8), HMRC Architecture Review Board will flag any design components that do NOT trace back to requirements. Vendor must either:
1. Justify as technical necessity (e.g., "Logging utility required for NFR-M-1 but not a requirement itself")
2. Remove component if unnecessary (scope creep)

**Acceptance Criteria**: Zero orphan components tolerated at M1 (Design Approval) unless justified and approved by HMRC.

### 5.3 Risk Assessment for Gaps

| Gap Type | Risk Level | Impact if Not Resolved | Mitigation |
|----------|-----------|------------------------|------------|
| **Design gaps at M1** | **CRITICAL** | Design approval blocked ’ project delay | Vendor must complete HLD/DLD for all 44 requirements by Week 8. HMRC Architecture Review Board will review and approve/reject. |
| **Implementation gaps at M2** | **MEDIUM** | 50% coverage acceptable at M2; full coverage required by M5 | Vendor must prioritize implementation. HMRC will monitor progress weekly. |
| **Implementation gaps at M5** | **CRITICAL** | Production launch blocked ’ contract penalty | Vendor must achieve 100% implementation by M5. No exceptions. |
| **Test gaps at M3** | **CRITICAL** | Testing approval blocked ’ UAT cannot proceed | Vendor must complete all tests by Week 40. HMRC QA Lead will review test results. |
| **Test gaps at M5** | **CRITICAL** | Production launch blocked ’ GDS assessment failure | Vendor must achieve 100% test coverage by M5. No exceptions. |
| **Orphan design components** | **LOW** | Potential scope creep or wasted effort | HMRC Architecture Review Board will review and approve/reject orphans at M1. |

**Critical Path**: Zero tolerance for design gaps at M1, implementation gaps at M5, or test gaps at M3/M5. Any critical gaps = milestone rejection and payment withholding.

---

## 6. VENDOR OBLIGATIONS & ACCEPTANCE CRITERIA

### 6.1 Traceability Matrix Completion Schedule

| Milestone | Traceability Deliverable | Due Date | Acceptance Criteria | Payment Trigger |
|-----------|--------------------------|----------|---------------------|-----------------|
| **M1 (Design Approval)** | **Updated Traceability Matrix with HLD/DLD Mapping** | **Week 8** | - All 44 requirements mapped to HLD components<br>- All 44 requirements mapped to DLD modules<br>- Zero design gaps (or all gaps justified and approved)<br>- Backward traceability: All HLD/DLD components trace to requirements (zero orphans or justified) | 15% payment upon M1 approval |
| **M2 (Development Milestone)** | **Updated Traceability Matrix with Implementation Mapping** | **Week 20** | - 50% implementation coverage (22/44 requirements implemented)<br>- Source code file references provided for implemented requirements<br>- Backward traceability: Implemented code modules trace to requirements | 20% payment upon M2 completion |
| **M3 (Testing Complete)** | **Final Traceability Matrix with Test Mapping** | **Week 40** | - 100% test coverage (all 44 requirements tested)<br>- Test case IDs and execution results provided<br>- 100% implementation coverage (all 44 requirements implemented)<br>- Zero test gaps<br>- Backward traceability: All test cases trace to requirements | 20% payment upon M3 approval |
| **M5 (Production Launch)** | **Final Traceability Matrix Approval** | **Week 52** | - 100% overall coverage (all 44 requirements designed, implemented, tested)<br>- Architecture Review Board approval<br>- Zero critical gaps<br>- Traceability matrix published as part of project handover | 20% payment upon M5 approval + GDS Live Assessment PASS |

### 6.2 Traceability Review Gates

**Gate 1 (Design Review, Week 8)**:
- **Reviewers**: HMRC Architecture Review Board (EA, CISO, Accessibility Specialist, Product Owner)
- **Review Focus**: HLD/DLD traceability to requirements, orphan component identification
- **Approval Criteria**: All 44 requirements mapped to design, zero unjustified orphans
- **Outcome**: APPROVED (proceed to implementation) / APPROVED WITH CONDITIONS (minor gaps, resolve within 2 weeks) / REJECTED (major gaps, revise and resubmit)

**Gate 2 (Implementation Review, Week 20)**:
- **Reviewers**: HMRC Technical Leads, EA
- **Review Focus**: Implementation progress, code quality, traceability to design
- **Approval Criteria**: 50% implementation coverage, code meets quality standards
- **Outcome**: ON TRACK (proceed) / AT RISK (mitigation plan required) / BEHIND (escalation to SRO)

**Gate 3 (Testing Review, Week 40)**:
- **Reviewers**: HMRC QA Lead, Accessibility Specialist, Security Architect, Product Owner
- **Review Focus**: Test coverage, test results, gap resolution
- **Approval Criteria**: 100% test coverage, 100% implementation coverage, all tests passing (or failures with resolution plan)
- **Outcome**: APPROVED (proceed to Private Beta) / APPROVED WITH CONDITIONS (minor test failures, resolve during beta) / REJECTED (major test failures, fix and retest)

**Gate 4 (Production Readiness, Week 52)**:
- **Reviewers**: HMRC Architecture Review Board, SRO, CTO, GDS Assessor
- **Review Focus**: Final traceability matrix, production readiness, GDS Service Standard compliance
- **Approval Criteria**: 100% overall coverage, GDS Live Assessment PASS, zero critical gaps
- **Outcome**: APPROVED FOR PRODUCTION (launch authorized) / NOT READY (blockers identified, resolve before launch)

### 6.3 Traceability Audit Trail

**Audit Requirements**: All traceability matrix updates must be version-controlled and auditable.

**Version Control**: Vendor must maintain traceability matrix in Git repository alongside HLD, DLD, source code, and test documentation.

**Change Log**: Every update to traceability matrix must include:
- Date of update
- Milestone/deliverable triggering update
- Summary of changes (e.g., "Mapped FR-1 to FR-5 to HLD components", "Added test cases for NFR-SEC-1 to NFR-SEC-6")
- Author (vendor personnel responsible for update)

**Audit Trail Example**:

| Version | Date | Milestone | Changes | Author |
|---------|------|-----------|---------|--------|
| 1.0 | 2025-10-14 | Baseline (Pre-Procurement) | Initial baseline: 44 requirements, 0% coverage | HMRC EA Team |
| 1.1 | 2026-03-09 | HLD Submission (Week 4) | [VENDOR: "Mapped all 44 requirements to HLD components"] | [VENDOR: Solution Architect] |
| 1.2 | 2026-04-06 | DLD Submission / M1 (Week 8) | [VENDOR: "Mapped all 44 requirements to DLD modules, APIs, schemas"] | [VENDOR: Technical Lead] |
| 1.3 | 2026-06-08 | M2 (Week 20) | [VENDOR: "Added source code references for 22 implemented requirements (50% coverage)"] | [VENDOR: Technical Lead] |
| 1.4 | 2026-09-14 | M3 (Week 40) | [VENDOR: "Added test case IDs and execution results for all 44 requirements (100% test coverage), added source code references for remaining 22 requirements (100% implementation coverage)"] | [VENDOR: QA Lead] |
| 2.0 | 2026-11-23 | M5 (Week 52) | Final traceability matrix approved by HMRC Architecture Review Board | [VENDOR: Project Manager] |

---

## 7. METRICS AND KPIS

### 7.1 Traceability Metrics

| Metric | Baseline (2025-10-14) | Target M1 (Week 8) | Target M2 (Week 20) | Target M3 (Week 40) | Target M5 (Week 52) | Status |
|--------|----------------------|-------------------|---------------------|---------------------|---------------------|--------|
| **Requirements with Design Coverage** | 0/44 (0%) | 44/44 (100%) | 44/44 (100%) | 44/44 (100%) | 44/44 (100%) | ó AWAITING VENDOR |
| **Requirements with Implementation Coverage** | 0/44 (0%) | 0/44 (0%) | 22/44 (50%) | 44/44 (100%) | 44/44 (100%) | ó AWAITING VENDOR |
| **Requirements with Test Coverage** | 0/44 (0%) | 0/44 (0%) | 0/44 (0%) | 44/44 (100%) | 44/44 (100%) | ó AWAITING VENDOR |
| **Overall Coverage (Design + Impl + Test)** | 0% | 33% | 50% | 100% | 100% | ó AWAITING VENDOR |
| **Orphan Design Components** | 0 (no design yet) | 0 (target) | 0 (target) | 0 (target) | 0 (target) | ó AWAITING VENDOR |
| **Orphan Test Cases** | 0 (no tests yet) | 0 (target) | 0 (target) | 0 (target) | 0 (target) | ó AWAITING VENDOR |
| **Critical Gaps** | 44 (all requirements) | 0 (target) | 0 (target) | 0 (target) | 0 (target) | ó AWAITING VENDOR |

**Vendor Action Required**: Update metrics table at each milestone with actual values. Any metric below target requires gap analysis and remediation plan.

### 7.2 Coverage by Requirement Type (Target: 100% for All Types)

| Requirement Type | Total | Target Coverage (M5) | Current Coverage (Baseline) | Status |
|------------------|-------|----------------------|----------------------------|--------|
| **Business Requirements (BR)** | 7 | 7/7 (100%) | 0/7 (0%) | ó AWAITING VENDOR |
| **Functional Requirements (FR)** | 11 | 11/11 (100%) | 0/11 (0%) | ó AWAITING VENDOR |
| **Non-Functional Requirements (NFR)** | 21 | 21/21 (100%) | 0/21 (0%) | ó AWAITING VENDOR |
| **Integration Requirements (INT)** | 5 | 5/5 (100%) | 0/5 (0%) | ó AWAITING VENDOR |
| **TOTAL** | **44** | **44/44 (100%)** | **0/44 (0%)** | ó AWAITING VENDOR |

**Acceptance Criteria**: No partial coverage accepted. All requirement types must achieve 100% coverage by M5 (Production Launch).

---

## 8. REVIEW AND APPROVAL

### 8.1 Review Checklist (For Vendor Submission at Each Milestone)

**M1 (Design Approval, Week 8) Checklist**:
- [ ] All 44 business requirements (BR) traced to HLD components
- [ ] All 44 functional requirements (FR) traced to HLD components
- [ ] All 44 non-functional requirements (NFR) traced to HLD architecture patterns
- [ ] All 44 integration requirements (INT) traced to HLD integration architecture
- [ ] All 44 requirements traced to DLD modules, APIs, database schemas
- [ ] All HLD components traced back to requirements (no orphans or justified)
- [ ] All DLD modules traced back to requirements (no orphans or justified)
- [ ] Backward traceability matrix populated (HLD/DLD artifacts ’ requirements)
- [ ] Zero design gaps (or all gaps justified and approved by HMRC)

**M2 (Development Milestone, Week 20) Checklist**:
- [ ] 50% implementation coverage (22/44 requirements implemented)
- [ ] Source code file references provided for all implemented requirements
- [ ] Backward traceability: All implemented code modules trace to requirements
- [ ] Implementation evidence provided (GitHub commit SHAs, file paths)

**M3 (Testing Complete, Week 40) Checklist**:
- [ ] 100% test coverage (all 44 requirements tested)
- [ ] Test case IDs provided for all 44 requirements
- [ ] Test execution results provided (pass/fail, evidence)
- [ ] 100% implementation coverage (all 44 requirements implemented)
- [ ] Zero test gaps
- [ ] Backward traceability: All test cases trace to requirements

**M5 (Production Launch, Week 52) Checklist**:
- [ ] 100% overall coverage (all 44 requirements designed, implemented, tested)
- [ ] All acceptance evidence provided (deliverables from SOW Section 4)
- [ ] HMRC Architecture Review Board approval obtained
- [ ] GDS Service Standard Live Assessment PASS obtained
- [ ] Zero critical gaps
- [ ] Traceability matrix published as part of project handover documentation

### 8.2 Approval Signatures

**M1 (Design Approval, Week 8)**:

| Role | Name | Review Date | Approval | Signature | Date |
|------|------|-------------|----------|-----------|------|
| **Product Owner** | [TBD] | [Week 8] | [ ] Approve [ ] Approve with Conditions [ ] Reject | _________ | [DATE] |
| **Enterprise Architect** | [TBD] | [Week 8] | [ ] Approve [ ] Approve with Conditions [ ] Reject | _________ | [DATE] |
| **Security Architect (CISO)** | [TBD] | [Week 8] | [ ] Approve [ ] Approve with Conditions [ ] Reject | _________ | [DATE] |
| **Accessibility Specialist** | [TBD] | [Week 8] | [ ] Approve [ ] Approve with Conditions [ ] Reject | _________ | [DATE] |
| **Data Protection Officer** | [TBD] | [Week 8] | [ ] Approve [ ] Approve with Conditions [ ] Reject | _________ | [DATE] |

**M3 (Testing Complete, Week 40)**:

| Role | Name | Review Date | Approval | Signature | Date |
|------|------|-------------|----------|-----------|------|
| **Product Owner** | [TBD] | [Week 40] | [ ] Approve [ ] Approve with Conditions [ ] Reject | _________ | [DATE] |
| **QA Lead** | [TBD] | [Week 40] | [ ] Approve [ ] Approve with Conditions [ ] Reject | _________ | [DATE] |
| **Enterprise Architect** | [TBD] | [Week 40] | [ ] Approve [ ] Approve with Conditions [ ] Reject | _________ | [DATE] |
| **Accessibility Specialist** | [TBD] | [Week 40] | [ ] Approve [ ] Approve with Conditions [ ] Reject | _________ | [DATE] |

**M5 (Production Launch, Week 52)**:

| Role | Name | Review Date | Approval | Signature | Date |
|------|------|-------------|----------|-----------|------|
| **Product Owner** | [TBD] | [Week 52] | [ ] Approve [ ] Reject | _________ | [DATE] |
| **Enterprise Architect** | [TBD] | [Week 52] | [ ] Approve [ ] Reject | _________ | [DATE] |
| **HMRC SRO** | [TBD] | [Week 52] | [ ] Approve [ ] Reject | _________ | [DATE] |
| **HMRC CTO** | [TBD] | [Week 52] | [ ] Approve [ ] Reject | _________ | [DATE] |
| **GDS Assessor** | [TBD] | [Week 52] | [ ] Approve (GDS Service Standard PASS) [ ] Reject | _________ | [DATE] |

---

## 9. APPENDICES

### Appendix A: Requirements Document

**Full requirements**: `projects/001-hmrc-chatbot/requirements.md`

**Requirements Summary**:
- 7 Business Requirements (BR-1 to BR-7): Helpline deflection, 24/7 availability, citizen satisfaction, GDS compliance, accessibility, ATRS, data protection
- 11 Functional Requirements (FR-1 to FR-11): Conversational interface, RAG, LLM, source citation, authentication, escalation, feedback, conversation management, Plain English, Welsh language, GOV.UK Design System
- 21 Non-Functional Requirements (NFR-P-1 to NFR-I-3): Performance, availability, scalability, security, compliance, usability, maintainability, interoperability
- 5 Integration Requirements (INT-1 to INT-5): Government Gateway, HMRC CMS, HMRC Backend APIs, ServiceNow, AWS Bedrock

### Appendix B: Architecture Principles

**Full principles**: `.arckit/memory/architecture-principles.md`

**Principles Summary**: 17 principles across 10 sections (Cloud-First, API-First, Security by Design, Accessibility-First, Responsible AI, Observability, Data Sovereignty, Data Quality, Approved Tech Stack, Infrastructure as Code, Microservices, RAG, Resilience, CI/CD, Testing, FinOps, Audit Logging)

### Appendix C: Statement of Work (SOW)

**Full SOW**: `projects/001-hmrc-chatbot/sow.md`

**SOW Deliverables** (Section 4): 42 deliverables across 5 phases (Design, Development, Testing, Deployment, Documentation & Knowledge Transfer)

### Appendix D: Traceability Tools

**Version Control**: Traceability matrix maintained in Git repository alongside HLD, DLD, source code, test documentation.

**Format**: Markdown (.md) for human readability and version control friendly format.

**Automation** (optional): Vendor may use traceability tools (Jira, Azure DevOps, Polarion, DOORS) to automate traceability matrix generation, but must export to Markdown format for HMRC review and approval.

---

## DOCUMENT CONTROL

| Version | Date | Author | Changes | Milestone |
|---------|------|--------|---------|-----------|
| **1.0** | **2025-10-14** | **HMRC Enterprise Architecture Team** | **Initial baseline: 44 requirements, 0% coverage** | **Pre-Procurement (Gate 1 Requirements Approval)** |
| 1.1 | [Week 4, 2026-03-09] | [VENDOR: Solution Architect] | [VENDOR: Mapped all 44 requirements to HLD components] | HLD Submission |
| 1.2 | [Week 8, 2026-04-06] | [VENDOR: Technical Lead] | [VENDOR: Mapped all 44 requirements to DLD modules] | M1 Design Approval |
| 1.3 | [Week 20, 2026-06-08] | [VENDOR: Technical Lead] | [VENDOR: Added source code references (50% implementation)] | M2 Development Milestone |
| 1.4 | [Week 40, 2026-09-14] | [VENDOR: QA Lead] | [VENDOR: Added test cases and execution results (100% coverage)] | M3 Testing Complete |
| 2.0 | [Week 52, 2026-11-23] | [VENDOR: Project Manager] | Final traceability matrix approved by HMRC Architecture Review Board | M5 Production Launch |

---

**END OF REQUIREMENTS TRACEABILITY MATRIX (BASELINE v1.0)**

---

**NEXT STEPS FOR VENDOR** (After Selection):

1. **Week 1 (Kickoff, 2026-02-09)**: Review baseline traceability matrix, understand traceability obligations
2. **Week 4 (HLD Submission, 2026-03-09)**: Update traceability matrix with HLD component mapping (version 1.1)
3. **Week 8 (DLD Submission / M1, 2026-04-06)**: Update traceability matrix with DLD module mapping (version 1.2), submit for Architecture Review Board approval
4. **Week 20 (M2, 2026-06-08)**: Update traceability matrix with implementation progress (50% coverage, version 1.3)
5. **Week 40 (M3, 2026-09-14)**: Update traceability matrix with test cases and execution results (100% coverage, version 1.4), submit for final review
6. **Week 52 (M5, 2026-11-23)**: Final traceability matrix (version 2.0) approved by Architecture Review Board, published as part of project handover

**CRITICAL**: Traceability matrix completion is a **contract obligation**. Final payment (20% at M5) contingent on achieving **100% requirements coverage** (all 44 requirements designed, implemented, AND tested with evidence).
