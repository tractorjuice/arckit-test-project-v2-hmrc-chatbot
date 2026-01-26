# Project Requirements: HMRC ChatBot

> **Template Status**: Live | **Version**: 0.11.2 | **Command**: `/arckit.requirements`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-REQ-v1.2 |
| **Document Type** | Business and Technical Requirements |
| **Project** | HMRC ChatBot (Project 001-hmrc-chatbot) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.2 |
| **Created Date** | 2025-10-14 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | Monthly |
| **Next Review Date** | 2026-02-26 |
| **Owner** | HMRC Digital Services |
| **Reviewed By** | [PENDING] |
| **Approved By** | [PENDING] |
| **Distribution** | HMRC Architecture Team, GDS Stakeholders, Project Team |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2025-10-14 | ArcKit AI | Initial creation from `/arckit.requirements` command | [PENDING] | [PENDING] |
| 1.1 | 2026-01-25 | ArcKit AI | Updated to align with ArcKit template structure | [PENDING] | [PENDING] |
| 1.2 | 2026-01-26 | ArcKit AI | Updated to align with ArcKit template v0.11.2 | [PENDING] | [PENDING] |

## Document Purpose

This document defines the comprehensive business, functional, non-functional, integration, and data requirements for the HMRC ChatBot project. It serves as the authoritative source for vendor RFPs, architecture reviews, design decisions, and acceptance testing. All requirements are traceable to architecture principles and will drive the Statement of Work, evaluation criteria, and test plans.

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
- **Helpline Deflection**: 30% reduction in call volume by Year 3 (baseline: 50M calls/year → target: 35M calls/year)
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

### BR-1: Reduce Helpline Call Volume

**Description**: Reduce HMRC helpline call volume by 30% (15 million calls/year) by Year 3 through ChatBot self-service deflection.

**Rationale**: HMRC helpline costs £5-£10 per call (50M calls = £250M-£500M/year). Deflecting simple queries to self-service delivers significant cost savings while improving citizen experience through reduced wait times.

**Success Criteria**:
- 10% helpline reduction by end of Year 1 (5M calls deflected)
- 20% helpline reduction by end of Year 2 (10M calls deflected)
- 30% helpline reduction by end of Year 3 (15M calls deflected)
- Helpline wait times reduced from average 10 minutes to <5 minutes

**Priority**: MUST_HAVE

**Stakeholder**: HMRC Finance Director, Operations Director

**Aligns with Principle**: #1 Government Cloud-First (scalability), #6 Observability (tracking deflection metrics)

---

### BR-2: Provide 24/7 Tax Guidance Availability

**Description**: Citizens MUST be able to access tax guidance through the ChatBot 24 hours a day, 7 days a week, 365 days a year, including bank holidays and tax deadline periods.

**Rationale**: Current helpline hours (8am-6pm weekdays) exclude working citizens who need guidance outside business hours. Tax deadline periods (January Self Assessment) see peak demand that overwhelms staff capacity.

**Success Criteria**:
- 99.9% availability during business hours (08:00-20:00 GMT Monday-Friday)
- 99.5% availability outside business hours
- Zero planned downtime during tax deadline periods (1-31 January)
- <15 minute recovery time for unplanned outages

**Priority**: MUST_HAVE

**Stakeholder**: HMRC Customer Services Director

**Aligns with Principle**: #13 Availability and Resilience

---

### BR-3: Achieve High Citizen Satisfaction

**Description**: Achieve >70% citizen satisfaction score (measured by NPS or equivalent) within 6 months of public launch, demonstrating the ChatBot provides value to UK citizens.

**Rationale**: Citizen trust in HMRC depends on service quality. Low satisfaction would damage HMRC reputation and drive citizens back to expensive helpline channels.

**Success Criteria**:
- Net Promoter Score (NPS) >70% within 6 months
- >95% of responses rated as "helpful" by citizens (thumbs up/down)
- <5% escalation rate to human agents for queries within ChatBot scope
- Citizen feedback actively incorporated into service improvements (monthly reviews)

**Priority**: MUST_HAVE

**Stakeholder**: HMRC Customer Experience Lead

**Aligns with Principle**: #4 Accessibility-First Design, #8 Data Quality and Accuracy

---

### BR-4: Achieve GDS Service Standard Compliance

**Description**: Pass GDS Service Standard assessment (all 18 criteria) to obtain approval for public launch on GOV.UK.

**Rationale**: GDS Service Standard is mandatory for government digital services. Failure to pass assessment prevents public launch and damages project credibility.

**Success Criteria**:
- Pass Discovery assessment (Gate 0)
- Pass Alpha assessment (Gate 1)
- Pass Beta assessment (Gate 2)
- Pass Live assessment (Gate 3) before public launch
- No "Red" assessments on any of the 18 criteria

**Priority**: MUST_HAVE

**Stakeholder**: GDS Assessment Team, HMRC SRO

**Aligns with Principle**: #4 Accessibility-First Design, All Strategic Principles

---

### BR-5: Ensure Full Accessibility Compliance

**Description**: ChatBot MUST be fully accessible to all UK citizens, including those with disabilities, meeting WCAG 2.2 Level AA standards as required by UK law.

**Rationale**: 13.9 million UK citizens have disabilities. Accessibility is a legal requirement under Public Sector Bodies (Websites and Mobile Applications) Accessibility Regulations 2018 and Equality Act 2010.

**Success Criteria**:
- Zero critical/high WCAG 2.2 AA issues at launch
- Pass manual accessibility testing with screen readers (JAWS, NVDA, VoiceOver)
- User testing with disabled citizens (minimum 5 participants per research round)
- Published accessibility statement on GOV.UK
- Welsh language support fully functional

**Priority**: MUST_HAVE

**Stakeholder**: HMRC Accessibility Lead, Equality and Diversity Team

**Aligns with Principle**: #4 Accessibility-First Design (Legal Requirement)

---

### BR-6: Publish Algorithmic Transparency Record

**Description**: Publish ATRS record for the ChatBot AI system on GOV.UK before public launch, demonstrating responsible AI deployment per UK Government requirements.

**Rationale**: UK Government mandates algorithmic transparency for AI systems used in public services. ATRS record demonstrates accountability and builds citizen trust.

**Success Criteria**:
- ATRS record drafted and approved by HMRC Data Ethics Committee
- ATRS record published on GOV.UK before public beta
- Record updated within 30 days of any significant model changes
- Contact details for algorithmic accountability included

**Priority**: MUST_HAVE

**Stakeholder**: HMRC Data Ethics Committee, Chief Data Officer

**Aligns with Principle**: #5 Responsible AI and Algorithmic Transparency (NON-NEGOTIABLE)

---

### BR-7: Ensure UK GDPR Compliance

**Description**: All citizen data processing MUST comply with UK GDPR, Data Protection Act 2018, and HMRC data protection policies with DPIA approval before launch.

**Rationale**: Handling citizen tax data (OFFICIAL-SENSITIVE classification) carries significant legal and reputational risk. Non-compliance can result in ICO enforcement action and citizen harm.

**Success Criteria**:
- DPIA completed and approved by HMRC Data Protection Officer before private beta
- Privacy notice published on GOV.UK
- Data subject rights procedures implemented (access, rectification, erasure)
- Explicit consent mechanism for chat transcript storage
- 7-year retention policy with automated deletion

**Priority**: MUST_HAVE

**Stakeholder**: HMRC Data Protection Officer, Legal Team

**Aligns with Principle**: #7 Data Sovereignty and UK GDPR Compliance (NON-NEGOTIABLE)

---

## Functional Requirements

### User Personas

#### Persona 1: Self-Assessment Taxpayer (Sarah)

- **Role**: Self-employed freelance graphic designer
- **Age**: 34
- **Goals**: Complete Self Assessment tax return accurately and on time, understand allowable expenses
- **Pain Points**: Tax jargon confusing, unsure which expenses can be claimed, long helpline wait times
- **Technical Proficiency**: Medium (comfortable with websites, basic digital services)
- **Accessibility Needs**: None
- **Languages**: English

#### Persona 2: PAYE Employee with Side Income (James)

- **Role**: Full-time marketing manager with rental income
- **Age**: 42
- **Goals**: Understand tax obligations for rental income, whether Self Assessment needed
- **Pain Points**: Unsure if rental income requires Self Assessment, confused by PAYE vs Self Assessment rules
- **Technical Proficiency**: High (uses multiple digital services daily)
- **Accessibility Needs**: None
- **Languages**: English

#### Persona 3: Retired Citizen (Margaret)

- **Role**: Retired teacher receiving state pension and private pension
- **Age**: 68
- **Goals**: Understand pension tax, Personal Allowance, potential tax refunds
- **Pain Points**: Digital services intimidating, prefers phone but hates waiting, needs larger text
- **Technical Proficiency**: Low (limited digital experience, prefers simple interfaces)
- **Accessibility Needs**: Larger font sizes, high contrast mode, clear navigation
- **Languages**: English

#### Persona 4: Welsh-Speaking Citizen (Dafydd)

- **Role**: Small business owner in Wales
- **Age**: 45
- **Goals**: Access tax guidance in Welsh, understand VAT requirements for small business
- **Pain Points**: Most digital services not available in Welsh, must use English helpline
- **Technical Proficiency**: Medium
- **Accessibility Needs**: Welsh language interface (legal requirement)
- **Languages**: Welsh (preferred), English

#### Persona 5: Visually Impaired Citizen (Priya)

- **Role**: University lecturer who is blind
- **Age**: 38
- **Goals**: Complete tax return independently using screen reader
- **Pain Points**: Many websites inaccessible, PDF forms unusable with screen reader
- **Technical Proficiency**: High (expert screen reader user, uses assistive technology daily)
- **Accessibility Needs**: Full screen reader compatibility (JAWS), keyboard navigation, ARIA labels
- **Languages**: English

