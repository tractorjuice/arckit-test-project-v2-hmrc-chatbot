# Stakeholder Drivers & Goals Analysis: HMRC Tax Assistant ChatBot

> **Template Status**: Live | **Version**: 1.1.0 | **Command**: `/arckit.stakeholders`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-STKE-v1.0 |
| **Document Type** | Stakeholder Drivers & Goals Analysis |
| **Project** | HMRC ChatBot (Project 001-hmrc-chatbot) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-02-03 |
| **Last Modified** | 2026-02-03 |
| **Review Cycle** | Quarterly |
| **Next Review Date** | 2026-05-03 |
| **Owner** | HMRC Digital Services |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | HMRC Architecture Review Board, GDS Stakeholders, Project Board |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-02-03 | ArcKit AI | Initial creation from `/arckit.stakeholders` command | PENDING | PENDING |

---

## Executive Summary

### Purpose
This document identifies the key stakeholders for the HMRC Tax Assistant ChatBot project, analyses their underlying drivers (motivations, concerns, pressures), maps those drivers to specific measurable goals, and defines the business outcomes that will prove stakeholder satisfaction. It provides end-to-end traceability from individual stakeholder concerns through to project success metrics, enabling informed prioritisation, effective communication, and proactive conflict resolution.

### Key Findings
The HMRC ChatBot project has strong stakeholder alignment around cost reduction (£75M annual savings target) and citizen experience improvement, but faces tension between delivery speed (Minister and SRO want rapid launch for tax year alignment) and thorough compliance assurance (CISO, DPO, and GDS require rigorous security, data protection, and service standard validation). A secondary tension exists between AI innovation ambitions and the conservative risk appetite inherent in handling OFFICIAL-SENSITIVE citizen tax data. The project benefits from a powerful synergy: almost all stakeholders agree that reducing helpline volume while maintaining accuracy is the primary objective, creating a unified "North Star" for decision-making.

### Critical Success Factors
- **Accuracy above all**: >95% AI response accuracy grounded in authoritative HMRC sources — inaccurate tax advice is the single greatest reputational risk
- **Security and data protection by design**: Zero data breaches, DPIA approval, and Cyber Essentials Plus certification before citizen data is processed
- **GDS Service Standard passage**: All 14 criteria met before public launch on GOV.UK — this is a hard gate with no workaround
- **Citizen adoption reaching critical mass**: 500,000 monthly active users within 3 months of launch to demonstrate value and justify investment
- **Ministerial confidence**: Ability to answer parliamentary questions positively about the service

### Stakeholder Alignment Score
**Overall Alignment**: MEDIUM-HIGH

Most stakeholders share the primary objective of reducing helpline costs while improving citizen experience. The MEDIUM-HIGH (rather than HIGH) rating reflects real tensions around delivery pace vs assurance rigour and around AI risk appetite. These tensions are manageable with the phased delivery approach and embedded security workstream described in the requirements document, but require active governance and transparent communication to maintain alignment throughout delivery.

---

## Stakeholder Identification

### Internal Stakeholders

| Stakeholder | Role/Department | Influence | Interest | Engagement Strategy |
|-------------|----------------|-----------|----------|---------------------|
| HMRC Minister (Financial Secretary to the Treasury) | Ministerial Sponsor | HIGH | HIGH | Quarterly briefings, parliamentary briefing packs |
| HMRC Permanent Secretary (Second Permanent Secretary) | Accounting Officer | HIGH | HIGH | Monthly programme board, NAO readiness reviews |
| HMRC Senior Responsible Owner (SRO) | Executive Sponsor, HMRC Digital | HIGH | HIGH | Weekly steering committee, decision authority |
| HMRC Finance Director | Finance & Investment | HIGH | MEDIUM | Quarterly business case reviews, FinOps reporting |
| HMRC Chief Digital & Information Officer (CDIO) | Digital & Technology | HIGH | HIGH | Fortnightly architecture reviews, technology decisions |
| HMRC Chief Information Security Officer (CISO) | Cyber Security | HIGH | HIGH | Security gates at each phase, threat model reviews |
| HMRC Data Protection Officer (DPO) | Information Governance | HIGH | HIGH | DPIA approval, ongoing compliance monitoring |
| HMRC Customer Services Director | Operations & Service Delivery | HIGH | HIGH | Weekly operational metrics, deflection tracking |
| Product Owner | HMRC Digital Services | MEDIUM | HIGH | Daily standups, sprint reviews, backlog prioritisation |
| Enterprise Architect | HMRC Architecture | MEDIUM | HIGH | Architecture review gates, principles compliance |
| Content Designers | HMRC Content Team | LOW | HIGH | Sprint-by-sprint content reviews, Plain English guidance |
| Tax Policy Experts | HMRC Policy Directorate | MEDIUM | MEDIUM | Knowledge base accuracy reviews, policy change notifications |
| Helpline Operations Staff | HMRC Customer Services | LOW | HIGH | Change impact sessions, training, feedback channels |
| Accessibility Specialist | HMRC Digital Inclusion | MEDIUM | HIGH | Accessibility gates, user research coordination |

### External Stakeholders

| Stakeholder | Organization | Relationship | Influence | Interest |
|-------------|--------------|--------------|-----------|----------|
| GDS Assessment Team | Government Digital Service | Oversight & Assessment | HIGH | HIGH |
| Information Commissioner's Office (ICO) | ICO | Regulator (Data Protection) | HIGH | MEDIUM |
| National Cyber Security Centre (NCSC) | NCSC | Advisor (Security Standards) | HIGH | LOW |
| National Audit Office (NAO) | NAO | Auditor (Value for Money) | HIGH | MEDIUM |
| HM Treasury (Spending Team) | HM Treasury | Funding & Spending Controls | HIGH | MEDIUM |
| UK Citizens (Taxpayers) | Public | Service Users / Beneficiaries | LOW | HIGH |
| Welsh Language Commissioner | Welsh Language Commissioner | Regulator (Welsh Language) | MEDIUM | MEDIUM |
| Parliamentary Committees (PAC, Treasury Select) | Parliament | Scrutiny | HIGH | LOW |
| AWS (Cloud Provider) | Amazon Web Services | Technology Supplier | LOW | HIGH |
| Delivery Partner / Systems Integrator | TBD (Procurement) | Implementation Partner | LOW | HIGH |

### Stakeholder Power-Interest Grid

```
                          INTEREST
              Low                         High
        ┌─────────────────────┬─────────────────────┐
        │                     │                     │
        │   KEEP SATISFIED    │   MANAGE CLOSELY    │
   High │                     │                     │
        │  • HM Treasury      │  • Minister         │
        │  • NAO              │  • Perm Secretary   │
        │  • ICO              │  • SRO              │
        │  • NCSC             │  • CDIO             │
 P      │  • Parliamentary    │  • CISO             │
 O      │    Committees       │  • DPO              │
 W      │  • Finance Director │  • Customer Svcs Dir│
 E      │                     │  • GDS Assessment   │
 R      ├─────────────────────┼─────────────────────┤
        │                     │                     │
        │      MONITOR        │    KEEP INFORMED    │
        │                     │                     │
   Low  │  • Welsh Lang       │  • Citizens         │
        │    Commissioner     │  • Product Owner    │
        │                     │  • Content Designers│
        │                     │  • Helpline Staff   │
        │                     │  • Accessibility    │
        │                     │  • Enterprise Arch  │
        │                     │  • Tax Policy       │
        │                     │  • AWS / Vendor     │
        └─────────────────────┴─────────────────────┘
```

| Stakeholder | Power | Interest | Quadrant | Engagement Strategy |
|-------------|-------|----------|----------|---------------------|
| Minister | HIGH | HIGH | Manage Closely | Quarterly briefings, PQ briefing packs, dashboard access |
| Permanent Secretary | HIGH | HIGH | Manage Closely | Monthly programme board, NAO readiness briefings |
| SRO | HIGH | HIGH | Manage Closely | Weekly steering committee, escalation authority |
| CDIO | HIGH | HIGH | Manage Closely | Fortnightly architecture reviews, technology approval |
| CISO | HIGH | HIGH | Manage Closely | Security review gates, threat intelligence briefings |
| DPO | HIGH | HIGH | Manage Closely | DPIA workshops, data protection review gates |
| Customer Services Director | HIGH | HIGH | Manage Closely | Weekly operational metrics, deflection dashboard |
| GDS Assessment Team | HIGH | HIGH | Manage Closely | Assessment preparation meetings, evidence portfolio |
| Finance Director | HIGH | MEDIUM | Keep Satisfied | Quarterly business case updates, FinOps reports |
| HM Treasury | HIGH | MEDIUM | Keep Satisfied | Spending review submissions, VfM evidence |
| NAO | HIGH | MEDIUM | Keep Satisfied | Audit readiness documentation, value for money case |
| ICO | HIGH | MEDIUM | Keep Satisfied | DPIA submission, annual compliance reporting |
| NCSC | HIGH | LOW | Keep Satisfied | Security architecture review, pen test scope agreement |
| Parliamentary Committees | HIGH | LOW | Keep Satisfied | Briefing packs if called, proactive transparency |
| Tax Policy Experts | MEDIUM | MEDIUM | Keep Informed | Monthly content review sessions |
| Citizens (Taxpayers) | LOW | HIGH | Keep Informed | GOV.UK communications, user research sessions, feedback |
| Product Owner | MEDIUM | HIGH | Keep Informed | Daily collaboration, sprint reviews |
| Enterprise Architect | MEDIUM | HIGH | Keep Informed | Architecture review gates |
| Accessibility Specialist | MEDIUM | HIGH | Keep Informed | Accessibility gates, testing coordination |
| Content Designers | LOW | HIGH | Keep Informed | Sprint reviews, content standards |
| Helpline Operations Staff | LOW | HIGH | Keep Informed | Change impact workshops, training sessions |
| Welsh Language Commissioner | MEDIUM | MEDIUM | Monitor | Welsh language compliance reporting |
| AWS | LOW | HIGH | Keep Informed | Account reviews, service updates |
| Delivery Partner | LOW | HIGH | Keep Informed | Contract management, sprint reviews |

