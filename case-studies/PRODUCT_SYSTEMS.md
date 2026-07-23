# Private Product Systems — Portfolio Summary

This document groups several private products and specialised systems that demonstrate different product, data and workflow challenges.

The descriptions are intentionally sanitised. Source code, client data, private infrastructure and proprietary logic are not published.

---

# The Neuro Space

## Snapshot

**Type:** Psychological-test platform and test-generation engine  
**Status:** Client product  
**My role:** Product Designer and Technical Product Developer  
**Code visibility:** Private

## Product purpose

The Neuro Space includes an engine for structuring and generating psychological tests rather than building every assessment as a fixed one-off page.

## Product capabilities

- Create and organise different psychological assessments
- Define questions, options and test structure
- Present a guided test-taking experience
- Store responses
- Calculate or map results according to test rules
- Present result and interpretation experiences
- Support administrative management of test content

## Technical areas demonstrated

- Configurable or schema-driven product logic
- Separation between test definitions and user responses
- Conditional flows
- Scoring and result logic
- Reusable UI patterns
- Administrative authoring tools
- Validation and incomplete-response handling

## Documentation still required

- Assessment schema
- Question-type inventory
- Scoring-engine explanation
- Result-generation flow
- Administrator and participant permissions
- Test-versioning strategy
- Validation and QA checklist

---

# UNQR

## Snapshot

**Type:** Dynamic QR-code generation and management platform  
**Status:** Product build  
**My role:** Product Designer and Technical Product Developer  
**Code visibility:** Private

## Product purpose

UNQR provides a managed system for creating and organising QR codes, with administrative control that goes beyond generating a static image.

## Product capabilities

- Create QR records
- Associate destinations and metadata
- Manage existing codes
- Organise resources by owner or account
- Provide administrative control
- Support future expansion into dynamic destinations and usage information

## Technical areas demonstrated

- CRUD operations
- Resource ownership
- User-to-record relationships
- Input validation
- Administrative permissions
- Asset generation
- Error and empty states

## Documentation still required

- Current production or prototype status
- Exact dynamic-routing behaviour
- Data-model diagram
- Access and ownership matrix
- QR-generation service or library
- Analytics and scan-tracking scope
- Deployment architecture

---

# Road Space OS

## Snapshot

**Type:** Space-management and administration platform  
**Status:** Product development  
**My role:** Product Architect and Technical Product Developer  
**Code visibility:** Private

## Product purpose

Road Space OS centralises information and administrative workflows related to physical spaces, resources and operations.

## Product capabilities

- Register and organise spaces
- Manage operational information
- Track statuses or availability
- Provide administrative dashboards
- Support user and operator workflows
- Centralise records that would otherwise remain distributed

## Technical areas demonstrated

- Domain modelling around spaces and resources
- Administrative dashboards
- Role-based access
- Status workflows
- Search, filtering and record management
- Product extensibility

## Documentation still required

- Space and resource entity model
- User-role matrix
- Core management workflows
- Status history and audit requirements
- Reporting requirements
- Integration opportunities

---

# Pañal Check

## Snapshot

**Type:** Consumer utility for diaper-expiration checking  
**Status:** Prototype / utility  
**My role:** Product Designer and Developer  
**Code visibility:** Private

## Product purpose

Pañal Check provides a simple guided experience for checking expiration-related information associated with diapers.

## Product capabilities

- Capture the required product information
- Validate user input
- Apply the relevant checking rules
- Present a clear result
- Communicate warnings or uncertainty
- Prioritise mobile usability

## Technical areas demonstrated

- Rule-based application logic
- Input validation
- Error and warning states
- Small-product scope control
- Mobile-first interface design

## Documentation still required

- Confirmed validation rules
- Product-code or date interpretation logic
- Supported brands or formats
- Disclaimer and uncertainty handling
- Test-case matrix

---

# DIVEP Academy

## Snapshot

**Type:** Academy and programme platform  
**Status:** Development and operational evolution  
**My role:** Product Operations and Technical Solutions Lead  
**Code visibility:** Private