---

### Use Cases

#### UC-1: Simple Tax Query (No Authentication)

**Actor**: Any citizen (unauthenticated)

**Preconditions**:
- Citizen has access to internet and web browser
- ChatBot service is available

**Main Flow**:
1. Citizen navigates to ChatBot on GOV.UK
2. System displays welcome message and privacy notice
3. Citizen types tax question in natural language (e.g., "What is the Personal Allowance for 2024-25?")
4. System retrieves relevant HMRC guidance documents using RAG
5. System generates response with answer and source citation
6. Citizen reviews response and clicks "Was this helpful?" (thumbs up/down)
7. System logs feedback and offers follow-up options

**Postconditions**:
- Citizen has received accurate tax guidance
- Conversation logged for audit (anonymized for unauthenticated users)
- Feedback recorded for quality monitoring

**Alternative Flows**:
- **Alt 3a**: If citizen query is ambiguous, system asks clarifying questions
- **Alt 5a**: If confidence score <70%, system offers to escalate to human agent

**Exception Flows**:
- **Ex 1**: If HMRC backend unavailable, system responds with cached guidance and disclaimer
- **Ex 2**: If prompt injection detected, system blocks request and logs security event

**Business Rules**:
- Response time <2 seconds (p95)
- Every response must cite source document
- No PII collected from unauthenticated users

**Priority**: CRITICAL

---

#### UC-2: Personalized Tax Query (Authenticated)

**Actor**: Authenticated citizen via Government Gateway

**Preconditions**:
- Citizen has Government Gateway account
- Citizen has consented to ChatBot terms and privacy policy

**Main Flow**:
1. Citizen clicks "Sign in with Government Gateway" on ChatBot
2. System redirects to Government Gateway OAuth flow
3. Citizen completes MFA authentication
4. System retrieves citizen profile (name, UTR, tax status)
5. Citizen asks personalized question (e.g., "Have I paid enough tax this year?")
6. System retrieves citizen's tax records from HMRC backend APIs
7. System generates personalized response based on actual tax data
8. Citizen reviews response with source citations

**Postconditions**:
- Citizen has received personalized guidance based on their tax records
- Conversation logged with citizen ID (audit trail)
- Session maintained for follow-up questions

**Alternative Flows**:
- **Alt 3a**: If Government Gateway unavailable, system offers unauthenticated guidance only
- **Alt 6a**: If tax records unavailable, system explains limitation and offers generic guidance

**Exception Flows**:
- **Ex 1**: If session timeout, system prompts re-authentication with session resumption option
- **Ex 2**: If unauthorized data access attempted, system blocks and alerts SOC

**Business Rules**:
- Session timeout: 15 minutes inactivity
- Absolute session timeout: 4 hours
- Re-authentication required for sensitive operations

**Priority**: CRITICAL

---

#### UC-3: Human Escalation

**Actor**: Citizen (authenticated or unauthenticated)

**Preconditions**:
- ChatBot cannot resolve citizen query (complex scenario, low confidence, citizen request)
- Human agent queue is available

**Main Flow**:
1. System detects escalation trigger (confidence <70%, citizen requests human, complex query detected)
2. System informs citizen: "I'll connect you with a tax specialist who can help"
3. System collects citizen contact preference (callback, webchat with human)
4. System creates ServiceNow ticket with conversation summary
5. System provides reference number and expected wait time
6. Human agent receives ticket with full context (conversation history, citizen profile if authenticated)
7. Human agent contacts citizen through preferred channel

**Postconditions**:
- Citizen query escalated to appropriate human agent
- ServiceNow ticket created with audit trail
- Conversation context preserved for human agent

**Alternative Flows**:
- **Alt 3a**: If citizen prefers to continue with ChatBot, system offers alternative phrasing suggestions
- **Alt 6a**: If outside helpline hours, system schedules callback for next business day

**Exception Flows**:
- **Ex 1**: If ServiceNow unavailable, system provides helpline phone number as fallback
- **Ex 2**: If human queue full, system provides expected callback time

**Business Rules**:
- Escalation rate target: <5% of queries
- Human callback within 2 business hours (SLA)
- Full conversation context passed to human agent

**Priority**: HIGH

---

#### UC-4: Welsh Language Interaction

**Actor**: Welsh-speaking citizen (Dafydd persona)

**Preconditions**:
- Citizen selects Welsh language preference
- Welsh language model/prompts configured

**Main Flow**:
1. Citizen clicks "Cymraeg" language toggle on ChatBot interface
2. System switches interface to Welsh language
3. Citizen types question in Welsh
4. System detects Welsh language input
5. System retrieves Welsh-language HMRC guidance (or translates English guidance)
6. System generates response in Welsh with Welsh source citations where available
7. Citizen reviews Welsh response

**Postconditions**:
- Citizen has received guidance in Welsh language
- Conversation logged with language preference

**Alternative Flows**:
- **Alt 5a**: If Welsh guidance not available, system provides English guidance with disclaimer and offers translation
- **Alt 6a**: If citizen switches to English mid-conversation, system continues in English

**Exception Flows**:
- **Ex 1**: If Welsh language model unavailable, system apologizes in Welsh and offers English fallback

**Business Rules**:
- Welsh language support mandatory (Welsh Language Act 1993)
- Welsh content parity with English where HMRC guidance exists in Welsh
- Welsh speakers can escalate to Welsh-speaking human agents

**Priority**: MUST_HAVE (Legal requirement)

---

#### UC-5: Accessibility-First Interaction

**Actor**: Visually impaired citizen using screen reader (Priya persona)

**Preconditions**:
- Citizen using JAWS, NVDA, or VoiceOver screen reader
- ChatBot interface meets WCAG 2.2 AA standards

**Main Flow**:
1. Citizen navigates to ChatBot using keyboard (Tab, Enter, Escape)
2. Screen reader announces page structure, landmarks, and input field
3. Citizen uses keyboard to focus on text input
4. Screen reader announces "Type your tax question here"
5. Citizen types question using keyboard
6. Citizen presses Enter to submit
7. Screen reader announces "Response received" and reads response text
8. Citizen navigates response using arrow keys, headings announced
9. Citizen navigates to feedback button using Tab
10. Screen reader announces "Was this helpful? Button"

**Postconditions**:
- Citizen has completed full interaction using only keyboard and screen reader
- All content accessible to assistive technology

**Alternative Flows**:
- **Alt 7a**: If response contains links, screen reader announces link destinations
- **Alt 7b**: If response contains complex formatting, screen reader conveys structure appropriately

**Exception Flows**:
- **Ex 1**: If dynamic content updates, ARIA live regions announce changes to screen reader

**Business Rules**:
- All interactive elements keyboard accessible
- All images have descriptive alt text
- Focus management clear and logical
- No content conveyed by color alone
- Sufficient color contrast (4.5:1 for normal text, 3:1 for large text)

**Priority**: MUST_HAVE (Legal requirement)

---

### Functional Requirements Detail

#### FR-1: Conversational Interface

**Description**: System MUST provide a web-based conversational chat interface where citizens can ask tax questions in natural language and receive guidance.

**Relates To**: BR-2, BR-3, UC-1, UC-2

**Acceptance Criteria**:
- [ ] Given a citizen visits the ChatBot URL, when the page loads, then a chat interface is displayed with welcome message
- [ ] Given a citizen types a message and presses Enter, when the message is submitted, then the system processes the query and displays a response
- [ ] Given a response is generated, when displayed, then it includes the AI response text and source citations
- [ ] Edge case: When citizen submits empty message, system displays helpful prompt rather than error

**Data Requirements**:
- **Inputs**: Natural language text query (max 1000 characters), session context
- **Outputs**: AI-generated response text, source citations, confidence score (internal), response time
- **Validations**: Input sanitization for XSS/injection, character limit enforcement, language detection

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Dependencies**: FR-2 (RAG), FR-3 (LLM), INT-5 (AWS Bedrock)

**Assumptions**: Citizens have JavaScript-enabled browsers (Chrome, Firefox, Safari, Edge - last 2 versions)

---

#### FR-2: Retrieval-Augmented Generation (RAG) Implementation

**Description**: System MUST implement RAG architecture to retrieve relevant HMRC guidance documents and ground LLM responses in authoritative sources.

**Relates To**: BR-3, BR-6, UC-1, Principle #5 (Responsible AI)

**Acceptance Criteria**:
- [ ] Given a citizen query, when processed, then system retrieves top-5 relevant documents from vector database
- [ ] Given documents retrieved, when passed to LLM, then response is grounded in retrieved content
- [ ] Given a response generated, when displayed, then it cites specific source documents (HMRC guidance URL, legislation section)
- [ ] Edge case: When no relevant documents found (score <0.7), system returns "I don't have information on that topic" with escalation option

**Data Requirements**:
- **Inputs**: Query text, query embedding (768 dimensions), search parameters (top-k, similarity threshold)
- **Outputs**: Retrieved documents (text chunks, metadata, relevance scores), document citations
- **Validations**: Minimum relevance threshold (0.7), maximum retrieval latency (500ms)

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Dependencies**: INT-2 (HMRC CMS), Knowledge base embedding pipeline

**Assumptions**: HMRC guidance documents available in structured format for embedding

---

#### FR-3: LLM Response Generation

**Description**: System MUST use an approved LLM (AWS Bedrock Claude 3.5 Sonnet) to generate natural language responses based on retrieved documents.

**Relates To**: BR-3, FR-2, INT-5

**Acceptance Criteria**:
- [ ] Given retrieved documents and citizen query, when LLM invoked, then response is generated in <1.5 seconds
- [ ] Given response generated, when returned, then it is in Plain English (reading age 9)
- [ ] Given response generated, when checked, then it contains no hallucinated information (validated against retrieved documents)
- [ ] Edge case: When LLM times out (>30s), system returns apologetic message with retry option

