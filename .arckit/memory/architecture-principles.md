# HMRC ChatBot Enterprise Architecture Principles

> **Template Status**: Live | **Version**: 0.11.2 | **Command**: `/arckit.principles`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-PRIN-v1.2 |
| **Document Type** | Enterprise Architecture Principles |
| **Project** | HMRC ChatBot System (Project 001-hmrc-chatbot) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.2 |
| **Created Date** | 2025-10-14 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | Quarterly |
| **Next Review Date** | 2026-04-26 |
| **Owner** | Enterprise Architecture Team |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | HMRC Architecture Review Board, GDS Stakeholders |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2025-10-14 | Enterprise Architecture Team | Initial draft for HMRC ChatBot project | PENDING | PENDING |
| 1.1 | 2026-01-25 | ArcKit AI | Updated to align with ArcKit template structure | PENDING | PENDING |
| 1.2 | 2026-01-26 | ArcKit AI | Updated to align with ArcKit template v0.11.2 | PENDING | PENDING |

---

## Executive Summary

This document establishes the immutable principles governing all technology architecture decisions for the HMRC ChatBot system. These principles ensure compliance with UK Government technology standards, security requirements, accessibility mandates, and AI governance frameworks while delivering secure, reliable, and user-centric tax advisory services to UK citizens.

**Scope**: HMRC ChatBot system and all supporting infrastructure
**Authority**: Government Digital Service (GDS) and HMRC Architecture Review Board
**Compliance**: Mandatory unless exception approved by HMRC Chief Technology Officer
**Regulatory Context**: UK GDPR, Technology Code of Practice, Service Standard, AI Playbook, WCAG 2.2 AA, Algorithmic Transparency Standard

**Philosophy**: These principles define WHAT qualities the architecture must have, guiding technology selection during research and design phases. While this document includes technology guidance specific to HMRC's approved stack, the core principles remain technology-agnostic.

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

**Rationale**:
Business demand is unpredictable and variable. Citizen data is sensitive and subject to strict regulatory controls. Systems must handle data appropriately without manual intervention or compliance gaps.

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

**Rationale**:
Tax guidance directly impacts citizen financial obligations. Errors can result in penalties, appeals, or loss of public trust. Quality is non-negotiable.

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

### 9. Single Source of Truth

**Principle Statement**:
Every data domain MUST have a single authoritative source. Derived copies must be clearly labeled and synchronized.

**Rationale**:
Multiple authoritative sources create inconsistency, reconciliation overhead, and data integrity issues. For tax guidance, conflicting information is unacceptable.

**Implications**:
- HMRC CMS is the system of record for tax guidance
- Derived/cached copies in vector database are read-only and labeled as derived
- Synchronization strategy defined for all derived copies
- Avoid bidirectional synchronization (creates split-brain scenarios)

**Validation Gates**:
- [ ] System of record identified for each data entity
- [ ] Derived copies documented with sync frequency
- [ ] No bidirectional sync without conflict resolution strategy
- [ ] Master data management strategy for shared reference data

---

## III. Integration Principles

### 10. Loose Coupling

**Principle Statement**:
Systems MUST be loosely coupled through published interfaces, avoiding shared databases, file systems, or tight runtime dependencies.

**Rationale**:
Loose coupling enables independent deployment, technology diversity, team autonomy, and system evolution without breaking dependencies.

**Implications**:
- Communicate through published APIs or asynchronous events
- No direct database access across system boundaries
- Each system manages its own data lifecycle
- Shared libraries kept minimal (favor duplication over coupling)
- Avoid distributed transactions across systems

**Validation Gates**:
- [ ] Systems communicate via APIs or events, not database
- [ ] No shared mutable state
- [ ] Each system has independent data store
- [ ] Deployment of one system doesn't require deployment of another
- [ ] Interface changes versioned with backward compatibility

---

### 11. Asynchronous Communication

**Principle Statement**:
Systems SHOULD use asynchronous communication for non-real-time interactions to improve resilience and decoupling.

**Rationale**:
Asynchronous patterns reduce temporal coupling, improve fault tolerance, and enable better scalability.

**When to Use Async**:
- HMRC backend API integration (tax records retrieval)
- Audit logging and compliance reporting
- Non-real-time business processes
- Event notification and pub/sub patterns

**When Synchronous is Acceptable**:
- Real-time chat interactions requiring immediate feedback
- Query operations (read-only, idempotent)
- Authentication flows

