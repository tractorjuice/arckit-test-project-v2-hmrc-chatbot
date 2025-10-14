# HMRC ChatBot Enterprise Architecture Principles

**Document Type**: Architectural Governance
**Version**: 1.0
**Effective Date**: 2025-10-14
**Last Updated**: 2025-10-14
**Owner**: Enterprise Architecture Team
**Status**: DRAFT
**Project**: HMRC ChatBot System

---

## Executive Summary

This document establishes the immutable principles governing all technology architecture decisions for the HMRC ChatBot system. These principles ensure compliance with UK Government technology standards, security requirements, accessibility mandates, and AI governance frameworks while delivering secure, reliable, and user-centric tax advisory services to UK citizens.

**Scope**: HMRC ChatBot system and all supporting infrastructure
**Authority**: Government Digital Service (GDS) and HMRC Architecture Review Board
**Compliance**: Mandatory unless exception approved by HMRC Chief Technology Officer
**Regulatory Context**: UK GDPR, Technology Code of Practice, Service Standard, AI Playbook, WCAG 2.2 AA, Algorithmic Transparency Standard

---

## I. Strategic Principles

### 1. Government Cloud-First Architecture

**Principle Statement**:
All new solutions MUST leverage approved UK Government cloud services (GOV.UK PaaS, AWS GovCloud UK, Azure UK Government) unless a documented exception is approved by the Cloud Centre of Excellence. On-premises deployment is prohibited except for OFFICIAL-SENSITIVE data requiring specific controls.

**Rationale**:
The UK Government Technology Code of Practice mandates cloud-first for agility, cost efficiency, and security. The ChatBot must scale elastically to handle citizen demand (peak during tax deadline seasons) and maintain resilience during service disruptions.

**Implications**:
- Prefer managed services over self-hosted alternatives
- Design for horizontal scalability and distributed systems
- Leverage cloud provider primitives (serverless, managed databases, queues)
- Plan for multi-region deployment within UK data sovereignty boundaries
- Use UK regions only (London, Cardiff) for all data processing and storage

**Approved Providers**:
- **Primary**: AWS UK regions (eu-west-2 London, eu-west-1 Ireland if approved)
- **Secondary**: Microsoft Azure UK South/UK West
- **GOV.UK PaaS**: For suitable workloads
- **Prohibited**: Non-UK regions, on-premises expansion, non-approved cloud providers

**Data Residency Requirements**:
- ALL citizen data MUST remain in UK sovereign territory
- Cross-border data transfers require Data Protection Impact Assessment (DPIA)
- Adherence to UK GDPR and Data Protection Act 2018

**Exceptions**:
- OFFICIAL-SENSITIVE data requiring specific on-premises controls (with NCSC approval)
- Legacy HMRC systems integration (documented migration plan required within 24 months)

**Validation Gates**:
- [ ] Solution deployed to UK cloud regions only
- [ ] Infrastructure-as-Code defined (Terraform preferred)
- [ ] Multi-availability zone strategy documented
- [ ] Cost model with HM Treasury FinOps tags defined
- [ ] Data residency compliance verified

---

### 2. API-First Integration with Government Gateway

**Principle Statement**:
All systems MUST expose functionality through well-defined, versioned APIs with OpenAPI 3.0+ specifications. Integration with HMRC backend systems MUST use Government Gateway authentication and approved integration patterns. Direct database access between domains is prohibited.

**Rationale**:
API-first design enables loose coupling, independent scaling, and clear service boundaries. Integration with HMRC's existing tax systems, National Insurance, and identity verification services requires standardized, secure APIs.

**Implications**:
- ChatBot exposes RESTful APIs for web, mobile, and voice channels
- OpenAPI 3.0+ specifications required before implementation
- No direct database connections across service boundaries
- Event-driven patterns for asynchronous HMRC backend integration
- Compliance with Government API standards (GDS API technical and data standards)

**Standards**:
- **REST APIs**: OpenAPI 3.0+, JSON payloads, HTTPS only (TLS 1.3+)
- **Authentication**: Government Gateway OAuth 2.0, GOV.UK Verify/One Login integration
- **Authorization**: Attribute-Based Access Control (ABAC) with citizen consent management
- **Rate Limiting**: Per-user quotas to prevent abuse (500 requests/hour per citizen)
- **Versioning**: URI versioning (e.g., /v1/chat, /v2/chat) with 12-month deprecation notice

**Government Gateway Integration**:
- Government Gateway authentication for user identity
- PDS (Personal Demographics Service) integration for citizen verification
- HMRC APIs for tax records, National Insurance, PAYE
- Real-time data retrieval (no caching of sensitive tax data)

**Exceptions**:
- Legacy HMRC system integration during 24-month migration period
- Batch data pipelines for training data (with anonymization and security review)

**Validation Gates**:
- [ ] OpenAPI specification approved by GDS API team
- [ ] Government Gateway integration tested
- [ ] Rate limiting and DDoS protection configured
- [ ] API versioning and deprecation strategy documented
- [ ] HMRC backend integration patterns approved

---

### 3. Security by Design - Zero Trust for Public Services (NON-NEGOTIABLE)

**Principle Statement**:
All architectures MUST implement Zero Trust security principles with defense-in-depth aligned to NCSC Cloud Security Principles and Cyber Essentials Plus. Security is NOT a feature to be added later—it is a foundational requirement. The ChatBot handles OFFICIAL-SENSITIVE data (citizen tax records, National Insurance numbers) and MUST meet HMG security standards.

**Rationale**:
HMRC is a high-value target for nation-state actors and cybercriminals. Citizen trust depends on impeccable security. The ChatBot must assume breach, eliminate implicit trust, and continuously verify all access requests.

**Zero Trust Pillars**:
1. **Identity-Based Access**: No network-based trust; every request authenticated
2. **Least Privilege**: Grant minimum necessary permissions, time-boxed where possible
3. **Encryption Everywhere**: Data encrypted in transit (TLS 1.3+) and at rest (AES-256 GCM)
4. **Continuous Verification**: Monitor, log, and analyze all access patterns
5. **Assume Breach**: Detect, contain, and respond to threats in real-time

**Mandatory Controls**:
- [ ] Multi-factor authentication (MFA) for all staff and administrative access
- [ ] Government Gateway authentication for all citizen access
- [ ] Service-to-service authentication (mutual TLS with AWS IAM roles or Azure Managed Identity)
- [ ] Secrets management via AWS Secrets Manager/Azure Key Vault (no hardcoded credentials)
- [ ] Network segmentation with micro-perimeters (VPC/VNet isolation)
- [ ] Encryption at rest for all data stores (citizen chat logs, tax data, training data)
- [ ] TLS 1.3+ for all network communication (TLS 1.2 minimum)
- [ ] Structured logging of all authentication/authorization events to SIEM
- [ ] Regular penetration testing by NCSC-approved CHECK teams (annual minimum)
- [ ] Vulnerability scanning (weekly automated, monthly manual review)
- [ ] Web Application Firewall (WAF) with OWASP Top 10 protection