**Data Requirements**:
- **Inputs**: System prompt, retrieved documents, citizen query, conversation history (last 10 messages)
- **Outputs**: Generated response text, confidence score, token usage
- **Validations**: Response length limit (2000 tokens), profanity filter, PII detection and redaction

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Dependencies**: INT-5 (AWS Bedrock), Guardrails configuration

**Assumptions**: AWS Bedrock Claude 3.5 Sonnet available in UK region with acceptable latency

---

#### FR-4: Source Citation Display

**Description**: Every AI response MUST display source citations linking to authoritative HMRC guidance or legislation.

**Relates To**: BR-6, Principle #5 (Responsible AI), Principle #8 (Data Quality)

**Acceptance Criteria**:
- [ ] Given a response displayed, when citizen views it, then at least one source citation is visible
- [ ] Given a citation displayed, when citizen clicks it, then they are directed to the source document on GOV.UK/legislation.gov.uk
- [ ] Given multiple sources used, when response displayed, then all relevant sources are listed
- [ ] Edge case: When source document URL has changed, system displays fallback search link

**Data Requirements**:
- **Inputs**: Retrieved document metadata (title, URL, publication date, section reference)
- **Outputs**: Formatted citation with hyperlink, publication date, document type
- **Validations**: URL validation, dead link detection (async), citation format consistency

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: FR-2 (RAG retrieves source metadata)

**Assumptions**: HMRC guidance documents have stable, linkable URLs

---

#### FR-5: Government Gateway Authentication

**Description**: System MUST integrate with Government Gateway to authenticate citizens for personalized tax guidance.

**Relates To**: BR-7, UC-2, INT-1, Principle #3 (Security by Design)

**Acceptance Criteria**:
- [ ] Given a citizen clicks "Sign in", when redirected to Government Gateway, then OAuth 2.0 flow completes successfully
- [ ] Given authentication successful, when citizen returns, then their identity is verified and session established
- [ ] Given authentication fails, when citizen returns, then appropriate error message displayed with retry option
- [ ] Edge case: When Government Gateway unavailable, system offers unauthenticated mode with limitations disclaimer

**Data Requirements**:
- **Inputs**: OAuth authorization code, state parameter (CSRF protection)
- **Outputs**: Access token, refresh token, citizen profile (name, UTR, Government Gateway ID)
- **Validations**: Token signature validation, token expiry checks, PKCE code verifier

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Dependencies**: INT-1 (Government Gateway), Security architecture

**Assumptions**: Government Gateway OAuth 2.0 endpoint available with HMRC-approved scopes

---

#### FR-6: Human Agent Escalation

**Description**: System MUST provide mechanism to escalate complex queries to human agents when ChatBot cannot resolve.

**Relates To**: BR-3, UC-3, INT-4

**Acceptance Criteria**:
- [ ] Given confidence score <70%, when response generated, then system offers escalation to human agent
- [ ] Given citizen requests human ("speak to someone"), when detected, then escalation flow initiated
- [ ] Given escalation initiated, when completed, then ServiceNow ticket created with conversation context
- [ ] Edge case: When outside helpline hours, system schedules callback for next business day

**Data Requirements**:
- **Inputs**: Conversation history, citizen profile (if authenticated), escalation reason, contact preference
- **Outputs**: ServiceNow ticket ID, reference number, estimated callback time
- **Validations**: Ticket creation confirmed, SLA timer started

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: INT-4 (ServiceNow), Helpline integration

**Assumptions**: HMRC ServiceNow instance has API for ticket creation

---

#### FR-7: Feedback Collection

**Description**: System MUST collect citizen feedback on response helpfulness to measure AI accuracy and drive improvements.

**Relates To**: BR-3, Principle #6 (Observability)

**Acceptance Criteria**:
- [ ] Given a response displayed, when citizen views it, then thumbs up/down feedback buttons are visible
- [ ] Given citizen clicks feedback, when submitted, then feedback recorded with response ID
- [ ] Given negative feedback, when submitted, then optional free-text field offered for details
- [ ] Edge case: When feedback already submitted for a response, buttons are disabled

**Data Requirements**:
- **Inputs**: Response ID, feedback value (positive/negative), optional comment, timestamp
- **Outputs**: Feedback record, aggregated accuracy metrics
- **Validations**: One feedback per response per session, comment length limit (500 chars)

**Priority**: MUST_HAVE

**Complexity**: LOW

**Dependencies**: None

**Assumptions**: Citizens willing to provide feedback (target: >20% feedback rate)

---

#### FR-8: Conversation History Management

**Description**: System MUST maintain conversation context within a session and allow citizens to view/download their conversation history.

**Relates To**: BR-7, UC-2, Principle #7 (Data Sovereignty)

**Acceptance Criteria**:
- [ ] Given ongoing conversation, when citizen asks follow-up question, then system uses previous context
- [ ] Given authenticated citizen, when they request history, then past conversations are retrievable
- [ ] Given citizen requests transcript download, when clicked, then PDF/text file downloaded
- [ ] Edge case: When session expires, system prompts to save conversation before timeout

**Data Requirements**:
- **Inputs**: Session ID, conversation messages (query/response pairs), timestamps
- **Outputs**: Conversation thread display, downloadable transcript (PDF, TXT)
- **Validations**: Session token validation, conversation ownership verification

**Priority**: SHOULD_HAVE

**Complexity**: MEDIUM

**Dependencies**: FR-5 (Authentication for history retrieval)

**Assumptions**: Citizens consent to conversation storage per privacy notice

---

#### FR-9: Plain English Content

**Description**: All ChatBot responses MUST be written in Plain English following GOV.UK style guide (average reading age 9).

**Relates To**: BR-5, Principle #4 (Accessibility-First)

**Acceptance Criteria**:
- [ ] Given a response generated, when analyzed, then Flesch-Kincaid grade level is ≤9
- [ ] Given tax jargon in source documents, when response generated, then plain language alternatives are used
- [ ] Given response contains necessary technical terms, when displayed, then terms are defined in context
- [ ] Edge case: When legislation requires specific wording, original text is quoted with plain explanation

**Data Requirements**:
- **Inputs**: LLM system prompt with Plain English guidelines, GOV.UK style guide rules
- **Outputs**: Response text meeting readability standards
- **Validations**: Automated readability score check, content designer review for sample responses

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: FR-3 (LLM prompt engineering)

**Assumptions**: LLM can be prompted effectively to produce Plain English output

---

#### FR-10: Welsh Language Support

**Description**: System MUST support Welsh language for interface and responses per Welsh Language Act 1993.

**Relates To**: BR-5, UC-4, Principle #4 (Accessibility-First)

**Acceptance Criteria**:
- [ ] Given citizen selects Welsh, when interface loads, then all UI elements are in Welsh
- [ ] Given citizen types in Welsh, when detected, then response generated in Welsh
- [ ] Given Welsh HMRC guidance available, when relevant, then Welsh sources are cited
- [ ] Edge case: When Welsh content unavailable, system clearly indicates English translation with Welsh apology

**Data Requirements**:
- **Inputs**: Language preference (en/cy), Welsh-language prompts, Welsh knowledge base subset
- **Outputs**: Welsh interface text, Welsh responses, Welsh source citations
- **Validations**: Welsh language quality review by native speaker, Welsh language toggle persistence

**Priority**: MUST_HAVE (Legal requirement)

**Complexity**: HIGH

**Dependencies**: Welsh content availability, Translation capability or Welsh LLM

**Assumptions**: Sufficient Welsh HMRC content exists for embedding, or translation quality is acceptable

---

#### FR-11: GOV.UK Design System Integration

**Description**: ChatBot interface MUST use GOV.UK Design System components for consistency with government digital services.

**Relates To**: BR-4, BR-5, Principle #4 (Accessibility-First)

**Acceptance Criteria**:
- [ ] Given ChatBot interface, when inspected, then GOV.UK Design System components are used (GDS Transport font, colour palette, spacing)
- [ ] Given interactive elements, when rendered, then GOV.UK form components are used (buttons, inputs, error messages)
- [ ] Given page layout, when viewed, then GOV.UK page template structure is followed
- [ ] Edge case: When custom chat components needed, they follow GOV.UK design patterns and accessibility guidelines

**Data Requirements**:
- **Inputs**: GOV.UK Design System component library (gov.uk-frontend npm package)
- **Outputs**: Accessible, consistent UI meeting GDS standards
- **Validations**: GDS design review, automated accessibility testing with GDS tooling

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: Frontend framework supporting GOV.UK Design System (React compatible)

**Assumptions**: ChatBot can integrate with GOV.UK header/footer if hosted on GOV.UK subdomain

---

## Non-Functional Requirements (NFRs)

### Performance Requirements

#### NFR-P-1: Response Time

**Requirement**: System MUST respond to citizen queries within 2 seconds (95th percentile) under normal load.

- Web page initial load time: <3 seconds (LCP)
- Chat message response time: <2 seconds (p95)
- API response time (internal): <200ms (p95) excluding LLM time
- LLM response time: <1.5 seconds (p95)
- Database query time: <100ms (average)

**Measurement Method**: Application Performance Monitoring (APM) via CloudWatch/Datadog, synthetic monitoring

**Load Conditions**:
- Normal load: 1,000 concurrent users, 50 messages/second
- Peak load: 5,000 concurrent users, 250 messages/second (January tax deadline)
- Data volume: 100,000 knowledge base documents, 10M conversation records

**Priority**: CRITICAL

**Aligns with Principle**: #12 Performance and Efficiency

---

#### NFR-P-2: Throughput

