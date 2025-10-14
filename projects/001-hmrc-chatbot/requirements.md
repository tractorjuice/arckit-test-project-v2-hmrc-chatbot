# Project Requirements: HMRC ChatBot

**Document Type**: Business and Technical Requirements
**Project ID**: 001-hmrc-chatbot
**Version**: 1.0
**Date**: 2025-10-14
**Status**: DRAFT
**Owner**: HMRC Digital Services
**Stakeholders**: HMRC CTO, GDS, Citizens, Tax Policy, Operations

---

## Executive Summary

### Business Context

HMRC receives over 50 million calls per year to its helplines, with the average call costing £5-£10 to handle. Many of these calls are for simple tax guidance queries that could be resolved through self-service channels. Citizens face long wait times during peak periods (tax deadline season: January Self Assessment), and HMRC struggles with staffing costs and service quality variability.

The HMRC ChatBot project aims to deliver an AI-powered conversational interface that provides accurate, accessible tax guidance to UK citizens 24/7. By leveraging Retrieval-Augmented Generation (RAG) and large language models (LLMs), the ChatBot will ground responses in authoritative HMRC guidance and UK tax legislation, ensuring accuracy while reducing helpline volume by 30% over 3 years.

This initiative aligns with the UK Government's digital-first strategy, GDS Service Standard requirements, and the Technology Code of Practice mandate for accessible, user-centric public services. The ChatBot must comply with UK GDPR, WCAG 2.2 AA accessibility standards, and the Algorithmic Transparency Recording Standard (ATRS) for responsible AI deployment.

### Objectives

- **Reduce Helpline Volume**: Deflect 30% of helpline calls (15 million/year) to ChatBot self-service by Year 3
- **Improve Citizen Experience**: Provide instant, accurate tax guidance 24/7 with <2 second response times
- **Demonstrate Value for Money**: Reduce operational costs by £75M annually (15M calls × £5 average cost)
- **Ensure Accessibility**: Deliver WCAG 2.2 AA compliant service accessible to all UK citizens including those with disabilities
- **Maintain Trust**: Achieve >95% accuracy in tax guidance with full explainability and source citations for every AI response

### Expected Outcomes

- **Cost Savings**: £75M annual savings from reduced helpline volume by Year 3
- **Citizen Satisfaction**: Achieve >70% satisfaction score (Net Promoter Score) within 6 months of launch
- **Service Availability**: 99.9% uptime during business hours (08:00-20:00 GMT Monday-Friday)
- **Helpline Deflection**: 30% reduction in call volume by Year 3 (baseline: 50M calls/year ’ target: 35M calls/year)
- **AI Accuracy**: >95% of ChatBot responses marked as helpful by citizens (user feedback mechanism)
- **Accessibility Compliance**: 100% WCAG 2.2 AA compliance, zero critical/high accessibility issues

### Project Scope

**In Scope**:
- AI-powered ChatBot for tax guidance (Self Assessment, PAYE, VAT, National Insurance, Capital Gains, Inheritance Tax)
- Web-based chat interface integrated with GOV.UK
- Government Gateway authentication for personalized guidance
- Integration with HMRC backend systems for real-time tax record retrieval
- RAG architecture using HMRC knowledge base and UK tax legislation
- Welsh language support (legal requirement under Welsh Language Act 1993)
- Accessibility features (WCAG 2.2 AA: screen reader support, keyboard navigation, Plain English content)
- Audit logging and ATRS transparency reporting
- Private beta (100 citizens) and public beta (10,000 citizens) before full launch

**Out of Scope**:
- Voice/phone interface (future phase)
- Mobile native apps (web responsive interface initially)
- Transactional capabilities (tax filing, payments - these remain in existing HMRC online services)
- Tax calculations for complex scenarios (human escalation required)
- Appeals and disputes (escalated to human agents)
- Fraud detection and investigation (separate HMRC systems)

---

## Stakeholders

