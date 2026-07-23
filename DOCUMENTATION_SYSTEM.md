# Documentation-First Portfolio System

This repository is designed as a professional evidence layer for private products and client systems.

The goal is to make my work understandable to recruiters, technical leads and collaborators without publishing confidential source code, user data or proprietary business logic.

## Why documentation instead of public code

Most production systems in this portfolio are private because they involve one or more of the following:

- Client-owned code and intellectual property
- Active business operations
- Personal or sensitive user information
- Internal processes and role definitions
- Production credentials and integrations
- Proprietary product logic

Publishing a repository is not the only way to demonstrate engineering ability. A strong technical case study can show how a system was understood, designed, implemented, tested and maintained.

## Documentation hierarchy

```text
README.md
    Professional positioning and selected systems

PROJECTS.md
    Master portfolio and project inventory

ENGINEERING.md
    General engineering and delivery approach

EXPERIENCE.md
    Professional roles and responsibilities

CERTIFICATIONS.md
    Technical and professional development

case-studies/
    Sanitised project-specific documentation
```

## Evidence levels

Each project should declare its available evidence.

### Level 1 — Summary

A concise public description covering:

- Product type
- Problem or opportunity
- My role
- Status
- Main capability areas

### Level 2 — Sanitised case study

A structured document covering:

- Context
- Users and roles
- Scope
- Architecture
- Data concepts
- Integrations
- Testing
- Deployment
- Challenges
- Results

No secrets, private screenshots or client data should appear.

### Level 3 — Visual walkthrough

A controlled presentation containing approved screenshots, flow diagrams or recorded demonstrations.

This material should only be shared when ownership and confidentiality allow it.

### Level 4 — Technical walkthrough

A live or recorded explanation of system decisions, repository organisation, data models, debugging practices and release workflows.

The codebase may remain private while the reasoning is discussed.

### Level 5 — Code review

Source-code access should only be provided when:

- I own the code or have explicit permission
- Sensitive data has been removed
- Secrets and environment values are protected
- Client agreements allow review

## Standard project document set

For larger products, the preferred documentation set is:

1. `00_PROJECT_OVERVIEW.md`
2. `01_PRODUCT_REQUIREMENTS.md`
3. `02_USERS_AND_ROLES.md`
4. `03_SYSTEM_ARCHITECTURE.md`
5. `04_DATA_MODEL.md`
6. `05_CORE_FLOWS.md`
7. `06_INTEGRATIONS.md`
8. `07_AUTH_AND_PERMISSIONS.md`
9. `08_TESTING_AND_QA.md`
10. `09_DEPLOYMENT_AND_ENVIRONMENTS.md`
11. `10_ERROR_HANDLING_AND_MONITORING.md`
12. `11_DECISION_LOG.md`
13. `12_RISKS_AND_LIMITATIONS.md`
14. `13_ROADMAP.md`
15. `14_CASE_STUDY.md`

Smaller projects may combine these areas into one case-study file.

## Sanitisation rules

Public documentation must never expose:

- API keys, tokens or credentials
- `.env` values
- Private URLs or admin routes
- Personal health, applicant or client data
- Database exports
- Real user identifiers
- Internal pricing or contracts
- Security-sensitive implementation details
- Proprietary client algorithms without permission

Use generic examples and fictional data when a workflow needs illustration.

## How to describe technical work accurately

Each case study should distinguish between:

- What I designed
- What I implemented directly
- What was implemented with collaborators
- What was generated or accelerated with AI tools
- What remains experimental or incomplete

The objective is to demonstrate responsibility and judgement, not to inflate ownership.

## Case-study quality checklist

Before publishing a case study, confirm that it answers:

- What problem did the system solve?
- Who used it?
- What was my role?
- What decisions did I own?
- What made the system technically challenging?
- How was data structured?
- How were permissions handled?
- Which integrations were required?
- How were failures and edge cases managed?
- How was the system tested?
- How did it reach staging and production?
- What changed as a result?
- What would I improve next?

## Interview use

For interviews, each major project should be explainable in three formats:

### 30-second version

Problem, product, role and outcome.

### 3-minute version

Users, architecture, core workflow, key challenge and result.

### 15-minute technical version

Data model, authentication, integrations, debugging, testing, deployment, trade-offs and lessons learned.

The public documentation provides the foundation for all three versions.
