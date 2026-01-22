# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an **ArcKit-managed architecture governance project** for the HMRC Tax Assistant Chatbot. It uses ArcKit's 40 slash commands to generate enterprise architecture artifacts through AI-assisted workflows.

**Project**: HMRC ChatBot - Conversational AI service for UK tax guidance
**Project ID**: 001-hmrc-chatbot
**Version**: 0.11.0 (ArcKit)

## Using ArcKit Commands

All architecture artifacts are generated via slash commands. Key commands for this project:

### Core Workflow (in order)
```
/arckit.principles      # Enterprise architecture principles (already created)
/arckit.stakeholders    # Stakeholder drivers, goals, outcomes
/arckit.risk            # Risk register (HM Treasury Orange Book)
/arckit.sobc            # Strategic Outline Business Case (Green Book 5-case)
/arckit.requirements    # Business and technical requirements (already created)
/arckit.data-model      # Data model with ERD, GDPR compliance
/arckit.research        # Technology research with build vs buy analysis
/arckit.wardley         # Strategic Wardley Maps
/arckit.diagram         # Architecture diagrams (C4, deployment, sequence)
/arckit.sow             # Statement of Work / RFP (already created)
/arckit.evaluate        # Vendor evaluation framework (already created)
/arckit.hld-review      # High-Level Design review
/arckit.dld-review      # Detailed Design review
/arckit.backlog         # Convert requirements to user stories
/arckit.servicenow      # ServiceNow service management design
/arckit.traceability    # Requirements traceability matrix (already created)
```

### UK Government Compliance
```
/arckit.tcop            # Technology Code of Practice (13 points)
/arckit.service-assessment  # GDS Service Standard (14 points)
/arckit.secure          # NCSC CAF, Cyber Essentials, UK GDPR
/arckit.ai-playbook     # Responsible AI assessment
/arckit.atrs            # Algorithmic Transparency Recording Standard (already created)
/arckit.dpia            # Data Protection Impact Assessment
```

## Project Structure

```
.arckit/
├── memory/
│   └── architecture-principles.md    # Global principles (created)
├── scripts/bash/                      # Helper scripts
└── templates/                         # Document templates

projects/001-hmrc-chatbot/
├── requirements.md                    # ✓ Created
├── sow.md                            # ✓ Created (Statement of Work)
├── evaluation-criteria.md            # ✓ Created
├── traceability-matrix.md            # ✓ Created
├── atrs-record.md                    # ✓ Created (Algorithmic Transparency)
└── vendors/                          # Vendor proposals and reviews
```

## Key Context for HMRC ChatBot

**UK Government Requirements** (from architecture principles):
- Cloud-First: AWS UK regions (eu-west-2) only, UK data sovereignty
- Zero Trust Security: NCSC Cloud Security Principles, Cyber Essentials Plus
- Accessibility: WCAG 2.2 AA mandatory (legal requirement)
- Responsible AI: ATRS record, explainability, bias testing, human oversight
- UK GDPR: DPIA required, 7-year retention for tax records
- GDS Service Standard: Must pass 18 criteria assessment

**Data Classification**:
- OFFICIAL-SENSITIVE: Tax records, NI numbers, Government Gateway credentials
- OFFICIAL: Chat transcripts, system logs
- Public: HMRC guidance, FAQs

**Technology Stack** (from principles):
- AI/LLM: AWS Bedrock (Claude 3.5 Sonnet), RAG architecture
- Backend: Python, Node.js/TypeScript
- Frontend: React + GOV.UK Design System
- Infrastructure: AWS (ECS Fargate, API Gateway, RDS PostgreSQL, OpenSearch)
- IaC: Terraform

## Working with Generated Artifacts

**Requirement ID Prefixes**:
- BR-xxx: Business Requirements
- FR-xxx: Functional Requirements
- NFR-xxx: Non-Functional (NFR-P performance, NFR-SEC security, NFR-A availability)
- INT-xxx: Integration Requirements
- DR-xxx: Data Requirements

**Traceability Chain**:
Stakeholders → Goals → Requirements → Data Model → Components → User Stories

## Helper Scripts

```bash
# Create new numbered project
.arckit/scripts/bash/create-project.sh --name "project-name" --json

# Generate document ID
.arckit/scripts/bash/generate-document-id.sh 001 REQ v1.0
# Output: ARC-001-REQ-v1.0

# List all projects
.arckit/scripts/bash/list-projects.sh
```

## Token Limit Handling

Large document generation (requirements, SOBC, research) may exceed Claude's 32K token output limit. Use the Write tool strategy:

```
/arckit.requirements but write directly to file using Write tool, show me only a summary
```