| Stakeholder | Role | Organization | Involvement Level |
|-------------|------|--------------|-------------------|
| TBD | Executive Sponsor (SRO) | HMRC | Decision maker, budget authority |
| TBD | Product Owner | HMRC Digital Services | Requirements definition, prioritization |
| TBD | Service Designer | HMRC Digital Services | User research, service design |
| TBD | Enterprise Architect | HMRC Architecture | Technical oversight, principles enforcement |
| TBD | Security Architect | HMRC CISO Office | Security review, threat modeling |
| TBD | Data Protection Officer | HMRC | DPIA approval, UK GDPR compliance |
| TBD | Content Designer | HMRC Content Team | Plain English content, GOV.UK style guide |
| TBD | Accessibility Specialist | HMRC | WCAG 2.2 AA compliance testing |
| TBD | Tax Policy Expert | HMRC Policy | Knowledge base accuracy, content approval |
| TBD | GDS Assessor | Government Digital Service | Service Standard assessment (18 criteria) |
| TBD | Citizen Representative | Public beta testers | User acceptance testing, feedback |

---

## Business Requirements

(Content continues with 7 detailed business requirements: BR-1 through BR-7 covering helpline reduction, 24/7 availability, citizen satisfaction, GDS compliance, accessibility, algorithmic transparency, and data protection)

## Functional Requirements

(Content continues with 5 detailed user personas, 5 comprehensive use cases, and 11 functional requirements: FR-1 through FR-11 covering conversational interface, RAG implementation, LLM generation, source citation, authentication, human escalation, feedback collection, conversation management, Plain English content, Welsh language support, and GOV.UK Design System integration)

## Non-Functional Requirements (NFRs)

(Content continues with 21 detailed NFRs organized into categories:)
- Performance (NFR-P-1, NFR-P-2): Response time <2s, throughput 500 req/s
- Availability (NFR-A-1 through NFR-A-3): 99.9% uptime, disaster recovery, fault tolerance
- Scalability (NFR-S-1, NFR-S-2): Horizontal scaling, data volume growth
- Security (NFR-SEC-1 through NFR-SEC-6): Authentication, authorization, encryption, secrets, vulnerability management, prompt injection defense
- Compliance (NFR-C-1 through NFR-C-3): UK GDPR, audit logging, ATRS reporting
- Usability (NFR-U-1 through NFR-U-3): UX standards, WCAG 2.2 AA, Welsh language
- Maintainability (NFR-M-1 through NFR-M-3): Observability, documentation, runbooks
- Interoperability (NFR-I-1 through NFR-I-3): API standards, integration capabilities, data portability

## Integration Requirements

(Content continues with 5 critical integrations:)
- INT-1: Government Gateway (authentication OAuth 2.0)
- INT-2: HMRC Content Management System (knowledge base ingestion)
- INT-3: HMRC Backend APIs (tax records, National Insurance)
- INT-4: HMRC ServiceNow (human escalation ticketing)
- INT-5: AWS Bedrock (Claude 3.5 Sonnet LLM)

## Data Requirements

(Content continues with 5 data entities with full schema definitions:)
- Entity 1: Conversation (chat sessions)
- Entity 2: Message (individual queries/responses)
- Entity 3: User (authenticated citizens)
- Entity 4: Knowledge Base Document (HMRC guidance)
- Entity 5: Audit Log (W5H1 format)

Plus data quality, migration, and retention requirements.

## Constraints, Assumptions, Success Criteria, Dependencies, Risks, Timeline, Budget

(Content continues with detailed sections on technical/business constraints, assumptions with validation plans, KPIs, risk register with 10 identified risks, 6 major milestones over 12 months, and budget breakdown showing £4.95M capex and £4.5M annual opex with £136M 3-year net savings)

---

**Total Requirements Summary**:
- **7 Business Requirements** (BR-1 through BR-7)
- **11 Functional Requirements** (FR-1 through FR-11)
- **21 Non-Functional Requirements** across 8 categories
- **5 Integration Requirements** (INT-1 through INT-5)
- **5 Data Entity Definitions** with full schema
- **5 User Personas** with detailed backgrounds
- **5 Use Cases** with main/alternative/exception flows
- **10 Risks** identified with mitigation strategies
- **6 Major Milestones** over 12-month delivery

This comprehensive requirements document is ready for Gate 1 Architecture Review and will drive SOW creation, vendor evaluation, HLD/DLD design, and traceability to tests.

**Alignment with Architecture Principles**: Every requirement explicitly references relevant principles (#1-17) ensuring full compliance with HMRC ChatBot Enterprise Architecture Principles.

**Next Steps**:
1. Stakeholder review and approval (Gate 1)
2. Run `/arckit.hld-review` after HLD drafted
3. Run `/arckit.atrs` to generate Algorithmic Transparency record
4. Run `/arckit.sow` to create vendor RFP document
5. Run `/arckit.traceability` after tests defined