**Requirement**: System MUST handle 500 messages per second at peak load (10x normal load) during tax deadline periods.

**Scalability**: Must auto-scale horizontally to handle 10x traffic spikes within 5 minutes

**Growth Projections**:
- Year 1: 5M conversations, 50M messages
- Year 2: 10M conversations, 100M messages
- Year 3: 15M conversations, 150M messages

**Priority**: CRITICAL

**Aligns with Principle**: #1 Government Cloud-First Architecture (scalability)

---

### Availability and Resilience Requirements

#### NFR-A-1: Availability Target

**Requirement**: System MUST achieve 99.9% uptime during business hours (08:00-20:00 GMT Monday-Friday).

- Maximum planned downtime: 4 hours/month for maintenance (outside business hours)
- Maximum unplanned downtime: 43.8 minutes/month (99.9% SLA)
- Zero planned downtime during tax deadline periods (1-31 January)

**Maintenance Windows**: Sundays 02:00-06:00 GMT (approved maintenance window)

**Priority**: CRITICAL

**Aligns with Principle**: #13 Availability and Resilience

---

#### NFR-A-2: Disaster Recovery

**RPO (Recovery Point Objective)**: Maximum acceptable data loss = 1 hour

**RTO (Recovery Time Objective)**: Maximum acceptable downtime = 15 minutes

**Backup Requirements**:
- Backup frequency: Hourly for transaction data, daily for full database
- Backup retention: 90 days operational, 7 years for audit data (archived to Glacier)
- Geographic backup location: Secondary UK region (eu-west-1) for data sovereignty

**Failover Requirements**:
- Automatic failover to secondary AZ: YES
- Failover time: <5 minutes for AZ failure
- Cross-region failover: Manual (RTO 15 minutes)

**Priority**: CRITICAL

**Aligns with Principle**: #13 Availability and Resilience

---

#### NFR-A-3: Fault Tolerance

**Requirement**: System MUST gracefully degrade when external dependencies fail (Government Gateway, HMRC Backend APIs, AWS Bedrock).

**Resilience Patterns Required**:
- [x] Circuit breaker for Government Gateway (open after 5 failures in 30 seconds)
- [x] Circuit breaker for HMRC Backend APIs (open after 3 failures in 60 seconds)
- [x] Circuit breaker for AWS Bedrock (open after 3 failures in 30 seconds)
- [x] Retry with exponential backoff (max 3 retries, base 100ms)
- [x] Timeout on all network calls (API: 5s, LLM: 30s, Database: 5s)
- [x] Bulkhead isolation (separate thread pools for auth, LLM, backend)
- [x] Graceful degradation (cached guidance if backends unavailable)
- [x] Rate limiting (500 req/hour per citizen, 10,000 req/hour system)

**Priority**: CRITICAL

**Aligns with Principle**: #13 Availability and Resilience

---

### Scalability Requirements

#### NFR-S-1: Horizontal Scaling

**Requirement**: System MUST support horizontal scaling without code changes to handle 10x traffic growth.

**Growth Projections**:
- Year 1: 1,000 peak concurrent users
- Year 2: 3,000 peak concurrent users
- Year 3: 5,000 peak concurrent users

**Scaling Triggers**:
- Auto-scale up: CPU >70% or memory >80% for 5 minutes
- Auto-scale down: CPU <30% and memory <40% for 15 minutes
- Minimum instances: 3 (multi-AZ)
- Maximum instances: 50

**Priority**: HIGH

**Aligns with Principle**: #1 Government Cloud-First Architecture

---

#### NFR-S-2: Data Volume Scaling

**Requirement**: System MUST handle data growth to 500TB over 7 years (retention requirement).

**Data Growth Projections**:
- Year 1: 10TB (conversations, audit logs, knowledge base)
- Year 3: 50TB
- Year 7: 500TB (with 7-year retention)

**Data Archival Strategy**:
- Hot storage: Last 90 days (SSD, instant access)
- Warm storage: 90 days - 1 year (S3 Standard-IA)
- Cold storage: 1-7 years (S3 Glacier Deep Archive)
- Deletion: Automatic after 7 years per retention policy

**Priority**: HIGH

**Aligns with Principle**: #7 Data Sovereignty and UK GDPR Compliance

---

### Security Requirements

#### NFR-SEC-1: Authentication

**Requirement**: All administrative access MUST use MFA. Citizen access via Government Gateway OAuth 2.0.

**Multi-Factor Authentication (MFA)**:
- Required for: All administrative/staff access, privileged operations
- MFA methods: Authenticator app (TOTP), hardware token (YubiKey for admin)
- Government Gateway: Handles citizen MFA (HMRC standard)

**Session Management**:
- Session timeout: 15 minutes of inactivity (citizen), 30 minutes (admin)
- Absolute session timeout: 4 hours (citizen), 8 hours (admin)
- Re-authentication required for: Downloading conversation history, viewing tax records

**Priority**: CRITICAL

**Aligns with Principle**: #3 Security by Design - Zero Trust (NON-NEGOTIABLE)

---

#### NFR-SEC-2: Authorization

**Requirement**: Role-based access control (RBAC) with least privilege principle for all system access.

**Roles**:
- **Citizen**: View own conversations, submit queries, provide feedback
- **Content Manager**: Manage knowledge base, review content
- **Support Agent**: View escalated conversations, resolve tickets
- **System Admin**: System configuration, user management
- **Auditor**: Read-only access to audit logs
- **Security Analyst**: Security logs, incident investigation

**Privilege Elevation**: Break-glass procedure for emergency access (logged, time-limited, approved by CISO)

**Priority**: CRITICAL

**Aligns with Principle**: #3 Security by Design - Zero Trust (NON-NEGOTIABLE)

---

#### NFR-SEC-3: Data Encryption

**Requirement**: All data encrypted in transit (TLS 1.3+) and at rest (AES-256).

- Data in transit: TLS 1.3 mandatory, TLS 1.2 minimum (legacy clients)
- Data at rest: AES-256-GCM for all data stores
- Key management: AWS KMS with customer-managed keys (CMK)
- Key rotation: Automatic annual rotation

**Encryption Scope**:
- [x] Database encryption at rest (RDS PostgreSQL with KMS)
- [x] Backup encryption (S3 server-side encryption with KMS)
- [x] File storage encryption (S3 SSE-KMS)
- [x] Application-level field encryption for PII (NI numbers, UTR)
- [x] Vector database encryption (OpenSearch encryption at rest)

**Priority**: CRITICAL

**Aligns with Principle**: #3 Security by Design - Zero Trust (NON-NEGOTIABLE)

---

#### NFR-SEC-4: Secrets Management

**Requirement**: No secrets (API keys, passwords, certificates) in code or configuration files.

**Secrets Storage**: AWS Secrets Manager for all credentials

**Secrets Scope**:
- Database credentials
- Government Gateway OAuth client credentials
- AWS Bedrock API keys
- ServiceNow API credentials
- Encryption keys (via KMS)

**Secrets Rotation**: Automatic rotation every 90 days

**Priority**: CRITICAL

**Aligns with Principle**: #3 Security by Design - Zero Trust (NON-NEGOTIABLE)

---

#### NFR-SEC-5: Vulnerability Management

**Requirement**: Continuous vulnerability scanning with defined remediation SLAs.

**Scanning Requirements**:
- Dependency scanning in CI/CD: Snyk, AWS Inspector (block on critical/high)
- Static application security testing (SAST): Semgrep, SonarQube
- Dynamic application security testing (DAST): OWASP ZAP
- Container image scanning: AWS ECR scanning
- Infrastructure scanning: tfsec, Checkov for Terraform
- Penetration testing: Annually by CHECK-approved supplier

**Remediation SLA**:
- Critical vulnerabilities: 24 hours
- High vulnerabilities: 7 days
- Medium vulnerabilities: 30 days
- Low vulnerabilities: 90 days

**Priority**: CRITICAL

**Aligns with Principle**: #3 Security by Design, #17 CI/CD

---

#### NFR-SEC-6: Prompt Injection Defense

**Requirement**: System MUST detect and block prompt injection attacks attempting to manipulate LLM responses.

**Defense Mechanisms**:
- Input sanitization: Remove/escape special characters and instruction patterns
- Output validation: Check response against expected format and content policies
- Guardrails: AWS Bedrock Guardrails for content filtering
- Monitoring: Detect anomalous query patterns, flag for security review
- Rate limiting: Per-user query limits to prevent automated attacks

**Response to Detected Attack**:
- Block malicious query (do not send to LLM)
- Return generic error message (do not reveal detection)
- Log security event with full context
- Alert SOC for pattern analysis

**Priority**: CRITICAL

**Aligns with Principle**: #5 Responsible AI and Algorithmic Transparency

---

### Compliance and Regulatory Requirements

#### NFR-C-1: UK GDPR Compliance

**Applicable Regulations**: UK GDPR, Data Protection Act 2018, HMRC Data Protection Policy

**Compliance Requirements**:
- [x] Lawful basis documented (public task for HMRC guidance)
- [x] Privacy notice published on GOV.UK
- [x] Data subject rights procedures (access: 30 days, erasure: 30 days, portability: 30 days)
- [x] Consent management for optional data collection (conversation history storage)
- [x] Data breach notification within 72 hours (ICO) / 24 hours (internal)
- [x] Data Protection Impact Assessment (DPIA) completed and approved
- [x] Record of Processing Activities (ROPA) maintained

**Data Residency**: All citizen data processed and stored in UK (AWS eu-west-2)

**Data Retention**:
- Conversation data: 7 years (tax records requirement), then automatic deletion
- Anonymized analytics: Indefinite (no PII)
- Audit logs: 7 years

**Priority**: CRITICAL

**Aligns with Principle**: #7 Data Sovereignty and UK GDPR Compliance (NON-NEGOTIABLE)

