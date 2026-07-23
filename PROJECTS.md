# Product and Platform Portfolio

This portfolio documents systems I have designed, built, implemented or helped evolve. Most production repositories are private because they contain proprietary business logic, operational data, client assets or active user information.

The purpose of this document is to make the scope of the work reviewable without exposing confidential code.

## Evidence model

Each project may be represented through one or more of the following:

- **Live product:** a publicly accessible application or website
- **Private codebase:** repository access is restricted
- **Sanitised case study:** architecture and decisions documented without secrets or client data
- **Controlled walkthrough:** product review subject to ownership and confidentiality constraints
- **Prototype:** functional or partially functional validation build
- **Documentation:** PRDs, architecture notes, data models, flows and implementation plans

---

# 1. Owned products and product experiments

## Consta

**Former name:** Glucosa Fácil  
**Status:** Production and active evolution  
**Type:** Modular health and habit-management product  
**Role:** Founder, Product Architect and Technical Product Developer  
**Live product:** https://constaapp.joseroad.com/

Consta evolved from a gestational-diabetes support tool into a broader product for personalised health tracking and habit management.

### Product areas

- Goal and context-based onboarding
- Modular health and habit-tracking tools
- Glucose, meals, pantry, shopping, weight, exercise and hydration workflows
- Medication, appointment and symptom tracking
- AI-assisted planning and food-related features
- Community, achievements and engagement mechanics
- Continuous iteration around real user needs

### Engineering areas

- Modular product architecture
- User-profile-driven experiences
- Authentication and permissions
- Relational data modelling
- Validation and error handling
- Staging and production workflows
- Debugging and product maintenance

[Open the sanitised case study](./case-studies/CONSTA.md)

---

## UNQR

**Status:** Product build  
**Type:** Dynamic QR-code generation and management platform  
**Role:** Product Designer and Technical Product Developer  
**Codebase:** Private

### Product areas

- QR-code creation and management
- Dynamic destination control
- Administrative workflows
- Organised ownership of generated assets
- Product and account-management experiences

### Engineering areas

- CRUD workflows
- User and resource relationships
- Administrative permissions
- Data persistence
- Error and validation states
- Scalable product organisation

---

## Road Space OS

**Status:** Product development  
**Type:** Space-management and administration platform  
**Role:** Product Architect and Technical Product Developer  
**Codebase:** Private

### Product areas

- Space and resource administration
- Operational records and status workflows
- User and administrative interfaces
- Centralised management of physical-space information

### Engineering areas

- Role-based workflows
- Data modelling around spaces, users and operations
- Administrative dashboards
- System extensibility
- Documentation and implementation planning

---

## Pañal Check

**Status:** Product prototype / utility  
**Type:** Diaper-expiration checking tool  
**Role:** Product Designer and Developer  
**Codebase:** Private

### Product areas

- Expiration-date checking
- Simple guided user workflow
- Clear result and warning states
- Mobile-first usability

### Engineering areas

- Input validation
- Rule-based calculation
- Error-state design
- Small-product architecture

---

## Agro Road

**Status:** Prototype and validation  
**Type:** Agritech incident-reporting platform  
**Role:** Founder and Product Architect  
**Codebase:** Private

### Product concept

- Report field incidents through Telegram or a web form
- Attach a field image and natural-language description
- Use AI and specialised identification services to assist classification
- Route incidents into role-based dashboards
- Track location, priority, status and follow-up
- Support producers, technicians, cooperatives and management

### Engineering areas

- Conversational interfaces
- AI and third-party integrations
- Incident data modelling
- Role-based workflows
- Fallback and failure-path design

---

# 2. Community and organisational ecosystems

## PrimerizaRD Digital Ecosystem

**Status:** Active ecosystem with ongoing product development  
**Type:** Community, education, events and digital-resource systems  
**Role:** Director of Marketing Strategy, Projects and Operations / Product Lead  
**Codebases:** Private

PrimerizaRD is not a single website. It is a connected product ecosystem that supports first-time mothers across content, community, events, resources and member experiences.

### Systems in the ecosystem

- **Tribu PrimerizaRD:** member and community platform
- **PrimerizaRD website:** public content and conversion experience
- **Mobile wrapper/app:** mobile experience currently in development
- **Gala voting:** online voting system integrated into the web ecosystem
- **Event registration management:** registration, attendance and operational workflows for Tribu events
- **Digital resources:** delivery and organisation of educational materials
- **Administrative tools:** internal management and content workflows