**Validation Gates**:
- [ ] Async patterns used for non-real-time flows
- [ ] Message durability and delivery guarantees defined
- [ ] Event schemas versioned and published
- [ ] Dead letter queues and error handling configured

---

## IV. Quality Attributes

### 12. Performance and Efficiency

**Principle Statement**:
All systems MUST meet defined performance targets under expected load with efficient use of computational resources.

**Rationale**:
Citizens expect responsive service. Poor performance damages trust and increases support costs.

**Performance Targets**:
- **Response Time**: p95 <2 seconds for chat messages
- **Throughput**: 10,000 concurrent users during peak
- **Concurrency**: Handle tax deadline surge (January, April)
- **Resource Efficiency**: Optimize LLM token usage

**Implications**:
- Performance requirements defined before implementation
- Load testing performed before production deployment
- Performance monitoring continuous, not just point-in-time
- Caching strategies for expensive operations (knowledge retrieval)

**Validation Gates**:
- [ ] Performance requirements defined with measurable targets
- [ ] Load testing performed at expected capacity (10,000 concurrent users)
- [ ] Performance metrics monitored in production
- [ ] Capacity planning model defined

---

### 13. Availability and Resilience

**Principle Statement**:
The ChatBot MUST be designed to gracefully handle failures. Assume dependencies (Government Gateway, HMRC APIs, LLM providers) will fail; plan accordingly. Citizens must receive service even during partial outages.

**Rationale**:
Failures are inevitable in distributed systems. The architecture must assume failures will occur and design for resilience rather than perfect reliability.

**Resilience Patterns** (MANDATORY):
- **Circuit Breaker**: Prevent cascade failures when HMRC backend APIs fail
- **Retry with Exponential Backoff**: Transient fault handling (3 retries max)
- **Timeout**: Every network call must have timeout (5 seconds for API calls, 30 seconds for LLM generation)
- **Bulkhead**: Isolate resources to limit blast radius
- **Graceful Degradation**: Fallback to cached guidance if HMRC APIs unavailable
- **Rate Limiting**: Protect from overload (500 requests/hour per citizen)

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

**Validation Gates**:
- [ ] Failure modes identified and mitigated
- [ ] Chaos engineering or fault injection testing performed
- [ ] RTO and RPO defined and tested
- [ ] Automated failover tested
- [ ] Degraded mode behavior documented

---

### 14. Maintainability and Evolvability

**Principle Statement**:
All systems MUST be designed for change, with clear separation of concerns, modular architecture, and comprehensive documentation.

**Rationale**:
Software spends most of its lifetime in maintenance. Design decisions should optimize for understandability and modifiability.

**Implications**:
- Modular architecture with clear boundaries (bounded contexts)
- Separation of concerns (business logic, data access, presentation)
- Code is self-documenting with meaningful names
- Architecture Decision Records (ADRs) for significant choices
- Automated testing to enable confident refactoring

**Validation Gates**:
- [ ] Architecture documentation exists and is current
- [ ] Module boundaries clear with defined responsibilities
- [ ] Automated test coverage enables safe refactoring
- [ ] Architecture Decision Records document key choices

---

## V. Development Practices

### 15. Infrastructure as Code

**Principle Statement**:
ALL infrastructure MUST be defined as code, version-controlled in Git, and deployed via CI/CD pipelines. Manual infrastructure changes are prohibited in production. This ensures repeatability, auditability, and compliance with HMG change management requirements.

**Rationale**:
Manual infrastructure changes create drift, inconsistency, and undocumented state. Infrastructure as Code (IaC) enables repeatability, auditability, and disaster recovery.

**IaC Standards**:
- **Primary Tool**: Terraform (HCL) with remote state in AWS S3 + DynamoDB locking
- **Version Control**: Git (GitHub with HMRC organization)
- **State Management**: Remote state with encryption at rest, state locking enabled
- **Secrets**: Never committed to code; use AWS Secrets Manager with dynamic references