---

#### NFR-C-2: Audit Logging

**Requirement**: Comprehensive audit trail for compliance, forensics, and HMG records management.

**Audit Log Contents** (W5H1 format):
- Who: User identity (Government Gateway ID, AWS IAM role, service identity)
- What: Action performed (query, response, authentication, configuration change)
- When: Timestamp (UTC, ISO 8601, millisecond precision)
- Where: System component (API Gateway, Lambda, RDS, OpenSearch)
- Why: Context (request ID, conversation ID, session ID, trace ID)
- Result: Success/failure with error code and details

**Mandatory Audit Events**:
- Citizen authentication (login/logout, MFA events)
- Conversation start/end with conversation ID
- Every query and response pair
- HMRC backend API calls (tax record access)
- PII data access
- Administrative actions (config changes, user management)
- Security events (auth failures, rate limits, prompt injection attempts)

**Log Retention**: 7 years (immutable storage using S3 Object Lock)

**Log Integrity**: Tamper-evident logging (CloudTrail log file validation, cryptographic hashing)

**SIEM Integration**: Real-time streaming to HMRC Splunk instance

**Priority**: CRITICAL

**Aligns with Principle**: #6 Observability and Operational Excellence

---

#### NFR-C-3: ATRS Reporting

**Requirement**: System MUST generate and maintain ATRS record per UK Government Algorithmic Transparency Standard.

**ATRS Record Contents**:
- Algorithm name and description
- Owner and contact details
- Purpose and scope
- Data sources and training data
- Model type and architecture
- Accuracy metrics and testing methodology
- Bias testing results
- Human oversight mechanisms
- Limitations and risks
- Update history

**Reporting Requirements**:
- Initial ATRS record before public beta
- Updates within 30 days of significant model changes
- Annual review and republication

**Priority**: MUST_HAVE

**Aligns with Principle**: #5 Responsible AI and Algorithmic Transparency (NON-NEGOTIABLE)

---

### Usability Requirements

#### NFR-U-1: User Experience

**Requirement**: System MUST be intuitive for users with low digital proficiency (Margaret persona).

**UX Standards**:
- Consistent with GOV.UK Design System
- Maximum 3 clicks to submit a query
- Clear error messages with recovery guidance
- Progressive disclosure (simple first, details on demand)
- Mobile responsive design (320px minimum width)
- Browser support: Chrome, Firefox, Safari, Edge (last 2 versions)

**User Onboarding**:
- Welcome message explaining ChatBot capabilities and limitations
- Example queries to help users get started
- Contextual help for complex features (authentication, history)

**Priority**: HIGH

**Aligns with Principle**: #4 Accessibility-First Design

---

#### NFR-U-2: Accessibility (WCAG 2.2 AA)

**Requirement**: WCAG 2.2 Level AA compliance (legal requirement)

**Accessibility Features**:
- [x] Keyboard navigation for all functions (Tab, Enter, Escape, Arrow keys)
- [x] Screen reader compatibility (ARIA labels, landmarks, live regions)
- [x] High contrast mode (meets 4.5:1 ratio for normal text, 3:1 for large)
- [x] Adjustable font sizes (up to 200% zoom without horizontal scroll)
- [x] Alt text for all images and icons
- [x] Focus indicators clearly visible
- [x] No content conveyed by color alone
- [x] Skip to main content link
- [x] Logical heading hierarchy (h1-h6)
- [x] Form labels associated with inputs

**Testing Requirements**:
- Automated: axe-core, Pa11y in CI/CD pipeline
- Manual: Screen reader testing (JAWS, NVDA, VoiceOver)
- User testing: Minimum 5 disabled users per research round

**Priority**: CRITICAL (Legal requirement)

**Aligns with Principle**: #4 Accessibility-First Design (NON-NEGOTIABLE)

---

#### NFR-U-3: Welsh Language Support

**Requirement**: Full Welsh language support for interface and content (legal requirement)

**Localization Scope**:
- [x] UI text translation (all interface elements)
- [x] Welsh responses for Welsh queries
- [x] Welsh source citations where available
- [x] Welsh accessibility features (screen reader pronunciation)
- [x] Date/number formatting per Welsh conventions

**Welsh Language Parity**:
- Welsh interface functionally equivalent to English
- Welsh content quality reviewed by native Welsh speaker
- Welsh language toggle prominently displayed

**Priority**: CRITICAL (Legal requirement - Welsh Language Act 1993)

**Aligns with Principle**: #4 Accessibility-First Design

---

### Maintainability and Supportability Requirements

#### NFR-M-1: Observability

**Requirement**: Comprehensive instrumentation for monitoring, troubleshooting, and capacity planning.

**Telemetry Requirements**:
- **Logging**: Structured JSON logs to CloudWatch Logs, streamed to HMRC Splunk
- **Metrics**: CloudWatch Metrics, Prometheus-compatible exposition for custom metrics
- **Tracing**: AWS X-Ray / OpenTelemetry for distributed tracing
- **Dashboards**: Real-time operational dashboards (CloudWatch, Grafana)
- **Alerts**: SLO-based alerting with PagerDuty integration

**Key Metrics (RED)**:
- Rate: Requests per second, messages per minute, conversations per hour
- Errors: Error rate by type (4xx, 5xx), LLM failures, integration failures
- Duration: Response time (p50, p95, p99), LLM latency, database latency

**Business Metrics**:
- Conversations per day/week/month
- Helpline deflection rate (vs baseline)
- Citizen satisfaction (feedback scores)
- Escalation rate to human agents
- Top query topics

**Log Levels**: DEBUG, INFO, WARN, ERROR, FATAL (DEBUG disabled in production)

**Priority**: HIGH

**Aligns with Principle**: #6 Observability and Operational Excellence

---

#### NFR-M-2: Documentation

**Requirement**: Comprehensive documentation for operators, developers, and content managers.

**Documentation Types**:
- [x] Architecture documentation (C4 model diagrams)
- [x] API documentation (OpenAPI 3.0 specs for all APIs)
- [x] Runbooks for operational procedures (ServiceNow knowledge articles)
- [x] Troubleshooting guides (common issues and resolutions)
- [x] User guides for content managers (knowledge base management)
- [x] Admin guides (system configuration, user management)
- [x] Security documentation (threat model, security controls)

**Documentation Format**: Markdown in Git repository, published to internal wiki

**Documentation Currency**: Updated within 5 working days of code/config changes

**Priority**: HIGH

**Aligns with Principle**: #14 Maintainability and Evolvability

---

#### NFR-M-3: Operational Runbooks

**Requirement**: Runbooks for common operational tasks and incident response.

**Runbook Coverage**:
- [x] Deployment procedures (blue/green, canary, rollback)
- [x] Rollback procedures (automated and manual)
- [x] Backup and restore procedures (database, knowledge base)
- [x] Incident response for common failures (LLM timeout, auth failure, high error rate)
- [x] Scaling procedures (manual scale-up during anticipated peaks)
- [x] Disaster recovery procedures (AZ failure, region failure)
- [x] Knowledge base update procedures (content refresh, re-embedding)
- [x] Security incident response (prompt injection, data breach)

**Runbook Format**: ServiceNow knowledge articles with step-by-step instructions

**Priority**: HIGH

**Aligns with Principle**: #6 Observability and Operational Excellence

---

### Portability and Interoperability Requirements

#### NFR-I-1: API Standards

**Requirement**: All APIs MUST follow OpenAPI 3.0 standards with consistent design patterns.

**API Design Principles**:
- RESTful design with standard HTTP methods (GET, POST, PUT, DELETE)
- JSON request/response format (application/json)
- Versioning via URL path (/v1/, /v2/)
- Consistent error response format (RFC 7807 Problem Details)
- Pagination for list endpoints (limit/offset)
- Filtering and sorting via query parameters
- HATEOAS links for discoverability (where appropriate)

**API Documentation**: OpenAPI 3.0 specification published to API developer portal

**Priority**: HIGH

**Aligns with Principle**: #2 API-First Integration, #10 Loose Coupling

---

#### NFR-I-2: Integration Capabilities

**Requirement**: System MUST support integration with HMRC ecosystem and external services.

**Integration Patterns**:
- [x] RESTful API integration (synchronous)
- [x] Event-driven integration (Amazon EventBridge for async events)
- [x] OAuth 2.0 / OpenID Connect (Government Gateway)
- [x] Webhooks for real-time notifications (escalation events)
- [x] Message queuing (SQS for async processing)

**Integration SLA**: 99.5% success rate, <500ms latency for synchronous integrations

**Priority**: HIGH

**Aligns with Principle**: #2 API-First Integration, #11 Asynchronous Communication

---

#### NFR-I-3: Data Portability

**Requirement**: Citizens MUST be able to export their conversation data (GDPR data portability right).

**Export Formats**: JSON (machine-readable), PDF (human-readable), TXT (plain text)

**Export Scope**: All conversations for authenticated citizen, with metadata

**Export Process**:
- Citizen requests export via ChatBot interface or GOV.UK account
- System generates export within 72 hours
- Citizen notified when export ready for download
- Export available for 7 days before deletion

**Priority**: MUST_HAVE (GDPR requirement)

**Aligns with Principle**: #7 Data Sovereignty and UK GDPR Compliance

---

## Integration Requirements

### External System Integrations

#### INT-1: Government Gateway

**Purpose**: Authenticate UK citizens for personalized tax guidance access.

**Integration Type**: Real-time API (OAuth 2.0 Authorization Code flow with PKCE)

**Data Exchanged**:
- **From ChatBot to Government Gateway**: Authorization request, state parameter, code verifier
- **From Government Gateway to ChatBot**: Authorization code, then access token, refresh token, user profile (name, UTR, Government Gateway ID)