**Quadrant Interpretation:**
- **Manage Closely** (High Power, High Interest): Key decision-makers requiring active engagement and regular dialogue
- **Keep Satisfied** (High Power, Low Interest): Influential stakeholders needing periodic updates and proactive assurance
- **Keep Informed** (Low Power, High Interest): Engaged stakeholders needing regular communication and input opportunities
- **Monitor** (Low Power, Low Interest): Minimal engagement required, reactive communication

---

## Stakeholder Drivers Analysis

### SD-1: Minister (Financial Secretary to the Treasury) - Deliver Manifesto Commitment on Digital Public Services

**Stakeholder**: Minister (Financial Secretary to the Treasury)

**Driver Category**: STRATEGIC / POLITICAL

**Driver Statement**: Demonstrate visible progress on modernising HMRC services through AI and digital transformation, enabling positive responses to parliamentary questions and media scrutiny about HMRC service quality, while reducing the political risk of helpline failures and long citizen wait times.

**Context & Background**:
HMRC helpline performance regularly features in parliamentary questions and media coverage. Wait times during January Self Assessment deadline period generate significant negative press. The Minister needs a demonstrable digital alternative that improves citizen experience and provides a positive narrative about government technology investment. AI in public services is also a high-profile policy area where the UK Government wants to demonstrate responsible leadership.

**Driver Intensity**: CRITICAL

**Enablers**:
- Rapid delivery to show visible progress within 12 months
- Positive citizen satisfaction metrics for ministerial dashboard
- Clean ATRS record demonstrating responsible AI deployment
- Good news stories from user research and beta testing

**Blockers**:
- Data breach or AI error generating negative headlines
- GDS Service Standard assessment failure
- NAO criticism of value for money
- Parliamentary committee scrutiny finding governance gaps

**Related Stakeholders**:
- Permanent Secretary (accountability for delivery), SRO (delivery responsibility), NAO (value scrutiny), Parliamentary Committees (oversight)

---

### SD-2: Permanent Secretary (Second Permanent Secretary) - Ensure Proper Governance and Avoid Accountability Failures

**Stakeholder**: HMRC Second Permanent Secretary (Accounting Officer)

**Driver Category**: RISK / COMPLIANCE

**Driver Statement**: Ensure the ChatBot programme follows proper governance, delivers value for money that withstands NAO scrutiny, and does not expose HMRC to accountability failures (data breaches, inaccurate advice causing citizen harm, or wasteful spending) that would result in Accounting Officer letters or Public Accounts Committee hearings.

**Context & Background**:
As Accounting Officer, the Permanent Secretary is personally accountable to Parliament for the proper use of public funds. Failed government IT projects (e.g., Universal Credit delays, NHS IT programme) carry significant career and institutional risk. The Permanent Secretary needs confidence that governance is robust, business case is sound, and delivery is well-managed. They are particularly alert to the novel risks of AI in a high-stakes domain (tax advice).

**Driver Intensity**: CRITICAL

**Enablers**:
- Robust business case with clear value for money evidence
- Strong programme governance (SRO, programme board, gateway reviews)
- Independent assurance (IPA reviews, internal audit)
- Phased delivery reducing financial exposure at each stage

**Blockers**:
- Weak business case or inability to demonstrate VfM
- Governance failures or lack of proper controls
- AI-related incidents generating PAC interest
- Cost overruns or schedule slippage without early warning

**Related Stakeholders**:
- Minister (political accountability), SRO (delegated delivery), Finance Director (spending controls), NAO (audit), HM Treasury (spending approval)

---

### SD-3: SRO (Senior Responsible Owner) - Deliver a Successful Digital Service on Time and Within Budget

**Stakeholder**: SRO, HMRC Digital

**Driver Category**: OPERATIONAL / PERSONAL

**Driver Statement**: Successfully deliver the HMRC ChatBot as a live service on GOV.UK by Month 12, passing GDS Service Standard assessment, achieving measurable helpline deflection, and establishing a platform for future AI-powered services — while managing personal reputation risk of leading a high-profile AI programme.

**Context & Background**:
The SRO has direct accountability for programme delivery to the Minister and Permanent Secretary. Success would establish HMRC as a leader in responsible AI deployment across government and advance the SRO's career. Failure — whether through missed deadlines, overspend, poor citizen experience, or security incidents — would be career-damaging. The SRO must balance pressure for rapid delivery against the need for thorough assurance.

**Driver Intensity**: CRITICAL

**Enablers**:
- Strong delivery team with AI and government digital experience
- Clear requirements and architecture (provided by existing ArcKit artifacts)
- Supportive CDIO and architecture team
- Agile delivery with iterative progress and early value demonstration

**Blockers**:
- Skills shortage (AI/ML, accessibility, security specialists)
- Dependency delays (Government Gateway, HMRC backend APIs)
- Scope creep from stakeholders wanting additional features
- GDS assessment failure requiring significant rework

**Related Stakeholders**:
- Minister (sponsor), Permanent Secretary (accountability), CDIO (technology), Product Owner (delivery), GDS (assessment)

---

### SD-4: HMRC Finance Director - Demonstrate Value for Money and Cost Savings

**Stakeholder**: HMRC Finance Director

**Driver Category**: FINANCIAL

**Driver Statement**: Ensure the ChatBot investment (£4.34M CapEx + £4.8M/year OpEx) delivers demonstrable return on investment through measurable helpline cost reduction, with a clear evidence trail for HM Treasury spending reviews and NAO value for money assessments.

**Context & Background**:
HMRC faces ongoing pressure to reduce operational costs while maintaining service quality. The helpline costs £250M-£500M annually (50M calls × £5-£10 per call). A 30% deflection would save £75M/year — a compelling financial case. However, the Finance Director must validate these projections against realistic adoption assumptions and ensure proper FinOps governance of cloud spending (AWS costs can escalate quickly at scale).

**Driver Intensity**: HIGH

**Enablers**:
- Clear cost baseline (helpline costs well documented)
- Measurable deflection metrics (calls before vs after ChatBot)
- FinOps practices for AWS cost management
- Phased rollout enabling early measurement and course correction

**Blockers**:
- Optimistic adoption projections not validated by beta testing
- AWS Bedrock costs exceeding budget at scale (token usage growth)
- Difficulty attributing helpline reduction to ChatBot (other factors)
- HM Treasury challenge on value for money methodology

**Related Stakeholders**:
- Permanent Secretary (accountability), HM Treasury (spending controls), NAO (VfM audit), SRO (delivery), Customer Services Director (operational costs)

---

### SD-5: HMRC CDIO - Modernise Technology and Build AI Capability

**Stakeholder**: HMRC Chief Digital & Information Officer

**Driver Category**: STRATEGIC

**Driver Statement**: Use the ChatBot project to establish HMRC's AI/ML platform capability, attract and retain digital talent, and position HMRC as a technology leader across government — building reusable components (RAG infrastructure, LLM integration, vector database) that can be leveraged for future AI services.

**Context & Background**:
HMRC competes with private sector and other government departments for scarce AI and digital talent. Having a flagship AI project creates recruitment appeal. The CDIO also sees strategic value in building reusable AI platform components rather than a one-off solution — the RAG infrastructure, LLM integration patterns, and observability framework should be reusable for future HMRC AI services (e.g., fraud detection, compliance checking, internal knowledge management).

**Driver Intensity**: HIGH

**Enablers**:
- Modern technology stack (AWS, Python, React, Terraform) attractive to talent
- Platform approach creating reusable AI infrastructure
- Open standards and open source where appropriate (GDS requirement)
- Innovation culture and learning from beta iterations

**Blockers**:
- Forced to use legacy technology for integration
- Vendor lock-in preventing platform reuse
- Security constraints making technology choices inflexible
- Inability to recruit AI specialists at civil service pay grades

**Related Stakeholders**:
- SRO (delivery), Enterprise Architect (architecture decisions), CISO (security constraints), Product Owner (feature scope)

---

### SD-6: HMRC CISO - Protect Citizen Data and HMRC Reputation from Cyber Threats

**Stakeholder**: HMRC Chief Information Security Officer

**Driver Category**: RISK / COMPLIANCE

**Driver Statement**: Ensure the ChatBot meets HMRC security standards (Zero Trust, NCSC Cloud Security Principles, Cyber Essentials Plus) with no security vulnerabilities in production, no data breaches, and robust defences against AI-specific threats (prompt injection, data extraction, model manipulation) — while not being seen as blocking innovation.

**Context & Background**:
HMRC is a prime target for cyber attacks. The ChatBot introduces novel attack surfaces: prompt injection could extract citizen data or manipulate tax advice, the LLM itself could leak training data, and the RAG architecture could be exploited to return manipulated guidance. The CISO must protect OFFICIAL-SENSITIVE data (NI numbers, tax records, Government Gateway credentials) while enabling the innovation agenda. Being perceived as blocking the project is politically undesirable, but a breach would be career-ending.

**Driver Intensity**: CRITICAL

**Enablers**:
- Security embedded from Day 1 (shift-left approach agreed in requirements)
- AWS security services (GuardDuty, Security Hub, WAF, Bedrock Guardrails)
- Dedicated security architect on the project team
- CHECK-approved pen testing supplier on HMRC framework

**Blockers**:
- Pressure to skip or compress security gates for timeline
- Novel AI attack vectors without established defence playbooks
- Shared responsibility model complexity with AWS
- Limited AI security testing tools and expertise in government

**Related Stakeholders**:
- DPO (data protection overlap), NCSC (security guidance), SRO (timeline pressure), Enterprise Architect (security architecture)

---

### SD-7: HMRC Data Protection Officer - Ensure UK GDPR Compliance and ICO Readiness

**Stakeholder**: HMRC Data Protection Officer

**Driver Category**: COMPLIANCE

**Driver Statement**: Ensure all citizen data processing complies with UK GDPR and Data Protection Act 2018, with an approved DPIA before any citizen data is processed, robust data subject rights procedures, lawful basis documentation, and readiness for ICO inspection — particularly given the novel risks of AI processing personal data.

**Context & Background**:
The ChatBot processes OFFICIAL-SENSITIVE personal data (NI numbers, tax records, Government Gateway credentials) using AI — a combination that triggers mandatory DPIA requirements under UK GDPR Article 35. AI processing of personal data is a priority area for the ICO. The DPO must ensure lawful basis (public task), purpose limitation (tax guidance only), data minimisation, and citizen rights are fully implemented. Any GDPR breach could result in ICO enforcement (fines up to £17.5M or 4% of turnover) and catastrophic reputational damage.