**Deployment Requirements**:
- Automated deployment via AWS CodePipeline or GitHub Actions
- Environment parity (dev, staging, prod) with identical IaC
- Immutable infrastructure (replace, don't modify)
- Rollback capability within 5 minutes (blue/green or canary deployments)

**Exceptions**:
- Emergency hotfixes (with post-incident IaC update required within 24 hours and PIR)

**Validation Gates**:
- [ ] Infrastructure defined as code
- [ ] Infrastructure code version-controlled
- [ ] Automated deployment pipeline for infrastructure
- [ ] No manual infrastructure changes in production

---

### 16. Automated Testing

**Principle Statement**:
All code changes MUST be validated through automated testing before deployment to production.

**Rationale**:
Testing is NOT optional. The ChatBot must meet rigorous quality standards before serving UK citizens.

**Test Pyramid**:
- **Unit Tests** (70%): Fast, isolated, high coverage (80%+ coverage)
- **Integration Tests** (20%): Test component interactions
- **End-to-End Tests** (10%): Critical user journeys

**AI-Specific Testing**:
- **Accuracy Testing**: 1000+ ground truth queries (>95% accuracy required)
- **Bias Testing**: Evaluate fairness across demographics
- **Adversarial Testing**: Prompt injection, jailbreak attempts
- **Hallucination Detection**: Validate AI outputs against ground truth

**Required Test Types**:
- Functional tests (does it work?)
- Performance tests (is it fast enough?)
- Security tests (is it secure?)
- Resilience tests (does it handle failures?)
- Accessibility tests (WCAG 2.2 AA compliance)

**Validation Gates**:
- [ ] Automated tests exist and pass before merge
- [ ] Test coverage meets defined thresholds (≥80%)
- [ ] Critical paths have end-to-end tests
- [ ] AI accuracy tests passing (>95%)

---

### 17. Continuous Integration and Deployment

**Principle Statement**:
All code changes MUST flow through automated CI/CD pipelines with quality gates before reaching production. This ensures security, quality, and compliance with HMG change management.

**Pipeline Stages** (MANDATORY):
1. **Build**: Compile, dependency resolution
2. **Test**: Unit, integration, contract tests
3. **Security Scan**: SAST, dependency vulnerability checks, secrets detection
4. **Deploy to Dev/Staging**: Automated deployment
5. **Approval Gate**: Manual approval by Architecture Review Board for production
6. **Deploy to Production**: Blue/green deployment with canary testing
7. **Monitoring**: Automated rollback on SLO violation

**Quality Gates**:
- Code coverage ≥80%
- No critical/high security vulnerabilities
- Code review approval required
- Accessibility tests passing

**Validation Gates**:
- [ ] Automated CI/CD pipeline exists
- [ ] Pipeline includes security scanning
- [ ] Deployment is automated and repeatable
- [ ] Rollback capability tested

---

## VI. Exception Process

### Requesting Architecture Exceptions

Exceptions to these principles require documented justification and formal approval per HMG governance standards.

**Valid Exception Reasons**:
- Technical constraints that prevent compliance
- Regulatory or legal requirements
- Transitional state during migration
- Pilot/proof-of-concept with defined end date

**Exception Request Must Include**:
1. **Principle Being Violated**: Specific principle and rationale
2. **Business Justification**: Why exception is necessary
3. **Risk Assessment**: Security, operational, compliance, and reputational risks
4. **Compensating Controls**: How risks will be mitigated
5. **Time Limit**: Exception expiration date (max 12 months)
6. **Remediation Plan**: Path to compliance with milestones

**Approval Authority**:
- **Low Risk**: HMRC Enterprise Architect
- **Medium Risk**: Architecture Review Board + HMRC CISO delegate
- **High Risk**: HMRC Chief Technology Officer + HMRC CISO

**Exception Registry**:
- All approved exceptions tracked in HMRC Exception Registry (ServiceNow)
- Quarterly reviews by Architecture Review Board
- Automatic expiration and re-approval process

---

## VII. Governance and Compliance

### Architecture Review Gates

All projects MUST undergo architecture review at these gates per GDS Service Standard:

**Discovery/Alpha**:
- [ ] Architecture principles understood
- [ ] High-level approach aligns with principles
- [ ] ATRS record drafted

**Beta/Design**:
- [ ] Detailed architecture documented
- [ ] Compliance with each principle validated
- [ ] Exceptions requested and approved
- [ ] Security and data principles validated

**Pre-Production**:
- [ ] Implementation matches approved architecture
- [ ] All validation gates passed
- [ ] Operational readiness verified

**Live Assessment (GDS Service Standard)**:
- [ ] Service meets all 18 GDS Service Standard criteria
- [ ] Cyber Essentials Plus certification obtained
- [ ] WCAG 2.2 AA accessibility audit passed
- [ ] DPIA approved

### Enforcement

- Architecture reviews are **mandatory** for all projects
- Principle violations must be remediated before production deployment
- Approved exceptions are time-bound and reviewed quarterly
- Retrospective reviews for compliance on live systems

---

## VIII. Appendix

### Principle Summary Checklist

| Principle | Category | Criticality | Validation |
|-----------|----------|-------------|------------|
| Government Cloud-First | Strategic | HIGH | UK region deployment |
| API-First Integration | Strategic | HIGH | OpenAPI specs, Gateway integration |
| Security by Design | Strategic | CRITICAL | Threat model, pen testing, Cyber Essentials Plus |
| Accessibility-First | Strategic | CRITICAL | WCAG 2.2 AA audit |
| Responsible AI | Strategic | CRITICAL | ATRS record, bias testing |
| Observability | Strategic | HIGH | Metrics, logs, traces, SLOs |
| Data Sovereignty | Data | CRITICAL | UK GDPR compliance, DPIA |
| Data Quality | Data | CRITICAL | 100% accuracy, source citation |
| Single Source of Truth | Data | HIGH | Data lineage documented |
| Loose Coupling | Integration | HIGH | API-based communication |
| Asynchronous Communication | Integration | MEDIUM | Async patterns for non-real-time |
| Performance | Quality | HIGH | Load testing (10,000 users) |
| Availability | Quality | CRITICAL | 99.9% SLA, RTO/RPO |
| Maintainability | Quality | MEDIUM | Documentation, ADRs |
| Infrastructure as Code | DevOps | HIGH | Terraform, automated deployment |
| Automated Testing | DevOps | HIGH | 80%+ coverage, AI accuracy tests |
| CI/CD | DevOps | HIGH | Pipeline with security gates |

### GOV.UK Service Standard Alignment

The ChatBot MUST meet the 18 criteria of the GDS Service Standard before going live:

1. Understand users and their needs
2. Solve a whole problem for users
3. Provide a joined up experience
4. Make the service simple to use
5. Make sure everyone can use the service (WCAG 2.2 AA)
6. Have a multidisciplinary team
7. Use agile ways of working
8. Iterate and improve frequently
9. Create a secure service (Zero Trust, Cyber Essentials Plus)
10. Define what success looks like
11. Choose the right tools and technology
12. Make new source code open
13. Use and contribute to open standards
14. Operate a reliable service (99.9% availability)
15. Support a sustainable service
16. Identify and address performance issues
17. Test the end-to-end service
18. Make the service accessible

### Glossary

- **ATRS**: Algorithmic Transparency Recording Standard
- **Bounded Context**: Domain-driven design concept for service boundaries
- **CHECK**: NCSC scheme for approved penetration testing suppliers
- **DPIA**: Data Protection Impact Assessment
- **FinOps**: Financial operations for cloud cost management
- **GDS**: Government Digital Service
- **Government Gateway**: HMRC authentication system for citizens
- **HMG**: His Majesty's Government
- **NCSC**: National Cyber Security Centre
- **PII**: Personally Identifiable Information
- **RAG**: Retrieval-Augmented Generation
- **RPO/RTO**: Recovery point/time objectives
- **SAST/DAST**: Static/dynamic application security testing
- **SLI/SLO/SLA**: Service level indicator/objective/agreement
- **WCAG**: Web Content Accessibility Guidelines
- **Zero Trust**: Security model assuming breach, no implicit trust

### Related Documents

- GDS Service Manual: https://www.gov.uk/service-manual
- Technology Code of Practice: https://www.gov.uk/guidance/the-technology-code-of-practice
- Service Standard: https://www.gov.uk/service-manual/service-standard
- UK Government AI Playbook: https://www.gov.uk/government/publications/ai-playbook
- Algorithmic Transparency Recording Standard: https://www.gov.uk/government/collections/algorithmic-transparency-recording-standard-hub
- Data Ethics Framework: https://www.gov.uk/government/publications/data-ethics-framework
- NCSC Cloud Security Principles: https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles
- GOV.UK Design System: https://design-system.service.gov.uk/
- WCAG 2.2 Guidelines: https://www.w3.org/WAI/WCAG22/quickref/
- UK GDPR Guidance: https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/

---

**Document Version History**

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | 2025-10-14 | Enterprise Architecture Team | Initial draft |
| 1.0 | 2025-10-14 | Enterprise Architecture Team | Ratified version |
| 1.1 | 2026-01-25 | ArcKit AI | Aligned with ArcKit template structure |
| 1.2 | 2026-01-26 | ArcKit AI | Updated to template v0.11.2 |

---

**Generated by**: ArcKit `/arckit.principles` command
**Generated on**: 2026-01-26
**ArcKit Version**: 0.11.2
**Project**: HMRC ChatBot (001-hmrc-chatbot)
**Model**: Claude Opus 4.5