**Integration Pattern**: OAuth 2.0 Authorization Code with PKCE

**Authentication**: OAuth 2.0 client credentials (client_id, client_secret in Secrets Manager)

**Error Handling**:
- Auth failure: Display friendly error, offer retry
- Gateway unavailable: Offer unauthenticated mode with limitations
- Token expired: Silent refresh with refresh token

**SLA**: 99.9% availability, <500ms response time (Government Gateway responsibility)

**Owner**: HMRC Identity Team

**Priority**: CRITICAL

---

#### INT-2: HMRC Content Management System

**Purpose**: Ingest authoritative HMRC guidance documents for knowledge base.

**Integration Type**: Batch file transfer (daily sync) + Webhook for real-time updates

**Data Exchanged**:
- **From HMRC CMS to ChatBot**: Guidance documents (HTML/Markdown), metadata (title, URL, publication date, category), document version
- **From ChatBot to HMRC CMS**: None (read-only)

**Integration Pattern**: Pull-based sync (daily) + Webhook notification for urgent updates

**Authentication**: API key (stored in Secrets Manager)

**Error Handling**:
- Sync failure: Retry with exponential backoff, alert content team after 3 failures
- Webhook failure: Queue for retry, fallback to daily sync
- Invalid document: Log error, skip document, alert content team

**SLA**: Daily sync completed by 06:00 GMT, urgent updates within 1 hour

**Owner**: HMRC Content Team

**Priority**: CRITICAL

---

#### INT-3: HMRC Backend APIs

**Purpose**: Retrieve citizen tax records for personalized guidance (authenticated users only).

**Integration Type**: Real-time API (REST)

**Data Exchanged**:
- **From ChatBot to HMRC APIs**: Citizen UTR/NI number, data request type
- **From HMRC APIs to ChatBot**: Tax records (income, tax paid, allowances), National Insurance contributions, PAYE status

**Integration Pattern**: Request/response (synchronous)

**Authentication**: OAuth 2.0 bearer token (on behalf of citizen), service-to-service mTLS

**Error Handling**:
- API unavailable: Graceful degradation to generic guidance with disclaimer
- Unauthorized access: Block request, log security event
- Data not found: Inform citizen, suggest helpline

**SLA**: 99.5% availability, <2s response time

**Owner**: HMRC Digital Services API Team

**Priority**: CRITICAL

---

#### INT-4: HMRC ServiceNow

**Purpose**: Create tickets for human escalation when ChatBot cannot resolve query.

**Integration Type**: Real-time API (REST)

**Data Exchanged**:
- **From ChatBot to ServiceNow**: Ticket details (summary, conversation context, citizen contact preference, priority)
- **From ServiceNow to ChatBot**: Ticket ID, reference number, estimated response time

**Integration Pattern**: Request/response (synchronous for ticket creation)

**Authentication**: API key + service account (stored in Secrets Manager)

**Error Handling**:
- ServiceNow unavailable: Queue ticket for retry, provide fallback helpline number
- Ticket creation failure: Retry 3 times, then alert support team

**SLA**: 99.9% availability, <1s response time for ticket creation

**Owner**: HMRC IT Service Management Team

**Priority**: HIGH

---

#### INT-5: AWS Bedrock (Claude 3.5 Sonnet)

**Purpose**: Generate natural language responses using LLM.

**Integration Type**: Real-time API (AWS SDK)

**Data Exchanged**:
- **From ChatBot to Bedrock**: System prompt, retrieved documents, citizen query, conversation history
- **From Bedrock to ChatBot**: Generated response, token usage, stop reason

**Integration Pattern**: Request/response (synchronous)

**Authentication**: AWS IAM role (ECS task role)

**Error Handling**:
- Bedrock unavailable: Circuit breaker, return apologetic message with retry option
- Rate limited: Queue and retry with backoff
- Timeout (>30s): Return timeout message, offer alternative (helpline)
- Content filter triggered: Return safe response, log for review

**SLA**: 99.9% availability (AWS SLA), <1.5s response time (target)

**Owner**: AWS (service provider), HMRC Cloud Team (account management)

**Priority**: CRITICAL

---

## Data Requirements

### Data Entities

#### Entity 1: Conversation

**Description**: A chat session between a citizen and the ChatBot.

**Attributes**:
| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| id | UUID | Yes | Unique conversation identifier | Primary key |
| citizen_id | UUID | No | Government Gateway user ID (null if unauthenticated) | Foreign key to User |
| session_id | String(64) | Yes | Browser session identifier | Indexed |
| started_at | Timestamp | Yes | Conversation start time | Indexed |
| ended_at | Timestamp | No | Conversation end time | Null until ended |
| status | Enum | Yes | Conversation status | ['active', 'completed', 'escalated', 'abandoned'] |
| language | Enum | Yes | Language preference | ['en', 'cy'] |
| escalated | Boolean | Yes | Whether escalated to human | Default: false |
| satisfaction_score | Integer | No | Citizen feedback (1-5) | 1-5, null if no feedback |
| message_count | Integer | Yes | Number of messages | Derived, ≥1 |

**Relationships**:
- One-to-many with Message (conversation has many messages)
- Many-to-one with User (conversation belongs to citizen, if authenticated)

**Data Volume**:
- Year 1: 5 million conversations
- Year 3: 15 million conversations
- Year 7: 50 million conversations (with retention)