**Compliance Frameworks**:
- **NCSC Cloud Security Principles**: All 14 principles MUST be addressed
- **Cyber Essentials Plus**: Mandatory for HMG systems
- **ISO 27001**: HMRC corporate requirement
- **UK GDPR**: Data protection by design and default
- **HMG Security Policy Framework (SPF)**

**Security Classifications**:
- **Citizen Identity Data**: OFFICIAL-SENSITIVE
- **Tax Records/National Insurance**: OFFICIAL-SENSITIVE
- **Chat Transcripts**: OFFICIAL (with PII redaction options)
- **Anonymized Training Data**: OFFICIAL
- **System Logs**: OFFICIAL

**Exceptions**:
- NONE. Security principles are non-negotiable.
- Specific control alternatives may be approved with compensating controls by HMRC CISO.

**Validation Gates**:
- [ ] Threat model completed using NCSC methodology
- [ ] Security controls mapped to NCSC Cloud Security Principles
- [ ] DPIA completed and approved by HMRC Data Protection Officer
- [ ] Penetration test plan with CHECK-approved supplier
- [ ] Incident response runbook integrated with HMRC Security Operations Centre (SOC)
- [ ] Cyber Essentials Plus certification obtained

---

### 4. Accessibility-First Design (Legal Requirement)

**Principle Statement**:
The ChatBot MUST comply with WCAG 2.2 Level AA as mandated by the Public Sector Bodies (Websites and Mobile Applications) Accessibility Regulations 2018. Accessibility is NOT optional—it is a legal and moral imperative to serve all UK citizens.

**Rationale**:
13.9 million people in the UK have a disability. HMRC serves all citizens regardless of ability. Non-compliance violates the Equality Act 2010 and excludes vulnerable taxpayers from essential services.

**WCAG 2.2 AA Requirements** (MANDATORY):
- **Perceivable**: Text alternatives for non-text content, captions for audio
- **Operable**: Keyboard navigation, no time limits for complex interactions
- **Understandable**: Clear language (Plain English standard), predictable navigation
- **Robust**: Compatible with assistive technologies (screen readers, voice control)

**Design Implications**:
- Text-based chat interface with clear visual hierarchy
- Voice interface option for citizens with visual impairments or reading difficulties
- Screen reader compatibility (ARIA labels, semantic HTML)
- Keyboard-only navigation (no mouse required)
- High contrast mode for visual impairments
- Timeout warnings with extensions for complex interactions (e.g., retrieving tax records)
- Plain English content aligned with GOV.UK style guide (average reading age 9)
- Multi-language support (English, Welsh as legal requirement per Welsh Language Act 1993)

**Testing Requirements**:
- Automated accessibility testing in CI/CD (axe-core, Pa11y)
- Manual testing with assistive technologies (JAWS, NVDA, VoiceOver)
- User testing with disabled citizens (minimum 5 participants per user research round)
- Annual accessibility audit by accredited third party

**Accessibility Statement**:
- Public accessibility statement required by law (published on GOV.UK)
- Documented known issues and remediation timeline
- Feedback mechanism for accessibility issues

**Exceptions**:
- NONE. Accessibility is a legal requirement under UK law.

**Validation Gates**:
- [ ] WCAG 2.2 AA automated testing passed (zero critical/high issues)
- [ ] Manual accessibility testing with screen readers completed
- [ ] User testing with disabled citizens completed
- [ ] Accessibility statement published
- [ ] Welsh language support implemented
- [ ] Plain English content reviewed by content designer

---

### 5. Responsible AI and Algorithmic Transparency (NON-NEGOTIABLE)

**Principle Statement**:
The ChatBot's AI/ML components MUST adhere to the UK Government AI Playbook, Data Ethics Framework, and Algorithmic Transparency Recording Standard (ATRS). All AI decisions affecting citizens' tax obligations MUST be explainable, auditable, and subject to human oversight.

**Rationale**:
AI systems making tax guidance recommendations directly impact citizens' financial obligations and compliance. Bias, hallucinations, or unexplainable decisions undermine trust and may lead to incorrect tax submissions, penalties, or litigation. Responsible AI is essential for public service legitimacy.

**AI Governance Requirements** (MANDATORY):
- **Explainability**: Every AI response MUST be traceable to source policy/legislation
- **Human Oversight**: High-stakes decisions (e.g., tax liability calculations) require human review
- **Bias Mitigation**: Regular fairness testing across protected characteristics (age, gender, ethnicity, disability)
- **Model Transparency**: Document model architecture, training data, limitations in ATRS
- **Accuracy**: Ground AI responses in authoritative HMRC guidance and legislation
- **Safety**: Implement guardrails to prevent harmful or incorrect tax advice

**Algorithmic Transparency Recording Standard (ATRS)**:
- ATRS record MUST be published for the ChatBot AI system
- Document purpose, data sources, model type, accuracy metrics, bias testing
- Publish on GOV.UK with updates when model changes
- Include contact for algorithmic accountability

**AI Ethics Principles** (aligned with UK Government Data Ethics Framework):
1. **Start with Clear User Need**: Solve genuine citizen problems (tax guidance complexity)
2. **Use Data and Tools Proportionately**: No excessive data collection or invasive profiling
3. **Be Alert to Bias**: Test for disparate impact on protected groups
4. **Be Transparent and Accountable**: Explain how AI makes decisions
5. **Embed Secure and Robust Practices**: Adversarial testing, prompt injection defense

**Responsible AI Design**:
- **Grounding in Authoritative Sources**: Retrieval-Augmented Generation (RAG) with HMRC knowledge base
- **Source Citation**: Every AI response cites relevant policy, legislation, or guidance document
- **Confidence Scoring**: Surface confidence levels; escalate low-confidence queries to human agents
- **Hallucination Detection**: Validate AI outputs against HMRC ground truth data
- **Human-in-the-Loop**: Human review for queries involving complex tax situations, appeals, or disputes
- **Guardrails**: Block responses involving tax avoidance schemes, illegal advice, or PII exposure

**Model Training and Data**:
- Training data MUST exclude PII unless anonymized and legally justified
- Use synthetic data for training where possible
- Document data lineage from source to model
- Regular retraining with updated HMRC guidance (quarterly minimum)