### Engineering and product areas

- Member and role-based experiences
- Event and registration data
- Voting logic and controlled participation
- Content and resource delivery
- Administrative interfaces
- Responsive and mobile-oriented experiences
- Integration between public, member and operational systems

[Open the ecosystem case study](./case-studies/PRIMERIZARD_ECOSYSTEM.md)

---

## DIVEP Academy and Digital Operations

**Status:** Active development and operational use  
**Type:** Academy, programme, applicant and internal-management systems  
**Role:** Digital Marketing and Product Operations Coordinator / Technical Solutions Lead  
**Codebases:** Private

### Systems and workflows

- Academy and learning experiences
- Applicant intake
- CRM lifecycle and status management
- Interview and appointment scheduling
- Automated email and calendar actions
- Applicant and internal portals
- Programme-specific workflows
- Operational dashboards and documentation

### Engineering areas

- CRM data structures
- Automation and integration architecture
- Role-based operational processes
- REST APIs and webhooks
- Error handling and escalation
- Cross-system data movement

---

# 3. Client products and specialised platforms

## The Neuro Space

**Status:** Client product  
**Type:** Psychological-test platform and test-generation engine  
**Role:** Product Designer and Technical Product Developer  
**Codebase:** Private

### Product areas

- Engine for creating and structuring psychological tests
- Test-taking user experiences
- Results and interpretation workflows
- Administrative management of test content
- Reusable logic for multiple assessment types

### Engineering areas

- Schema-driven or configurable assessment structures
- Conditional flows
- Scoring and result logic
- Administrative authoring experiences
- Data separation between tests, responses and results

---

## La Mafia Positiva

**Status:** Client platform  
**Type:** Website, landing pages, custom CMS and administrative workflows  
**Role:** Product Designer and Developer  
**Codebase:** Private

### Product areas

- Public brand and conversion experience
- Custom content-management workflows
- Administrative portal
- Reusable design and publishing structures

---

## Dra. Berniza

**Status:** Client platform  
**Type:** Professional website, landing experience and custom administration  
**Role:** Product Designer and Developer  
**Codebase:** Private

### Product areas

- Service and professional positioning
- Lead and conversion flows
- Custom content management
- Administrative editing experience

---

## UBC Website

**Status:** Client platform  
**Type:** Website and managed content experience  
**Role:** Product Designer and Developer  
**Codebase:** Private

### Product areas

- Structured institutional content
- Responsive interface
- Managed publishing workflows
- Administrative control

---

## José Road Platform

**Status:** Active personal-brand platform  
**Type:** Portfolio, professional positioning and product/service presentation  
**Role:** Owner, Product Designer and Developer  
**Live website:** https://joseroad.com/jose-road

### Product areas

- Professional profile and positioning
- Portfolio and project presentation
- Service and contact flows
- Content and brand-system implementation

---

# 4. Documentation and AI-development systems

## Road OS Documentation System

**Status:** Active research and implementation  
**Type:** Project-documentation framework for human teams and AI agents  
**Role:** System Designer and Author  
**Codebase and documentation:** Private, with sanitised methodology documented in this profile

### Purpose

Road OS is an attempt to make project context durable and usable across time, tools and collaborators. It defines how product, design and engineering knowledge should be structured so that a human developer or AI development agent can understand a project before changing it.

### Documentation areas

- Product requirements and scope
- Current-state repository audits
- Technical architecture
- Data models and flows
- Product gaps and implementation roadmaps
- Decisions, risks and constraints
- Environment and deployment information
- Agent instructions and safe operating rules
- Demo-readiness and quality-assurance reports

[Open the documentation-system case study](./case-studies/ROAD_OS_DOCUMENTATION.md)

---

# 5. Portfolio review policy

Because these systems include client work and active products, this public repository does not publish their source code.

A professional review should focus on:

1. The problem and system context
2. My exact role and ownership
3. Architecture and data decisions
4. Critical workflows and edge cases
5. Testing, debugging and deployment practices
6. Results and lessons learned

Detailed technical walkthroughs should only include information that I own or have permission to discuss. Secrets, personal data, production credentials and proprietary client logic must remain private.