**Driver Intensity**: CRITICAL

**Enablers**:
- DPIA template and process established within HMRC
- UK GDPR lawful basis clear (public task — HMRC statutory function)
- Data classification already defined (OFFICIAL-SENSITIVE for PII)
- Privacy by design embedded in architecture principles

**Blockers**:
- AI processing creating new personal data (inferences, profiles)
- Unclear data retention requirements for AI training data
- Difficulty ensuring right to erasure when data in vector database
- Cross-border data processing risk if AWS services route via non-UK regions

**Related Stakeholders**:
- CISO (security/privacy overlap), ICO (regulator), SRO (delivery), Citizens (data subjects)

---

### SD-8: HMRC Customer Services Director - Reduce Helpline Pressure While Maintaining Service Quality

**Stakeholder**: HMRC Customer Services Director

**Driver Category**: OPERATIONAL

**Driver Statement**: Reduce helpline call volume by 30% (15M calls/year) by Year 3 without degrading service quality or creating a two-tier experience where digitally excluded citizens receive worse service. Ensure the ChatBot handles genuine deflection (resolving queries) rather than false deflection (citizens giving up and calling anyway).

**Context & Background**:
The Customer Services Director manages 50M+ calls/year with constrained headcount and budget. January Self Assessment deadline creates extreme pressure with long wait times generating complaints, parliamentary questions, and negative media coverage. The ChatBot promises relief, but the Director is pragmatic: previous digital self-service initiatives (online forms, FAQ pages) achieved limited deflection because citizens still preferred phone for complex or emotional queries. The Director needs evidence that the ChatBot actually resolves queries rather than just deflecting them to later calls.

**Driver Intensity**: HIGH

**Enablers**:
- ChatBot handling simple, repetitive queries (Personal Allowance, deadlines, allowable expenses)
- Warm handover to human agents for complex queries (context preserved)
- 24/7 availability catching queries outside helpline hours
- Measurable deflection analytics (ChatBot resolution vs subsequent call)

**Blockers**:
- ChatBot providing wrong answers, causing callbacks for correction
- Poor escalation experience (citizen repeating query to human agent)
- Digital exclusion — vulnerable citizens unable to use ChatBot
- Helpline staff resistance (perceiving ChatBot as job threat)

**Related Stakeholders**:
- Helpline Operations Staff (directly affected), Citizens (service quality), SRO (delivery), Finance Director (cost savings)

---

### SD-9: GDS Assessment Team - Ensure Service Meets GDS Service Standard

**Stakeholder**: GDS Assessment Team

**Driver Category**: COMPLIANCE / QUALITY

**Driver Statement**: Assess the HMRC ChatBot against all 14 GDS Service Standard criteria and ensure it meets the standard for user-centred design, accessibility, technology choices, and operational readiness before approving progression to Live on GOV.UK.

**Context & Background**:
GDS assessments are mandatory gates for government digital services. The assessment team evaluates evidence across 14 criteria including user research, accessibility, technology choices, performance measurement, and sustainability. Failure means the service cannot launch on GOV.UK. The team takes a rigorous, evidence-based approach and will not lower the bar for political pressure. They are particularly focused on genuine user research with real citizens, accessibility compliance, and sustainable operational model.

**Driver Intensity**: HIGH

**Enablers**:
- Early engagement with GDS (pre-assessment discussions)
- Strong user research programme with diverse participants
- Evidence portfolio documenting decisions and outcomes
- Accessibility testing with disabled users

**Blockers**:
- Insufficient user research (especially with assisted digital users)
- Accessibility gaps at assessment time
- Unclear performance metrics or measurement strategy
- Technology choices not justified against alternatives

**Related Stakeholders**:
- SRO (approval required for launch), Product Owner (evidence preparation), Accessibility Specialist (criterion 5)

---

### SD-10: UK Citizens (Taxpayers) - Get Fast, Accurate, Accessible Tax Guidance

**Stakeholder**: UK Citizens (50M+ taxpayers, including 13.9M with disabilities)

**Driver Category**: CUSTOMER / USER

**Driver Statement**: Access clear, accurate, trustworthy tax guidance quickly and easily — without long wait times, confusing jargon, or accessibility barriers — through a channel that is available when needed (including evenings, weekends, and deadline periods) and that provides personalised answers based on individual tax circumstances.

**Context & Background**:
Citizens currently face 10+ minute helpline wait times (much longer in January), confusing GOV.UK guidance pages, and anxiety about tax compliance. Many citizens have simple questions (Personal Allowance, deadlines, allowable expenses) that do not require human expertise. Vulnerable citizens — elderly, disabled, non-English-speaking, digitally excluded — face additional barriers. Citizens need to trust that AI-provided guidance is as accurate as human agent advice. Trust in HMRC is fragile; any perception of giving wrong advice or mishandling data will drive citizens back to the helpline.

**Driver Intensity**: HIGH

**Enablers**:
- Plain English responses (reading age 9 per GOV.UK style guide)
- Source citations proving answers are based on official guidance
- 24/7 availability including tax deadline periods
- Accessible design (WCAG 2.2 AA, screen reader support, Welsh language)
- Government Gateway integration for personalised answers

**Blockers**:
- Inaccurate or misleading tax guidance from AI
- Complex, jargon-heavy responses
- Poor accessibility (inaccessible to screen readers, no Welsh)
- Privacy concerns about AI processing personal tax data
- Digital exclusion for citizens without internet access or digital skills

**Related Stakeholders**:
- All internal stakeholders (service delivery), Welsh Language Commissioner (Welsh provision), ICO (data protection), Accessibility groups

---

### SD-11: Helpline Operations Staff - Job Security and Manageable Workload

**Stakeholder**: HMRC Helpline Operations Staff (~10,000 FTE)

**Driver Category**: PERSONAL / OPERATIONAL

**Driver Statement**: Understand how the ChatBot affects their roles and job security, receive proper training on the new escalation process, and benefit from reduced pressure during peak periods — rather than being made redundant by automation.

**Context & Background**:
Helpline staff face intense pressure during peak periods (January Self Assessment), handle emotionally charged calls from anxious citizens, and have limited tools for complex queries. While some staff welcome technology that could reduce call volume pressure, many fear job losses from automation. Union representation (PCS union) will monitor the programme. The messaging must be honest: the ChatBot handles simple queries, freeing staff for complex cases where human empathy and judgment add genuine value.

**Driver Intensity**: MEDIUM

**Enablers**:
- Clear communication that ChatBot handles simple queries; humans handle complex cases
- Training on new escalation workflows and tools
- Reduced peak-period pressure and improved working conditions
- Career development into AI oversight, content management, quality assurance roles

**Blockers**:
- Perception of ChatBot as job replacement
- Poor escalation process (extra work without benefit)
- Union opposition derailing programme
- Lack of training or support during transition

**Related Stakeholders**:
- Customer Services Director (line management), SRO (programme messaging), PCS Union (representation)

---

### SD-12: ICO (Information Commissioner's Office) - Ensure Data Protection Compliance for AI Systems

**Stakeholder**: Information Commissioner's Office

**Driver Category**: COMPLIANCE / REGULATORY

**Driver Statement**: Ensure HMRC's use of AI to process citizen personal data complies with UK GDPR, with particular focus on automated decision-making (Article 22), DPIA (Article 35), transparency, and data subject rights — as part of the ICO's strategic priority on AI and data protection.

**Context & Background**:
The ICO has identified AI and automated decision-making as a strategic priority area. HMRC processing NI numbers, tax records, and Government Gateway credentials through an AI system is exactly the type of high-risk processing that attracts ICO attention. The ICO expects to see a comprehensive DPIA, clear lawful basis, robust transparency (ATRS record, privacy notice), and effective data subject rights procedures. Proactive engagement is better than reactive investigation.

**Driver Intensity**: HIGH

**Enablers**:
- Proactive DPIA submission before private beta
- Published ATRS record demonstrating transparency
- Clear privacy notice on GOV.UK
- Implemented data subject rights procedures

**Blockers**:
- Processing citizen data before DPIA approval
- Lack of transparency about AI processing
- Inability to honour right to erasure for AI training data
- Data breach during beta testing

**Related Stakeholders**:
- DPO (primary liaison), CISO (security/privacy), Citizens (data subjects)

---

### SD-13: HM Treasury - Ensure Value for Money and Spending Controls

**Stakeholder**: HM Treasury (Spending Team)

**Driver Category**: FINANCIAL

**Driver Statement**: Verify that the HMRC ChatBot investment represents value for money per Green Book appraisal standards, with realistic benefits projections, appropriate spending controls, and clear accountability — particularly given the novel nature of AI investment in public services.

**Context & Background**:
HM Treasury scrutinises all significant government technology investments. The ChatBot business case projects £150M savings over 3 years against £18.74M investment — a compelling 8:1 ratio. However, Treasury will challenge benefit realisation assumptions, question whether cheaper alternatives were considered, and probe operational cost trajectories (AWS/Bedrock costs at scale). The project falls within HMT spending approval thresholds and will be subject to standard business case controls.

**Driver Intensity**: MEDIUM

**Enablers**:
- Strong financial business case with conservative assumptions
- Phased investment with decision gates
- Benchmarking against similar government AI projects
- Clear benefit realisation plan with measurable milestones

**Blockers**:
- Over-optimistic savings projections
- Uncontrolled cloud spending growth
- Inability to attribute cost savings to ChatBot specifically
- Spending review changing budget allocations

**Related Stakeholders**:
- Finance Director (HMRC budget holder), Permanent Secretary (Accounting Officer), NAO (VfM audit)

---

### SD-14: NAO (National Audit Office) - Assess Value for Money and Governance

**Stakeholder**: National Audit Office

**Driver Category**: COMPLIANCE / RISK

**Driver Statement**: Have confidence that HMRC's ChatBot programme follows proper governance, delivers genuine value for money, manages risks appropriately, and does not become another failed government IT project that the NAO must report to Parliament.