**Bias and Fairness Testing**:
- Test for disparate impact across age, gender, ethnicity, disability, geography, socioeconomic status
- Monitor response quality across user demographics
- Quarterly fairness audits with public reporting

**Safety and Security**:
- Prompt injection defenses (input sanitization, output validation)
- Adversarial testing for jailbreak attempts
- Rate limiting to prevent API abuse
- Monitor for toxic/harmful outputs

**Exceptions**:
- NONE. Responsible AI principles are mandatory for public sector AI systems.

**Validation Gates**:
- [ ] ATRS record completed and approved by HMRC Data Ethics Committee
- [ ] Model explainability tested (source citation for 100% of responses)
- [ ] Bias testing completed with report published
- [ ] Human oversight procedures documented and trained
- [ ] Guardrails tested (adversarial testing, prompt injection defense)
- [ ] Data Ethics Framework alignment verified
- [ ] Public transparency report published

---

### 6. Observability and Operational Excellence

**Principle Statement**:
All systems MUST emit structured telemetry (logs, metrics, traces) enabling real-time monitoring, troubleshooting, and capacity planning. Observability is a first-class architectural requirement for operating a citizen-facing public service with high availability targets.

**Rationale**:
The ChatBot must maintain 99.9% uptime during business hours (08:00-20:00 GMT). Citizen trust depends on reliable, responsive service. Observability enables proactive issue detection, rapid incident response, and continuous improvement.

**Telemetry Standards**:
- **Logging**: Structured JSON logs to centralized SIEM (Splunk, ELK stack)
- **Metrics**: Prometheus-compatible exposition, RED metrics (Rate, Errors, Duration)
- **Tracing**: OpenTelemetry instrumentation, distributed trace context propagation
- **Alerting**: SLO-based alerting with actionable runbooks

**Required Metrics**:
- Request volume, latency (p50, p95, p99), error rate per endpoint
- AI response time and quality (citizen satisfaction scores)
- Government Gateway authentication success/failure rates
- HMRC backend API integration latency and availability
- Resource utilization (CPU, memory, I/O)
- Business metrics (conversations/hour, escalation rate to human agents)
- Security events (auth failures, rate limit violations, prompt injection attempts)

**Service Level Objectives (SLOs)**:
- **Availability**: 99.9% during business hours (08:00-20:00 GMT Mon-Fri)
- **Latency**: p95 response time <2 seconds for chat messages
- **Error Rate**: <0.1% of requests result in 5xx errors
- **AI Accuracy**: >95% of responses marked helpful by citizens (user feedback)

**Log Retention** (aligned with HMG records management):
- **Security logs**: 7 years (HMG standard)
- **Audit logs (citizen interactions)**: 7 years (tax records retention requirement)
- **Application logs**: 90 days
- **Chat transcripts**: 7 years (with PII redaction options, citizen consent required)

**Incident Management**:
- Integration with HMRC ServiceNow for incident ticketing
- Escalation to HMRC SOC for security incidents
- Runbooks for common failure scenarios (API outage, model degradation, DDoS attack)
- Post-incident reviews (PIR) within 5 working days

**Exceptions**:
- Prototype/PoC systems (documented as non-production, no citizen data)

**Validation Gates**:
- [ ] Logging, metrics, tracing instrumented
- [ ] Dashboards configured in HMRC monitoring platform
- [ ] SLOs/SLIs defined with error budgets
- [ ] Alerts configured with runbooks for on-call team
- [ ] Integration with HMRC SOC and ServiceNow tested
- [ ] Incident response procedures documented and trained

---

## II. Data Principles

### 7. Data Sovereignty and UK GDPR Compliance (NON-NEGOTIABLE)

**Principle Statement**:
All citizen data MUST remain in UK sovereign territory and comply with UK GDPR, Data Protection Act 2018, and HMG Information Assurance standards. Data classification, residency, retention, and access controls are NON-NEGOTIABLE requirements.

**Data Classification** (Government Security Classifications):
1. **OFFICIAL-SENSITIVE**: Tax records, National Insurance numbers, Government Gateway credentials, financial data
2. **OFFICIAL**: Chat transcripts (with PII), system logs (with identifiable data), training data (before anonymization)
3. **Public**: HMRC public guidance, tax thresholds, generic FAQs

**Data Residency Requirements**:
- ALL citizen data MUST be processed and stored in UK regions (AWS eu-west-2, Azure UK South)
- NO cross-border data transfers unless legally justified with Standard Contractual Clauses (SCCs) and DPIA
- Data processors MUST be UK-based or approved for HMG contracts