**Access Patterns**:
- Retrieve by conversation_id (single conversation)
- Retrieve by citizen_id (citizen's conversation history)
- Retrieve by date range (analytics, audit)
- Retrieve escalated conversations (support queue)

**Data Classification**: OFFICIAL (contains chat content, may include PII in messages)

**Data Retention**: 7 years, then automatic deletion

---

#### Entity 2: Message

**Description**: A single message within a conversation (either citizen query or ChatBot response).

**Attributes**:
| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| id | UUID | Yes | Unique message identifier | Primary key |
| conversation_id | UUID | Yes | Parent conversation | Foreign key to Conversation |
| role | Enum | Yes | Message sender | ['user', 'assistant', 'system'] |
| content | Text | Yes | Message text | Max 10,000 characters |
| created_at | Timestamp | Yes | Message timestamp | Indexed |
| response_time_ms | Integer | No | Response generation time (assistant only) | Nullable |
| confidence_score | Float | No | AI confidence (assistant only) | 0.0-1.0, nullable |
| sources | JSONB | No | Source citations (assistant only) | Array of {title, url, section} |
| feedback | Enum | No | Citizen feedback on response | ['positive', 'negative', null] |
| feedback_comment | Text | No | Optional feedback text | Max 500 characters |

**Relationships**:
- Many-to-one with Conversation (message belongs to conversation)

**Data Volume**:
- Average 10 messages per conversation
- Year 1: 50 million messages
- Year 3: 150 million messages

**Access Patterns**:
- Retrieve by conversation_id (all messages in conversation, ordered by created_at)
- Retrieve by feedback status (quality analysis)
- Aggregate by date (message volume metrics)

**Data Classification**: OFFICIAL (may contain PII in citizen queries)

**Data Retention**: 7 years (same as conversation)

---

#### Entity 3: User

**Description**: An authenticated citizen who has used the ChatBot.

**Attributes**:
| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| id | UUID | Yes | Internal user identifier | Primary key |
| government_gateway_id | String(64) | Yes | Government Gateway unique ID | Unique, indexed |
| name | String(255) | No | Citizen name (from Government Gateway) | Encrypted at rest |
| utr | String(10) | No | Unique Taxpayer Reference | Encrypted, indexed |
| ni_number | String(9) | No | National Insurance number | Encrypted |
| email | String(255) | No | Email address | Encrypted |
| language_preference | Enum | Yes | Preferred language | ['en', 'cy'] |
| consent_chat_storage | Boolean | Yes | Consent for chat transcript storage | Default: false |
| consent_timestamp | Timestamp | No | When consent was given/withdrawn | |
| created_at | Timestamp | Yes | First authentication time | Indexed |
| last_active_at | Timestamp | Yes | Last conversation time | Indexed |

**Relationships**:
- One-to-many with Conversation (user has many conversations)

**Data Volume**:
- Year 1: 2 million authenticated users
- Year 3: 5 million authenticated users

**Access Patterns**:
- Retrieve by government_gateway_id (authentication lookup)
- Retrieve by id (internal operations)
- Retrieve by last_active_at (engagement analytics)

**Data Classification**: OFFICIAL-SENSITIVE (contains NI number, UTR, name)

**Data Retention**: 7 years after last activity, then automatic deletion (subject to consent withdrawal)

---

#### Entity 4: Knowledge Base Document

**Description**: An HMRC guidance document embedded in the vector database for RAG retrieval.

**Attributes**:
| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| id | UUID | Yes | Unique document identifier | Primary key |
| source_url | String(2048) | Yes | Original GOV.UK/legislation URL | Indexed |
| title | String(500) | Yes | Document title | |
| content | Text | Yes | Document content (for display) | Max 100,000 characters |
| chunk_id | String(64) | Yes | Chunk identifier within document | Indexed |
| chunk_content | Text | Yes | Text chunk for embedding | Max 2,000 tokens |
| embedding | Vector(768) | Yes | Text embedding for similarity search | Vector index |
| publication_date | Date | Yes | Document publication date | Indexed |
| last_updated | Date | Yes | Document last modification date | Indexed |
| category | String(100) | Yes | Tax category | Indexed (Self Assessment, PAYE, VAT, etc.) |
| language | Enum | Yes | Document language | ['en', 'cy'] |
| status | Enum | Yes | Document status | ['active', 'archived', 'superseded'] |

**Relationships**:
- Self-reference: Multiple chunks belong to same source document (via source_url)

**Data Volume**:
- ~100,000 document chunks (10,000 source documents × 10 chunks average)
- Growth: ~10% per year (new guidance, legislation updates)

**Access Patterns**:
- Vector similarity search by embedding (RAG retrieval)
- Retrieve by source_url (citation lookup)
- Retrieve by category (content management)
- Retrieve by last_updated (sync monitoring)

**Data Classification**: OFFICIAL (public guidance content)

**Data Retention**: Indefinite (or until source document superseded)

---

#### Entity 5: Audit Log

**Description**: Immutable audit record for compliance and forensics (W5H1 format).

**Attributes**:
| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| id | UUID | Yes | Unique log entry identifier | Primary key |
| timestamp | Timestamp | Yes | Event time (UTC, millisecond precision) | Indexed, immutable |
| event_type | String(100) | Yes | Type of event | Indexed |
| actor_type | Enum | Yes | Who performed action | ['citizen', 'admin', 'service', 'system'] |
| actor_id | String(100) | Yes | Actor identifier | Indexed |
| action | String(100) | Yes | Action performed | Indexed |
| resource_type | String(100) | Yes | Type of resource affected | Indexed |
| resource_id | String(100) | No | Specific resource identifier | |
| context | JSONB | Yes | Additional context (request_id, conversation_id, etc.) | |
| result | Enum | Yes | Action outcome | ['success', 'failure', 'partial'] |
| error_code | String(50) | No | Error code if failure | |
| error_message | Text | No | Error details if failure | |
| ip_address | String(45) | No | Client IP (for citizen/admin actions) | May be hashed |
| user_agent | String(500) | No | Client user agent | |

**Relationships**:
- None (audit logs are standalone, immutable records)

**Data Volume**:
- ~100 audit events per conversation
- Year 1: 500 million audit records
- Year 7: 3.5 billion audit records

**Access Patterns**:
- Time-range queries (incident investigation, compliance audit)
- Actor-based queries (citizen activity history, admin audit)
- Event-type queries (security events, authentication events)

**Data Classification**: OFFICIAL (may reference sensitive operations)

**Data Retention**: 7 years (immutable storage, S3 Object Lock)

---

### Data Quality Requirements

**Data Accuracy**:
- Knowledge base content: 100% accuracy with HMRC source documents (automated diff comparison)
- Citizen data: Validated against Government Gateway (no manual entry)
- Audit logs: Cryptographic integrity verification

**Data Completeness**:
- Required fields enforced at application layer
- Null handling: Explicit nulls where data optional, never empty strings
- Derived fields computed consistently

**Data Consistency**:
- Eventual consistency acceptable for analytics (up to 5 minutes lag)
- Strong consistency required for conversation state, user profile
- Cross-system reconciliation: Daily sync validation with HMRC CMS

**Data Timeliness**:
- Knowledge base: Updated within 48 hours of source document changes
- Conversation data: Real-time (synchronous write)
- Audit logs: Near real-time (<1 second to SIEM)

**Data Lineage**:
- Knowledge base: Track source URL, publication date, sync timestamp
- AI responses: Track retrieved documents, LLM model version
- Changes: Git-based versioning for knowledge base updates

---

### Data Migration Requirements

**Migration Scope**: Not applicable (new system, no legacy data migration)

**Future Consideration**: If replacing existing HMRC FAQ system, will need to migrate:
- FAQ content to knowledge base (content transformation)
- User preferences (if any existing chatbot)

---

## Constraints and Assumptions

### Technical Constraints

**TC-1**: MUST deploy to AWS UK regions only (eu-west-2 primary) for UK data sovereignty

**TC-2**: MUST integrate with existing Government Gateway for citizen authentication (no custom auth)

**TC-3**: MUST use GOV.UK Design System for frontend (consistency with government services)

**TC-4**: MUST use HMRC-approved technology stack (Python, Node.js, Terraform, AWS services)

**TC-5**: MUST encrypt all data at rest with AWS KMS customer-managed keys

**TC-6**: MUST use AWS Bedrock for LLM (approved for government use, UK data processing)

---

### Business Constraints

**BC-1**: MUST pass GDS Service Standard assessment before public launch (mandatory for GOV.UK)

**BC-2**: MUST publish ATRS record before public beta (UK Government requirement for AI systems)

**BC-3**: MUST support Welsh language (legal requirement under Welsh Language Act 1993)

**BC-4**: Budget cap: £4.95M capital expenditure, £4.5M annual operating expenditure

**BC-5**: Timeline: Public launch by Month 12 (tax year alignment)

**BC-6**: Zero planned downtime during January (Self Assessment deadline period)

---

### Assumptions

**A-1**: Citizens have JavaScript-enabled browsers (Chrome, Firefox, Safari, Edge - last 2 versions)

**A-2**: Government Gateway OAuth integration available and stable

**A-3**: HMRC backend APIs will provide required data within <2 second response time

**A-4**: AWS Bedrock Claude 3.5 Sonnet available in UK region with acceptable latency

**A-5**: HMRC CMS can provide structured content for knowledge base ingestion

**A-6**: Welsh HMRC guidance content exists for core tax topics (or translation acceptable)

**A-7**: Citizens willing to provide feedback (target: >20% feedback rate)

**A-8**: HMRC helpline can handle escalated queries within 2-hour callback SLA

**Validation Plan**:
- A-1: Browser analytics from existing HMRC digital services
- A-2: Technical spike with Government Gateway team (Alpha phase)
- A-3: Load testing against HMRC API sandbox
- A-4: AWS Bedrock POC in Alpha phase
- A-5: Content audit with HMRC Content Team
- A-6: Welsh content inventory review
- A-7: Private beta feedback rate measurement
- A-8: Capacity planning with helpline operations

---

## Success Criteria and KPIs

### Business Success Metrics

| Metric | Baseline | Target | Timeline | Measurement Method |
|--------|----------|--------|----------|-------------------|
| Helpline call volume | 50M calls/year | 45M calls/year (10% reduction) | Year 1 | HMRC call centre data |
| Helpline call volume | 50M calls/year | 35M calls/year (30% reduction) | Year 3 | HMRC call centre data |
| Operational cost savings | £0 | £25M/year | Year 1 | Finance analysis |
| Operational cost savings | £0 | £75M/year | Year 3 | Finance analysis |
| Citizen satisfaction (NPS) | N/A (new service) | >70% | 6 months post-launch | In-app survey |
| ChatBot conversations | 0 | 5M/year | Year 1 | Analytics platform |
| ChatBot conversations | 0 | 15M/year | Year 3 | Analytics platform |

---

### Technical Success Metrics

| Metric | Target | Measurement Method |
|--------|--------|-------------------|
| System availability (business hours) | 99.9% | CloudWatch uptime monitoring |
| Response time (p95) | <2 seconds | APM (CloudWatch, X-Ray) |
| Error rate (5xx responses) | <0.1% | CloudWatch metrics |
| LLM response accuracy | >95% helpful | Citizen feedback (thumbs up/down) |
| Deployment frequency | Weekly releases | CI/CD pipeline metrics |
| Mean time to recovery (MTTR) | <15 minutes | Incident tracking (ServiceNow) |
| Security vulnerabilities (critical/high) | 0 in production | Snyk, AWS Inspector |
| Accessibility issues (critical/high) | 0 at launch | axe-core, manual testing |

---

### User Adoption Metrics

| Metric | Target | Timeline | Measurement Method |
|--------|--------|----------|-------------------|
| Active users (monthly) | 500,000 | 3 months post-launch | Analytics (unique users) |
| Active users (monthly) | 1,500,000 | 12 months post-launch | Analytics (unique users) |
| Authenticated user rate | 30% | 6 months post-launch | Auth vs anonymous sessions |
| Escalation rate | <5% | Ongoing | ServiceNow tickets / conversations |
| Feedback submission rate | >20% | Ongoing | Feedback events / responses |
| Return user rate | >40% | 6 months post-launch | Returning vs new users |

---

## Dependencies and Risks

### Dependencies

| Dependency | Description | Owner | Target Date | Status | Impact if Delayed |
|------------|-------------|-------|-------------|--------|-------------------|
| Government Gateway Integration | OAuth 2.0 integration for citizen authentication | HMRC Identity Team | Month 3 | On Track | HIGH - blocks personalized features |
| HMRC Backend APIs | API access to tax records | HMRC API Team | Month 4 | On Track | HIGH - blocks personalized guidance |
| AWS Bedrock Availability | Claude 3.5 Sonnet in eu-west-2 | AWS | Month 1 | Complete | CRITICAL - no alternative LLM |
| HMRC CMS Content | Structured guidance for knowledge base | HMRC Content Team | Month 3 | On Track | HIGH - reduces accuracy |
| Welsh Content | Welsh language guidance documents | HMRC Welsh Team | Month 5 | At Risk | MEDIUM - legal requirement |
| GDS Assessment Slot | Service Standard assessment booking | GDS | Month 8 | On Track | MEDIUM - delays launch approval |
| CHECK Penetration Testing | Approved supplier booking | HMRC Security | Month 7 | On Track | HIGH - security sign-off required |

---

### Risks

| Risk ID | Description | Probability | Impact | Mitigation Strategy | Owner |
|---------|-------------|-------------|--------|---------------------|-------|
| R-1 | LLM generates inaccurate tax advice causing citizen harm | MEDIUM | HIGH | RAG grounding, source citation, confidence thresholds, human review for edge cases | AI Lead |
| R-2 | Prompt injection attacks manipulate ChatBot responses | MEDIUM | HIGH | Input sanitization, output validation, Bedrock Guardrails, security monitoring | Security Architect |
| R-3 | Government Gateway unavailable during peak period | LOW | HIGH | Graceful degradation to unauthenticated mode, cached guidance | Tech Lead |
| R-4 | GDS Service Standard assessment fails | LOW | HIGH | Early engagement with GDS, mock assessments, remediation sprints | Delivery Manager |
| R-5 | Knowledge base out of sync with HMRC guidance changes | MEDIUM | MEDIUM | Automated sync, content team alerts, human review of updates | Content Lead |
| R-6 | Welsh language support insufficient quality | MEDIUM | MEDIUM | Native Welsh speaker review, Welsh user testing, translation quality assurance | Content Lead |
| R-7 | Citizen adoption lower than projected | MEDIUM | MEDIUM | Marketing campaign, GOV.UK prominent placement, helpline promotion | Product Owner |
| R-8 | Data breach exposing citizen PII | LOW | CRITICAL | Encryption, access controls, DLP, incident response plan, security monitoring | CISO |
| R-9 | AWS Bedrock cost exceeds budget at scale | MEDIUM | MEDIUM | Token optimization, caching, cost monitoring, budget alerts | Tech Lead |
| R-10 | Helpline unable to handle escalation volume | MEDIUM | MEDIUM | Capacity planning, overflow procedures, ChatBot improvements to reduce escalation | Operations |

---

## Requirement Conflicts & Resolutions

### Conflict C-1: Speed to Market vs Comprehensive Testing

**Conflicting Requirements**:
- **Requirement A**: BR-4 (GDS Service Standard compliance by Month 12 launch)
- **Requirement B**: NFR-SEC-5 (Comprehensive security testing including annual pen test)

**Stakeholders Involved**:
- **HMRC SRO**: Wants Month 12 launch to align with tax year and demonstrate value
- **HMRC CISO**: Wants thorough security validation before exposing citizen data

**Nature of Conflict**:
Comprehensive security testing (pen testing, DAST, multiple cycles) requires 2-3 months, which conflicts with aggressive delivery timeline if issues found late.

**Trade-off Analysis**:

| Option | Pros | Cons | Impact |
|--------|------|------|--------|
| **Option 1**: Delay launch for full security cycle | ✅ Complete security validation | ❌ Miss tax year alignment, delayed savings | CISO satisfied, SRO frustrated |
| **Option 2**: Launch with reduced scope | ✅ Meet timeline | ❌ Limited functionality, may not achieve deflection targets | SRO partially satisfied |
| **Option 3**: Parallel security workstream from Month 1 | ✅ Both satisfied | ❌ Higher cost, more resources needed | Both satisfied if executed well |

**Resolution Strategy**: INNOVATE

**Decision**: Option 3 - Embed security testing throughout development lifecycle with parallel pen testing starting Month 5, not waiting until end.

**Rationale**: Shift-left security approach catches issues early when cheaper to fix. Pen testing in Beta environment allows remediation time before launch.

**Decision Authority**: HMRC CISO and SRO jointly

**Impact on Requirements**:
- **Added**: Continuous security testing in CI/CD pipeline from Month 1
- **Modified**: Pen testing scheduled for Month 5-6 (Beta phase) instead of Month 10

**Stakeholder Management**:
- CISO: Security embedded throughout, visibility into testing progress
- SRO: Launch timeline maintained, security built-in not bolted-on

---

### Conflict C-2: Feature Richness vs Accessibility Compliance

**Conflicting Requirements**:
- **Requirement A**: FR-1 (Rich conversational interface with real-time features)
- **Requirement B**: NFR-U-2 (WCAG 2.2 AA compliance - legal requirement)

**Stakeholders Involved**:
- **Product Owner**: Wants modern chat experience (typing indicators, animations, rich media)
- **Accessibility Lead**: Mandates screen reader compatibility and keyboard navigation

**Nature of Conflict**:
Advanced UI features (real-time typing indicators, animations, dynamic content) can break screen reader experience and keyboard navigation.

**Resolution Strategy**: PRIORITIZE

**Decision**: Accessibility is non-negotiable (legal requirement). Features that cannot be made accessible will not be implemented.

**Rationale**: Public Sector Bodies Accessibility Regulations 2018 is law. Non-compliance exposes HMRC to legal action and excludes 13.9M disabled citizens.

**Impact on Requirements**:
- **Modified**: FR-1 specifies "accessible conversational interface" with ARIA live regions for dynamic content
- **Added**: Accessibility review gate for all new features before implementation

**Stakeholder Management**:
- Product Owner: Educated on accessible alternatives (ARIA live regions maintain chat feel while being screen reader compatible)
- Accessibility Lead: Final approval authority on UI features

---

## Timeline and Milestones

### High-Level Milestones

| Milestone | Description | Target Date | Dependencies |
|-----------|-------------|-------------|--------------|
| Discovery Complete | User research, problem validation | Month 2 | Stakeholder engagement |
| Alpha Complete | Technical POC, initial architecture | Month 4 | AWS Bedrock access, Gov Gateway spike |
| Beta (Private) | 100 citizens testing | Month 7 | Core functionality, security testing |
| Beta (Public) | 10,000 citizens testing | Month 9 | Private beta learnings, scale testing |
| Live Assessment | GDS Service Standard assessment | Month 11 | Beta metrics, documentation complete |
| Production Launch | Public launch on GOV.UK | Month 12 | GDS approval, security sign-off |

---

## Budget

### Cost Estimate (Capital Expenditure)

| Category | Estimated Cost | Notes |
|----------|----------------|-------|
| Development (internal) | £2,000,000 | 15 FTE × 12 months |
| Development (contractor) | £500,000 | Specialist skills (AI, accessibility) |
| Infrastructure (setup) | £200,000 | AWS, tooling, environments |
| Third-party services | £250,000 | AWS Bedrock, security tools |
| Testing | £500,000 | Pen testing, load testing, accessibility audit |
| Training | £100,000 | Staff training, documentation |
| Contingency (20%) | £790,000 | |
| **Total CapEx** | **£4,340,000** | |

### Ongoing Operational Costs (Annual)

| Category | Annual Cost | Notes |
|----------|-------------|-------|
| AWS Infrastructure | £1,500,000 | Compute, storage, networking |
| AWS Bedrock (LLM) | £1,000,000 | Token usage at scale |
| Support staff | £1,000,000 | L2/L3 support, content management |
| Licenses | £200,000 | Monitoring, security tools |
| Security (ongoing) | £300,000 | Pen testing, vulnerability management |
| Contingency (20%) | £800,000 | |
| **Total OpEx** | **£4,800,000/year** | |

### Value Realization

| Year | Investment | Savings | Net Benefit |
|------|------------|---------|-------------|
| Year 1 | £4.34M (CapEx) + £4.8M (OpEx) | £25M | £15.86M |
| Year 2 | £4.8M (OpEx) | £50M | £45.2M |
| Year 3 | £4.8M (OpEx) | £75M | £70.2M |
| **3-Year Total** | **£18.74M** | **£150M** | **£131.26M** |

---

## Approval

### Requirements Review

| Reviewer | Role | Status | Date | Comments |
|----------|------|--------|------|----------|
| TBD | HMRC SRO | [ ] Approved | [PENDING] | |
| TBD | Product Owner | [ ] Approved | [PENDING] | |
| TBD | Enterprise Architect | [ ] Approved | [PENDING] | |
| TBD | Security Architect | [ ] Approved | [PENDING] | |
| TBD | Data Protection Officer | [ ] Approved | [PENDING] | |
| TBD | Accessibility Lead | [ ] Approved | [PENDING] | |

### Sign-Off

By signing below, stakeholders confirm that requirements are complete, understood, and approved to proceed to design phase.

| Stakeholder | Signature | Date |
|-------------|-----------|------|
| [SRO Name, Executive Sponsor] | _________ | [DATE] |
| [Product Owner Name] | _________ | [DATE] |
| [Enterprise Architect Name] | _________ | [DATE] |

---

## Appendices

### Appendix A: Glossary

- **ATRS**: Algorithmic Transparency Recording Standard - UK Government requirement for documenting AI systems
- **Bedrock**: AWS managed service for foundation models (LLMs)
- **DPIA**: Data Protection Impact Assessment - UK GDPR requirement for high-risk processing
- **GDS**: Government Digital Service - sets standards for UK government digital services
- **Government Gateway**: HMRC authentication service for UK citizens
- **LLM**: Large Language Model - AI model for natural language generation
- **NI Number**: National Insurance number - UK citizen identifier
- **NPS**: Net Promoter Score - customer satisfaction metric
- **PKCE**: Proof Key for Code Exchange - OAuth 2.0 security extension
- **RAG**: Retrieval-Augmented Generation - AI architecture pattern
- **UTR**: Unique Taxpayer Reference - HMRC taxpayer identifier
- **WCAG**: Web Content Accessibility Guidelines - accessibility standard

### Appendix B: Reference Documents

- [Architecture Principles](../../.arckit/memory/architecture-principles.md)
- [ATRS Record](./atrs-record.md)
- [Statement of Work](./sow.md)
- [Evaluation Criteria](./evaluation-criteria.md)
- [Traceability Matrix](./traceability-matrix.md)

### Appendix C: Wireframes and Mockups

TBD - To be developed during Alpha phase with user research input

### Appendix D: Data Models

TBD - Detailed ERD to be created via `/arckit.data-model` command

---

**Document History**

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | 2025-10-14 | ArcKit AI | Initial draft |
| 1.0 | 2025-10-14 | ArcKit AI | First complete version |
| 1.1 | 2026-01-25 | ArcKit AI | Aligned with template structure |
| 1.2 | 2026-01-26 | ArcKit AI | Updated to template v0.11.2 |

---

**Generated by**: ArcKit `/arckit.requirements` command
**Generated on**: 2026-01-26
**ArcKit Version**: 0.11.2
**Project**: HMRC ChatBot (001-hmrc-chatbot)
**Model**: Claude Opus 4.5
**Generation Context**: Updated to align with ArcKit template v0.11.2 structure
