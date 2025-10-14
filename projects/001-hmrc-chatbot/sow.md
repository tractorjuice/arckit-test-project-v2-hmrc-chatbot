# Statement of Work (SOW): HMRC Tax Guidance ChatBot

**Document Type**: Procurement - Statement of Work / Request for Proposal (RFP)
**RFP ID**: HMRC-CHATBOT-2025-001
**Project ID**: 001-hmrc-chatbot
**Issue Date**: 2025-10-14
**Proposal Due Date**: 2025-12-09 (8 weeks from issue)
**Version**: 1.0
**Issuing Organization**: HM Revenue & Customs (HMRC) Digital Services
**Procurement Framework**: G-Cloud 14
**Point of Contact**: procurement-chatbot@hmrc.gov.uk

---

## 1. Executive Summary

### 1.1 Purpose of This SOW

This Statement of Work (SOW) defines the requirements, deliverables, and evaluation criteria for the design, development, and deployment of the **HMRC Tax Guidance ChatBot**an AI-powered conversational interface providing 24/7 tax guidance to UK citizens. HMRC is seeking qualified vendors via the G-Cloud 14 framework to deliver a production-ready ChatBot system that meets UK Government technology standards, security requirements, and accessibility mandates.

### 1.2 Background

**Current State and Business Drivers**:

HMRC receives over **50 million calls per year** to its helplines, with the average call costing **£5-£10** to handle. Many of these calls are for simple tax guidance queries that could be resolved through self-service channels. Citizens face long wait times during peak periods (January Self Assessment deadline season), and HMRC struggles with staffing costs and service quality variability.

The digital-first strategy mandated by the UK Government Technology Code of Practice requires modern, accessible, user-centric public services. Citizens increasingly expect instant, 24/7 access to government services via digital channels. Traditional phone helplines cannot scale cost-effectively to meet this demand.

**Strategic Importance**:

This initiative aligns with:
- **UK Government Digital-First Strategy**: Technology Code of Practice, GDS Service Standard
- **AI and Data Strategy**: UK Government AI Playbook, Data Ethics Framework, Algorithmic Transparency Recording Standard (ATRS)
- **Accessibility Mandate**: Public Sector Bodies Accessibility Regulations 2018 (WCAG 2.2 AA)
- **Welsh Language Requirement**: Welsh Language Act 1993
- **Value for Money**: HM Treasury Green Book principles (£75M annual savings target by Year 3)

### 1.3 Project Overview

**Objective**:

Deliver an AI-powered ChatBot system that provides accurate, explainable tax guidance to UK citizens 24/7, grounded in authoritative HMRC guidance and UK tax legislation using Retrieval-Augmented Generation (RAG) architecture.

**Scope**:

- AI-powered conversational interface for tax guidance (Self Assessment, PAYE, VAT, National Insurance, Capital Gains, Inheritance Tax)
- Web-based chat interface integrated with GOV.UK
- Government Gateway authentication for personalized guidance
- Integration with HMRC backend systems for real-time tax record retrieval
- RAG architecture using HMRC knowledge base (100,000+ documents) and UK tax legislation
- Welsh language support (legal requirement under Welsh Language Act 1993)
- WCAG 2.2 Level AA accessibility compliance (legal requirement)
- Audit logging and ATRS transparency reporting
- Private beta (100 citizens) and public beta (10,000 citizens) before full launch

**Expected Outcomes**:

- **Cost Savings**: £75M annual savings from reduced helpline volume by Year 3 (30% deflection of 50M calls)
- **Citizen Satisfaction**: >70% Net Promoter Score (NPS) within 6 months of launch
- **Service Availability**: 99.9% uptime during business hours (08:00-20:00 GMT Monday-Friday)
- **AI Accuracy**: >95% of ChatBot responses marked as helpful by citizens
- **Accessibility Compliance**: 100% WCAG 2.2 AA compliance, zero critical/high accessibility issues

**Budget Range**:

- **Capital Expenditure (Capex)**: £4.5M - £5.5M (design, development, deployment over 12 months)
- **Operational Expenditure (Opex)**: £4.0M - £5.0M per annum (AWS infrastructure, LLM API costs, support and maintenance)
- **3-Year Total Cost of Ownership (TCO)**: £16.5M - £20.5M
- **3-Year Net Savings**: £136M - £139M (£75M annual savings × 3 years - TCO)

**Timeline**:

12-month implementation timeline from contract signing to production launch:
- Months 1-2: Design phase (HLD, DLD, security design)
- Months 3-8: Development and integration
- Months 9-10: Testing (performance, security, accessibility)
- Month 11: Private beta (100 citizens)
- Month 12: Public beta (10,000 citizens) ’ Production launch

---

## 2. Scope of Work

### 2.1 In Scope

The selected vendor will be responsible for:

#### **Phase 1: Design and Architecture (Months 1-2)**

1. **High-Level Design (HLD)**
   - Solution architecture with C4 model diagrams (Context, Container, Component, Code)
   - Technology stack selection aligned with HMRC Architecture Principles
   - Integration architecture for Government Gateway, HMRC backend APIs, AWS Bedrock
   - RAG architecture design (embedding model, vector database, LLM orchestration)
   - Security architecture aligned with NCSC Cloud Security Principles and Zero Trust
   - Disaster recovery and business continuity strategy (RPO <1 hour, RTO <15 minutes)
   - WCAG 2.2 AA accessibility strategy and design
   - Welsh language support architecture

2. **Detailed Design (DLD)**
   - Component specifications for all microservices (Citizen Identity, Conversational AI, Knowledge Management, HMRC Integration, Audit & Compliance)
   - API contracts (OpenAPI 3.0+ specifications)
   - Data models and database schemas (PostgreSQL, OpenSearch vector store)
   - Security controls mapping to NCSC Cloud Security Principles (all 14 principles)
   - AI model selection and justification (LLM, embedding model)
   - Prompt engineering strategy for accurate tax guidance
   - Guardrails design for AI safety (hallucination detection, bias mitigation, prompt injection defense)

3. **Security and Compliance Design**
   - Threat model using NCSC methodology
   - Data Protection Impact Assessment (DPIA) aligned with UK GDPR
   - Equality Impact Assessment (EqIA) for protected characteristics
   - Algorithmic Transparency Recording Standard (ATRS) record (Tier 1 + Tier 2)
   - Penetration testing plan with CHECK-approved supplier
   - Cyber Essentials Plus certification plan

#### **Phase 2: Development and Integration (Months 3-8)**

4. **Core ChatBot Application Development**
   - Conversational AI service with natural language understanding (NLU)
   - RAG pipeline implementation (query ’ embedding ’ vector search ’ LLM generation ’ validation)
   - Knowledge base ingestion pipeline from HMRC content management system
   - Source citation and explainability (100% of AI responses must cite source documents)
   - Confidence scoring and human escalation logic (<70% confidence ’ human agent)
   - Multi-turn dialogue management for complex tax scenarios
   - Welsh language processing and response generation

5. **Integration Development**
   - Government Gateway OAuth 2.0 authentication integration
   - HMRC backend API integration (tax records, National Insurance, PAYE)
   - HMRC ServiceNow integration for human escalation ticketing
   - AWS Bedrock integration for Claude 3.5 Sonnet LLM
   - HMRC content management system integration for knowledge base updates

6. **Frontend Development**
   - Web-based chat interface using GOV.UK Design System components
   - Responsive design for desktop, tablet, mobile (no native apps in scope)
   - WCAG 2.2 AA compliant UI (screen reader support, keyboard navigation, high contrast mode)
   - Welsh language UI (toggle between English and Welsh)
   - Citizen feedback mechanism (thumbs up/down, "Was this helpful?")

7. **Infrastructure as Code (IaC)**
   - Terraform modules for all AWS resources (VPC, ECS Fargate, RDS PostgreSQL, OpenSearch, S3, CloudFront, API Gateway, Lambda)
   - CI/CD pipeline configuration (GitHub Actions or AWS CodePipeline)
   - Automated deployment with blue/green or canary release strategy
   - Multi-environment setup (dev, staging, production) in AWS UK regions (eu-west-2 London)

8. **Observability and Monitoring**
   - Structured logging (JSON format) to HMRC Splunk instance
   - Prometheus-compatible metrics exposition (RED metrics: Rate, Errors, Duration)
   - OpenTelemetry distributed tracing
   - SLO-based alerting with actionable runbooks
   - Dashboards for operational metrics and business KPIs
   - Integration with HMRC Security Operations Centre (SOC) for security events

#### **Phase 3: Testing and Quality Assurance (Months 9-10)**

9. **Comprehensive Testing**
   - Unit testing (e80% code coverage, 100% coverage for critical paths)
   - Integration testing (component interactions, HMRC API integration)
   - Contract testing for HMRC backend APIs (Pact or similar)
   - End-to-end testing for critical user journeys (Playwright or Cypress)
   - AI accuracy testing (1000+ ground truth queries, >95% accuracy required)
   - Bias and fairness testing across protected characteristics (age, gender, ethnicity, disability, geography)
   - Adversarial testing (prompt injection, jailbreak attempts, toxic input handling)
   - Performance testing (load testing for 10,000 concurrent users, latency <2s p95)
   - Security testing (SAST, DAST, dependency vulnerability scans, penetration testing by CHECK-approved supplier)
   - Accessibility testing (automated via axe-core/Pa11y, manual with assistive technologies)

#### **Phase 4: Deployment and Launch (Months 11-12)**

10. **Beta Deployments**
    - Private beta deployment (100 citizens, diverse demographics)
    - User acceptance testing (UAT) with citizen feedback
    - Public beta deployment (10,000 citizens)
    - Performance monitoring and optimization
    - Bug fixes and iterative improvements based on beta feedback

11. **Production Deployment**
    - Production launch with canary deployment strategy (10% ’ 50% ’ 100% traffic)
    - Hypercare support for first 30 days (24/7 on-call team)
    - Monitoring and incident response
    - Post-launch optimization based on operational metrics

#### **Phase 5: Documentation and Knowledge Transfer (Ongoing, Final Deliverables Month 12)**

12. **Documentation Deliverables**
    - Technical documentation (architecture, design decisions, component docs)
    - API documentation (OpenAPI 3.0+ specifications, Swagger UI)
    - Operations manual (system administration, maintenance procedures)
    - Runbooks for common operational tasks (deployment, rollback, scaling, incident response)
    - Disaster recovery procedures (tested with DR drill results)
    - User manual and training materials for HMRC staff

13. **Knowledge Transfer and Training**
    - Technical training for HMRC development team (architecture, codebase, deployment)
    - Operations training for HMRC SRE team (monitoring, incident response, maintenance)
    - Content designer training for knowledge base management
    - Citizen support team training for escalation handling

### 2.2 Out of Scope

The following are explicitly NOT part of this engagement:

- **Voice/Phone Interface**: Future phase; web chat interface only in this project
- **Mobile Native Apps**: Responsive web interface only; no iOS/Android apps
- **Transactional Capabilities**: Tax filing, payment processing remain in existing HMRC online services
- **Tax Calculations for Complex Scenarios**: Complex calculations require human agent review (escalation)
- **Appeals and Disputes**: Escalated to human agents; not handled by ChatBot
- **Fraud Detection and Investigation**: Separate HMRC systems; not integrated in this phase
- **HMRC Backend System Modernization**: Existing HMRC APIs used as-is; modernization is separate initiative
- **Content Creation**: HMRC content team responsible for creating/updating tax guidance content; vendor ingests existing content
- **24/7 Human Agent Support**: HMRC responsible for human agent staffing; vendor provides escalation integration only

### 2.3 Client Responsibilities

HMRC will provide:

1. **Access and Infrastructure**:
   - AWS account access (eu-west-2 London region) with appropriate IAM roles
   - Access to HMRC development, staging, and production environments
   - Government Gateway API credentials and documentation
   - HMRC backend API credentials and sandbox environments
   - HMRC content management system API access for knowledge base ingestion

2. **Subject Matter Expertise**:
   - Tax policy experts for knowledge base validation and accuracy testing
   - Content designers for Plain English content review
   - Accessibility specialists for WCAG 2.2 AA compliance review
   - Security architects for threat modeling and security review
   - Data Protection Officer (DPO) for DPIA approval

3. **Governance and Approvals**:
   - Architecture Review Board approvals at design gates
   - DPIA approval by HMRC Data Protection Officer
   - Equality Impact Assessment (EqIA) approval by HMRC Equality Lead
   - Security risk assessment approval by HMRC CISO
   - GDS Service Standard assessment coordination

4. **Testing Resources**:
   - Beta testing participants (100 private beta, 10,000 public beta citizens)
   - UAT participants from HMRC staff and citizen representatives
   - Ground truth dataset for AI accuracy testing (1000+ tax queries with verified answers)

5. **Operational Support**:
   - HMRC Splunk instance for centralized logging
   - HMRC ServiceNow for incident ticketing
   - HMRC Security Operations Centre (SOC) integration
   - On-call escalation contacts for production incidents

---

## 3. Requirements

### 3.1 Requirements Summary

This project encompasses **7 Business Requirements (BR)**, **11 Functional Requirements (FR)**, **21 Non-Functional Requirements (NFR)** across 8 categories, **5 Integration Requirements (INT)**, and **5 Data Entity Definitions**. Full requirements are documented in `requirements.md` (Appendix A). Key requirements are summarized below.

### 3.2 Business Requirements (MUST)

**BR-1: Helpline Call Deflection (MUST)**
- **Target**: Deflect 30% of helpline calls (15 million/year) to ChatBot self-service by Year 3
- **Phased Goals**: Year 1: 10% deflection, Year 2: 20% deflection, Year 3: 30% deflection
- **Measurement**: Call volume reduction tracked monthly via HMRC call center analytics
- **Validation**: BI dashboard with call deflection KPIs
- **Aligns with Principle**: #16 FinOps and Value for Money