**Context & Background**:
The NAO regularly examines government digital and technology programmes. Recent NAO reports have highlighted risks in government AI adoption, including lack of skills, poor governance, and unrealistic benefit projections. The NAO will expect to see robust programme governance, realistic business case, effective risk management, and measurable outcomes. The ChatBot's high profile (AI in public services, HMRC's scale) makes it a likely candidate for NAO attention.

**Driver Intensity**: MEDIUM

**Enablers**:
- IPA (Infrastructure and Projects Authority) reviews at each gate
- Clear governance structure with documented decisions (ADRs)
- Transparent spending controls and benefit tracking
- Architecture Decision Records providing audit trail

**Blockers**:
- Weak governance or undocumented decision-making
- Benefit realisation plan without measurement infrastructure
- Cost overruns without early warning mechanisms
- Programme milestones slipping without transparent reporting

**Related Stakeholders**:
- Permanent Secretary (accountable), Finance Director (spending), SRO (delivery), HM Treasury (VfM)

---

## Driver-to-Goal Mapping

### Goal G-1: Deflect 10% of Helpline Calls by End of Year 1

**Derived From Drivers**: SD-1, SD-3, SD-4, SD-8, SD-13

**Goal Owner**: SRO / Customer Services Director (joint)

**Goal Statement**: Reduce HMRC helpline call volume by 10% (5 million calls/year) by the end of the first year of operation through ChatBot self-service resolution, measured against the 50M call/year baseline.

**Why This Matters**: This goal directly satisfies the Minister's need for visible progress (SD-1), the SRO's delivery accountability (SD-3), the Finance Director's cost savings case (SD-4), the Customer Services Director's operational relief (SD-8), and Treasury's value for money requirements (SD-13). Achieving 10% in Year 1 is the critical proof point that validates the investment and builds confidence for further rollout.

**Success Metrics**:
- **Primary Metric**: HMRC helpline monthly call volume (compared to same month prior year, seasonally adjusted)
- **Secondary Metrics**:
  - ChatBot conversation volume (monthly, target: 5M Year 1)
  - ChatBot resolution rate (conversations completed without subsequent helpline call within 48 hours)
  - Helpline average wait time reduction

**Baseline**: 50 million helpline calls/year (FY 2025-26)

**Target**: 45 million helpline calls/year by Month 12 (FY 2026-27)

**Measurement Method**: HMRC telephony system call volume data (existing reporting), correlated with ChatBot analytics platform conversation data. Attribution: citizen who uses ChatBot and does NOT call helpline within 48 hours on same topic = successful deflection.

**Dependencies**:
- ChatBot live on GOV.UK by Month 12 (GDS approval required)
- Sufficient HMRC guidance coverage in knowledge base (>80% of top-50 query topics)
- GOV.UK and HMRC.gov.uk prominently linking to ChatBot
- Helpline IVR updated to offer ChatBot as alternative channel