**UK GDPR Compliance**:
- **Lawful Basis**: Public task (HMRC's legal obligation to collect taxes and provide guidance)
- **Data Minimization**: Collect only data necessary for tax guidance (no excessive profiling)
- **Purpose Limitation**: Use data ONLY for tax guidance; no secondary uses without consent
- **Citizen Rights**: Right to access, rectification, erasure, portability, objection
- **Data Protection by Design**: Privacy-enhancing technologies, PII redaction, anonymization

**Retention Policies**:
- **Chat transcripts**: 7 years (aligned with tax records retention), then automatic deletion
- **Anonymized training data**: 10 years for AI model improvement
- **Audit logs**: 7 years (HMG requirement)
- **Backups**: 90 days, encrypted, UK-only storage

**Citizen Consent and Control**:
- Explicit consent for chat transcript storage (opt-in, not opt-out)
- Clear privacy notice before chat session (link to full privacy policy on GOV.UK)
- Citizen can request chat transcript deletion (subject to legal retention requirements)
- Consent withdrawal mechanism (via GOV.UK account)

**Data Protection Impact Assessment (DPIA)**:
- DPIA required before launch (mandatory for high-risk processing under UK GDPR)
- Annual DPIA reviews for system changes
- Approval by HMRC Data Protection Officer
- Summary published on GOV.UK (redacted sensitive details)

**Data Sharing**:
- NO data sharing with third parties without legal gateway
- HMRC internal sharing only (e.g., fraud investigation, compliance) with audit trail
- Anonymized data sharing for research requires Data Ethics Committee approval

**Exceptions**:
- NONE. Data protection is a legal requirement under UK GDPR and Data Protection Act 2018.

**Validation Gates**:
- [ ] All data processing in UK regions verified
- [ ] DPIA completed and approved by DPO
- [ ] Data classification applied to all datasets
- [ ] Retention policies configured with automated deletion
- [ ] Citizen consent flows implemented
- [ ] Data subject rights procedures documented
- [ ] Privacy notice published on GOV.UK

---

### 8. Data Quality and Accuracy for Tax Guidance

**Principle Statement**:
The ChatBot's knowledge base MUST reflect current, accurate HMRC guidance and UK tax legislation. Data pipelines MUST maintain data quality standards and provide end-to-end lineage for auditability. Inaccurate tax advice exposes citizens to penalties and damages HMRC credibility.

**Quality Standards**:
- **Accuracy**: All guidance MUST match official HMRC publications and legislation (100% accuracy requirement)
- **Completeness**: Cover all common tax scenarios (Self Assessment, PAYE, VAT, Capital Gains, Inheritance Tax)
- **Timeliness**: Update knowledge base within 48 hours of policy changes (e.g., Budget announcements)
- **Consistency**: No conflicting guidance across channels (ChatBot, GOV.UK, helpline)

**Knowledge Base Management**:
- Single source of truth: HMRC content management system
- Version control for all guidance documents (Git-based)
- Review and approval workflow (content designers, tax policy experts)
- Automated ingestion pipeline from HMRC CMS to ChatBot knowledge base
- Quarterly content audits for accuracy and completeness

**Lineage Requirements**:
- Every AI response MUST cite source document (HMRC guidance, legislation section)
- Track lineage from legislation → policy → guidance → knowledge base → AI response
- Audit trail for all content updates (who, what, when, why)
- Impact analysis for legislative changes (which guidance needs updating)

**Validation and Testing**:
- Automated testing of AI responses against HMRC ground truth dataset (1000+ test queries)
- Monthly accuracy reviews by tax policy experts
- Citizen feedback loop (thumbs up/down, "Was this helpful?")
- A/B testing for response quality improvements

**Exceptions**:
- NONE. Accuracy of tax guidance is non-negotiable.

**Validation Gates**:
- [ ] Knowledge base sourced from HMRC authoritative content
- [ ] Automated ingestion pipeline tested and monitored
- [ ] Source citation implemented for 100% of AI responses
- [ ] Accuracy testing framework with 1000+ ground truth queries
- [ ] Quarterly content audit process documented
- [ ] Citizen feedback mechanism integrated

---

## III. Technology Standards

### 9. Approved Technology Stack (Government Aligned)

**Principle Statement**:
Technology choices MUST align with GDS technology standards, HMRC approved technologies, and HMG security requirements. This ensures supportability, security, talent availability, and value for money.

**Programming Languages** (in order of preference):
1. **Backend/AI**: Python 3.11+ (AI/ML libraries: LangChain, Hugging Face, OpenAI SDK)
2. **API Services**: Node.js/TypeScript 20+, Go 1.21+ (for high-performance services)
3. **Frontend**: TypeScript/React 18+, GOV.UK Design System components
4. **Infrastructure**: Terraform (HCL), Python (AWS CDK/Boto3)

**AI/ML Frameworks**:
- **LLM Orchestration**: LangChain, LlamaIndex (for RAG architecture)
- **Model Serving**: AWS Bedrock (Claude 3.5 Sonnet), Azure OpenAI Service (GPT-4)
- **Embedding Models**: AWS Titan Embeddings, OpenAI text-embedding-3
- **Vector Database**: AWS OpenSearch with vector search, Pinecone (if approved)
- **Guardrails**: AWS Bedrock Guardrails, custom content filters

**Databases**:
- **Relational**: Amazon RDS PostgreSQL 15+ (citizen profiles, audit logs)
- **Vector Store**: Amazon OpenSearch with k-NN plugin (knowledge base embeddings)
- **Cache**: Amazon ElastiCache (Redis 7+) for session management
- **Document Store**: Amazon S3 (chat transcripts, encrypted at rest)

**Messaging/Streaming**:
- **Event Bus**: Amazon EventBridge (for HMRC backend integration events)
- **Queuing**: Amazon SQS (for async processing, human escalation queue)
- **Streaming**: Amazon Kinesis (for real-time analytics, audit logs)

**API and Integration**:
- **API Gateway**: AWS API Gateway (REST and WebSocket for real-time chat)
- **Authentication**: AWS Cognito (Government Gateway integration)
- **Service Mesh**: AWS App Mesh (for microservices communication)

**Frontend**:
- **Framework**: React 18+ with TypeScript
- **Design System**: GOV.UK Design System (mandatory for consistency with GOV.UK)
- **Accessibility**: gov.uk-frontend components (WCAG 2.2 AA compliant)
- **Hosting**: AWS Amplify or CloudFront + S3

**Infrastructure**:
- **Container Orchestration**: Amazon ECS Fargate (serverless containers)
- **Serverless**: AWS Lambda (for event-driven tasks, API endpoints)
- **IaC**: Terraform (preferred), AWS CDK (TypeScript/Python)

**Security Tools**:
- **Secrets Management**: AWS Secrets Manager
- **WAF**: AWS WAF with OWASP Top 10 rules
- **DDoS Protection**: AWS Shield Advanced
- **SIEM**: Integration with HMRC Splunk instance
- **Vulnerability Scanning**: AWS Inspector, Snyk (for dependencies)

**Exceptions**:
- Proof-of-concept systems (time-boxed, max 3 months, no citizen data)
- Specialized use cases requiring HMRC CISO approval
- Legacy system integration (documented in integration patterns)

**Validation Gates**:
- [ ] Technology choices from approved list OR exception documented
- [ ] Rationale for choices linked to requirements
- [ ] AWS UK region usage confirmed
- [ ] GOV.UK Design System components used
- [ ] Support and maintenance plan defined

---

### 10. Infrastructure as Code and GitOps (MANDATORY)

**Principle Statement**:
ALL infrastructure MUST be defined as code, version-controlled in Git, and deployed via CI/CD pipelines. Manual infrastructure changes are prohibited in production. This ensures repeatability, auditability, and compliance with HMG change management requirements.

**IaC Standards**:
- **Primary Tool**: Terraform (HCL) with remote state in AWS S3 + DynamoDB locking
- **Version Control**: Git (GitHub with HMRC organization, or AWS CodeCommit for OFFICIAL-SENSITIVE)
- **State Management**: Remote state with encryption at rest, state locking enabled
- **Secrets**: Never committed to code; use AWS Secrets Manager with dynamic references

**Deployment Requirements**:
- Automated deployment via AWS CodePipeline or GitHub Actions (approved for HMG use)
- Environment parity (dev, staging, prod) with identical IaC
- Immutable infrastructure (replace, don't modify)
- Rollback capability within 5 minutes (blue/green or canary deployments)

**Change Management**:
- All production changes via pull request with Architecture Review Board approval
- Peer review required (minimum 2 approvers for production changes)
- Automated testing of IaC (terraform plan, terraform validate, tfsec for security scanning)
- Change records logged in HMRC ServiceNow for audit compliance

**Exceptions**:
- Emergency hotfixes (with post-incident IaC update required within 24 hours and PIR)

**Validation Gates**:
- [ ] Infrastructure defined in Terraform with modules
- [ ] CI/CD pipeline configured with approval gates for production
- [ ] Secrets managed via AWS Secrets Manager (no hardcoded secrets)
- [ ] State file encrypted and access-controlled
- [ ] Rollback procedure tested in staging
- [ ] Change management integration with ServiceNow

---

## IV. Architecture Patterns

### 11. Microservices with Domain-Driven Design

**Principle Statement**:
The ChatBot solution SHOULD decompose along business domain boundaries using microservices patterns. Domains include: Citizen Identity, Conversational AI, Knowledge Management, HMRC Integration, Audit & Compliance.

**Bounded Contexts** (DDD):
1. **Citizen Identity Context**: Government Gateway authentication, profile management
2. **Conversational AI Context**: NLU, dialogue management, LLM orchestration
3. **Knowledge Management Context**: Content ingestion, vector search, source citation
4. **HMRC Integration Context**: Backend API integration (tax records, National Insurance)
5. **Audit & Compliance Context**: Logging, monitoring, ATRS reporting

**Design Guidelines**:
- One service per bounded context
- Database per service (no shared databases)
- Async communication via EventBridge/SQS (preferred over sync REST calls)
- API Gateway as single entry point for frontend
- Saga pattern for distributed transactions (e.g., multi-step tax guidance workflows)

**Service Communication**:
- **Synchronous**: REST APIs for user-facing operations (chat messages)
- **Asynchronous**: Events for backend integration (e.g., HMRC data retrieval), audit logging

**Validation Gates**:
- [ ] Bounded contexts identified and documented in C4 diagrams
- [ ] Service boundaries align with domain model
- [ ] Inter-service communication patterns defined (sync vs async)
- [ ] Data consistency strategy documented (eventual consistency for non-critical data)

---

### 12. Retrieval-Augmented Generation (RAG) for AI Accuracy

**Principle Statement**:
The ChatBot MUST use Retrieval-Augmented Generation (RAG) architecture to ground AI responses in authoritative HMRC guidance and legislation. LLMs MUST NOT generate tax advice from parametric memory alone—all responses grounded in retrieved documents.

**RAG Architecture**:
1. **Knowledge Base**: HMRC guidance documents, tax legislation, FAQs (stored as embeddings in vector database)
2. **Retrieval**: Semantic search to retrieve top-k relevant documents for citizen query
3. **Augmentation**: Pass retrieved documents as context to LLM
4. **Generation**: LLM generates response grounded in retrieved documents with source citations
5. **Validation**: Post-processing to verify factual accuracy and flag low-confidence responses

**Implementation**:
- **Embedding Model**: AWS Titan Embeddings or OpenAI text-embedding-3-large
- **Vector Database**: Amazon OpenSearch with k-NN plugin (UK region)
- **LLM**: AWS Bedrock Claude 3.5 Sonnet (via AWS UK region with data residency guarantees)
- **Orchestration**: LangChain or LlamaIndex for RAG pipeline
- **Source Citation**: Extract document references from retrieved context and surface to citizen

**Quality Assurance**:
- Evaluate retrieval quality (precision@k, recall@k) monthly
- Evaluate generation quality (factual consistency, helpfulness) via citizen feedback
- Human-in-the-loop review for complex queries (escalation threshold: confidence <70%)

**Exceptions**:
- NONE. RAG is mandatory for grounding AI responses in authoritative sources.

**Validation Gates**:
- [ ] RAG architecture implemented with retrieval + generation pipeline
- [ ] Knowledge base populated with HMRC authoritative content
- [ ] Source citation implemented for 100% of responses
- [ ] Retrieval quality metrics tracked (precision, recall)
- [ ] Human escalation threshold configured

---

### 13. Resilience and Fault Tolerance (High Availability)

**Principle Statement**:
The ChatBot MUST be designed to gracefully handle failures. Assume dependencies (Government Gateway, HMRC APIs, LLM providers) will fail; plan accordingly. Citizens must receive service even during partial outages.

**Resilience Patterns** (MANDATORY):
- **Circuit Breaker**: Prevent cascade failures when HMRC backend APIs fail
- **Retry with Exponential Backoff**: Transient fault handling (3 retries max)
- **Timeout**: Every network call must have timeout (5 seconds for API calls, 30 seconds for LLM generation)
- **Bulkhead**: Isolate resources to limit blast radius (separate thread pools for critical paths)
- **Graceful Degradation**: Fallback to cached guidance if HMRC APIs unavailable
- **Rate Limiting**: Protect from overload (500 requests/hour per citizen, 10,000 requests/hour system-wide)

**Availability Targets**:
- **Critical Systems (Chat API, Auth)**: 99.9% during business hours (08:00-20:00 GMT Mon-Fri)
- **HMRC Backend Integration**: 99.5% (external dependency)
- **Non-Critical (Analytics)**: 99% (best-effort)

**Disaster Recovery**:
- **RPO (Recovery Point Objective)**: 1 hour (max acceptable data loss)
- **RTO (Recovery Time Objective)**: 15 minutes (max acceptable downtime)
- **Automated backups**: Daily snapshots of databases, encrypted, stored in secondary UK region
- **Multi-AZ deployment**: Services deployed across multiple AWS Availability Zones in eu-west-2
- **Failover testing**: Quarterly disaster recovery drills

**Chaos Engineering**:
- Quarterly chaos experiments (simulate AZ failure, API outage, LLM degradation)
- GameDays to test incident response and recovery procedures

**Validation Gates**:
- [ ] Failure modes analyzed (FMEA)
- [ ] Resilience patterns implemented (circuit breaker, retries, timeouts)
- [ ] RPO/RTO defined and tested
- [ ] Multi-AZ deployment verified
- [ ] Chaos engineering experiments scheduled
- [ ] Disaster recovery runbook documented

---

## V. Development Practices

### 14. Continuous Integration / Continuous Deployment (CI/CD)

**Principle Statement**:
All code changes MUST flow through automated CI/CD pipelines with quality gates before reaching production. This ensures security, quality, and compliance with HMG change management.

**Pipeline Stages** (MANDATORY):
1. **Build**: Compile, dependency resolution (Python, Node.js, Terraform)
2. **Test**: Unit, integration, contract tests (minimum 80% coverage)
3. **Security Scan**:
   - SAST (Semgrep, SonarQube)
   - Dependency vulnerability checks (Snyk, AWS Inspector)
   - IaC security (tfsec, Checkov)
   - Secrets detection (git-secrets, TruffleHog)
4. **Artifact**: Immutable artifact creation (Docker image, Lambda ZIP, Terraform plan)
5. **Deploy to Dev**: Automated deployment to development environment
6. **Deploy to Staging**: Automated deployment to staging environment
7. **Smoke Tests**: Basic health checks, API contract tests, accessibility tests
8. **Approval Gate**: Manual approval by Architecture Review Board for production
9. **Deploy to Production**: Blue/green deployment with canary testing (10% traffic → 100%)
10. **Monitoring**: Automated rollback on SLO violation (error rate >0.5%, latency >3s)

**Quality Gates**:
- Code coverage ≥80% (unit tests)
- No critical/high security vulnerabilities (block deployment)
- Static analysis passing (pylint, eslint, tfsec)
- Accessibility tests passing (WCAG 2.2 AA, zero critical issues)
- AI accuracy tests passing (>95% accuracy on ground truth dataset)

**Approval Requirements**:
- Development → Staging: Automated (post successful tests)
- Staging → Production: Manual approval by 2 reviewers (Architecture Review Board + HMRC CISO delegate)

**Rollback**:
- Automated rollback if SLO violated within 15 minutes of deployment
- Manual rollback capability within 5 minutes

**Validation Gates**:
- [ ] CI/CD pipeline configured end-to-end (build → test → deploy)
- [ ] Quality gates enforced at each stage
- [ ] Security scanning integrated (SAST, dependency checks)
- [ ] Approval gates configured for production
- [ ] Rollback procedure automated and tested
- [ ] Deployment metrics tracked (lead time, deployment frequency, MTTR)

---

### 15. Testing Strategy (Comprehensive)

**Principle Statement**:
Testing is NOT optional. Test automation MUST be comprehensive across unit, integration, contract, accessibility, and AI quality levels. The ChatBot must meet rigorous quality standards before serving UK citizens.

**Test Pyramid**:
1. **Unit Tests** (70%): Fast, isolated, deterministic (Jest, pytest)
2. **Integration Tests** (20%): Component interactions, real dependencies (Testcontainers, mocks for HMRC APIs)
3. **Contract Tests** (5%): API contract compliance with HMRC backend APIs (Pact)
4. **End-to-End Tests** (5%): Critical user journeys (Playwright, Cypress)

**AI-Specific Testing**:
- **Accuracy Testing**: 1000+ ground truth queries with expected answers (>95% accuracy required)
- **Bias Testing**: Evaluate fairness across demographics (age, gender, ethnicity, disability)
- **Adversarial Testing**: Prompt injection, jailbreak attempts, toxic input handling
- **Hallucination Detection**: Validate AI outputs against HMRC ground truth data

**Non-Functional Testing**:
- **Performance**: Load testing for peak demand (10,000 concurrent users, k6 or Locust)
- **Security**: SAST/DAST, penetration testing by CHECK-approved supplier (annual)
- **Accessibility**: Automated (axe-core, Pa11y) + manual (assistive technology testing)
- **Chaos Engineering**: Failure injection to validate resilience (quarterly)

**Coverage Requirements**:
- Unit test coverage: ≥80%
- Critical paths (authentication, AI generation, HMRC integration): 100% coverage
- Contract tests: All HMRC backend APIs
- Accessibility: WCAG 2.2 AA automated + manual tests

**User Acceptance Testing**:
- Private beta with 100 citizens (diverse demographics)
- Public beta with 10,000 citizens before full launch
- Citizen feedback loop (in-app surveys, helpfulness ratings)

**Validation Gates**:
- [ ] Test strategy documented per test level
- [ ] Coverage thresholds met (≥80% unit, 100% critical paths)
- [ ] AI accuracy tests passing (>95% on ground truth dataset)
- [ ] Bias testing completed with report published
- [ ] Accessibility tests passing (WCAG 2.2 AA)
- [ ] Performance baselines established (10,000 concurrent users)
- [ ] Security testing integrated in CI/CD (SAST, dependency scans)

---

## VI. Cost and Financial Governance

### 16. FinOps and Value for Money (HM Treasury Standards)

**Principle Statement**:
Every architectural decision has cost implications and must demonstrate value for money per HM Treasury Green Book principles. Solutions MUST be designed with cost efficiency in mind, and spending MUST be observable and attributable to budget holders.

**Cost Tagging Requirements** (MANDATORY):
- `project`: HMRC-ChatBot
- `environment`: dev | staging | prod
- `owner`: Team identifier (e.g., AI-Services-Team)
- `cost-center`: HMRC finance code
- `data-classification`: OFFICIAL | OFFICIAL-SENSITIVE
- `service`: Citizen-Identity | AI-Engine | Knowledge-Base | HMRC-Integration | Audit

**Cost Optimization Strategies**:
- Right-size resources (no over-provisioning; use AWS Compute Optimizer recommendations)
- Use AWS Savings Plans for predictable workloads (ECS Fargate, Lambda)
- Auto-scaling to match demand (scale down during off-hours, scale up during tax deadlines)
- Data lifecycle policies (hot → warm → cold → Glacier → deletion per retention policy)
- Monitor LLM API costs (token usage optimization, caching frequent queries)

**Budget Management**:
- Monthly cost reviews per service (target: <£50,000/month for full production service)
- Budget alerts at 80%, 100%, 120% thresholds via AWS Budgets
- Idle resource detection and remediation (weekly automated scans)
- Showback to HMRC business units (cost per conversation, cost per citizen served)

**Value for Money Assessment**:
- Compare cost vs. alternative channels (phone helpline cost: ~£5-10/call, ChatBot target: <£0.50/conversation)
- Measure cost savings from reduced helpline volume
- Track cost per successful tax guidance interaction

**Validation Gates**:
- [ ] All resources tagged per HM Treasury policy
- [ ] Cost estimates documented in design (monthly operational cost, 5-year TCO)
- [ ] Auto-scaling configured for elastic workloads
- [ ] Budget alerts configured in AWS Budgets
- [ ] Value for money analysis documented (cost vs. helpline alternative)

---

## VII. Compliance and Audit

### 17. Audit Logging and Traceability (HMG Records Management)

**Principle Statement**:
All access to citizen data and all privileged operations MUST be logged immutably for compliance, forensic analysis, and HMG records management requirements. The ChatBot handles sensitive tax data and requires comprehensive audit trails.

**Audit Log Requirements** (W5H1):
- **Who**: User or service identity (Government Gateway ID, AWS IAM role)
- **What**: Action performed (CRUD operation, data access, configuration change)
- **When**: Timestamp (UTC, millisecond precision)
- **Where**: System/service component (API Gateway, Lambda, RDS)
- **Why**: Context (API request ID, conversation ID, session ID)
- **Result**: Success or failure with error details

**Audit Events** (MANDATORY):
- Citizen authentication (Government Gateway login/logout)
- Chat conversation start/end with conversation ID
- HMRC backend API calls (tax record retrieval, National Insurance lookup)
- PII data access (citizen profile, tax records)
- Administrative actions (configuration changes, user management)
- Security events (authentication failures, rate limit violations, prompt injection attempts)
- AI model inference (query, response, confidence score, source citations)

**Log Retention** (HMG Records Management):
- **Audit logs (citizen interactions)**: 7 years (tax records retention requirement)
- **Security logs**: 7 years (HMG standard)
- **Application logs**: 90 days
- **Chat transcripts**: 7 years (with citizen consent, encrypted, PII redaction options)

**Immutable Storage**:
- Write-once-read-many (WORM) storage for compliance (S3 Object Lock with Governance mode)
- Tamper-evident logging (cryptographic hashing, AWS CloudTrail log file validation)

**SIEM Integration**:
- Real-time streaming to HMRC Splunk instance
- Alerts for security anomalies (authentication failures, unusual access patterns)
- Integration with HMRC Security Operations Centre (SOC)

**Validation Gates**:
- [ ] Audit logging implemented for all sensitive operations
- [ ] Log integrity ensured (S3 Object Lock, CloudTrail validation)
- [ ] Retention policies configured (7 years for audit logs)
- [ ] SIEM integration tested (real-time streaming to HMRC Splunk)
- [ ] Audit log queries tested (demonstrate ability to answer "Who accessed what data when?")

---

## VIII. Exception Process

### Exception Request Procedure

Exceptions to these principles require documented justification and formal approval per HMG governance standards.

**Exception Request Must Include**:
1. **Principle Being Violated**: Specific principle and rationale
2. **Business Justification**: Why exception is necessary (e.g., legacy system constraint, unavailable technology in UK region)
3. **Risk Assessment**: Security, operational, compliance, and reputational risks
4. **Compensating Controls**: How risks will be mitigated (e.g., additional monitoring, manual reviews)
5. **Time Limit**: Exception expiration date (max 12 months)
6. **Remediation Plan**: Path to compliance with milestones

**Approval Authority**:
- **Low Risk** (e.g., technology choice for non-critical component): HMRC Enterprise Architect
- **Medium Risk** (e.g., temporary relaxation of testing requirements): Architecture Review Board + HMRC CISO delegate
- **High Risk** (e.g., data residency exception, security control deviation): HMRC Chief Technology Officer + HMRC CISO

**Exception Registry**:
- All approved exceptions tracked in HMRC Exception Registry (ServiceNow)
- Quarterly reviews by Architecture Review Board
- Automatic expiration and re-approval process

**Examples of Exceptions**:
- Legacy HMRC API integration requiring temporary relaxation of API-first principles (24-month remediation plan required)
- Prototype system using non-approved AI framework (time-boxed to 3 months, no citizen data)

---

## IX. Governance and Enforcement

### Architecture Review Process

All projects MUST undergo architecture review at these gates per GDS Service Standard:

**Gate 0: Discovery Complete**
- Review: Problem definition, user needs, alignment with HMRC strategy
- Reviewers: HMRC Senior Responsible Officer (SRO), Enterprise Architect

**Gate 1: Requirements Complete (Alpha)**
- Review: Architecture principles applied to requirements, ATRS record drafted
- Reviewers: Domain Architect, Enterprise Architect, HMRC Data Protection Officer

**Gate 2: High-Level Design (HLD) (Alpha)**
- Review: Technology choices, integration patterns, security controls, accessibility strategy
- Reviewers: Enterprise Architect, Security Architect (NCSC-aligned), Domain Architect
- Deliverables: HLD document, threat model, DPIA, ATRS record

**Gate 3: Detailed Design (DLD) (Beta)**
- Review: Component design, API contracts, data models, AI model selection
- Reviewers: Domain Architect, Technical Leads, Content Designers (for Plain English)

**Gate 4: Pre-Production (Beta)**
- Review: Infrastructure, CI/CD, observability, runbooks, accessibility audit results
- Reviewers: SRE, Security Operations, Accessibility Specialist

**Gate 5: Live Assessment (GDS Service Standard)**
- Review: Demonstrate service meets GDS Service Standard (18 criteria)
- Reviewers: GDS Service Assessors, HMRC Senior Responsible Officer
- Outcome: Service approved to go live on GOV.UK

### Review Outcomes

- **APPROVED**: Proceed to next phase
- **APPROVED WITH CONDITIONS**: Minor issues, must address before deployment
- **REJECTED**: Major concerns, revise and resubmit

### Compliance Monitoring

- Automated compliance scans (AWS Config Rules, Terraform Sentinel policies)
- Quarterly architecture audits by HMRC Internal Audit
- Annual principle review and update cycle by Architecture Review Board
- Monthly security posture reviews with HMRC SOC

---

## X. Amendment Process

### Modifying Principles

These principles are living documents but changes require rigor and alignment with GDS standards:

**Amendment Proposal Requirements**:
1. **Problem statement**: Why change is needed (e.g., new legislation, GDS guidance update)
2. **Impact analysis**: Affected systems and projects
3. **Industry benchmark**: How other government departments handle this (GDS, DVLA, DWP)
4. **Migration plan**: For existing systems (timelines, cost, risk)

**Approval Process**:
1. Proposal to HMRC Enterprise Architecture Team
2. Review by Architecture Review Board
3. Stakeholder feedback period (2 weeks, including GDS if relevant)
4. HMRC Chief Technology Officer final approval
5. Communication to all engineering teams
6. Grace period for compliance (90 days)

**Annual Review**:
- Principles reviewed annually to align with updated GDS guidance, UK GDPR changes, AI regulation
- Incorporation of lessons learned from ChatBot operation

---

## XI. GOV.UK Service Standard Alignment

The ChatBot MUST meet the 18 criteria of the GDS Service Standard before going live:

1. **Understand users and their needs**: User research with diverse citizen groups
2. **Solve a whole problem for users**: End-to-end tax guidance, not just FAQs
3. **Provide a joined up experience**: Integrate with GOV.UK account, Government Gateway, HMRC online services
4. **Make the service simple to use**: Plain English, intuitive interface, minimal cognitive load
5. **Make sure everyone can use the service**: WCAG 2.2 AA accessibility
6. **Have a multidisciplinary team**: Content designers, user researchers, developers, data scientists, security engineers
7. **Use agile ways of working**: Sprints, retrospectives, continuous delivery
8. **Iterate and improve frequently**: Monthly releases, continuous improvement based on citizen feedback
9. **Create a secure service**: Zero Trust, Cyber Essentials Plus, NCSC Cloud Security Principles
10. **Define what success looks like**: SLOs, citizen satisfaction metrics, helpline volume reduction
11. **Choose the right tools and technology**: GDS-approved technologies (see Technology Standards section)
12. **Make new source code open**: Publish non-sensitive code on GitHub under Open Government Licence (security-sensitive components excluded)
13. **Use and contribute to open standards**: OpenAPI, WCAG, OAuth 2.0, OpenTelemetry
14. **Operate a reliable service**: 99.9% availability, disaster recovery tested
15. **Support a sustainable service**: Documentation, runbooks, knowledge transfer, long-term support plan
16. **Identify and address performance issues**: Load testing, performance monitoring, optimization
17. **Test the end-to-end service**: E2E testing, user acceptance testing, private beta
18. **Make the service accessible**: WCAG 2.2 AA, assistive technology testing, accessibility statement

**Live Assessment**:
- Service MUST pass GDS Live Assessment before public launch
- Assessment by independent GDS assessors
- Evidence required for all 18 criteria

---

## Appendices

### Appendix A: Glossary

- **ATRS**: Algorithmic Transparency Recording Standard (HMG requirement for AI systems)
- **Bounded Context**: Domain-driven design concept for service boundaries
- **CHECK**: NCSC scheme for approved penetration testing suppliers
- **DLD**: Detailed Level Design
- **DPIA**: Data Protection Impact Assessment (UK GDPR requirement)
- **FinOps**: Financial operations for cloud cost management
- **GDS**: Government Digital Service
- **Government Gateway**: HMRC authentication system for citizens
- **HLD**: High-Level Design
- **HMG**: Her Majesty's Government
- **NCSC**: National Cyber Security Centre
- **PII**: Personally Identifiable Information
- **RAG**: Retrieval-Augmented Generation (AI architecture pattern)
- **RPO/RTO**: Recovery point/time objectives for disaster recovery
- **SAST/DAST**: Static/dynamic application security testing
- **SLI/SLO/SLA**: Service level indicator/objective/agreement
- **SPF**: Security Policy Framework (HMG)
- **WCAG**: Web Content Accessibility Guidelines
- **Zero Trust**: Security model assuming breach, no implicit trust

### Appendix B: Reference Architecture Diagrams

**High-Level Architecture**:
```
[Citizen] → [CloudFront + WAF] → [API Gateway] → [ECS Fargate Services]
                                                    ├─ Citizen Identity Service (Government Gateway)
                                                    ├─ Conversational AI Service (RAG + LLM)
                                                    ├─ Knowledge Management Service (Vector DB)
                                                    └─ HMRC Integration Service (Backend APIs)

[Data Stores]:
- RDS PostgreSQL (Citizen profiles, audit logs)
- OpenSearch (Vector embeddings for RAG)
- ElastiCache Redis (Session management)
- S3 (Chat transcripts, encrypted)

[External Integrations]:
- AWS Bedrock (Claude 3.5 Sonnet LLM)
- Government Gateway (Authentication)
- HMRC Backend APIs (Tax records, National Insurance)
```

**Security Architecture**:
```
[Defense in Depth]:
1. AWS WAF (OWASP Top 10 rules, rate limiting)
2. API Gateway (authentication, authorization)
3. VPC with private subnets (no public internet access for ECS tasks)
4. Security Groups (least privilege network access)
5. IAM Roles (least privilege AWS access)
6. Encryption at rest (RDS, S3, OpenSearch)
7. Encryption in transit (TLS 1.3)
8. Secrets Manager (no hardcoded credentials)
9. CloudTrail + CloudWatch (audit logging)
10. AWS GuardDuty (threat detection)
```

**AI/RAG Architecture**:
```
[Citizen Query] → [Input Validation] → [Embedding Model] → [Vector Search (OpenSearch)]
                                                            ↓
[Retrieved Documents] → [Prompt Construction] → [LLM (AWS Bedrock Claude)] → [Response Generation]
                                                                            ↓
                                              [Post-Processing: Validation, Source Citation] → [Response to Citizen]
                                                                            ↓
                                              [Audit Log: Query, Response, Sources, Confidence]
```

### Appendix C: Related Documents

- **GDS Service Manual**: https://www.gov.uk/service-manual
- **Technology Code of Practice**: https://www.gov.uk/guidance/the-technology-code-of-practice
- **Service Standard**: https://www.gov.uk/service-manual/service-standard
- **UK Government AI Playbook**: https://www.gov.uk/government/publications/ai-playbook
- **Algorithmic Transparency Recording Standard**: https://www.gov.uk/government/collections/algorithmic-transparency-recording-standard-hub
- **Data Ethics Framework**: https://www.gov.uk/government/publications/data-ethics-framework
- **NCSC Cloud Security Principles**: https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles
- **GOV.UK Design System**: https://design-system.service.gov.uk/
- **WCAG 2.2 Guidelines**: https://www.w3.org/WAI/WCAG22/quickref/
- **UK GDPR Guidance**: https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/
- **HMG Security Policy Framework**: https://www.gov.uk/government/publications/security-policy-framework

### Appendix D: Compliance Checklist

**Pre-Launch Compliance**:
- [ ] GDS Service Standard assessment passed (18 criteria)
- [ ] WCAG 2.2 AA accessibility audit passed
- [ ] Cyber Essentials Plus certification obtained
- [ ] DPIA approved by HMRC Data Protection Officer
- [ ] ATRS record published on GOV.UK
- [ ] Penetration test by CHECK-approved supplier (no critical/high findings)
- [ ] NCSC Cloud Security Principles addressed (14 principles)
- [ ] Privacy notice published on GOV.UK
- [ ] Welsh language support implemented
- [ ] Accessibility statement published
- [ ] Live service agreement signed
- [ ] Disaster recovery tested (RPO/RTO validated)
- [ ] Incident response procedures documented and trained
- [ ] On-call rota established with runbooks

---

**Document Control**

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2025-10-14 | Enterprise Architecture Team | Initial draft for HMRC ChatBot project |

**Approvals** (Pending)

| Role | Name | Signature | Date |
|------|------|-----------|------|
| HMRC Chief Technology Officer | [PENDING] | _________ | [PENDING] |
| HMRC Chief Information Security Officer | [PENDING] | _________ | [PENDING] |
| HMRC Enterprise Architect | [PENDING] | _________ | [PENDING] |
| HMRC Data Protection Officer | [PENDING] | _________ | [PENDING] |
| GDS Senior Responsible Officer | [PENDING] | _________ | [PENDING] |
