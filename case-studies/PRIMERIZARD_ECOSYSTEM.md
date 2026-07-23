# PrimerizaRD Digital Ecosystem — Sanitised Case Study

## Snapshot

**Status:** Active ecosystem with ongoing development  
**Product type:** Community, education, events and digital-resource platforms  
**My role:** Director of Marketing Strategy, Projects and Operations / Product Lead  
**Code visibility:** Private

## Executive summary

PrimerizaRD supports first-time mothers through education, community, events, downloadable resources and digital tools. The technical challenge is not a single website; it is the coordination of several connected experiences serving public visitors, members, administrators, event participants and internal teams.

My work includes product strategy, requirements, workflow design, platform structure, implementation coordination, testing, documentation and the connection between communication, operations and technology.

## Ecosystem components

### Tribu PrimerizaRD

A member-oriented platform for community experiences, resources and ongoing participation.

Relevant areas include:

- Member access
- Community and resource organisation
- Role-based experiences
- Event-related workflows
- Administrative management

### Public website

The public-facing platform supports education, positioning, discovery, conversion and access to PrimerizaRD initiatives.

### Mobile wrapper/app

A mobile experience is under development to bring selected community, content and tool workflows into a more accessible mobile format.

### Gala voting system

A voting experience integrated into the digital ecosystem supports controlled participation in the PrimerizaRD gala.

Product and engineering considerations include:

- Participant eligibility
- Voting rules
- Duplicate-vote prevention
- Clear confirmation states
- Administrative visibility
- Result integrity

### Event-registration management

A system supports registration and operational management for Tribu events.

Relevant workflows include:

- Registration capture
- Participant records
- Capacity and attendance considerations
- Confirmation communications
- Administrative follow-up
- Event-specific reporting

### Digital-resource delivery

PrimerizaRD creates educational resources such as plans, checklists and guides. The platform must support clear discovery, controlled delivery and consistent brand presentation.

### NueveLunas (in development)

A pregnancy-tracking companion app in concept and early development, planned to launch its first phase inside the PrimerizaRD ecosystem so it can reach an existing community instead of starting from zero. See the [product summary](./PRODUCT_SYSTEMS.md#nuevelunas) for scope details.

## Users and roles

| Role | Main needs |
|---|---|
| Public visitor | Discover resources, programmes and events |
| Member | Access community experiences and member resources |
| Event participant | Register, receive confirmation and participate |
| Voter | Complete an eligible gala vote clearly and safely |
| Content administrator | Manage educational and public content |
| Operations team | Review registrations, statuses and event information |
| Leadership | Understand engagement and operational performance |

## My contribution

### Product and operations

- Translate community and operational needs into product requirements
- Define user journeys across public, member and event experiences
- Prioritise tools and workflows based on real organisational needs
- Connect content, product, operations and communication

### System design

- Separate public, member and administrative concerns
- Define data and status needs for registration and participation workflows
- Plan role-based access and operational visibility
- Design systems that can expand without forcing all functionality into one interface

### Delivery

- Coordinate implementation and iteration
- Review flows and interfaces
- Test critical experiences
- Identify operational edge cases
- Document requirements, decisions and follow-up tasks

## Architecture perspective

```text
Public website ───────────────┐
                              │
Tribu member platform ────────┼── Shared brand, users, content and operations
                              │
Event registration ───────────┤
                              │
Gala voting ──────────────────┤
                              │
Mobile wrapper/app ───────────┘
```

The systems may remain technically separate while sharing product rules, user context and operational goals.

## Data concepts

- User or member
- Role
- Content resource
- Event
- Registration
- Attendance or participation status
- Candidate or voting option
- Vote
- Communication status
- Administrative action

## Important edge cases

- Duplicate registrations
- Incomplete participant records
- Capacity limits
- Invalid or repeated votes
- Member access versus public access
- Mobile and responsive behaviour
- Failed confirmation or notification delivery
- Changes to an event after registration
- Administrative corrections with traceability

## Testing focus

- Registration happy path and validation
- Duplicate and invalid submissions
- Member and administrator permissions
- Voting eligibility and confirmation
- Responsive experience
- Notification delivery
- Administrative review workflows
- Regression testing when shared components change

## Documentation priorities

The next documentation layer should include:

1. Ecosystem map
2. Repository and platform inventory
3. User and role matrix
4. Event-registration data model
5. Voting rules and integrity checklist
6. Mobile wrapper scope
7. Content and resource architecture
8. Integration inventory
9. Staging and production workflow
10. Ownership and maintenance matrix

## Confidentiality note

The repositories, administrative routes, member data, event records and voting implementation remain private. This document presents the product and engineering scope without exposing sensitive information.