**Risks to Achievement**:
- Low citizen adoption (users don't find or trust the ChatBot)
- Poor AI accuracy causing citizens to call helpline for correction
- GDS assessment delay pushing launch beyond Month 12

---

### Goal G-2: Achieve >95% AI Response Accuracy by Private Beta

**Derived From Drivers**: SD-1, SD-3, SD-6, SD-7, SD-8, SD-10

**Goal Owner**: Product Owner / AI Technical Lead (joint)

**Goal Statement**: Achieve >95% of ChatBot responses rated as "helpful" by citizens (thumbs up/down feedback) during private beta, with 100% of responses citing authoritative HMRC source documents.

**Why This Matters**: Accuracy is the single most important quality attribute. Inaccurate tax advice could cause citizen harm (incorrect tax returns, penalties), generate negative press (SD-1 blocker), trigger ICO investigation if inaccurate data processing (SD-7), and undermine citizen trust (SD-10). The CISO (SD-6) also considers inaccurate outputs a security issue (AI manipulation risk). The Customer Services Director (SD-8) needs high accuracy to prevent false deflection (citizens calling helpline after receiving bad ChatBot advice).

**Success Metrics**:
- **Primary Metric**: Citizen feedback score — percentage of responses rated "helpful" (thumbs up)
- **Secondary Metrics**:
  - Source citation rate (target: 100% of responses cite at least one source)
  - Ground truth accuracy test results (1000+ queries against known-correct answers)
  - Hallucination detection rate (responses containing information not in source documents)

**Baseline**: N/A (new system — establishing baseline during alpha)

**Target**: >95% helpful rating; 100% source citation; <1% hallucination rate

**Measurement Method**: In-app feedback mechanism (thumbs up/down with optional comment), automated ground truth testing suite in CI/CD, manual accuracy audit by tax policy experts (monthly sample of 200 responses).

**Dependencies**:
- Comprehensive knowledge base covering top-50 citizen query topics
- RAG architecture correctly retrieving relevant documents (precision >0.85)
- LLM prompt engineering producing Plain English, accurate responses
- Tax policy expert availability for accuracy validation

**Risks to Achievement**:
- Knowledge base gaps in obscure tax topics
- LLM hallucination on edge cases despite RAG grounding
- Outdated guidance in knowledge base (policy changes not synced)
- Insufficient beta feedback volume to measure accurately

---

### Goal G-3: Pass GDS Service Standard Assessment Before Launch

**Derived From Drivers**: SD-1, SD-2, SD-3, SD-9

**Goal Owner**: SRO / Product Owner (joint)

**Goal Statement**: Pass GDS Service Standard assessment across all 14 criteria with no "Red" ratings, completing Discovery, Alpha, Beta, and Live assessments on schedule to enable public launch by Month 12.

**Why This Matters**: GDS assessment is a hard gate — failure prevents launch on GOV.UK. The Minister (SD-1) and Permanent Secretary (SD-2) cannot accept a failed assessment. The SRO's (SD-3) delivery accountability depends on it. The GDS team (SD-9) will rigorously evaluate evidence against all 14 criteria.

**Success Metrics**:
- **Primary Metric**: GDS assessment outcome at each gate (Green/Amber/Red per criterion)
- **Secondary Metrics**:
  - Number of criteria rated "Green" vs "Amber" vs "Red"
  - Time between assessment and remediation (if Amber ratings)
  - Evidence portfolio completeness score

**Baseline**: No previous assessment (new service)

**Target**: All 14 criteria Green or Amber (no Red) at each gate; all Green at Live assessment

**Measurement Method**: GDS assessment panel report (formal output), internal mock assessment scores (monthly from Month 6).

**Dependencies**:
- User research with minimum 30 citizens across all personas
- Accessibility testing with minimum 5 disabled users per round
- Performance data from beta period (real metrics, not projections)
- Operational readiness documentation (support model, monitoring, incident response)

**Risks to Achievement**:
- Insufficient user research evidence (common failure point)
- Accessibility gaps discovered late (hard to fix quickly)
- Performance metrics not meeting targets during beta
- Incomplete operational readiness documentation

---

### Goal G-4: Achieve Zero Security Incidents in First 12 Months

**Derived From Drivers**: SD-2, SD-6, SD-7, SD-12

**Goal Owner**: CISO

**Goal Statement**: Achieve zero security incidents involving citizen data exposure, prompt injection exploitation, or unauthorised access to HMRC systems in the first 12 months of operation, with Cyber Essentials Plus certification obtained before private beta.

**Why This Matters**: A security breach would be catastrophic for the programme — triggering ICO investigation (SD-12), Permanent Secretary accountability (SD-2), and media coverage that could force service shutdown. The CISO (SD-6) has staked professional credibility on security-by-design. The DPO (SD-7) requires security as a prerequisite for DPIA approval.

**Success Metrics**:
- **Primary Metric**: Number of security incidents involving citizen data = 0
- **Secondary Metrics**:
  - Prompt injection attempts blocked / total attempts (target: 100% blocked)
  - Mean time to detect security events (target: <5 minutes)
  - Critical/high vulnerabilities in production (target: 0)
  - Cyber Essentials Plus certification status

**Baseline**: N/A (new system)

**Target**: Zero data-related security incidents; Cyber Essentials Plus before private beta; zero critical/high vulnerabilities in production

**Measurement Method**: HMRC SOC security monitoring (Splunk, GuardDuty), vulnerability scanning dashboards (Snyk, AWS Inspector), penetration test reports (CHECK-approved supplier), security incident register.

**Dependencies**:
- CHECK-approved pen test supplier booked for Month 5-6
- Security architect embedded in delivery team from Month 1
- AWS GuardDuty, Security Hub, and WAF configured before beta
- Prompt injection defence testing framework established

**Risks to Achievement**:
- Novel AI attack vectors not covered by standard pen testing
- Zero-day vulnerability in third-party dependency
- Misconfigured AWS security services
- Insider threat or social engineering

---

### Goal G-5: Complete and Approve DPIA Before Private Beta

**Derived From Drivers**: SD-7, SD-12

**Goal Owner**: DPO

**Goal Statement**: Complete a Data Protection Impact Assessment covering all citizen data processing by the ChatBot, obtain HMRC DPO approval, and submit to ICO (if required) at least 4 weeks before private beta begins.

**Why This Matters**: UK GDPR Article 35 mandates a DPIA for high-risk processing. AI processing of personal tax data clearly meets the threshold. The DPO (SD-7) requires this before any citizen data is processed. The ICO (SD-12) considers DPIA compliance a priority enforcement area. Processing without an approved DPIA would violate UK GDPR.

**Success Metrics**:
- **Primary Metric**: DPIA approval status (Approved by DPO: Yes/No)
- **Secondary Metrics**:
  - All identified risks mitigated to acceptable level
  - ICO consultation completed (if required under Article 36)
  - Privacy notice published on GOV.UK

**Baseline**: No DPIA exists

**Target**: DPIA approved 4+ weeks before private beta (approximately Month 5)

**Measurement Method**: HMRC DPIA register, DPO sign-off document, ICO correspondence (if applicable).

**Dependencies**:
- Data flows documented and finalised
- Security architecture confirmed (encryption, access controls)
- Retention policies agreed and configured
- Data subject rights procedures designed and tested

**Risks to Achievement**:
- Scope changes requiring DPIA re-assessment
- ICO consultation extending timeline (8 weeks minimum)
- Unresolvable data protection risks blocking approval
- DPO capacity constraints

---

### Goal G-6: Achieve WCAG 2.2 AA Compliance with Zero Critical Issues at Launch

**Derived From Drivers**: SD-9, SD-10

**Goal Owner**: Accessibility Specialist

**Goal Statement**: Achieve 100% WCAG 2.2 Level AA compliance with zero critical or high accessibility issues at launch, validated by automated testing, manual screen reader testing, and user testing with minimum 5 disabled citizens.

**Why This Matters**: Accessibility is a legal requirement (Public Sector Bodies Accessibility Regulations 2018) and GDS Service Standard criterion 5. 13.9M UK citizens have disabilities. The GDS assessment team (SD-9) will specifically evaluate accessibility evidence. Citizens (SD-10) include personas who rely entirely on assistive technology. Failure to comply exposes HMRC to legal action under the Equality Act 2010.

**Success Metrics**:
- **Primary Metric**: Number of WCAG 2.2 AA critical/high issues = 0
- **Secondary Metrics**:
  - Automated accessibility test pass rate (axe-core, Pa11y)
  - Screen reader testing completion (JAWS, NVDA, VoiceOver)
  - Disabled user research participants per round (minimum 5)
  - Accessibility statement published on GOV.UK

**Baseline**: N/A (new service)

**Target**: Zero critical/high issues; automated tests passing in CI/CD; screen reader testing complete; accessibility statement published

**Measurement Method**: axe-core and Pa11y automated testing in CI/CD (blocking on critical/high), manual testing reports from accessibility specialist, user research session reports.

**Dependencies**:
- GOV.UK Design System components used (inherent accessibility)
- Content designers following Plain English and GOV.UK style guide
- Accessibility specialist available throughout development
- Disabled citizens recruited for user research

**Risks to Achievement**:
- Custom chat UI components not inherently accessible
- Dynamic content (typing indicators, live updates) breaking screen readers
- Welsh language content not tested for accessibility
- Difficulty recruiting disabled citizens for user testing

---

### Goal G-7: Demonstrate £25M Cost Savings in Year 1

**Derived From Drivers**: SD-4, SD-13, SD-14

**Goal Owner**: Finance Director

**Goal Statement**: Demonstrate £25M in operational cost savings in Year 1 through measured helpline call volume reduction, validated by finance analysis and attributed to ChatBot deflection.

**Why This Matters**: The financial business case (£150M savings over 3 years) is the primary justification for the investment. The Finance Director (SD-4) needs evidence for spending reviews. HM Treasury (SD-13) requires value for money validation. The NAO (SD-14) will assess whether projected benefits were realised. £25M Year 1 savings (5M calls × £5 average cost) is the conservative projection.

**Success Metrics**:
- **Primary Metric**: Verified cost savings (£) from reduced helpline operations
- **Secondary Metrics**:
  - Cost per ChatBot conversation vs cost per helpline call
  - AWS/Bedrock operational costs vs budget
  - Total cost of ownership (TCO) trending

**Baseline**: Helpline cost: £250M-£500M/year (50M calls × £5-£10 per call)

**Target**: £25M Year 1 savings (conservative: 5M calls deflected × £5 average)

**Measurement Method**: HMRC finance analysis comparing helpline costs year-on-year (controlling for other factors), ChatBot operational cost tracking (AWS billing, FinOps dashboards).

**Dependencies**:
- Goal G-1 achieved (10% helpline deflection)
- FinOps practices established (AWS cost monitoring and optimisation)
- Finance team methodology agreed for attributing savings

**Risks to Achievement**:
- Helpline cost savings offset by new ChatBot operational costs
- Difficulty isolating ChatBot impact from other service changes
- AWS costs exceeding budget at scale
- Finance methodology challenge from Treasury or NAO

---

### Goal G-8: Publish ATRS Record Before Public Beta

**Derived From Drivers**: SD-1, SD-7, SD-12

**Goal Owner**: Product Owner / AI Technical Lead

**Goal Statement**: Publish a comprehensive Algorithmic Transparency Recording Standard (ATRS) record on GOV.UK before public beta, demonstrating responsible AI deployment and meeting UK Government transparency requirements.

**Why This Matters**: UK Government mandates ATRS for AI systems in public services. The Minister (SD-1) needs to demonstrate responsible AI leadership. The DPO (SD-7) considers transparency a GDPR requirement. The ICO (SD-12) expects algorithmic transparency as part of data protection compliance. The ATRS record has already been drafted (ARC-001-ATRS-v1.0).

**Success Metrics**:
- **Primary Metric**: ATRS record published on GOV.UK (Yes/No)
- **Secondary Metrics**:
  - All mandatory ATRS fields completed
  - Data Ethics Committee approval obtained
  - Update process documented for model changes

**Baseline**: Draft ATRS record exists (ARC-001-ATRS-v1.0)

**Target**: Approved and published ATRS record before public beta (Month 8)

**Measurement Method**: GOV.UK publication status, Data Ethics Committee minutes.

**Dependencies**:
- AI model architecture finalised
- Bias testing completed with results documented
- Data Ethics Committee review scheduled
- GOV.UK publishing process agreed with GDS

**Risks to Achievement**:
- Data Ethics Committee requesting significant changes
- Model architecture changes requiring ATRS re-draft
- GDS publishing process delays
- Bias testing revealing issues requiring model changes

---

### Goal G-9: Ensure Welsh Language Parity by Launch

**Derived From Drivers**: SD-9, SD-10

**Goal Owner**: Content Lead / Product Owner

**Goal Statement**: Deliver full Welsh language support (interface and AI responses) with functional parity to English for all core tax guidance topics by public launch, meeting Welsh Language Act 1993 requirements.

**Why This Matters**: Welsh language support is a legal requirement. GDS assessment (SD-9) evaluates accessibility including language provision. Citizens in Wales (SD-10, Dafydd persona) have a legal right to access services in Welsh. The Welsh Language Commissioner monitors government service compliance.

**Success Metrics**:
- **Primary Metric**: Welsh/English functional parity score (percentage of features available in Welsh)
- **Secondary Metrics**:
  - Welsh language AI response quality (native speaker review)
  - Welsh user satisfaction scores
  - Welsh Language Commissioner compliance status

**Baseline**: No Welsh language support exists

**Target**: 100% UI parity, >90% content coverage for top-50 topics, native speaker quality validation

**Measurement Method**: Feature comparison matrix (Welsh vs English), Welsh language quality review by native speakers, Welsh citizen user testing.

**Dependencies**:
- Welsh HMRC guidance content available for knowledge base
- Welsh language AI capability (translation or Welsh-language model)
- Native Welsh-speaking content reviewer recruited
- Welsh-speaking citizens recruited for user testing

**Risks to Achievement**:
- Insufficient Welsh HMRC guidance content
- AI translation quality inadequate for tax guidance accuracy
- Native Welsh reviewer availability
- Welsh Language Commissioner finding compliance gaps

---

## Goal-to-Outcome Mapping

### Outcome O-1: Operational Efficiency — 10% Helpline Cost Reduction

**Supported Goals**: G-1, G-7

**Outcome Statement**: HMRC helpline operational costs reduced by £25M/year (10% of baseline) through ChatBot self-service deflection, with 5 million citizen queries resolved without human agent involvement.

**Measurement Details**:
- **KPI**: Annual helpline cost reduction (£)
- **Current Value**: £250M-£500M/year (50M calls × £5-£10/call)
- **Target Value**: £225M-£475M/year (45M calls)
- **Measurement Frequency**: Monthly (with quarterly formal reporting)
- **Data Source**: HMRC telephony system, Finance operational reporting
- **Report Owner**: Finance Director / Customer Services Director

**Business Value**:
- **Financial Impact**: £25M annual savings (Year 1), scaling to £75M by Year 3
- **Strategic Impact**: Demonstrates government AI value, positions HMRC as digital leader
- **Operational Impact**: Reduced helpline pressure, improved staff working conditions during peak
- **Customer Impact**: Reduced wait times, 24/7 availability for simple queries

**Timeline**:
- **Phase 1 (Months 1-3 post-launch)**: 3% helpline reduction (1.5M calls deflected, £7.5M savings)
- **Phase 2 (Months 4-6 post-launch)**: 6% helpline reduction (3M calls deflected, £15M savings)
- **Phase 3 (Months 7-12 post-launch)**: 10% helpline reduction (5M calls deflected, £25M savings)
- **Sustainment (Year 2+)**: 20% reduction (Year 2), 30% reduction (Year 3)

**Stakeholder Benefits**:
- **Minister**: Positive parliamentary response on HMRC modernisation
- **Finance Director**: Demonstrable ROI for investment committee
- **Customer Services Director**: Reduced peak-period pressure
- **Helpline Staff**: More manageable workload, focus on complex cases
- **Citizens**: Shorter wait times when they do need to call

**Leading Indicators** (early signals of success):
- ChatBot conversation volume growing week-on-week
- ChatBot resolution rate (conversations without subsequent call) >70%
- Helpline call volume declining month-on-month (seasonally adjusted)

**Lagging Indicators** (final proof of success):
- Annual helpline call volume reduction verified by finance
- £25M cost savings validated by internal audit
- Helpline average wait time reduction sustained over 12 months

---

### Outcome O-2: Citizen Satisfaction — Trust in AI-Powered Tax Guidance

**Supported Goals**: G-2, G-6, G-9

**Outcome Statement**: Citizens trust and value the HMRC ChatBot, evidenced by >70% NPS score, >95% helpfulness rating, and >40% return user rate within 6 months of public launch.

**Measurement Details**:
- **KPI**: Net Promoter Score (NPS) and response helpfulness rating
- **Current Value**: N/A (new service)
- **Target Value**: NPS >70%, helpfulness >95%, return rate >40%
- **Measurement Frequency**: Weekly (real-time dashboard), monthly (formal report)
- **Data Source**: In-app feedback (thumbs up/down), NPS survey (quarterly), analytics platform
- **Report Owner**: Product Owner

**Business Value**:
- **Financial Impact**: Higher satisfaction drives adoption, driving greater helpline deflection
- **Strategic Impact**: Citizen trust in government AI services — transferable to other departments
- **Operational Impact**: Positive feedback reduces escalation rate (<5%)
- **Customer Impact**: Citizens feel served, not frustrated; reduced tax compliance anxiety

**Timeline**:
- **Phase 1 (Months 1-3)**: Establish baseline — NPS >50%, helpfulness >85%
- **Phase 2 (Months 4-6)**: Improve through iteration — NPS >60%, helpfulness >90%
- **Phase 3 (Months 7-12)**: Meet target — NPS >70%, helpfulness >95%
- **Sustainment (Year 2+)**: Maintain and improve through continuous iteration

**Stakeholder Benefits**:
- **Minister**: Positive citizen experience for media/parliamentary narrative
- **SRO**: Programme success metric achieved
- **GDS Assessment Team**: Evidence for Service Standard criteria 1, 4, 10
- **Citizens**: Better service experience than helpline for simple queries

**Leading Indicators**:
- Daily helpfulness rating trending upward
- Repeat user rate increasing (citizens choosing ChatBot over helpline)
- Positive user research feedback themes

**Lagging Indicators**:
- Quarterly NPS score meeting target
- Annual citizen satisfaction survey results
- Reduced complaints about HMRC service quality

---

### Outcome O-3: Compliance — Full Regulatory Compliance Achieved

**Supported Goals**: G-3, G-4, G-5, G-8

**Outcome Statement**: HMRC ChatBot achieves full compliance with GDS Service Standard (14 criteria), UK GDPR (DPIA approved), Cyber Essentials Plus, WCAG 2.2 AA, ATRS, and Welsh Language Act 1993 — with zero compliance failures or enforcement actions.

**Measurement Details**:
- **KPI**: Compliance status across all regulatory frameworks (pass/fail)
- **Current Value**: Not applicable (pre-launch)
- **Target Value**: Pass/Approved across all frameworks
- **Measurement Frequency**: At each governance gate; annually for renewals
- **Data Source**: GDS assessment reports, DPIA register, Cyber Essentials certification, accessibility audit reports, ATRS publication, Welsh Language Commissioner correspondence
- **Report Owner**: Enterprise Architect / DPO (joint)

**Business Value**:
- **Financial Impact**: Avoids ICO fines (up to £17.5M), legal action costs
- **Strategic Impact**: Demonstrates HMRC as exemplar of responsible AI governance
- **Operational Impact**: Enables public launch on GOV.UK (GDS gate)
- **Customer Impact**: Citizens protected by robust data protection and accessibility

**Timeline**:
- **Phase 1 (Month 5)**: DPIA approved, Cyber Essentials Plus obtained
- **Phase 2 (Month 8)**: ATRS published, accessibility audit completed
- **Phase 3 (Month 11)**: GDS Live assessment passed
- **Sustainment (Annual)**: Re-certification, annual DPIA review, ATRS updates

**Stakeholder Benefits**:
- **Permanent Secretary**: No accountability failures, no PAC hearings
- **CISO**: Security standards met, professional credibility maintained
- **DPO**: GDPR compliance demonstrated, ICO relationship maintained
- **GDS Assessment Team**: Service meets standard

**Leading Indicators**:
- Governance gates passing on schedule
- Security scanning producing clean results
- Mock GDS assessment scores improving

**Lagging Indicators**:
- GDS Live assessment outcome (Green across all criteria)
- Zero ICO enforcement actions in first 2 years
- Zero security incidents in first 12 months

---

### Outcome O-4: Platform Capability — Reusable AI Infrastructure

**Supported Goals**: G-2 (indirectly)

**Outcome Statement**: HMRC has a production-grade, reusable AI platform (RAG infrastructure, LLM integration, vector database, observability) that can be leveraged for at least 2 additional AI use cases within 24 months.

**Measurement Details**:
- **KPI**: Number of additional HMRC AI services built on ChatBot platform components
- **Current Value**: 0
- **Target Value**: 2+ additional use cases in pipeline by Month 18
- **Measurement Frequency**: Quarterly (strategic review)
- **Data Source**: HMRC Digital Strategy portfolio, Architecture Review Board decisions
- **Report Owner**: CDIO

**Business Value**:
- **Financial Impact**: Reduced cost for future AI services (platform amortisation)
- **Strategic Impact**: HMRC established as AI leader in government
- **Operational Impact**: Faster time-to-market for future AI capabilities
- **Customer Impact**: More AI-powered services improving citizen experience

**Timeline**:
- **Phase 1 (Months 1-12)**: Build and validate platform via ChatBot
- **Phase 2 (Months 13-18)**: Identify and scope 2 additional use cases
- **Phase 3 (Months 19-24)**: Deploy first additional AI service on platform
- **Sustainment (Year 3+)**: Platform maturity, self-service AI capability

**Stakeholder Benefits**:
- **CDIO**: Strategic technology vision realised
- **Enterprise Architect**: Reusable architecture patterns established
- **Finance Director**: Better ROI through platform amortisation
- **SRO**: Legacy beyond single project

**Leading Indicators**:
- Platform components documented as reusable
- Architecture Decision Records capturing platform patterns
- Internal interest from other HMRC teams for AI services

**Lagging Indicators**:
- Second AI service deployed on platform
- Platform investment amortised across multiple services
- HMRC recognised as government AI leader

---

## Complete Traceability Matrix

### Stakeholder → Driver → Goal → Outcome

| Stakeholder | Driver ID | Driver Summary | Goal ID | Goal Summary | Outcome ID | Outcome Summary |
|-------------|-----------|----------------|---------|--------------|------------|-----------------|
| Minister | SD-1 | Demonstrate digital modernisation | G-1 | 10% helpline deflection Year 1 | O-1 | £25M cost reduction |
| Minister | SD-1 | Demonstrate digital modernisation | G-3 | Pass GDS assessment | O-3 | Full compliance |
| Minister | SD-1 | Demonstrate digital modernisation | G-8 | Publish ATRS record | O-3 | Full compliance |
| Permanent Secretary | SD-2 | Avoid accountability failures | G-3 | Pass GDS assessment | O-3 | Full compliance |
| Permanent Secretary | SD-2 | Avoid accountability failures | G-4 | Zero security incidents | O-3 | Full compliance |
| SRO | SD-3 | Deliver on time, within budget | G-1 | 10% helpline deflection Year 1 | O-1 | £25M cost reduction |
| SRO | SD-3 | Deliver on time, within budget | G-2 | >95% AI accuracy | O-2 | Citizen satisfaction |
| SRO | SD-3 | Deliver on time, within budget | G-3 | Pass GDS assessment | O-3 | Full compliance |
| Finance Director | SD-4 | Demonstrate value for money | G-1 | 10% helpline deflection Year 1 | O-1 | £25M cost reduction |
| Finance Director | SD-4 | Demonstrate value for money | G-7 | £25M Year 1 savings | O-1 | £25M cost reduction |
| CDIO | SD-5 | Build AI capability | G-2 | >95% AI accuracy | O-4 | Reusable AI platform |
| CISO | SD-6 | Protect citizen data | G-4 | Zero security incidents | O-3 | Full compliance |
| DPO | SD-7 | Ensure UK GDPR compliance | G-5 | DPIA approved before beta | O-3 | Full compliance |
| DPO | SD-7 | Ensure UK GDPR compliance | G-8 | Publish ATRS record | O-3 | Full compliance |
| Customer Svcs Director | SD-8 | Reduce helpline pressure | G-1 | 10% helpline deflection Year 1 | O-1 | £25M cost reduction |
| Customer Svcs Director | SD-8 | Reduce helpline pressure | G-2 | >95% AI accuracy | O-2 | Citizen satisfaction |
| GDS Assessment Team | SD-9 | Ensure Service Standard met | G-3 | Pass GDS assessment | O-3 | Full compliance |
| GDS Assessment Team | SD-9 | Ensure Service Standard met | G-6 | WCAG 2.2 AA compliance | O-3 | Full compliance |
| Citizens | SD-10 | Fast, accurate, accessible guidance | G-2 | >95% AI accuracy | O-2 | Citizen satisfaction |
| Citizens | SD-10 | Fast, accurate, accessible guidance | G-6 | WCAG 2.2 AA compliance | O-2 | Citizen satisfaction |
| Citizens | SD-10 | Fast, accurate, accessible guidance | G-9 | Welsh language parity | O-2 | Citizen satisfaction |
| Helpline Staff | SD-11 | Job security, manageable workload | G-1 | 10% helpline deflection Year 1 | O-1 | £25M cost reduction |
| ICO | SD-12 | Data protection compliance | G-5 | DPIA approved before beta | O-3 | Full compliance |
| ICO | SD-12 | Data protection compliance | G-8 | Publish ATRS record | O-3 | Full compliance |
| HM Treasury | SD-13 | Value for money | G-7 | £25M Year 1 savings | O-1 | £25M cost reduction |
| NAO | SD-14 | Value for money, governance | G-7 | £25M Year 1 savings | O-1 | £25M cost reduction |

### Conflict Analysis

**Competing Drivers**:

- **Conflict 1**: **Speed vs Assurance** — The Minister (SD-1) and SRO (SD-3) want rapid delivery (Month 12 launch) but the CISO (SD-6), DPO (SD-7), and GDS (SD-9) require thorough security testing, DPIA completion, and evidence-based assessment that takes time.
  - **Resolution Strategy**: Parallel security and compliance workstreams embedded from Month 1 (agreed in requirements document conflict resolution C-1). Security testing starts in Alpha, not at the end. DPIA drafted alongside development. GDS pre-assessment engagement from Month 3. This preserves the timeline while building assurance incrementally.

- **Conflict 2**: **Innovation vs Risk Appetite** — The CDIO (SD-5) wants to push AI capabilities (platform, reuse, advanced features) but the CISO (SD-6) and DPO (SD-7) have conservative risk appetite for AI processing OFFICIAL-SENSITIVE data.
  - **Resolution Strategy**: MVP scope for launch (text chat with RAG), with advanced features (voice, personalized recommendations) deferred to post-launch phases. AI platform components built to production standard but reuse roadmap is post-launch. This satisfies CISO/DPO for launch while preserving CDIO's strategic vision.

- **Conflict 3**: **Automation vs Employment** — The Finance Director (SD-4) wants maximum deflection to maximise savings, but Helpline Staff (SD-11) fear job losses. PCS Union may oppose if messaging is poor.
  - **Resolution Strategy**: Honest messaging — ChatBot handles simple, repetitive queries; humans handle complex cases needing empathy and judgment. Staff redeployed to complex casework, AI oversight, content management, and quality assurance. No compulsory redundancies in Year 1. Joint consultation with PCS Union. This aligns Finance Director savings (simple queries deflected) with staff interests (better working conditions, career development).

- **Conflict 4**: **Feature Richness vs Accessibility** — Product Owner wants modern chat UX (typing indicators, animations, rich cards) but Accessibility Specialist mandates WCAG 2.2 AA compliance that constrains UI choices.
  - **Resolution Strategy**: Accessibility is non-negotiable (legal requirement). All features must pass accessibility review before implementation. Use ARIA live regions for dynamic content. GOV.UK Design System components by default. This is already resolved in requirements document (conflict C-2) with accessibility having final approval authority on UI features.

**Synergies**:

- **Synergy 1**: SD-1 (Minister visibility) + SD-4 (cost savings) + SD-8 (operational relief) — All three stakeholders benefit from helpline deflection. Achieving Goal G-1 simultaneously satisfies the Minister's narrative, the Finance Director's business case, and the Customer Services Director's operational needs. This is the project's core alignment.

- **Synergy 2**: SD-6 (security) + SD-7 (data protection) + SD-12 (ICO compliance) — Security and data protection requirements are deeply aligned. Investment in encryption, access controls, and audit logging satisfies all three stakeholders simultaneously. DPIA and security architecture reinforce each other.

- **Synergy 3**: SD-9 (GDS standard) + SD-10 (citizen needs) + SD-6 (WCAG compliance) — GDS Service Standard criteria, citizen user needs, and accessibility requirements all point in the same direction: user-centred, accessible, well-researched service design. Good user research satisfies GDS criteria 1-5, citizens' desire for usable service, and accessibility requirements.

- **Synergy 4**: SD-2 (governance) + SD-13 (VfM) + SD-14 (NAO readiness) — Strong governance, clear business case, and audit-ready documentation satisfy the Permanent Secretary, HM Treasury, and NAO simultaneously. Investment in governance processes pays dividends across all three.

---

## Communication & Engagement Plan

### Minister (Financial Secretary to the Treasury)

**Primary Message**: The HMRC Tax Assistant ChatBot is on track to launch by [tax year start], providing 24/7 tax guidance to citizens and demonstrating responsible AI leadership in government.

**Key Talking Points**:
- Projected £25M Year 1 savings, scaling to £75M by Year 3
- Responsible AI deployment with published ATRS record
- Citizen satisfaction targets exceeded during beta testing
- Full accessibility and Welsh language compliance

**Communication Frequency**: Quarterly (more frequent during assessment/launch)

**Preferred Channel**: Ministerial briefing pack with dashboard summary; oral briefing via SRO

**Success Story**: "HMRC ChatBot answered 5 million citizen tax queries in its first year, saving £25M and achieving 95%+ satisfaction — with zero data incidents and full transparency through the published Algorithmic Transparency record."

---

### Permanent Secretary

**Primary Message**: Programme governance is robust, value for money is demonstrated, and risk management is comprehensive — the programme is ready for any level of scrutiny.

**Key Talking Points**:
- IPA gateway reviews completed at each phase
- Business case meets Green Book appraisal standards
- Risk register actively managed with escalation to programme board
- NAO readiness documentation maintained throughout

**Communication Frequency**: Monthly (programme board)

**Preferred Channel**: Programme board papers with risk register, gateway review outcomes

**Success Story**: "The ChatBot programme passed all governance gates, delivered on time and within budget, with independent assurance confirming proper governance and value for money."

---

### CISO

**Primary Message**: Security is embedded from Day 1 with Zero Trust architecture, and all NCSC Cloud Security Principles are addressed — this programme demonstrates security-by-design for AI systems.

**Key Talking Points**:
- Threat model completed using NCSC methodology
- Prompt injection defences tested and validated
- CHECK pen testing completed in Beta with zero critical findings
- Cyber Essentials Plus certified before private beta
- All OFFICIAL-SENSITIVE data encrypted at rest (AES-256) and in transit (TLS 1.3)

**Communication Frequency**: Monthly (security review); ad-hoc for security events

**Preferred Channel**: Security review meetings, threat intelligence briefings, Splunk dashboards

**Success Story**: "Zero security incidents in first 12 months despite 50,000+ prompt injection attempts blocked. Security-by-design approach validated — becoming the template for future HMRC AI services."

---

### Citizens

**Primary Message**: HMRC has a new way to get quick, accurate tax guidance — available 24/7, in English and Welsh, and designed to be accessible to everyone.

**Key Talking Points**:
- Get answers to common tax questions instantly, without waiting on hold
- Powered by official HMRC guidance — every answer cites its source
- Available on GOV.UK, works with screen readers, available in Welsh
- Your data is protected and you control what's stored

**Communication Frequency**: At launch and key milestones

**Preferred Channel**: GOV.UK announcements, HMRC newsletter, helpline IVR messages, social media

**Success Story**: "Sarah, a self-employed graphic designer, got clear guidance on allowable business expenses at 10pm on a Sunday — when the helpline was closed. The ChatBot cited the exact HMRC guidance page so she could verify the answer."

---

### Helpline Operations Staff

**Primary Message**: The ChatBot handles the repetitive, simple queries so you can focus on the complex cases where your expertise and empathy make a real difference to citizens.

**Key Talking Points**:
- ChatBot handles simple queries (Personal Allowance, deadlines, allowable expenses)
- Complex cases, appeals, and emotional situations remain with human agents
- Training provided on new escalation workflow — ChatBot passes full context to you
- New career paths in AI oversight, content management, and quality assurance

**Communication Frequency**: Monthly (change impact sessions); weekly during launch

**Preferred Channel**: All-staff communications, team briefings, intranet, PCS Union consultation

**Success Story**: "During January Self Assessment deadline, helpline wait times dropped from 25 minutes to 8 minutes because the ChatBot handled 40% of simple queries. Staff reported feeling less pressured and able to give proper attention to complex cases."

---

## Change Impact Assessment

### Impact on Stakeholders

| Stakeholder | Current State | Future State | Change Magnitude | Resistance Risk | Mitigation Strategy |
|-------------|---------------|--------------|------------------|-----------------|---------------------|
| Citizens | Phone/web self-service for tax queries | AI-powered chat alongside existing channels | MEDIUM | LOW | Clear communication, easy-to-use interface, ability to reach human |
| Helpline Staff | Handle all inbound queries | Handle complex queries; ChatBot handles simple | HIGH | MEDIUM | Training, career development, union consultation, no compulsory redundancies |
| Content Team | Manage GOV.UK pages | Also manage ChatBot knowledge base | MEDIUM | LOW | Training, clear processes, tooling support |
| Tax Policy Experts | Review published guidance | Also review AI knowledge base accuracy | LOW | LOW | Minimal additional workload, structured review process |
| IT Operations | Manage traditional web services | Also manage AI/ML infrastructure | MEDIUM | LOW | Runbooks, training, operational documentation |
| Customer Services Director | Manage helpline operations | Manage helpline + ChatBot channel | MEDIUM | LOW | Operational dashboards, clear escalation workflow |

### Change Readiness

**Champions** (Enthusiastic supporters):
- **CDIO** — Sees strategic opportunity for AI platform and digital talent
- **SRO** — Career-defining programme, strong personal commitment
- **Product Owner** — Building innovative AI service, professionally exciting
- **Digital team members** — Working with cutting-edge AI technology

**Fence-sitters** (Neutral, need convincing):
- **Finance Director** — Supportive of savings but sceptical of projections until beta evidence
- **Tax Policy Experts** — Open to ChatBot but concerned about accuracy in edge cases
- **Customer Services Director** — Wants to believe but has seen previous digital initiatives underdeliver

**Resisters** (Opposed or skeptical):
- **Helpline Staff (some)** — Fear job losses, perceive ChatBot as replacement — Strategy: transparent communication, no compulsory redundancies, career development into AI-adjacent roles
- **PCS Union** — Will scrutinise workforce impact — Strategy: early joint consultation, workforce impact assessment, redeployment commitments
- **Security-cautious individuals** — Concerned about AI processing sensitive data — Strategy: security-by-design evidence, pen test results, CISO endorsement

---

## Risk Register (Stakeholder-Related)

### Risk R-1: Minister Loses Confidence Due to Negative Press

**Related Stakeholders**: Minister, SRO, Permanent Secretary

**Risk Description**: Negative media coverage about AI errors, data concerns, or service failures causes the Minister to lose confidence in the programme, potentially leading to programme pause or cancellation.

**Impact on Goals**: G-1 (deflection targets missed), G-3 (launch delayed)

**Probability**: LOW

**Impact**: CRITICAL

**Mitigation Strategy**: Proactive media strategy, rapid response capability for incidents, ministerial briefing packs with positive metrics, controlled beta rollout to limit blast radius of any issues.

**Contingency Plan**: If negative coverage occurs, SRO provides immediate ministerial briefing with facts, remediation plan, and timeline. Temporary service restriction (e.g., remove authenticated features) while addressing root cause.

---

### Risk R-2: GDS Assessment Fails at Live Stage

**Related Stakeholders**: GDS Assessment Team, SRO, Minister

**Risk Description**: GDS Service Standard assessment at Live stage identifies Red ratings on one or more criteria, preventing public launch and requiring rework that delays the programme.

**Impact on Goals**: G-3 (directly blocked), G-1 (launch delay reduces Year 1 deflection), G-7 (delayed savings)

**Probability**: MEDIUM

**Impact**: HIGH

**Mitigation Strategy**: Early GDS engagement (pre-assessment meeting Month 6), monthly internal mock assessments from Month 6, remediation sprints for any Amber areas, strong user research evidence portfolio, dedicated assessment preparation lead.

**Contingency Plan**: If Red rating received, rapid remediation sprint (4-6 weeks), request re-assessment. Negotiate conditional approval with remediation plan if issues are minor.

---

### Risk R-3: Helpline Staff Resistance Undermines Programme

**Related Stakeholders**: Helpline Staff, PCS Union, Customer Services Director

**Risk Description**: Helpline staff actively or passively resist the ChatBot through union action, negative internal communications, or poor escalation handling — undermining citizen experience and operational metrics.

**Impact on Goals**: G-1 (poor escalation experience drives citizens back to helpline), G-2 (accuracy perception damaged by staff comments)

**Probability**: MEDIUM

**Impact**: MEDIUM

**Mitigation Strategy**: Early PCS Union engagement (Month 2), workforce impact assessment published, no compulsory redundancies commitment, career development programme for AI-adjacent roles, helpline staff input into escalation workflow design, regular all-hands communications.

**Contingency Plan**: If union raises formal dispute, escalate to HR Director with SRO involvement. Offer enhanced consultation period and independent workforce review.

---

### Risk R-4: Data Breach Triggers ICO Investigation

**Related Stakeholders**: CISO, DPO, ICO, Permanent Secretary, Citizens

**Risk Description**: A security incident exposes citizen personal data (NI numbers, tax records), triggering ICO investigation, potential fine, and catastrophic reputational damage.

**Impact on Goals**: G-4 (directly failed), G-3 (potential service suspension), G-1 (citizen trust destroyed)

**Probability**: LOW

**Impact**: CRITICAL

**Mitigation Strategy**: Zero Trust architecture, encryption at rest and in transit, annual CHECK pen testing, continuous security monitoring (SOC integration), prompt injection defences, DPIA with thorough risk assessment, incident response plan tested quarterly.

**Contingency Plan**: Activate HMRC data breach incident response plan. Notify ICO within 72 hours, affected citizens without undue delay. Contain breach, forensic investigation, remediation. Potentially suspend service during investigation. Ministerial briefing within 4 hours.

---

### Risk R-5: Citizen Adoption Below Projections

**Related Stakeholders**: SRO, Finance Director, Minister, Customer Services Director

**Risk Description**: Citizens don't discover, trust, or find value in the ChatBot, resulting in adoption significantly below projections and undermining the business case.

**Impact on Goals**: G-1 (deflection targets missed), G-7 (savings not achieved)

**Probability**: MEDIUM

**Impact**: HIGH

**Mitigation Strategy**: Prominent placement on GOV.UK and HMRC pages, helpline IVR offering ChatBot as alternative, marketing campaign at tax deadline, continuous UX improvement based on user research, easy onboarding with example queries.

**Contingency Plan**: If adoption below 50% of target after 3 months, intensify marketing, revise helpline IVR strategy, conduct user research to understand barriers, adjust savings projections in business case.

---

### Risk R-6: AI Inaccuracy Causes Citizen Harm

**Related Stakeholders**: Citizens, Minister, Tax Policy Experts, SRO

**Risk Description**: ChatBot provides materially incorrect tax advice that a citizen relies on, leading to incorrect tax return, penalties, or financial loss — generating complaints, media coverage, and potential legal liability.

**Impact on Goals**: G-2 (accuracy target failed), G-1 (citizens lose trust, stop using), G-3 (GDS concern about service quality)

**Probability**: MEDIUM

**Impact**: HIGH

**Mitigation Strategy**: RAG grounding in authoritative sources, 100% source citation, confidence thresholds with escalation, disclaimer that ChatBot provides guidance not legal advice, ground truth testing with 1000+ queries, monthly accuracy audits by tax policy experts, citizen feedback loop.

**Contingency Plan**: If material error discovered, immediately update knowledge base, notify affected citizens if identifiable, publish correction on GOV.UK, review and enhance guardrails, notify GDS assessor proactively.

---

## Governance & Decision Rights

### Decision Authority Matrix (RACI)

| Decision Type | Responsible | Accountable | Consulted | Informed |
|---------------|-------------|-------------|-----------|----------|
| Programme budget and spending | Finance Director | SRO | HM Treasury, Permanent Secretary | Minister, NAO |
| Technology architecture | Enterprise Architect | CDIO | CISO, DPO, Tech Lead | SRO, GDS |
| Security architecture | Security Architect | CISO | NCSC, DPO, Enterprise Architect | SRO, CDIO |
| Data protection decisions | DPO | Permanent Secretary | CISO, ICO (if needed) | SRO, Legal |
| Requirements prioritisation | Product Owner | SRO | Citizens (via research), Delivery Lead | All stakeholders |
| GDS assessment readiness | Product Owner | SRO | GDS Assessment Team, Accessibility Lead | Minister, Permanent Secretary |
| Go/No-go for private beta | SRO | Permanent Secretary | CISO, DPO, GDS, Tech Lead | Minister, all |
| Go/No-go for public launch | SRO | Permanent Secretary | CISO, DPO, GDS, Minister's office | All stakeholders |
| AI model selection and changes | AI Technical Lead | CDIO | CISO, DPO, Data Ethics Committee | SRO, Product Owner |
| Knowledge base content approval | Content Lead | Tax Policy Expert | Legal, Product Owner | Delivery team |
| Incident response (security) | SOC Team | CISO | SRO, DPO, Comms | Permanent Secretary, Minister (if required) |
| Workforce impact decisions | Customer Services Director | SRO | PCS Union, HR Director | Permanent Secretary, Finance Director |

### Escalation Path

1. **Level 1**: Product Owner / Delivery Manager (day-to-day delivery decisions, sprint scope, minor technical choices)
2. **Level 2**: SRO / Programme Board (scope changes, timeline variances, budget reallocations, inter-team conflicts)
3. **Level 3**: Permanent Secretary / Minister's office (strategic direction changes, programme continuation decisions, ministerial accountability issues, public communications)

### Governance Forums

| Forum | Frequency | Chair | Purpose | Attendees |
|-------|-----------|-------|---------|-----------|
| Programme Board | Monthly | SRO | Strategic decisions, risk review, milestone tracking | Permanent Secretary rep, CDIO, CISO, DPO, Finance, Customer Services |
| Security Review | Monthly | CISO | Security posture, threat review, compliance | Security Architect, DPO, SOC Lead, Enterprise Architect |
| Architecture Review | Fortnightly | Enterprise Architect | Technical decisions, principles compliance | CDIO, Tech Lead, Security Architect |
| Sprint Review | Fortnightly | Product Owner | Delivery progress, demo, feedback | Delivery team, stakeholder reps |
| User Research Review | Monthly | Service Designer | Research findings, citizen insights | Product Owner, Accessibility Lead, Content Designer |
| Data Ethics Committee | Quarterly | Chief Data Officer | AI ethics, bias review, ATRS | DPO, AI Lead, External advisor |

---

## Validation & Sign-off

### Stakeholder Review

| Stakeholder | Review Date | Comments | Status |
|-------------|-------------|----------|--------|
| SRO | PENDING | | PENDING |
| CDIO | PENDING | | PENDING |
| CISO | PENDING | | PENDING |
| DPO | PENDING | | PENDING |
| Customer Services Director | PENDING | | PENDING |
| Finance Director | PENDING | | PENDING |

### Document Approval

| Role | Name | Signature | Date |
|------|------|-----------|------|
| SRO (Executive Sponsor) | | | |
| CDIO | | | |
| Enterprise Architect | | | |

---

## Appendices

### Appendix A: Stakeholder Interview Summaries

#### Interview with Customer Services Director - TBD

**Key Points**:
- Helpline under extreme pressure during January peak — ChatBot could relieve this
- Concerned about "false deflection" — citizens trying ChatBot, failing, then calling helpline (double handling)
- Wants warm handover to human agents with full context — citizens should not repeat themselves
- Previous digital self-service initiatives (online forms) achieved limited deflection

**Quotes**:
- "I'll believe it when I see it — previous digital initiatives promised deflection and didn't deliver. This needs to actually resolve queries, not just deflect them."

**Follow-up Actions**:
- Define "genuine deflection" metric (ChatBot resolution without subsequent call within 48 hours)
- Design warm handover workflow with Customer Services Director input

---

#### Interview with CISO - TBD

**Key Points**:
- Novel attack surface concerns — prompt injection is new territory for HMRC security
- Wants security architect embedded in delivery team from Day 1, not bolted on later
- Requires CHECK pen testing with specific AI attack scenarios
- Concerned about LLM data leakage (training data, system prompts)

**Quotes**:
- "This is the first time we're putting an AI system in front of citizens with access to OFFICIAL-SENSITIVE data. I need to be confident before we go live, not hopeful."

**Follow-up Actions**:
- Book CHECK pen test supplier with AI security expertise for Month 5
- Develop prompt injection test framework during Alpha
- Embed security architect in delivery team from Month 1

---

### Appendix B: Survey Results

To be conducted during Discovery phase — citizen survey on tax guidance needs, channel preferences, and attitudes toward AI-powered services.

---

### Appendix C: References

- [Architecture Principles (ARC-000-PRIN-v1.0)](../000-global/ARC-000-PRIN-v1.0.md)
- [Requirements (ARC-001-REQ-v1.0)](./ARC-001-REQ-v1.0.md)
- [Statement of Work (ARC-001-SOW-v1.0)](./ARC-001-SOW-v1.0.md)
- [Evaluation Criteria (ARC-001-EVAL-v1.0)](./ARC-001-EVAL-v1.0.md)
- [Traceability Matrix (ARC-001-TRAC-v1.0)](./ARC-001-TRAC-v1.0.md)
- [ATRS Record (ARC-001-ATRS-v1.0)](./ARC-001-ATRS-v1.0.md)
- GDS Service Manual: https://www.gov.uk/service-manual
- Technology Code of Practice: https://www.gov.uk/guidance/the-technology-code-of-practice
- UK Government AI Playbook: https://www.gov.uk/government/publications/ai-playbook
- HM Treasury Orange Book (Risk Management): https://www.gov.uk/government/publications/orange-book
- HM Treasury Green Book (Business Case): https://www.gov.uk/government/publications/the-green-book-appraisal-and-evaluation-in-central-government

---

## Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2026-02-03 | ArcKit AI | Initial creation |

---

**Generated by**: ArcKit `/arckit.stakeholders` command
**Generated on**: 2026-02-03
**ArcKit Version**: 1.1.0
**Project**: HMRC ChatBot (Project 001-hmrc-chatbot)
**AI Model**: Claude Opus 4.5