## Product purpose

DIVEP Academy supports educational programmes and participant experiences connected to DIVEP operations.

## Product and operational areas

- Programme and course presentation
- Participant or student access
- Registration workflows
- Progress or participation information
- Administrative management
- Communication and scheduling connections

## Technical areas demonstrated

- User and programme relationships
- Role-based interfaces
- Academy and operations integration
- Forms, status and communication workflows
- Data movement across custom and SaaS systems

## Documentation still required

- Academy scope and modules
- Student and administrator roles
- Programme data model
- Authentication and access
- Progress-tracking scope
- Integration map
- Release roadmap

---

# Site Capture

## Snapshot

**Type:** Internal tool for capturing and archiving live no-code sites (Framer and similar builders) as static HTML
**Status:** Active, in production use
**My role:** Tool Designer and Developer
**Code visibility:** Private
**Part of:** [ROAD Ecosystem](./ROAD_ECOSYSTEM.md)

## Product purpose

No-code site builders (Framer in particular) do not always make it simple to take a full, faithful static snapshot of a published site for migration, backup or platform-change purposes. Site Capture solves that internally: it captures a live site and produces a static HTML output that preserves structure, assets and metadata, ready to be redeployed (for example, via Vercel) or archived.

## Technical areas demonstrated

- Static-site capture and asset handling
- Preservation of SEO/meta tags, Open Graph and font-loading behaviour during capture
- Migration workflows between no-code platforms and static hosting
- Reusable internal tooling rather than a one-off script per migration

## Documentation still required

- Supported source platforms beyond Framer
- Known limitations (dynamic content, forms, CMS-driven sections)
- Redeployment checklist per target host

---

# Prospecta CRM

## Snapshot

**Type:** SaaS CRM product
**Status:** In active development
**My role:** Product Architect and Technical Product Developer
**Code visibility:** Private

## Product purpose

Prospecta is an owned SaaS product in development, aimed at CRM-style pipeline and prospect management. It is an independent product effort rather than a client engagement.

## Documentation still required

- Target market and positioning
- Core pipeline/data model
- Current development stage and launch criteria

---

# Mini CRM

## Snapshot

**Type:** SaaS CRM solution
**Status:** In active development
**My role:** Product Architect and Technical Product Developer
**Code visibility:** Private

## Product purpose

A second, more lightweight CRM solution in development alongside Prospecta, exploring a simpler product shape for smaller teams or a different segment.

## Documentation still required

- Differentiation from Prospecta CRM
- Target segment and scope boundaries
- Current development stage

---

# NueveLunas

## Snapshot

**Type:** Pregnancy-tracking companion app
**Status:** Concept and early development
**My role:** Product Designer and Technical Product Developer
**Code visibility:** Private
**Related ecosystem:** [PrimerizaRD Digital Ecosystem](./PRIMERIZARD_ECOSYSTEM.md)

## Product purpose

NueveLunas is a product concept for guiding and tracking a pregnancy journey week by week. It is being developed in connection with PrimerizaRD, where its first release phase is planned to launch, giving it an existing community and distribution channel rather than requiring cold-start user acquisition.

## Product areas (planned)

- Week-by-week pregnancy tracking and guidance
- Educational content tied to gestational stage
- Connection to PrimerizaRD's existing community and resources for first-phase launch

## Documentation still required

- Confirmed data model for tracking entries and gestational stages
- Launch-phase scope versus later, standalone-app phases
- Relationship and data boundary between NueveLunas and the wider PrimerizaRD platform

---

# Portfolio interpretation

Together, these systems demonstrate experience across:

- Configurable engines
- Administrative platforms
- Role-based applications
- Dynamic resources
- Consumer utilities
- Data modelling
- Validation and edge cases
- Product documentation
- Private production and client environments

A technical interview should select one or two of these systems for a deeper architecture and debugging walkthrough rather than attempting to discuss every project equally.