**BR-2: 24/7 Availability (MUST)**
- **Target**: ChatBot available 24/7/365 with 99.9% uptime during business hours (08:00-20:00 GMT Mon-Fri)
- **Response Time**: <2 seconds for 95th percentile (p95) of chat messages
- **Measurement**: Uptime tracked via AWS CloudWatch with SLO alerting
- **Validation**: Monthly uptime reports, incident post-mortems for violations
- **Aligns with Principle**: #13 Resilience and Fault Tolerance

**BR-3: Citizen Satisfaction (MUST)**
- **Target**: Achieve >70% Net Promoter Score (NPS) within 6 months of launch
- **Accuracy**: >95% of responses marked helpful by citizens (thumbs up/down feedback)
- **Measurement**: In-app surveys, feedback collection, sentiment analysis
- **Validation**: Monthly citizen satisfaction reports
- **Aligns with Principle**: #8 Data Quality and Accuracy

**BR-4: GDS Service Standard Compliance (MUST)**
- **Target**: Pass GDS Service Standard Live Assessment (18 criteria) before public launch
- **Assessment**: Independent GDS assessors evaluate service at Beta and Live stages
- **Validation**: GDS assessment report with PASS status
- **Aligns with Principle**: Section XI (GOV.UK Service Standard Alignment)

**BR-5: Accessibility Compliance (MUST - Legal Requirement)**
- **Target**: 100% WCAG 2.2 Level AA compliance
- **Legal Basis**: Public Sector Bodies Accessibility Regulations 2018, Equality Act 2010
- **Measurement**: Automated testing (axe-core, Pa11y) + manual testing with assistive technologies
- **Validation**: Third-party accessibility audit with zero critical/high issues
- **Aligns with Principle**: #4 Accessibility-First Design

**BR-6: Algorithmic Transparency (MUST - Legal Requirement)**
- **Target**: Publish ATRS record on GOV.UK before Private Beta launch
- **Content**: Owner, AI model details, data sources, bias testing, explainability, governance
- **Updates**: ATRS updated at each milestone (Private Beta, Public Beta, Production, annually)
- **Validation**: ATRS reviewed by HMRC Data Ethics Committee and published publicly
- **Aligns with Principle**: #5 Responsible AI and Algorithmic Transparency

**BR-7: Data Protection Compliance (MUST - Legal Requirement)**
- **Target**: 100% UK GDPR and Data Protection Act 2018 compliance
- **Requirements**: DPIA approved by DPO, UK data residency, citizen consent, data subject rights
- **Retention**: Chat transcripts 7 years (tax records retention requirement), audit logs 7 years
- **Validation**: DPIA approval, privacy notice published, data subject rights procedures tested
- **Aligns with Principle**: #7 Data Sovereignty and UK GDPR Compliance

### 3.3 Functional Requirements (MUST)

**FR-1: Conversational Interface (MUST)**
- Natural language understanding for UK English and Welsh
- Multi-turn dialogue management for complex tax scenarios
- Contextual understanding of citizen queries
- Support for common tax topics: Self Assessment, PAYE, VAT, National Insurance, Capital Gains, Inheritance Tax
- **Aligns with Principle**: #4 Accessibility-First Design

**FR-2: Retrieval-Augmented Generation (RAG) with HMRC Knowledge Base (MUST)**
- Semantic search over 100,000+ HMRC guidance documents
- Embedding model for query and document vectorization (AWS Titan Embeddings or OpenAI text-embedding-3)
- Vector database for fast retrieval (Amazon OpenSearch with k-NN plugin)
- Top-k document retrieval (k=3-5) for context augmentation
- 100% source citation linking AI responses to authoritative HMRC documents
- **Aligns with Principle**: #12 Retrieval-Augmented Generation (RAG) for AI Accuracy

**FR-3: Large Language Model (LLM) Response Generation (MUST)**
- LLM: AWS Bedrock Claude 3.5 Sonnet (or equivalent UK-hosted LLM approved by HMRC)
- Prompt engineering for accurate, Plain English tax guidance
- Guardrails for AI safety (hallucination detection, bias mitigation, toxic content filtering)
- Confidence scoring for AI responses (0-100%)
- Human escalation for low-confidence responses (<70% confidence threshold)
- **Aligns with Principle**: #5 Responsible AI and Algorithmic Transparency

**FR-4: Source Citation and Explainability (MUST)**
- Every AI response MUST cite source documents (HMRC guidance, legislation section)
- Clickable links to full source documents on GOV.UK
- "Why did the ChatBot say this?" explainability feature
- Lineage tracking from legislation ’ policy ’ guidance ’ AI response
- **Aligns with Principle**: #8 Data Quality and Accuracy

**FR-5: Government Gateway Authentication (MUST)**
- OAuth 2.0 integration with Government Gateway for authenticated citizen access
- Support for personalized guidance using citizen tax records (with consent)
- Guest mode for unauthenticated general tax queries
- Multi-factor authentication (MFA) support
- **Aligns with Principle**: #2 API-First Integration with Government Gateway

**FR-6: Human Escalation (MUST)**
- Escalate complex queries to human agents via HMRC ServiceNow integration
- Escalation triggers: Low confidence (<70%), complex tax scenarios, appeals/disputes
- Provide chat transcript to human agent for context
- Target escalation rate: <10% of conversations
- **Aligns with Principle**: #5 Responsible AI (Human-in-the-Loop)

**FR-7: Citizen Feedback Collection (MUST)**
- Thumbs up/down feedback for each AI response
- "Was this helpful?" rating (Yes/No)
- Optional free-text feedback
- Periodic in-app surveys for NPS and satisfaction metrics
- **Aligns with Principle**: #8 Data Quality and Accuracy

**FR-8: Conversation Management (MUST)**
- Save and resume conversations for authenticated citizens
- Conversation history (last 30 days) accessible via GOV.UK account
- Export conversation transcript (PDF) for citizen records
- Delete conversation option (subject to 7-year retention requirement if tax advice provided)
- **Aligns with Principle**: #7 Data Sovereignty and UK GDPR Compliance

**FR-9: Plain English Content (MUST)**
- All AI responses in Plain English (average reading age 9, GOV.UK style guide)
- No jargon or overly technical language unless necessary
- Content design review for clarity and accessibility
- **Aligns with Principle**: #4 Accessibility-First Design

**FR-10: Welsh Language Support (MUST - Legal Requirement)**
- UI available in Welsh and English (toggle button)
- AI responses in Welsh for Welsh-language queries
- Knowledge base ingestion for Welsh-language HMRC guidance
- Welsh Language Act 1993 compliance
- **Aligns with Principle**: #4 Accessibility-First Design

**FR-11: GOV.UK Design System Integration (MUST)**
- Use GOV.UK Design System components for consistent UX with GOV.UK
- GOV.UK Frontend library for accessible, responsive components
- Consistent styling, typography, and interaction patterns
- **Aligns with Principle**: #9 Approved Technology Stack

### 3.4 Non-Functional Requirements

#### 3.4.1 Performance (MUST)

**NFR-P-1: Response Time (MUST)**
- **Target**: <2 seconds response time for 95th percentile (p95) of chat messages
- **Measurement**: API Gateway latency metrics, CloudWatch dashboards
- **Validation**: Load testing with 10,000 concurrent users, p95 latency <2s
- **Aligns with Principle**: #6 Observability and Operational Excellence

**NFR-P-2: Throughput (MUST)**
- **Target**: Support 500 concurrent requests per second during peak periods
- **Peak Period**: January (Self Assessment deadline season), July (Tax Credit renewals)
- **Measurement**: API Gateway request count, ECS Fargate CPU/memory utilization
- **Validation**: Load testing with 10,000 concurrent users, 500 req/s sustained
- **Aligns with Principle**: #13 Resilience and Fault Tolerance

#### 3.4.2 Availability (MUST)

**NFR-A-1: Uptime (MUST)**
- **Target**: 99.9% uptime during business hours (08:00-20:00 GMT Mon-Fri)
- **Calculation**: (Total Business Hours - Downtime) / Total Business Hours × 100%
- **Allowed Downtime**: 8.64 minutes/day, ~4.3 hours/month (business hours only)
- **Measurement**: AWS CloudWatch uptime monitoring with SLO alerting
- **Aligns with Principle**: #13 Resilience and Fault Tolerance

**NFR-A-2: Disaster Recovery (MUST)**
- **RPO (Recovery Point Objective)**: <1 hour (max acceptable data loss)
- **RTO (Recovery Time Objective)**: <15 minutes (max acceptable downtime)
- **Backup**: Daily automated backups of PostgreSQL and OpenSearch, encrypted, stored in secondary UK region
- **Multi-AZ Deployment**: All services deployed across multiple AWS Availability Zones in eu-west-2
- **DR Testing**: Quarterly disaster recovery drills with documented results
- **Aligns with Principle**: #13 Resilience and Fault Tolerance

**NFR-A-3: Fault Tolerance (MUST)**
- **Circuit Breaker**: Prevent cascade failures when HMRC backend APIs fail
- **Retry Logic**: Exponential backoff with 3 retries max for transient failures
- **Graceful Degradation**: Fallback to cached guidance if HMRC APIs unavailable
- **Rate Limiting**: 500 requests/hour per citizen, 10,000 requests/hour system-wide
- **Aligns with Principle**: #13 Resilience and Fault Tolerance

#### 3.4.3 Scalability (MUST)

**NFR-S-1: Horizontal Scaling (MUST)**
- **Auto-Scaling**: ECS Fargate tasks auto-scale based on CPU (70% threshold) and request count
- **Database**: RDS PostgreSQL with read replicas for scaling read traffic
- **Elasticity**: Scale up during peak periods (January, July), scale down during off-peak
- **Aligns with Principle**: #1 Government Cloud-First Architecture

**NFR-S-2: Data Volume Growth (MUST)**
- **Conversations**: Support 10 million conversations/year by Year 3
- **Knowledge Base**: Scale to 200,000+ documents (2× growth over 3 years)
- **Storage**: S3 for cost-effective storage growth (chat transcripts, audit logs)
- **Aligns with Principle**: #1 Government Cloud-First Architecture

#### 3.4.4 Security (MUST - NON-NEGOTIABLE)

**NFR-SEC-1: Authentication and Authorization (MUST)**
- **Citizen Authentication**: Government Gateway OAuth 2.0, MFA support
- **Staff Authentication**: HMRC Active Directory integration, MFA mandatory
- **Service-to-Service Authentication**: AWS IAM roles, mutual TLS
- **Authorization**: Attribute-Based Access Control (ABAC) with citizen consent
- **Aligns with Principle**: #3 Security by Design - Zero Trust

**NFR-SEC-2: Encryption (MUST)**
- **In Transit**: TLS 1.3 for all network communication (TLS 1.2 minimum)
- **At Rest**: AES-256 GCM encryption for all data stores (RDS, S3, OpenSearch)
- **Key Management**: AWS Key Management Service (KMS) with Customer Managed Keys (CMK)
- **Aligns with Principle**: #3 Security by Design - Zero Trust

**NFR-SEC-3: Secrets Management (MUST)**
- **No Hardcoded Secrets**: All credentials via AWS Secrets Manager
- **Rotation**: Automated secret rotation (30 days for database credentials)
- **Access Control**: Least privilege IAM policies for secret access
- **Aligns with Principle**: #3 Security by Design - Zero Trust

**NFR-SEC-4: Vulnerability Management (MUST)**
- **Scanning**: Weekly automated vulnerability scans (AWS Inspector, Snyk)
- **Remediation SLA**: Critical vulnerabilities patched within 7 days, high within 30 days
- **Penetration Testing**: Annual penetration test by CHECK-approved supplier
- **Aligns with Principle**: #3 Security by Design - Zero Trust

**NFR-SEC-5: Compliance (MUST)**
- **Cyber Essentials Plus**: Mandatory for HMG systems
- **NCSC Cloud Security Principles**: All 14 principles addressed
- **ISO 27001**: HMRC corporate requirement
- **Aligns with Principle**: #3 Security by Design - Zero Trust

**NFR-SEC-6: AI Safety and Security (MUST)**
- **Prompt Injection Defense**: Input sanitization, output validation
- **Adversarial Testing**: Jailbreak attempts, toxic input handling
- **Rate Limiting**: Prevent API abuse (500 requests/hour per citizen)
- **Content Filtering**: Block responses for tax avoidance schemes, illegal advice
- **Aligns with Principle**: #5 Responsible AI and Algorithmic Transparency

#### 3.4.5 Compliance (MUST - Legal Requirements)

**NFR-C-1: UK GDPR Compliance (MUST)**
- **Lawful Basis**: Public task (HMRC's legal obligation to collect taxes and provide guidance)
- **Data Minimization**: Collect only data necessary for tax guidance
- **Citizen Rights**: Access, rectification, erasure, portability, objection
- **Privacy Notice**: Published on GOV.UK before chat session
- **Aligns with Principle**: #7 Data Sovereignty and UK GDPR Compliance

**NFR-C-2: Audit Logging (MUST)**
- **W5H1 Format**: Who, What, When, Where, Why, Result
- **Events**: Authentication, chat conversations, HMRC API calls, PII access, admin actions, security events
- **Retention**: 7 years for audit logs (HMG standard)
- **Immutability**: S3 Object Lock with Governance mode, CloudTrail log file validation
- **Aligns with Principle**: #17 Audit Logging and Traceability

**NFR-C-3: ATRS Reporting (MUST)**
- **Publication**: ATRS record published on GOV.UK before Private Beta
- **Updates**: ATRS updated at Private Beta, Public Beta, Production, and annually
- **Content**: Owner, AI model, data sources, bias testing, explainability, governance
- **Aligns with Principle**: #5 Responsible AI and Algorithmic Transparency

#### 3.4.6 Usability (MUST)

**NFR-U-1: GOV.UK UX Standards (MUST)**
- **Design System**: GOV.UK Design System components (gov.uk-frontend)
- **Plain English**: Content aligned with GOV.UK style guide (reading age 9)
- **User Research**: Beta testing with 100+ citizens, diverse demographics
- **Aligns with Principle**: #4 Accessibility-First Design

**NFR-U-2: Accessibility (MUST - Legal Requirement)**
- **WCAG 2.2 Level AA**: 100% compliance (legal requirement)
- **Screen Readers**: JAWS, NVDA, VoiceOver compatibility
- **Keyboard Navigation**: No mouse required for all functionality
- **High Contrast Mode**: Support for visual impairments
- **Timeout Warnings**: Extensions for complex interactions
- **Aligns with Principle**: #4 Accessibility-First Design

**NFR-U-3: Welsh Language (MUST - Legal Requirement)**
- **UI**: Fully bilingual (English/Welsh toggle)
- **AI Responses**: Welsh-language responses for Welsh queries
- **Content**: Welsh translations for all HMRC guidance in knowledge base
- **Aligns with Principle**: #4 Accessibility-First Design

#### 3.4.7 Maintainability (MUST)

**NFR-M-1: Observability (MUST)**
- **Logging**: Structured JSON logs to HMRC Splunk
- **Metrics**: Prometheus-compatible, RED metrics (Rate, Errors, Duration)
- **Tracing**: OpenTelemetry distributed tracing
- **Dashboards**: Operational and business KPIs
- **Aligns with Principle**: #6 Observability and Operational Excellence

**NFR-M-2: Documentation (MUST)**
- **Architecture**: HLD, DLD, C4 diagrams
- **API**: OpenAPI 3.0+ specifications, Swagger UI
- **Operations**: Runbooks for deployment, rollback, scaling, incident response
- **User**: Training materials for HMRC staff
- **Aligns with Principle**: Section V (Development Practices)

**NFR-M-3: Knowledge Transfer (MUST)**
- **Technical Training**: HMRC dev team (architecture, codebase, deployment)
- **Operations Training**: HMRC SRE team (monitoring, incident response)
- **Content Training**: Knowledge base management for content designers
- **Aligns with Principle**: Section V (Development Practices)

#### 3.4.8 Interoperability (MUST)

**NFR-I-1: API Standards (MUST)**
- **OpenAPI 3.0+**: All APIs documented with OpenAPI specs
- **REST**: JSON payloads, HTTPS only, semantic HTTP status codes
- **Versioning**: URI versioning (e.g., /v1/chat) with 12-month deprecation notice
- **Aligns with Principle**: #2 API-First Integration

**NFR-I-2: Integration Capabilities (MUST)**
- **Government Gateway**: OAuth 2.0 authentication
- **HMRC Backend APIs**: RESTful integration with circuit breakers
- **HMRC ServiceNow**: Ticket creation for human escalation
- **AWS Bedrock**: LLM API integration (Claude 3.5 Sonnet)
- **Aligns with Principle**: #2 API-First Integration

**NFR-I-3: Data Portability (MUST)**
- **Export**: Citizens can export conversation transcripts (PDF)
- **Backup**: Daily database backups in standard formats (PostgreSQL dump)
- **Vendor Lock-In**: Minimize by using open standards and portable data formats
- **Aligns with Principle**: #7 Data Sovereignty and UK GDPR Compliance

### 3.5 Integration Requirements

**INT-1: Government Gateway OAuth 2.0 (MUST)**
- OAuth 2.0 Authorization Code flow for citizen authentication
- MFA support
- Scopes: `openid`, `profile`, `email`, `tax_records` (with citizen consent)
- **Aligns with Principle**: #2 API-First Integration

**INT-2: HMRC Content Management System (MUST)**
- RESTful API integration for knowledge base ingestion
- Automated pipeline for content updates (every 48 hours)
- Versioning and audit trail for content changes
- **Aligns with Principle**: #8 Data Quality and Accuracy

**INT-3: HMRC Backend APIs (MUST)**
- Tax Records API (Self Assessment, PAYE)
- National Insurance API (NI number verification, contributions)
- Circuit breaker pattern for fault tolerance
- **Aligns with Principle**: #2 API-First Integration

**INT-4: HMRC ServiceNow (MUST)**
- Create incident tickets for human escalation
- Provide chat transcript context to human agents
- Bi-directional status updates (ticket opened, resolved)
- **Aligns with Principle**: #2 API-First Integration

**INT-5: AWS Bedrock (MUST)**
- Claude 3.5 Sonnet LLM via AWS Bedrock API
- UK data residency (eu-west-2 region)
- Token usage monitoring for cost optimization
- Guardrails API for content filtering
- **Aligns with Principle**: #5 Responsible AI, #9 Approved Technology Stack

### 3.6 Data Requirements

**Entity 1: Conversation** (chat sessions)
- `conversation_id` (UUID, PK)
- `user_id` (FK to User, nullable for guest mode)
- `start_time`, `end_time` (timestamp)
- `language` (enum: en, cy)
- `status` (enum: active, completed, escalated)

**Entity 2: Message** (individual queries/responses)
- `message_id` (UUID, PK)
- `conversation_id` (FK)
- `role` (enum: user, assistant, system)
- `content` (text)
- `timestamp` (timestamp)
- `sources` (JSON array of cited documents)
- `confidence_score` (float 0-100)

**Entity 3: User** (authenticated citizens)
- `user_id` (UUID, PK)
- `government_gateway_id` (string, unique)
- `email` (encrypted)
- `language_preference` (enum: en, cy)
- `created_at`, `updated_at` (timestamp)

**Entity 4: Knowledge Base Document**
- `document_id` (UUID, PK)
- `title`, `url`, `content` (text)
- `embedding` (vector)
- `source` (enum: HMRC guidance, legislation, FAQ)
- `last_updated` (timestamp)

**Entity 5: Audit Log** (W5H1 format)
- `log_id` (UUID, PK)
- `timestamp` (timestamp)
- `user_id`, `service_id` (who)
- `action` (what)
- `resource` (where)
- `context` (why)
- `result` (success/failure)

**Data Retention**:
- **Chat Transcripts**: 7 years (with citizen consent)
- **Audit Logs**: 7 years (HMG standard)
- **User Profiles**: Active + 7 years after last interaction
- **Knowledge Base**: Indefinite (current guidance only)

**Data Quality**:
- **Accuracy**: 100% for knowledge base (matched to HMRC authoritative sources)
- **Completeness**: No missing required fields
- **Timeliness**: Knowledge base updated within 48 hours of policy changes
- **Consistency**: No conflicting guidance across channels

### 3.7 Technical Constraints

**TC-1: Architecture Principles (MUST)**
- Solution MUST comply with HMRC Enterprise Architecture Principles (17 principles, see Appendix B)
- Non-negotiable principles: #3 (Security by Design), #4 (Accessibility), #5 (Responsible AI), #7 (Data Sovereignty)
- Exception process available for non-critical principles (approval required)

**TC-2: Cloud Platform (MUST)**
- AWS UK regions ONLY (eu-west-2 London primary, eu-west-1 Ireland for DR if approved)
- No cross-border data transfers (UK data sovereignty)
- Managed AWS services preferred (ECS Fargate, RDS, OpenSearch, S3, Lambda)

**TC-3: Technology Stack (SHOULD)**
- **Programming Languages**: Python 3.11+, Node.js/TypeScript 20+, Go 1.21+
- **AI/ML**: AWS Bedrock (Claude 3.5 Sonnet), LangChain/LlamaIndex, AWS Titan Embeddings
- **Databases**: PostgreSQL 15+, OpenSearch with k-NN, Redis 7+
- **Frontend**: React 18+ with TypeScript, GOV.UK Design System
- **IaC**: Terraform (HCL preferred), AWS CDK (TypeScript/Python)
- Vendors may propose alternatives with justification

**TC-4: Existing Infrastructure (MUST)**
- Integrate with HMRC Splunk for centralized logging
- Integrate with HMRC ServiceNow for incident ticketing
- Integrate with HMRC Security Operations Centre (SOC) for security events
- Use HMRC-provided AWS account with pre-configured VPC and security groups

**TC-5: Data Residency (MUST - NON-NEGOTIABLE)**
- All citizen data MUST remain in UK sovereign territory
- AWS eu-west-2 (London) region mandatory
- No data replication to non-UK regions

---

## 4. Deliverables

### 4.1 Design Phase Deliverables (Months 1-2)

| Deliverable | Description | Format | Due Date | Acceptance Criteria |
|-------------|-------------|--------|----------|---------------------|
| **High-Level Design (HLD)** | Solution architecture, C4 diagrams (Context, Container, Component), technology stack, integration patterns | PDF/Markdown + Diagrams (draw.io, Mermaid, or PlantUML) | Week 4 | Approved by HMRC Architecture Review Board. All 17 principles addressed. |
| **Detailed Design (DLD)** | Component specs, API contracts (OpenAPI 3.0+), data models, security controls, RAG architecture | PDF/Markdown + OpenAPI specs | Week 8 | Approved by HMRC technical reviewers. All APIs documented. |
| **Security Design** | Threat model (NCSC methodology), security controls mapping (NCSC Cloud Security Principles), penetration test plan | PDF/Markdown | Week 6 | Approved by HMRC Security Architect and CISO delegate. |
| **Data Protection Impact Assessment (DPIA)** | UK GDPR compliance assessment, data flows, risks, mitigations | PDF (HMG DPIA template) | Week 6 | Approved by HMRC Data Protection Officer. |
| **Equality Impact Assessment (EqIA)** | Impact on protected characteristics (Equality Act 2010), accessibility strategy | PDF (HMG EqIA template) | Week 6 | Approved by HMRC Equality Lead. |
| **Algorithmic Transparency Record (ATRS)** | Tier 1 (public summary) + Tier 2 (technical details), AI model, data sources, bias testing plan | Markdown (GOV.UK format) | Week 8 | Approved by HMRC Data Ethics Committee. Ready for GOV.UK publication. |
| **Test Strategy** | Unit, integration, E2E, accessibility, AI accuracy, bias, performance, security testing approach | PDF/Markdown | Week 8 | Approved by HMRC QA Lead. Coverage targets defined (e80% unit, 100% critical paths). |

### 4.2 Development Phase Deliverables (Months 3-8, Ongoing)

| Deliverable | Description | Format | Due Date | Acceptance Criteria |
|-------------|-------------|--------|----------|---------------------|
| **Source Code** | All application code (backend, frontend, AI pipeline) | Git repository (GitHub or AWS CodeCommit) | Ongoing | Code review approved (2 reviewers). Passes CI/CD quality gates. e80% unit test coverage. |
| **Infrastructure as Code (IaC)** | Terraform modules for all AWS resources | Git repository (Terraform HCL) | Ongoing | Deployable to all environments (dev, staging, prod). Passes `terraform plan`, `terraform validate`, `tfsec` security scans. |
| **Database Schemas** | DDL scripts, migration scripts (Flyway or Liquibase), seed data | SQL scripts in Git repo | Week 12 | Schema review approved. Migrations tested in staging. |
| **API Documentation** | Interactive API documentation for all endpoints | OpenAPI 3.0+ spec + Swagger UI | Ongoing | All endpoints documented. Request/response examples provided. |
| **Unit Tests** | Automated unit tests for all components | Code (pytest, Jest, Go test) | Ongoing | e80% code coverage. 100% coverage for critical paths (auth, AI generation, HMRC integration). |
| **Integration Tests** | Automated integration tests for component interactions | Code (Testcontainers, mocks for HMRC APIs) | Ongoing | Critical integration paths covered (Government Gateway, HMRC APIs, LLM). |
| **AI Accuracy Tests** | Ground truth dataset (1000+ queries) with automated accuracy evaluation | Code + dataset (JSON/CSV) | Week 20 | >95% accuracy on ground truth dataset. |

### 4.3 Testing Phase Deliverables (Months 9-10)

| Deliverable | Description | Format | Due Date | Acceptance Criteria |
|-------------|-------------|--------|----------|---------------------|
| **Performance Test Results** | Load testing results (10,000 concurrent users, 500 req/s sustained) | PDF report + k6/Locust scripts | Week 36 | p95 latency <2s. 99.9% success rate. No memory leaks. |
| **Security Test Results** | SAST, DAST, dependency scans, penetration test report (CHECK-approved supplier) | PDF report | Week 38 | Zero critical/high vulnerabilities. Penetration test PASS with no unmitigated findings. |
| **Accessibility Test Results** | Automated (axe-core, Pa11y) + manual (assistive technologies) testing results | PDF report | Week 36 | 100% WCAG 2.2 AA compliance. Zero critical/high issues. Tested with JAWS, NVDA, VoiceOver. |
| **Bias and Fairness Test Results** | Bias testing across protected characteristics (age, gender, ethnicity, disability) | PDF report | Week 36 | <5% difference in accuracy across demographic groups. No disparate impact identified. |
| **User Acceptance Testing (UAT) Report** | Private beta (100 citizens) + public beta (10,000 citizens) feedback and metrics | PDF report + BI dashboard | Week 44 | >70% NPS. >95% helpfulness rating. <10% escalation rate. |

### 4.4 Deployment Phase Deliverables (Months 11-12)

| Deliverable | Description | Format | Due Date | Acceptance Criteria |
|-------------|-------------|--------|----------|---------------------|
| **Deployed Application (Private Beta)** | Fully functional ChatBot in private beta environment | Running system (AWS eu-west-2) | Week 44 | 100 beta citizens onboarded. Monitoring dashboards live. |
| **Deployed Application (Public Beta)** | Fully functional ChatBot in public beta environment | Running system (AWS eu-west-2) | Week 48 | 10,000 beta citizens onboarded. Performance targets met. |
| **Deployed Application (Production)** | Fully functional ChatBot in production | Running system (AWS eu-west-2) | Week 52 | Passes final UAT. GDS Service Standard Live Assessment PASS. |
| **CI/CD Pipeline** | Automated build, test, security scan, deploy pipeline | AWS CodePipeline or GitHub Actions config | Week 36 | Deploys to all environments. Quality gates enforced. Rollback tested. |
| **Monitoring & Alerting** | Dashboards (operational + business KPIs), SLO-based alerts, runbooks | Grafana/CloudWatch dashboards + runbooks (Markdown) | Week 38 | All key metrics tracked (response time, error rate, NPS). Alerts trigger within 5 minutes. Runbooks tested. |
| **Disaster Recovery Plan** | DR procedures, backup/restore scripts, multi-AZ failover | PDF + scripts | Week 39 | DR drill successfully executed (RPO <1 hour, RTO <15 minutes verified). |

### 4.5 Documentation Deliverables (Ongoing, Final Deliverables Month 12)

| Deliverable | Description | Format | Due Date | Acceptance Criteria |
|-------------|-------------|--------|----------|---------------------|
| **Technical Documentation** | Architecture, design decisions, component docs, code comments | Markdown (Git repo) or Confluence | Ongoing | Kept current with code changes. Architecture Decision Records (ADRs) for major decisions. |
| **API Documentation** | Full API reference with examples, authentication guide | OpenAPI 3.0+ spec + docs site (Swagger UI or Redoc) | Ongoing | All endpoints documented. Postman collection provided. |
| **Operations Manual** | System administration, monitoring, scaling, backup/restore procedures | PDF/Markdown | Week 50 | SRE team trained. All operational tasks documented. |
| **Runbooks** | Deployment, rollback, scaling, incident response procedures | Markdown (Git repo) | Week 50 | Runbooks tested during UAT. On-call team trained. |
| **User Manual (Staff)** | Training materials for HMRC staff (content designers, support team) | PDF/Confluence + training videos | Week 48 | Staff training completed. Knowledge base management procedures documented. |
| **Disaster Recovery Runbook** | DR procedures tested and documented | Markdown | Week 50 | DR drill results included. Runbook validated by SRE team. |

### 4.6 Knowledge Transfer Deliverables (Month 12)

| Activity | Description | Participants | Timeline | Acceptance Criteria |
|----------|-------------|--------------|----------|---------------------|
| **Technical Training** | Architecture walkthrough, codebase tour, deployment procedures, troubleshooting | HMRC dev team (5-10 engineers) | Weeks 50-52 (3 sessions, 4 hours each) | Team can deploy changes, troubleshoot incidents, and extend functionality independently. |
| **Operations Training** | Monitoring, incident response, scaling, backup/restore, disaster recovery | HMRC SRE team (3-5 engineers) | Weeks 50-52 (3 sessions, 4 hours each) | Team can operate system 24/7, respond to incidents, and perform DR. |
| **Content Management Training** | Knowledge base ingestion, content updates, quality assurance | HMRC content designers (3-5 staff) | Week 48 (2 sessions, 2 hours each) | Team can update knowledge base, validate content accuracy. |
| **Support Team Training** | ChatBot features, escalation procedures, common issues | HMRC citizen support team (10-20 staff) | Week 48 (2 sessions, 2 hours each) | Team can support escalated queries, understand ChatBot capabilities. |

---

## 5. Project Timeline and Milestones

### 5.1 High-Level Timeline

**Total Duration**: 12 months from contract signing to production launch

| Phase | Duration | Key Milestones |
|-------|----------|----------------|
| **Initiation** | Weeks 1-2 | Kickoff, resource onboarding, AWS environment setup, NDA/contracts signed |
| **Design** | Weeks 3-8 | HLD complete (Week 4), DLD complete (Week 8), DPIA/EqIA/ATRS approved, Design approval gate |
| **Development Sprint 1-4** | Weeks 9-20 | Core ChatBot (Weeks 9-12), RAG pipeline (Weeks 13-16), HMRC integrations (Weeks 17-20) |
| **Development Sprint 5-8** | Weeks 21-32 | Frontend (Weeks 21-24), IaC/CI/CD (Weeks 25-28), Observability (Weeks 29-32) |
| **Testing** | Weeks 33-40 | Unit/integration tests (ongoing), Performance testing (Week 36), Security testing (Week 38), Accessibility testing (Week 36), UAT prep (Week 40) |
| **Private Beta** | Weeks 41-44 | 100 citizens, feedback collection, bug fixes |
| **Public Beta** | Weeks 45-48 | 10,000 citizens, performance monitoring, optimization |
| **Production Launch** | Weeks 49-52 | GDS Live Assessment, production deployment, hypercare (30 days), knowledge transfer |
| **Warranty** | Weeks 53-64 (Months 13-15) | 90-day warranty period, bug fixes, optimization |

### 5.2 Key Milestones

| Milestone | Target Week | Deliverables Due | Exit Criteria | Payment Milestone |
|-----------|-------------|------------------|---------------|-------------------|
| **M0: Project Kickoff** | Week 1 | Project plan, resource assignments, kickoff presentation | Kickoff meeting held, teams introduced, AWS access granted | 10% (upon contract signing) |
| **M1: Design Approval** | Week 8 | HLD, DLD, Security Design, DPIA, EqIA, ATRS, Test Strategy | Architecture Review Board approval. DPIA/EqIA approved by DPO/Equality Lead. ATRS approved by Data Ethics Committee. | 15% (upon design approval) |
| **M2: Development Milestone (50% Complete)** | Week 20 | Core ChatBot, RAG pipeline, HMRC integrations working in dev environment | Demo to stakeholders. Unit tests e80% coverage. Integration tests passing. | 20% (upon Sprint 4 completion) |
| **M3: Testing Complete** | Week 40 | All testing complete (performance, security, accessibility, bias, UAT prep) | Performance targets met. Security PASS (zero critical/high vulnerabilities). Accessibility PASS (WCAG 2.2 AA). Bias testing <5% disparity. | 20% (upon testing completion) |
| **M4: Private Beta Launch** | Week 44 | 100 citizens onboarded, feedback collected | Private beta live. >70% NPS from beta users. <10% escalation rate. | 10% (upon Private Beta launch) |
| **M5: Production Launch** | Week 52 | Production deployment, GDS Live Assessment PASS, knowledge transfer complete | Production live. GDS Service Standard PASS. ATRS published on GOV.UK. 99.9% uptime achieved. Staff training complete. | 20% (upon production go-live) |
| **M6: Warranty End** | Week 64 (Month 15) | 90-day warranty complete, final documentation, lessons learned | No outstanding critical/high bugs. System stable. Final sign-off by HMRC SRO. | 5% (upon warranty completion) |

### 5.3 Proposal and Selection Timeline

| Event | Date |
|-------|------|
| **RFP Issued** | 2025-10-14 |
| **Vendor Questions Due** | 2025-10-28 (2 weeks after RFP issue) |
| **Answers Published to All Vendors** | 2025-11-04 (3 weeks after RFP issue) |
| **Proposals Due** | 2025-12-09 (8 weeks after RFP issue, 5pm GMT) |
| **Technical Evaluation (Cost Sealed)** | 2025-12-09 to 2025-12-23 (2 weeks) |
| **Vendor Shortlisting** | 2025-12-23 (top 3-5 vendors) |
| **Vendor Presentations** | 2026-01-06 to 2026-01-10 (1 week, 2-hour sessions per vendor) |
| **Cost Evaluation (Shortlisted Vendors Only)** | 2026-01-13 to 2026-01-17 (1 week) |
| **Final Vendor Selection** | 2026-01-20 (decision announced) |
| **All Vendors Notified** | 2026-01-22 |
| **Contract Negotiation** | 2026-01-23 to 2026-02-06 (2 weeks) |
| **Contract Signing / Project Start** | 2026-02-09 (Week 1) |

---

## 6. Vendor Qualifications and Requirements

### 6.1 Mandatory Qualifications (MUST - Pass/Fail)

Vendors MUST meet the following minimum qualifications to be considered. Failure to meet any mandatory qualification will result in automatic disqualification.

**MQ-1: Experience Delivering Government AI Systems (MUST)**
- Minimum **5 years** of experience delivering AI/ML systems for UK Government or equivalent public sector organizations (NHS, MOD, DWP, HMRC, DVLA, etc.)
- At least **2 reference projects** involving AI-powered chatbots or conversational AI in production use by citizens
- Demonstrated experience with Retrieval-Augmented Generation (RAG) architecture

**MQ-2: UK Government Security Clearance (MUST)**
- Vendor company must be eligible for UK Government contracts (no exclusions)
- Key personnel (Solution Architect, Technical Lead, Security Architect) must hold or be eligible for **Security Check (SC)** clearance minimum
- Vendor must sign HMRC Non-Disclosure Agreement (NDA) and Data Processing Agreement (DPA)

**MQ-3: Reference Projects (MUST)**
- Minimum **3 reference projects** in the past **3 years** demonstrating:
  1. AI/ML system in production serving UK citizens or public sector users
  2. Cloud-based solution on AWS or Azure (preferably AWS UK regions)
  3. Integration with UK Government authentication systems (Government Gateway, GOV.UK Verify, or GOV.UK One Login)
- References must include client name, contact information, project scope, technologies used, and outcomes achieved

**MQ-4: Certifications (MUST)**
- Vendor company must hold **Cyber Essentials Plus** certification (current, not expired)
- Vendor company must be on **G-Cloud 14 framework** (or eligible to apply before contract signing)
- Key personnel must hold relevant certifications:
  - [ ] **AWS Certified Solutions Architect - Professional** (or equivalent Azure/GCP) for Solution Architect
  - [ ] **CISSP, CEH, or equivalent security certification** for Security Architect
  - [ ] **AWS Certified Machine Learning - Specialty** (or equivalent) for AI/ML Lead

**MQ-5: Financial Stability (MUST)**
- Company must provide **2 years of audited financial statements** demonstrating financial stability
- Minimum annual revenue: **£5M** for past 2 years
- Professional liability insurance: **£5M** minimum coverage
- Cyber liability insurance: **£2M** minimum coverage

**MQ-6: UK Presence (MUST)**
- Vendor must have a **UK office or registered UK subsidiary**
- On-site presence in London (HMRC offices) required for design workshops, GDS assessments, and key milestones
- Minimum **50% onshore** team allocation (UK-based staff)

**MQ-7: Accessibility Expertise (MUST)**
- At least **1 dedicated accessibility specialist** on team with:
  - WCAG 2.2 Level AA certification (IAAP CPACC or WAS preferred)
  - Experience delivering WCAG 2.2 AA compliant public sector services
  - Proven track record of accessibility testing with assistive technologies

### 6.2 Preferred Qualifications (Scored, Not Mandatory)

Preference will be given to vendors with:

**PQ-1: UK Tax Domain Experience**
- Prior work with HMRC, HM Treasury, or other UK tax/revenue authorities
- Understanding of UK tax system (Self Assessment, PAYE, VAT, National Insurance)
- Experience with HMRC technology estate (Government Gateway, HMRC backend APIs)

**PQ-2: GDS Service Standard Experience**
- Delivered services that passed **GDS Service Standard Live Assessment** (18 criteria)
- Experience with GDS Discovery, Alpha, Beta, Live phases
- Familiarity with GDS Design System and GOV.UK style guide

**PQ-3: AWS UK Region Experience**
- Production workloads running in AWS UK regions (eu-west-2, eu-west-1)
- Experience with UK data residency and sovereignty requirements
- AWS Well-Architected Framework reviews for UK Government workloads

**PQ-4: Responsible AI and ATRS Experience**
- Published **Algorithmic Transparency Recording Standard (ATRS)** records for previous projects
- Experience with UK Government AI Playbook and Data Ethics Framework
- Bias testing and fairness audits for AI systems serving diverse populations

**PQ-5: Agile and DevOps Maturity**
- Demonstrable Agile delivery (Scrum, Kanban) with citizen user research
- Mature CI/CD practices with automated quality gates
- Infrastructure as Code (Terraform) and GitOps practices

**PQ-6: Welsh Language Capability**
- Native Welsh speakers on team or partnership with Welsh language service provider
- Experience delivering bilingual (English/Welsh) public sector services
- Welsh Language Act 1993 compliance experience

### 6.3 Approved Technology Stack

Vendors SHOULD use the following approved technologies. Alternative technology proposals will be considered if vendors provide strong justification and demonstrate superior fit for requirements.

**Programming Languages** (in order of preference):
1. **Backend/AI**: Python 3.11+ (preferred for AI/ML, LangChain, Hugging Face)
2. **API Services**: Node.js/TypeScript 20+ (preferred for API Gateway, Lambda functions)
3. **Frontend**: TypeScript/React 18+ (mandatory for GOV.UK Design System integration)
4. **Infrastructure**: Terraform (HCL) preferred, AWS CDK (TypeScript/Python) acceptable

**AI/ML Stack**:
- **LLM**: AWS Bedrock Claude 3.5 Sonnet (mandatory for UK data residency)
- **Embedding Model**: AWS Titan Embeddings or OpenAI text-embedding-3-large
- **Vector Database**: Amazon OpenSearch with k-NN plugin (preferred), Pinecone (if UK-hosted)
- **LLM Orchestration**: LangChain or LlamaIndex
- **Guardrails**: AWS Bedrock Guardrails, custom content filters

**Databases**:
- **Relational**: Amazon RDS PostgreSQL 15+ (mandatory for OFFICIAL-SENSITIVE data)
- **Cache**: Amazon ElastiCache Redis 7+ (session management)
- **Object Storage**: Amazon S3 (chat transcripts, encrypted at rest)

**Compute**:
- **Container Orchestration**: Amazon ECS Fargate (preferred for serverless containers)
- **Serverless Functions**: AWS Lambda (for event-driven tasks)
- **Alternative**: Amazon EKS (if vendor provides strong justification for Kubernetes)

**Frontend**:
- **Framework**: React 18+ with TypeScript (mandatory)
- **Design System**: GOV.UK Design System (gov.uk-frontend components, mandatory)
- **Hosting**: AWS Amplify or CloudFront + S3

**Infrastructure as Code**:
- **Primary**: Terraform (HCL)
- **Alternative**: AWS CDK (TypeScript or Python)

**Security and Observability**:
- **Secrets Management**: AWS Secrets Manager (mandatory)
- **WAF**: AWS WAF with OWASP Top 10 rules
- **Monitoring**: Prometheus + Grafana (preferred), AWS CloudWatch, integration with HMRC Splunk
- **Tracing**: OpenTelemetry

**CI/CD**:
- **Pipeline**: GitHub Actions (preferred), AWS CodePipeline, GitLab CI
- **Security Scanning**: Semgrep (SAST), Snyk (dependency vulnerabilities), tfsec (IaC security), git-secrets

**Proposed Alternatives**:
Vendors may propose alternative technologies if they demonstrate:
1. Superior fit for requirements (with evidence)
2. Cost-effectiveness or performance advantages
3. UK data residency and sovereignty compliance
4. HMRC IT operations supportability
5. Alignment with HMRC Architecture Principles

### 6.4 Team Requirements

**Minimum Team Composition** (core team, on-site and offshore):

| Role | Minimum Experience | Allocation | Mandatory? |
|------|-------------------|------------|------------|
| **Solution Architect** | 10+ years, AWS Certified Solutions Architect Professional, UK Gov experience | e50% dedicated | YES |
| **Security Architect** | 8+ years, CISSP or equivalent, NCSC Cloud Security Principles expertise | e25% dedicated | YES |
| **AI/ML Lead** | 8+ years, AWS Certified ML Specialty, RAG architecture experience | e75% dedicated | YES |
| **Technical Lead / Engineering Manager** | 8+ years, team leadership experience | e75% dedicated | YES |
| **Senior Backend Engineers (Python)** | 5+ years Python, AI/ML pipeline experience | 3 FTE | YES |
| **Senior Backend Engineers (Node.js/Go)** | 5+ years Node.js or Go, API development | 2 FTE | YES |
| **Senior Frontend Engineer (React/TypeScript)** | 5+ years React, GOV.UK Design System experience | 2 FTE | YES |
| **DevOps Engineer** | 5+ years AWS, Terraform, CI/CD | 2 FTE | YES |
| **QA Lead** | 5+ years, test automation, accessibility testing | e50% dedicated | YES |
| **QA Engineers** | 3+ years, test automation (Python/JavaScript) | 2 FTE | YES |
| **Accessibility Specialist** | WCAG 2.2 AA certified, assistive technology testing | e25% dedicated | YES |
| **Content Designer** | Plain English writing, GOV.UK style guide experience | e25% dedicated | YES |
| **Technical Writer** | API documentation, technical writing for developers | e50% dedicated | YES |
| **Scrum Master / Delivery Manager** | Agile delivery, stakeholder management | e50% dedicated | PREFERRED |

**Total Team Size**: Approximately **20-25 FTE** over 12-month delivery period

**Key Personnel Requirements**:
- Key personnel (Solution Architect, AI/ML Lead, Technical Lead, Security Architect) must be named in proposal with CVs attached
- Key personnel cannot be changed without HMRC approval (30-day notice, CV review, interview)
- Key personnel must be available for kickoff and all milestone reviews

**Onshore/Offshore Mix**:
- **Minimum 50% onshore** (UK-based staff) required for compliance and stakeholder engagement
- **Solution Architect, Security Architect, AI/ML Lead, Technical Lead**: 100% onshore (UK-based)
- **Frontend, Backend, DevOps, QA**: Mix of onshore/offshore acceptable (subject to 50% overall minimum)
- All staff must be eligible for UK Government contracts (background checks may be required)

---

## 7. Proposal Requirements

### 7.1 Proposal Format

Proposals must follow this structure. **Page limits are strict** and will be enforced. Proposals exceeding page limits will be penalized in scoring.

#### **Section 1: Executive Summary** (Max 3 pages)
- High-level understanding of HMRC's objectives and challenges
- Proposed approach and key differentiators
- Summary of costs (detailed cost proposal in separate document)
- Commitment to timeline (12-month delivery)

#### **Section 2: Company Overview and Qualifications** (Max 8 pages)
- Company history, size, financial stability
- UK Government experience (list of projects with HMRC, GDS, NHS, MOD, etc.)
- Relevant certifications (Cyber Essentials Plus, G-Cloud 14, ISO 27001, SOC 2)
- **Evidence of mandatory qualifications (MQ-1 through MQ-7)** - failure to provide evidence will result in disqualification

#### **Section 3: Understanding of Requirements** (Max 10 pages)
- Demonstrate deep understanding of HMRC's business drivers (£75M savings, 30% helpline deflection)
- Interpretation of key requirements (RAG architecture, WCAG 2.2 AA, ATRS, UK GDPR)
- Identification of risks, assumptions, and dependencies
- Questions or ambiguities requiring clarification

#### **Section 4: Technical Solution** (Max 40 pages)
- **High-Level Architecture** (C4 Context and Container diagrams)
  - RAG pipeline design (query ’ embedding ’ vector search ’ LLM generation ’ validation ’ source citation)
  - Microservices architecture (Citizen Identity, Conversational AI, Knowledge Management, HMRC Integration, Audit & Compliance)
  - Integration approach (Government Gateway, HMRC backend APIs, AWS Bedrock, ServiceNow)

- **Technology Stack and Rationale**
  - Programming languages, AI/ML frameworks, databases, cloud services
  - Justification for technology choices aligned with HMRC Architecture Principles
  - If proposing alternatives to approved stack, provide strong justification

- **Security and Compliance Architecture**
  - Zero Trust security model
  - Mapping to NCSC Cloud Security Principles (all 14 principles)
  - UK GDPR compliance strategy (data minimization, citizen consent, data subject rights)
  - Cyber Essentials Plus compliance approach

- **AI Safety and Responsible AI**
  - Bias mitigation and fairness testing strategy
  - Explainability and source citation implementation
  - Guardrails for hallucination detection, prompt injection defense, toxic content filtering
  - ATRS record creation and publication plan

- **Accessibility Strategy**
  - WCAG 2.2 Level AA compliance approach
  - GOV.UK Design System integration
  - Assistive technology testing (JAWS, NVDA, VoiceOver)
  - Welsh language support architecture

- **Performance and Scalability**
  - Approach to meet <2s p95 latency and 500 req/s throughput
  - Auto-scaling strategy (ECS Fargate, RDS read replicas)
  - Caching strategy (ElastiCache Redis)

- **Disaster Recovery and Resilience**
  - Multi-AZ deployment in AWS eu-west-2
  - Backup and restore strategy (RPO <1 hour, RTO <15 minutes)
  - Circuit breaker, retry, graceful degradation patterns

#### **Section 5: Project Approach and Methodology** (Max 15 pages)
- **Agile Delivery Methodology**
  - Sprint structure (2-week sprints recommended)
  - User research and citizen feedback loops
  - Continuous integration and deployment approach

- **Project Timeline and Milestones**
  - 12-month timeline with 6 major milestones (M0 through M6)
  - Gantt chart or similar visualization
  - Dependencies and critical path

- **Risk Management**
  - Top 10 risks identified with probability, impact, mitigation strategies
  - Include: LLM API cost overruns, Government Gateway integration delays, DPIA approval delays, GDS assessment failure

- **Quality Assurance**
  - Testing strategy (unit, integration, E2E, performance, security, accessibility, AI accuracy, bias)
  - Acceptance criteria for each deliverable
  - User acceptance testing (UAT) approach for private/public beta

- **Change Management**
  - Change request process aligned with HMRC governance
  - Handling of scope changes, timeline changes, cost changes

#### **Section 6: Team and Resources** (Max 10 pages)
- **Team Structure**
  - Organization chart showing roles and reporting lines
  - Onshore/offshore mix (minimum 50% onshore)

- **Key Personnel**
  - CVs for Solution Architect, AI/ML Lead, Technical Lead, Security Architect
  - Include: Name, years of experience, relevant certifications, project references

- **Staff Augmentation Plan**
  - How to scale team if needed (e.g., additional QA engineers for testing phase)

- **Knowledge Transfer Plan**
  - Training approach for HMRC dev team, SRE team, content designers, support staff
  - Documentation deliverables (technical docs, API docs, operations manual, runbooks)

#### **Section 7: Experience and References** (Max 12 pages)
- **Minimum 3 Reference Projects** with:
  - **Client Name and Contact Information** (name, email, phone)
  - **Project Scope**: Objectives, challenges, solution delivered
  - **Technologies Used**: Cloud platform, AI/ML frameworks, databases, frontend
  - **Team Size and Duration**: Number of FTEs, project timeline
  - **Challenges Overcome**: Technical, organizational, or regulatory challenges
  - **Outcomes Achieved**: Quantitative metrics (e.g., 99.9% uptime, <2s latency, £XM cost savings)

- **Industry-Specific Experience**
  - UK Government / public sector projects (HMRC, GDS, NHS, MOD, DVLA, DWP)
  - AI/ML and chatbot projects in production
  - GDS Service Standard assessments passed

- **Awards and Recognition** (if applicable)

#### **Section 8: Assumptions, Dependencies, and Risks** (Max 5 pages)
- **Assumptions**
  - Key assumptions made in proposal (e.g., "HMRC will provide AWS account access within 5 days of kickoff")
  - Validation plan for each assumption

- **Dependencies on HMRC**
  - Access to HMRC systems (Government Gateway, backend APIs, Splunk, ServiceNow)
  - Subject matter expert availability (tax policy, content designers, security architects)
  - Approvals timeline (Architecture Review Board, DPO, CISO, GDS)

- **Identified Risks**
  - Top 10 project risks with mitigation strategies
  - Vendor responsibilities vs. HMRC responsibilities for risk mitigation

### 7.2 Cost Proposal Format

**CRITICAL**: Cost proposal must be provided in a **SEPARATE PDF document** to allow for technical evaluation independent of cost. Cost proposals will not be opened until after technical evaluation and shortlisting.

**File Naming**: `[VENDOR_NAME]_HMRC_ChatBot_Cost_Proposal.pdf`

Cost proposal must include:

#### **7.2.1 Fixed Price Breakdown** (Preferred)

**Total Fixed Price**: £[X.XX]M for all deliverables (design, development, deployment, 90-day warranty)

**Payment Milestone Breakdown**:
| Milestone | Deliverables | Payment (£) | Payment (%) |
|-----------|--------------|-------------|-------------|
| M0: Contract Signing | Contract signed, kickoff complete | £[X] | 10% |
| M1: Design Approval (Week 8) | HLD, DLD, DPIA, EqIA, ATRS approved | £[X] | 15% |
| M2: Development Milestone (Week 20) | Core ChatBot, RAG, integrations working in dev | £[X] | 20% |
| M3: Testing Complete (Week 40) | All tests passed, UAT ready | £[X] | 20% |
| M4: Private Beta Launch (Week 44) | 100 citizens onboarded, feedback collected | £[X] | 10% |
| M5: Production Launch (Week 52) | Production live, GDS PASS, training complete | £[X] | 20% |
| M6: Warranty End (Week 64) | 90-day warranty complete, final sign-off | £[X] | 5% |
| **TOTAL** | | **£[X.XX]M** | **100%** |

**Cost Breakdown by Phase**:
- Initiation (Weeks 1-2): £[X]
- Design (Weeks 3-8): £[X]
- Development (Weeks 9-32): £[X]
- Testing (Weeks 33-40): £[X]
- Beta Deployments (Weeks 41-48): £[X]
- Production Launch (Weeks 49-52): £[X]
- Warranty (Weeks 53-64): £[X]

#### **7.2.2 Time and Materials Breakdown** (If Fixed Price Not Possible)

**Hourly/Daily Rates by Role**:
| Role | Hourly Rate (£) | Daily Rate (£) | Estimated Hours/Days |
|------|-----------------|----------------|----------------------|
| Solution Architect | £[X] | £[X] | [X] hours |
| AI/ML Lead | £[X] | £[X] | [X] hours |
| Technical Lead | £[X] | £[X] | [X] hours |
| Senior Engineer | £[X] | £[X] | [X] hours |
| Engineer | £[X] | £[X] | [X] hours |
| QA Lead | £[X] | £[X] | [X] hours |
| QA Engineer | £[X] | £[X] | [X] hours |
| DevOps Engineer | £[X] | £[X] | [X] hours |
| Accessibility Specialist | £[X] | £[X] | [X] hours |
| Content Designer | £[X] | £[X] | [X] hours |
| Technical Writer | £[X] | £[X] | [X] hours |

**Total Estimated Cost**: £[X.XX]M (labor only)

**Not-to-Exceed Cap**: £[X.XX]M (labor cap to manage HMRC budget risk)

#### **7.2.3 Infrastructure and Third-Party Costs**

**AWS Infrastructure Costs** (estimated annual opex):
- ECS Fargate compute: £[X]/month × 12 months = £[X]
- RDS PostgreSQL: £[X]/month × 12 months = £[X]
- OpenSearch: £[X]/month × 12 months = £[X]
- S3 storage: £[X]/month × 12 months = £[X]
- CloudFront CDN: £[X]/month × 12 months = £[X]
- Data transfer: £[X]/month × 12 months = £[X]
- **Subtotal AWS (Year 1)**: £[X]/year

**LLM API Costs** (estimated annual opex):
- AWS Bedrock Claude 3.5 Sonnet: £[X] per million tokens
- Estimated tokens/month: [X] million tokens
- **Subtotal LLM (Year 1)**: £[X]/year

**Third-Party Services**:
- Monitoring (Grafana Cloud, DataDog, etc.): £[X]/year
- Security tools (Snyk, Semgrep): £[X]/year
- Other SaaS tools: £[X]/year
- **Subtotal Third-Party (Year 1)**: £[X]/year

**Total Infrastructure Costs (Year 1)**: £[X]/year
**Total Infrastructure Costs (3-Year TCO)**: £[X] (Years 1-3 with estimated growth)

#### **7.2.4 Ongoing Support and Maintenance** (Post-Warranty)

**Annual Support and Maintenance Cost**: £[X]/year (starting Month 16, after 90-day warranty)

**Included Services**:
- Bug fixes and patches
- Security vulnerability remediation (SLA: critical within 7 days, high within 30 days)
- Knowledge base updates (automated ingestion pipeline support)
- AWS infrastructure maintenance and optimization
- Monitoring and alerting support
- 8x5 support (business hours Monday-Friday)

**SLA for Support**:
| Severity | Response Time | Resolution Time | Support Hours |
|----------|---------------|-----------------|---------------|
| Severity 1 (System Down) | 1 hour | 4 hours | 24/7 (escalation) |
| Severity 2 (Major Feature Broken) | 4 hours | 24 hours | 8x5 |
| Severity 3 (Minor Issue) | 1 business day | 5 business days | 8x5 |
| Severity 4 (Enhancement) | 5 business days | Best effort | 8x5 |

**Out of Scope for Annual Maintenance**:
- New feature development (separate SOW required)
- Major architectural changes (separate SOW required)
- Integrations with new HMRC systems beyond those specified (separate SOW required)

#### **7.2.5 Total Cost Summary (3-Year TCO)**

| Cost Category | Year 1 (Capex) | Year 2 (Opex) | Year 3 (Opex) | 3-Year Total |
|---------------|----------------|---------------|---------------|--------------|
| **Design and Development** (Fixed Price or T&M) | £[X.XX]M | - | - | £[X.XX]M |
| **AWS Infrastructure** | £[X]/year | £[X]/year | £[X]/year | £[X]M |
| **LLM API Costs** (AWS Bedrock) | £[X]/year | £[X]/year | £[X]/year | £[X]M |
| **Third-Party Services** | £[X]/year | £[X]/year | £[X]/year | £[X]K |
| **Annual Support and Maintenance** (Post-Warranty) | - | £[X]/year | £[X]/year | £[X]M |
| **TOTAL 3-Year TCO** | £[X.XX]M | £[X.XX]M | £[X.XX]M | **£[X.XX]M** |

**3-Year Net Savings** (Business Case):
- Savings from helpline deflection: £75M/year × 3 years = £225M
- Less: 3-Year TCO: £[X.XX]M
- **Net Savings**: £[X]M

#### **7.2.6 Pricing Terms and Assumptions**

**Payment Terms**: Net 30 days from invoice date (invoices issued upon milestone completion and acceptance)

**Currency**: British Pounds Sterling (GBP £)

**Validity Period**: Pricing valid for **90 days** from RFP issue date (2025-10-14 to 2026-01-12)

**Assumptions Affecting Pricing**:
1. HMRC provides AWS account access and pre-configured VPC/security groups within 5 days of kickoff
2. Government Gateway API credentials and sandbox access provided within 10 days of kickoff
3. HMRC subject matter experts available for workshops and reviews within agreed timelines
4. HMRC Architecture Review Board, DPO, CISO approvals within 10 business days of submission
5. Ground truth dataset for AI accuracy testing provided by HMRC by Week 12
6. Beta testing participants (100 private, 10,000 public) recruited and onboarded by HMRC
7. No material changes to scope during delivery (change requests subject to change management process)

**Exclusions** (Not Included in Pricing):
- HMRC staff time and subject matter experts
- HMRC-provided AWS infrastructure costs (HMRC AWS account, HMRC pays AWS bills directly)
- Travel expenses for on-site workshops/meetings (if required, charged at cost with receipts)
- Third-party penetration testing by CHECK-approved supplier (HMRC procures separately)
- GDS Service Standard assessment fees (if applicable)

### 7.3 Submission Instructions

**Deadline**: Proposals must be received by **2025-12-09 at 5:00 PM GMT**

**Submission Method**: Email to **procurement-chatbot@hmrc.gov.uk**

**Required Files**:
1. **Technical Proposal**: `[VENDOR_NAME]_HMRC_ChatBot_Technical_Proposal.pdf`
2. **Cost Proposal** (SEPARATE FILE): `[VENDOR_NAME]_HMRC_ChatBot_Cost_Proposal.pdf`
3. **Company Qualifications Evidence** (SEPARATE FILE): `[VENDOR_NAME]_HMRC_ChatBot_Qualifications.pdf`
   - Include: Cyber Essentials Plus certificate, G-Cloud 14 listing, ISO 27001/SOC 2 certificates, financial statements, insurance certificates
4. **Key Personnel CVs** (SEPARATE FILE): `[VENDOR_NAME]_HMRC_ChatBot_CVs.pdf`
   - Include CVs for: Solution Architect, AI/ML Lead, Technical Lead, Security Architect

**Email Subject Line**: `HMRC ChatBot RFP Response - [VENDOR_NAME]`

**File Format**: PDF only (Word documents will not be accepted)

**File Size**: Maximum 50MB per file (use compression if necessary, but ensure readability)

**Questions**:
- Submit questions by **2025-10-28** to **procurement-chatbot@hmrc.gov.uk**
- **Subject Line**: `HMRC ChatBot RFP Question - [VENDOR_NAME]`
- All questions and answers will be published to all vendors by **2025-11-04** (anonymized vendor names)
- Do not include proprietary or confidential information in questions (visible to all vendors)

**Late Proposals**: Will **NOT** be accepted (no exceptions)

**Incomplete Proposals**: Missing mandatory qualifications evidence will result in automatic disqualification

---

## 8. Evaluation Criteria

### 8.1 Evaluation Process

Proposals will be evaluated in **two phases** to ensure fair and unbiased assessment:

**Phase 1: Technical Evaluation (Cost Sealed)**
1. **Mandatory Qualifications Check** (Pass/Fail): All vendors reviewed for MQ-1 through MQ-7. Failure to meet any mandatory qualification = automatic disqualification.
2. **Technical Scoring**: Qualified vendors scored on 100-point scale across 5 criteria (see Section 8.2)
3. **Shortlisting**: Top **3-5 vendors** with highest technical scores invited to Phase 2

**Phase 2: Cost Evaluation and Selection**
1. **Cost Proposals Opened**: Only for shortlisted vendors
2. **Vendor Presentations**: 2-hour sessions (1 hour presentation, 1 hour Q&A) with HMRC evaluation committee
3. **Combined Scoring**: Technical score (70% weight) + Cost score (30% weight) = Final score
4. **Final Selection**: Vendor with highest combined score selected (subject to best value determination)
5. **Contract Negotiation**: 2-week negotiation period with selected vendor

### 8.2 Technical Evaluation Criteria (100 Points)

Technical proposals will be scored on a **100-point scale** across 5 criteria:

| Criteria | Weight | Max Points | Scoring Focus |
|----------|--------|------------|---------------|
| **1. Technical Approach and Solution Design** | 35% | 35 | RAG architecture quality, AI safety, security design, scalability, alignment with HMRC Architecture Principles |
| **2. Project Approach and Methodology** | 20% | 20 | Agile delivery, realistic timeline, risk management, quality assurance, change management |
| **3. Team Qualifications and Experience** | 25% | 25 | Team expertise, certifications, key personnel CVs, onshore/offshore mix |
| **4. Relevant Experience and References** | 15% | 15 | UK Gov AI projects, GDS Service Standard, similar chatbot projects, reference quality |
| **5. Understanding of Requirements and Problem Domain** | 5% | 5 | Demonstrated understanding of HMRC challenges, tax domain knowledge, identified risks |
| **TOTAL** | **100%** | **100** | |

#### **Detailed Scoring Rubric**

**Criterion 1: Technical Approach and Solution Design (35 points)**

- **RAG Architecture (10 points)**
  - 9-10: Excellent RAG design with embedding model, vector DB, LLM orchestration, source citation, confidence scoring, human escalation. Innovative approach.
  - 7-8: Good RAG design addressing all requirements. Standard approach.
  - 5-6: Adequate RAG design but missing some details (e.g., confidence scoring, human escalation).
  - 0-4: Poor or incomplete RAG design. Major gaps.

- **AI Safety and Responsible AI (8 points)**
  - 7-8: Comprehensive bias mitigation, explainability, guardrails (hallucination detection, prompt injection defense), ATRS creation plan. Exceeds requirements.
  - 5-6: Good AI safety approach addressing all requirements.
  - 3-4: Adequate AI safety but missing some elements (e.g., adversarial testing, bias mitigation).
  - 0-2: Poor or incomplete AI safety approach.

- **Security and Compliance (8 points)**
  - 7-8: Excellent Zero Trust security design. All 14 NCSC Cloud Security Principles addressed. UK GDPR, Cyber Essentials Plus, DPIA/EqIA plans robust.
  - 5-6: Good security design addressing all requirements.
  - 3-4: Adequate security but missing some details (e.g., incomplete NCSC mapping, weak DPIA plan).
  - 0-2: Poor or incomplete security approach. Major gaps.

- **Architecture Quality (9 points)**
  - 8-9: Clear C4 diagrams (Context, Container, Component). Microservices aligned with DDD. Technology stack well-justified. Scalability, resilience, DR robust.
  - 6-7: Good architecture with clear diagrams and technology choices.
  - 4-5: Adequate architecture but lacks clarity or justification.
  - 0-3: Poor architecture with unclear diagrams, unjustified technology choices, or major design flaws.

**Criterion 2: Project Approach and Methodology (20 points)**

- **Agile Delivery and Timeline (8 points)**
  - 7-8: Realistic 12-month timeline with clear sprints, milestones, dependencies. Agile methodology well-defined with user research loops.
  - 5-6: Good timeline and Agile approach.
  - 3-4: Adequate but overly optimistic timeline or weak Agile methodology.
  - 0-2: Unrealistic timeline or poor Agile approach.

- **Risk Management (6 points)**
  - 5-6: Comprehensive risk register with top 10+ risks, probability/impact, detailed mitigation strategies. Proactive approach.
  - 3-4: Good risk management addressing key risks.
  - 1-2: Adequate but generic risks or weak mitigations.
  - 0: No risk management or very poor approach.

- **Quality Assurance (6 points)**
  - 5-6: Comprehensive testing strategy (unit, integration, E2E, performance, security, accessibility, AI accuracy, bias). Clear acceptance criteria.
  - 3-4: Good QA approach covering main test types.
  - 1-2: Adequate but missing some test types (e.g., bias testing, adversarial testing).
  - 0: Poor or incomplete QA approach.

**Criterion 3: Team Qualifications and Experience (25 points)**

- **Key Personnel Quality (12 points)**
  - 11-12: Exceptional CVs for Solution Architect, AI/ML Lead, Technical Lead, Security Architect. Highly relevant experience (UK Gov AI, GDS, RAG, WCAG 2.2 AA). Strong certifications.
  - 8-10: Good CVs with relevant experience and certifications.
  - 5-7: Adequate CVs but lacking some experience (e.g., no UK Gov or GDS projects).
  - 0-4: Weak CVs with insufficient experience or certifications.

- **Team Composition and Depth (8 points)**
  - 7-8: Well-structured team meeting all role requirements. Good onshore/offshore mix (e50% onshore). Depth in AI/ML, security, accessibility.
  - 5-6: Good team composition meeting requirements.
  - 3-4: Adequate team but missing some roles or weak in key areas.
  - 0-2: Insufficient team or poor composition.

- **Certifications (5 points)**
  - 5: All mandatory certifications held (AWS Solutions Architect Professional, CISSP, AWS ML Specialty, WCAG 2.2 AA). Additional certifications (e.g., Terraform, GCP).
  - 3-4: All mandatory certifications held.
  - 1-2: Some mandatory certifications missing but plan to obtain.
  - 0: Missing multiple mandatory certifications.

**Criterion 4: Relevant Experience and References (15 points)**

- **Reference Projects Quality (9 points)**
  - 8-9: Exceptional references with 3+ UK Gov AI/chatbot projects in production. Clear evidence of similar scope, GDS Service Standard PASS, quantified outcomes (uptime, latency, cost savings).
  - 6-7: Good references with relevant UK Gov or public sector projects.
  - 4-5: Adequate references but lacking UK Gov experience or production chatbot projects.
  - 0-3: Weak references with little relevance to HMRC ChatBot.

- **UK Government and GDS Experience (6 points)**
  - 5-6: Extensive UK Gov experience (HMRC, GDS, NHS, MOD). Multiple GDS Service Standard assessments passed. Deep understanding of GDS phases (Discovery, Alpha, Beta, Live).
  - 3-4: Good UK Gov experience with some GDS assessments.
  - 1-2: Limited UK Gov experience or no GDS assessments.
  - 0: No UK Gov or GDS experience.

**Criterion 5: Understanding of Requirements and Problem Domain (5 points)**

- **Demonstrated Understanding (5 points)**
  - 5: Exceptional understanding of HMRC challenges (£75M savings, 30% helpline deflection, citizen satisfaction). Insightful questions about tax domain, HMRC integrations, regulatory compliance. Proactive identification of risks/ambiguities.
  - 3-4: Good understanding with some insightful questions.
  - 1-2: Adequate understanding but superficial or generic.
  - 0: Poor understanding or no evidence of domain knowledge.

### 8.3 Cost Evaluation Criteria (For Shortlisted Vendors Only)

Cost will be evaluated using **Best Value approach** (not lowest price):

**Cost Scoring Method**:
- **Technical Score**: 70% weight (from Phase 1 technical evaluation)
- **Cost Score**: 30% weight (calculated below)
- **Final Score** = (Technical Score × 0.7) + (Cost Score × 0.3)

**Cost Score Calculation** (30 points max):
- Vendor with **lowest 3-year TCO** receives **30 points**
- Other vendors scored proportionally:
  - **Cost Score** = (Lowest 3-Year TCO / Vendor's 3-Year TCO) × 30 points

**Example**:
- Vendor A: 3-Year TCO = £18M ’ Cost Score = (£16M / £18M) × 30 = 26.67 points
- Vendor B: 3-Year TCO = £16M ’ Cost Score = (£16M / £16M) × 30 = 30.00 points (lowest)
- Vendor C: 3-Year TCO = £20M ’ Cost Score = (£16M / £20M) × 30 = 24.00 points

**Cost Evaluation Factors**:
- **3-Year TCO** (capex + opex): Design/development, AWS infrastructure, LLM API costs, support/maintenance
- **Value for Money**: Cost per conversation, cost savings from helpline deflection, ROI
- **Pricing Transparency**: Clear breakdown, realistic assumptions, no hidden costs
- **Flexibility**: Fixed price vs. T&M, payment milestone structure

### 8.4 Vendor Presentations (For Shortlisted Vendors Only)

Shortlisted vendors (top 3-5 from Phase 1) will be invited to present proposals to HMRC evaluation committee.

**Presentation Details**:
- **Date**: 2026-01-06 to 2026-01-10 (Week of presentations, scheduled individually)
- **Duration**: 2 hours (1 hour presentation, 1 hour Q&A)
- **Format**: In-person at HMRC offices in London (or virtual if COVID-19 restrictions apply)
- **Attendees** (HMRC side): Architecture Review Board, HMRC CISO delegate, Data Protection Officer, Procurement Lead, Technical Leads, Domain Architects
- **Attendees** (Vendor side): Solution Architect, AI/ML Lead, Technical Lead, Security Architect (max 5 vendor attendees)

**Presentation Content** (suggested structure):
1. **Introduction** (5 min): Company overview, team introductions
2. **Technical Solution Deep-Dive** (30 min):
   - Live demo of RAG architecture (if possible, mock demo acceptable)
   - C4 diagrams walkthrough (Context, Container, Component)
   - AI safety and security deep-dive (bias mitigation, guardrails, NCSC principles)
3. **Delivery Approach** (15 min):
   - 12-month timeline and milestones
   - Risk management and mitigation
   - Quality assurance and testing strategy
4. **Team and Experience** (10 min):
   - Key personnel introductions (if available)
   - Reference project case studies
5. **Q&A** (60 min): Open discussion with evaluation committee

**Presentation Scoring**:
- Presentations do NOT change technical scores from Phase 1
- Presentations are used to clarify technical approach, assess team competency, evaluate cultural fit
- Evaluation committee may request additional information or clarifications after presentation

### 8.5 Selection Decision

**Decision Authority**: HMRC Senior Responsible Officer (SRO) with recommendation from evaluation committee

**Selection Criteria**:
1. **Highest Combined Score** (Technical 70% + Cost 30%)
2. **Best Value** (not necessarily lowest price): Balance of technical quality, cost, risk, and confidence in delivery
3. **Cultural Fit**: Alignment with HMRC values, Agile culture, citizen-centric approach
4. **Reference Checks**: Positive feedback from reference clients (phone interviews with reference contacts)

**Selection Timeline**:
- **Shortlist Announced**: 2025-12-23 (top 3-5 vendors invited to presentations)
- **Vendor Presentations**: 2026-01-06 to 2026-01-10
- **Reference Checks**: 2026-01-13 to 2026-01-17
- **Final Selection Decision**: 2026-01-20
- **All Vendors Notified**: 2026-01-22 (successful and unsuccessful vendors)
- **Debriefing Available**: Unsuccessful vendors may request written feedback (provided within 10 business days)

**Contract Negotiation**:
- **Duration**: 2026-01-23 to 2026-02-06 (2 weeks)
- **Topics**: Payment terms, deliverable acceptance criteria, change management process, IP rights, warranties, termination clauses
- **Contract Signing**: Target date 2026-02-09 (Week 1 project kickoff)

---

## 9. Contract Terms and Conditions

### 9.1 Contract Type

**Fixed Price Contract** (Preferred)

Fixed price for all deliverables with milestone-based payments (see Section 7.2.1). Vendor assumes risk for cost overruns. HMRC pays only for accepted deliverables.

**Alternative: Time and Materials with Not-to-Exceed Cap**

If Fixed Price not feasible, T&M contract with not-to-exceed cap (maximum £[X]M) to protect HMRC budget. Vendor invoices monthly based on actual hours worked at agreed rates. HMRC reserves right to terminate if cap approached without sufficient progress.

### 9.2 Payment Terms

**Payment Schedule** (for Fixed Price contract):

| Milestone | Payment (%) | Payment (£) | Trigger |
|-----------|-------------|-------------|---------|
| M0: Contract Signing | 10% | £[X] | Contract executed, kickoff complete |
| M1: Design Approval (Week 8) | 15% | £[X] | HLD, DLD, DPIA, EqIA, ATRS approved by Architecture Review Board, DPO, Data Ethics Committee |
| M2: Development Milestone (Week 20) | 20% | £[X] | Core ChatBot, RAG pipeline, HMRC integrations demonstrated in dev environment. Unit tests e80% coverage. |
| M3: Testing Complete (Week 40) | 20% | £[X] | All tests passed (performance, security, accessibility, bias). Penetration test PASS. UAT ready. |
| M4: Private Beta Launch (Week 44) | 10% | £[X] | 100 citizens onboarded. Private beta operational. Feedback collected. |
| M5: Production Launch (Week 52) | 20% | £[X] | Production live. GDS Service Standard PASS. ATRS published. 99.9% uptime achieved. Knowledge transfer complete. |
| M6: Warranty End (Week 64) | 5% | £[X] | 90-day warranty complete. No outstanding critical/high bugs. Final sign-off by HMRC SRO. |

**Payment Terms**: Net 30 days from invoice date

**Invoicing**: Vendor submits invoice upon milestone completion. HMRC reviews deliverables against acceptance criteria (see Section 9.3). If accepted, payment processed within 30 days. If rejected, vendor addresses feedback and resubmits.

**Retainage**: 5% of total contract value held until warranty completion (Milestone M6) to ensure vendor support during warranty period.

### 9.3 Acceptance Criteria

Each deliverable must meet defined acceptance criteria (see Section 4).

**Acceptance Process**:
1. **Vendor Submits Deliverable**: Email to HMRC project manager with deliverable attachment and completion checklist
2. **HMRC Reviews** (5 business days): Architecture Review Board (for design), Technical Leads (for code), QA team (for tests)
3. **HMRC Decision** (within 5 business days):
   - **ACCEPTED**: Formal acceptance sign-off via email. Payment milestone triggered.
   - **REJECTED WITH FEEDBACK**: Specific deficiencies listed. Vendor addresses feedback and resubmits.
   - **CLARIFICATIONS REQUESTED**: Additional information needed. Vendor responds within 3 business days.
4. **Vendor Addresses Feedback** (up to 10 business days for major revisions)
5. **Resubmission and Re-Review**: Repeat steps 2-3 until accepted

**Acceptance Criteria Examples**:
- **HLD Acceptance**: All 17 architecture principles addressed. C4 diagrams clear and complete. Technology choices justified. Approved by Architecture Review Board (majority vote).
- **Code Acceptance**: Passes code review (2 reviewers). Passes CI/CD quality gates (unit tests e80% coverage, SAST/dependency scans pass). Deployable to staging environment.
- **Performance Test Acceptance**: p95 latency <2s. 99.9% success rate under 10,000 concurrent users. No memory leaks or resource exhaustion.
- **Accessibility Test Acceptance**: WCAG 2.2 AA automated tests pass (axe-core, Pa11y). Manual testing with JAWS, NVDA, VoiceOver successful. Zero critical/high issues.

**Disputes**:
If vendor disagrees with rejection, escalate to HMRC SRO and vendor Project Director for resolution within 5 business days.

### 9.4 Warranty and Support

**Warranty Period**: **90 days** from production go-live (Weeks 53-64, Milestone M6)

**Warranty Coverage**:
- All defects (bugs) identified during warranty period fixed at **no additional cost** to HMRC
- Defects include: Functional bugs, performance degradation, security vulnerabilities introduced by vendor code, accessibility issues

**Warranty SLA**:
| Severity | Response Time | Resolution Time |
|----------|---------------|-----------------|
| Severity 1 (System Down, Security Breach) | 1 hour | 4 hours |
| Severity 2 (Major Feature Broken) | 4 hours | 24 hours |
| Severity 3 (Minor Issue) | 1 business day | 5 business days |
| Severity 4 (Cosmetic, Enhancement) | 5 business days | Best effort |

**Warranty Exclusions**:
- Defects caused by HMRC modifications to code or infrastructure
- Defects caused by third-party systems (Government Gateway, HMRC backend APIs) outside vendor control
- New feature requests (not defects)

**Post-Warranty**: After 90-day warranty, defects covered by Annual Support and Maintenance contract (see Section 9.5)

### 9.5 Ongoing Support and Maintenance (Optional)

**Annual Support and Maintenance Contract**: £[X]/year (starting Month 16, after 90-day warranty)

**Included Services**:
- **Bug Fixes**: Address defects reported by HMRC or citizens
- **Security Patches**: Remediate security vulnerabilities (SLA: critical within 7 days, high within 30 days)
- **Knowledge Base Updates**: Support for automated ingestion pipeline when HMRC updates content
- **AWS Infrastructure Optimization**: Right-sizing, cost optimization recommendations
- **Monitoring and Alerting**: Review dashboards, tune alerts, respond to SLO violations
- **Minor Enhancements**: Up to 160 hours/year of minor enhancements (e.g., UI tweaks, new knowledge base sources)

**Support Hours**: 8x5 (08:00-18:00 GMT Monday-Friday, UK bank holidays excluded)

**24/7 Escalation**: Severity 1 issues (system down, security breach) receive 24/7 on-call support via escalation process

**SLA for Support** (same as warranty SLA above)

**Out of Scope**:
- New feature development requiring >160 hours (separate SOW and budget required)
- Major architectural changes (separate SOW)
- Integrations with new HMRC systems not specified in original requirements (separate SOW)

**Renewal**: Annual contract renewed yearly with price escalation limited to UK CPI (Consumer Price Index)

### 9.6 Intellectual Property Rights

**Work Product Ownership**: **HMRC owns all custom-developed work product**

All deliverables, source code, documentation, designs, and other work product created specifically for HMRC ChatBot project become the **exclusive property of HMRC** upon final payment (Milestone M6). Vendor assigns all IP rights, including copyright, to HMRC.

**Vendor Pre-Existing IP**: Vendor retains ownership of:
- Pre-existing frameworks, libraries, tools, and reusable components
- General methodologies and knowledge

**License to HMRC**: Vendor grants HMRC a **perpetual, irrevocable, royalty-free, worldwide license** to use vendor pre-existing IP incorporated in the work product.

**Open Source Components**:
- Vendor must disclose all open-source components and licenses used in the project (provide Software Bill of Materials - SBOM)
- Open-source licenses must be compatible with HMRC's use (e.g., Apache 2.0, MIT, BSD acceptable; GPL requires legal review)
- HMRC reserves right to reject open-source components with restrictive licenses (e.g., AGPL)

**Source Code Publication**: HMRC may publish non-sensitive source code on GitHub under **Open Government Licence v3.0** (aligned with GDS Service Standard Criterion 12). Security-sensitive components (authentication, secrets management) excluded from publication.

### 9.7 Data and Security

**Data Ownership**: **HMRC retains ownership of all citizen data**, tax data, and HMRC content

**Data Security**: Vendor must comply with:
- HMRC Security Policies (provided upon contract signing)
- NCSC Cloud Security Principles (all 14 principles)
- UK GDPR and Data Protection Act 2018
- Cyber Essentials Plus requirements

**Data Handling**:
- Vendor must NOT use HMRC data for vendor's own purposes (e.g., training vendor's own AI models)
- Vendor must NOT share HMRC data with third parties without HMRC written consent
- Upon contract termination, vendor must **return or securely destroy** all HMRC data within 30 days (with certificate of destruction)

**Data Processing Agreement (DPA)**: Vendor must sign HMRC Data Processing Agreement before accessing any citizen data (UK GDPR Article 28 requirement)

**Background Checks**: Vendor staff with access to OFFICIAL-SENSITIVE data (tax records, citizen PII) must pass **Baseline Personnel Security Standard (BPSS)** background checks or Security Check (SC) clearance if required by HMRC

**Audit Rights**: HMRC reserves right to audit vendor's security practices and data handling (annual audit or upon reasonable suspicion of breach)

### 9.8 Confidentiality

**Non-Disclosure Agreement (NDA)**: Vendor must sign HMRC NDA before RFP response (required to access detailed requirements and HMRC system documentation)

**Confidential Information**: Includes HMRC citizen data, tax data, system architecture, security controls, business plans, and any information marked "OFFICIAL" or "OFFICIAL-SENSITIVE"

**Obligations**:
- Vendor must NOT disclose confidential information to third parties without HMRC written consent
- Vendor must protect confidential information with same level of care as vendor protects its own confidential information (minimum: industry-standard security controls)
- Confidentiality obligation survives contract termination for **5 years**

**Exceptions**: Confidential information does NOT include information that is:
- Publicly available (not through vendor's breach)
- Independently developed by vendor without access to HMRC confidential information
- Required to be disclosed by law (with advance notice to HMRC to seek protective order)

### 9.9 Liability and Indemnification

**Liability Cap**: **£10M** (2× contract value, or as negotiated)

**Exceptions to Liability Cap** (unlimited liability):
- IP infringement claims
- Data breaches due to vendor negligence or breach of security obligations
- Fraud or willful misconduct
- Breaches of confidentiality or data protection obligations

**Indemnification**: Vendor indemnifies and holds HMRC harmless against:
- **IP Infringement**: Claims that vendor's work product infringes third-party IP rights (patents, copyrights, trademarks)
- **Data Breaches**: Claims arising from vendor's breach of data protection obligations (UK GDPR fines, citizen compensation)
- **Violations of Law**: Claims arising from vendor's violation of laws or regulations

**Insurance**: Vendor must maintain:
- **Professional Liability Insurance**: £5M minimum
- **Cyber Liability Insurance**: £2M minimum (covering data breaches, ransomware, cyber incidents)
- **General Liability Insurance**: £2M minimum

Vendor must provide certificates of insurance upon contract signing and annually thereafter.

### 9.10 Termination

**Termination for Convenience**: HMRC may terminate contract at any time with **60 days written notice** to vendor

Upon termination for convenience:
- HMRC pays vendor for all work completed and accepted up to termination date
- Vendor provides transition assistance (see Section 9.11)
- No termination penalties

**Termination for Cause**: Either party may terminate if other party:
- **Breaches material terms** of contract (e.g., failure to deliver, security breach, data protection violation) and fails to cure within **30 days** of written notice
- Becomes insolvent, enters administration, or ceases business operations

Upon termination for cause by HMRC:
- HMRC pays vendor ONLY for work completed and accepted (no payment for incomplete milestones)
- Vendor must immediately return all HMRC data and confidential information
- HMRC may seek damages for breach (subject to liability cap)

**Termination by Vendor for HMRC Breach**:
- Vendor may terminate if HMRC fails to pay invoices for >90 days after due date
- Vendor provides 30 days written notice; HMRC has 30 days to cure (pay outstanding invoices)
- If HMRC cures, contract continues; if not, vendor may terminate and seek payment for completed work

### 9.11 Transition Assistance

Upon contract termination (for any reason), vendor must provide **90 days of transition assistance** at no additional cost to HMRC.

**Transition Assistance Includes**:
- **Knowledge Transfer**: Training for HMRC team or new vendor on system architecture, codebase, deployment, operations
- **Documentation**: Complete all outstanding documentation (technical docs, API docs, runbooks)
- **Source Code Handover**: Provide all source code, IaC, configuration files, database schemas in Git repository
- **Access Credentials**: Provide all access credentials (AWS accounts, third-party services) securely
- **Support**: Continue to provide support for production system during transition period (same SLA as warranty/maintenance)

**New Vendor Support**: If HMRC engages new vendor, outgoing vendor must cooperate with new vendor for smooth transition (e.g., attend handover meetings, answer questions)

### 9.12 Change Management

**Change Request Process**:
1. **Either Party Submits Written Change Request**: Email with description of change, rationale, urgency
2. **Vendor Provides Impact Analysis** (within 10 business days):
   - Impact on cost (£ increase/decrease)
   - Impact on schedule (weeks delay/acceleration)
   - Impact on scope (what's added/removed)
   - Impact on quality or risk
3. **HMRC Reviews and Decides** (within 10 business days):
   - **APPROVED**: Change order issued, contract amended
   - **REJECTED**: No change, original contract continues
   - **NEGOTIATE**: Further discussion to refine change proposal
4. **Change Order Executed**: Both parties sign change order, contract formally amended
5. **Implementation**: Vendor proceeds with approved change

**Approval Thresholds**:
- **Changes <£50K or <2 weeks delay**: HMRC Technical Lead approval
- **Changes £50K-£250K or 2-8 weeks delay**: HMRC Project Manager + Architecture Review Board approval
- **Changes >£250K or >8 weeks delay**: HMRC SRO approval

**Emergency Changes**:
- Critical security vulnerabilities or production incidents may require immediate changes without full impact analysis
- Vendor proceeds with emergency change, provides impact analysis within 5 business days retrospectively
- HMRC reserves right to reject retroactive change order if impact deemed unreasonable

**Scope Creep Prevention**:
- Vendor must flag potential scope creep early (e.g., "This new requirement was not in original SOW and will require change order")
- HMRC and vendor review requirements quarterly to ensure alignment and address scope creep proactively

---

## 10. Appendices

### Appendix A: Detailed Requirements Document

**File**: `projects/001-hmrc-chatbot/requirements.md`

Full requirements document (7 Business Requirements, 11 Functional Requirements, 21 Non-Functional Requirements, 5 Integration Requirements, 5 Data Entities, 5 User Personas, 5 Use Cases) available in project repository.

Vendors must review full requirements document and incorporate all requirements into proposals.

### Appendix B: Enterprise Architecture Principles

**File**: `.arckit/memory/architecture-principles.md`

HMRC ChatBot Enterprise Architecture Principles (17 principles across 10 sections) available in project repository.

All proposals must demonstrate compliance with architecture principles. Non-negotiable principles: #3 (Security by Design), #4 (Accessibility), #5 (Responsible AI), #7 (Data Sovereignty).

### Appendix C: UK Government Standards and Compliance

**Mandatory Compliance Frameworks**:

1. **GDS Service Standard** (18 criteria): https://www.gov.uk/service-manual/service-standard
2. **Technology Code of Practice**: https://www.gov.uk/guidance/the-technology-code-of-practice
3. **UK Government AI Playbook**: https://www.gov.uk/government/publications/ai-playbook
4. **Algorithmic Transparency Recording Standard (ATRS)**: https://www.gov.uk/government/collections/algorithmic-transparency-recording-standard-hub
5. **Data Ethics Framework**: https://www.gov.uk/government/publications/data-ethics-framework
6. **NCSC Cloud Security Principles**: https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles
7. **Cyber Essentials Plus**: https://www.ncsc.gov.uk/cyberessentials/overview
8. **WCAG 2.2 Level AA**: https://www.w3.org/WAI/WCAG22/quickref/
9. **UK GDPR**: https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/
10. **Welsh Language Act 1993**: https://www.legislation.gov.uk/ukpga/1993/38/contents

Vendors must review all standards and demonstrate compliance in proposals.

### Appendix D: GOV.UK Design System

**GOV.UK Design System**: https://design-system.service.gov.uk/

All frontend components must use GOV.UK Design System (gov.uk-frontend library). This ensures:
- Consistent UX with GOV.UK
- WCAG 2.2 AA accessibility compliance out-of-the-box
- Responsive design for mobile, tablet, desktop
- Browser compatibility (Chrome, Firefox, Safari, Edge - last 2 versions)

Vendors must demonstrate familiarity with GOV.UK Design System and provide examples of previous projects using it.

### Appendix E: Integration Specifications

**Government Gateway**:
- OAuth 2.0 Authorization Code flow
- Scopes: `openid`, `profile`, `email`, `tax_records`
- Documentation: Available upon NDA signature and contract award

**HMRC Backend APIs**:
- Tax Records API (Self Assessment, PAYE)
- National Insurance API
- API specifications: Available upon contract award
- Sandbox environment provided for development and testing

**HMRC Content Management System**:
- RESTful API for knowledge base ingestion
- Webhook support for real-time content updates
- API specifications: Available upon contract award

**HMRC ServiceNow**:
- Incident creation API for human escalation
- Documentation: Available upon contract award

**AWS Bedrock**:
- Claude 3.5 Sonnet LLM via AWS Bedrock API (eu-west-2 region)
- Documentation: https://docs.aws.amazon.com/bedrock/

### Appendix F: Glossary

- **ATRS**: Algorithmic Transparency Recording Standard (HMG requirement for AI systems)
- **BPSS**: Baseline Personnel Security Standard (background check for government contractors)
- **C4 Model**: Context, Container, Component, Code diagrams (architecture visualization)
- **CHECK**: NCSC scheme for approved penetration testing suppliers
- **DLD**: Detailed Level Design
- **DPIA**: Data Protection Impact Assessment (UK GDPR requirement for high-risk processing)
- **EqIA**: Equality Impact Assessment (Equality Act 2010 requirement)
- **FinOps**: Financial operations for cloud cost management
- **GDS**: Government Digital Service
- **Government Gateway**: HMRC authentication system for citizens
- **HLD**: High-Level Design
- **HMG**: His Majesty's Government
- **NDA**: Non-Disclosure Agreement
- **NCSC**: National Cyber Security Centre
- **NLU**: Natural Language Understanding
- **NPS**: Net Promoter Score (citizen satisfaction metric)
- **PII**: Personally Identifiable Information
- **RAG**: Retrieval-Augmented Generation (AI architecture pattern for grounding LLM responses)
- **RPO/RTO**: Recovery Point Objective / Recovery Time Objective (disaster recovery metrics)
- **SAST/DAST**: Static Application Security Testing / Dynamic Application Security Testing
- **SLI/SLO/SLA**: Service Level Indicator / Objective / Agreement
- **SOW**: Statement of Work
- **SRO**: Senior Responsible Officer (executive sponsor for government projects)
- **TCO**: Total Cost of Ownership
- **UAT**: User Acceptance Testing
- **WCAG**: Web Content Accessibility Guidelines
- **Zero Trust**: Security model assuming breach, no implicit trust

### Appendix G: HMRC Contact Information

**Procurement Lead**:
procurement-chatbot@hmrc.gov.uk
HMRC Digital Services
10 South Colonnade
London E14 4PU

**Questions Submission**:
Email: procurement-chatbot@hmrc.gov.uk
Subject: "HMRC ChatBot RFP Question - [VENDOR_NAME]"
Deadline: 2025-10-28

**Proposal Submission**:
Email: procurement-chatbot@hmrc.gov.uk
Subject: "HMRC ChatBot RFP Response - [VENDOR_NAME]"
Deadline: 2025-12-09, 5:00 PM GMT

---

## 11. Questions and Vendor Communication

### Questions Process

All questions regarding this SOW/RFP must be submitted in writing to ensure fairness to all vendors.

**Email**: procurement-chatbot@hmrc.gov.uk
**Subject Line**: `HMRC ChatBot RFP Question - [VENDOR_NAME]`
**Deadline for Questions**: **2025-10-28** (2 weeks after RFP issue)

**Question Format**:
- **Section Reference**: Specify section number (e.g., "Section 6.3 - Approved Technology Stack")
- **Question**: Clear, specific question
- **Context**: Rationale or background for question (optional)

**Example**:
```
Section Reference: 6.3 - Approved Technology Stack
Question: Is Azure OpenAI Service acceptable as an alternative to AWS Bedrock for LLM hosting, given Azure UK South region provides UK data residency?
Context: Our team has deep expertise with Azure OpenAI Service and can demonstrate equivalent UK data residency guarantees.
```

**Answers Published**: All questions and answers will be published to **all vendors** by **2025-11-04** (3 weeks after RFP issue)
- Vendor names anonymized (e.g., "Vendor A asked...")
- Answers binding on HMRC and incorporated into SOW as amendments if necessary

**Important Notes**:
- Do NOT include proprietary or confidential information in questions (all Q&A visible to competitors)
- No private communications with HMRC procurement team during RFP period (all questions via email)
- Vendors may NOT contact HMRC technical staff directly during RFP period (grounds for disqualification)

### Contact Information

**Primary Contact** (Procurement):
Email: procurement-chatbot@hmrc.gov.uk
Phone: (Available after contract award for operational matters)

**HMRC Digital Services**:
10 South Colonnade
London E14 4PU
United Kingdom

---

## Document Control

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | 2025-10-07 | HMRC Enterprise Architecture Team | Initial draft |
| 0.2 | 2025-10-10 | HMRC Procurement + EA Team | Stakeholder review feedback incorporated |
| 1.0 | 2025-10-14 | HMRC Procurement Lead | **Issued to vendors via G-Cloud 14** |

## Approvals

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Executive Sponsor (SRO) | [TBD] | _________ | [PENDING] |
| Procurement Lead | [TBD] | _________ | [PENDING] |
| Enterprise Architect | [TBD] | _________ | [PENDING] |
| HMRC CISO | [TBD] | _________ | [PENDING] |
| Legal Review | [TBD] | _________ | [PENDING] |
| Data Protection Officer | [TBD] | _________ | [PENDING] |

---

**END OF STATEMENT OF WORK**

---

**IMPORTANT NOTES FOR VENDORS**:

1. **Read Full Requirements**: This SOW references detailed requirements in `projects/001-hmrc-chatbot/requirements.md`. Vendors MUST review full requirements document.

2. **Architecture Principles Compliance**: All proposals must demonstrate compliance with 17 HMRC Architecture Principles (`.arckit/memory/architecture-principles.md`). Non-negotiable principles: #3 (Security), #4 (Accessibility), #5 (Responsible AI), #7 (Data Sovereignty).

3. **Mandatory Qualifications**: Failure to provide evidence of MQ-1 through MQ-7 = automatic disqualification.

4. **Separate Cost Proposal**: Cost proposal MUST be in separate PDF. Cost will not be reviewed until after technical evaluation and shortlisting.

5. **UK Data Residency**: All citizen data MUST remain in UK (AWS eu-west-2 London). No exceptions.

6. **WCAG 2.2 AA**: Legal requirement. Zero critical/high accessibility issues accepted.

7. **ATRS Publication**: Vendor must create ATRS record for publication on GOV.UK before Private Beta.

8. **GDS Service Standard**: Service must pass GDS Live Assessment (18 criteria) before public launch.

9. **Fixed Price Preferred**: HMRC prefers fixed price contracts with milestone-based payments to manage budget risk.

10. **Questions Deadline**: 2025-10-28. All questions answered publicly by 2025-11-04.

11. **Proposal Deadline**: 2025-12-09, 5:00 PM GMT. Late proposals will NOT be accepted.

**Good luck with your proposal!**
