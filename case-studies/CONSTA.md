# Consta — Sanitised Product Case Study

## Snapshot

**Former name:** Glucosa Fácil  
**Status:** Production and active evolution  
**Product type:** Modular health and habit-management platform  
**My role:** Founder, Product Architect and Technical Product Developer  
**Code visibility:** Private  
**Live product:** https://constaapp.joseroad.com/

## Executive summary

Consta began as a practical tool created around the need to manage gestational-diabetes information. As the product evolved, it became clear that users needed a broader system for personal health routines rather than a single-condition tracker.

The platform was repositioned and redesigned as an independent modular product. Users can activate different tracking and planning areas according to their goals and health context. My responsibility spans product strategy, architecture, user experience, data and workflow design, implementation decisions, testing, debugging and continuous iteration.

## Product problem

Health and habit-management information is often scattered across notes, spreadsheets, messaging applications and specialised tools. A rigid product also forces users into features they do not need.

Consta addresses this through a modular model in which the experience adapts to the user's context and selected tools.

## User contexts

Current onboarding and product thinking support contexts such as:

- Improving eating habits
- General diabetes management
- Healthy pregnancy and prevention
- Gestational diabetes

These contexts influence recommendations, enabled modules and the language of the product experience.

## Product modules

- Glucose tracking
- Meal and food-planning workflows
- Pantry and shopping-list management
- Weight
- Exercise
- Hydration
- Medication
- Medical appointments
- Symptoms
- Community groups and forums
- Group challenges
- Mentorship
- Achievements and points

## My contribution

### Product

- Identified the need to evolve beyond a single-condition product
- Defined the independent Consta positioning
- Structured modular onboarding and feature activation
- Prioritised modules and product phases
- Connected user needs with technical requirements

### System and data design

- Defined relationships between users, profiles, modules and tracking records
- Planned for optional modules without duplicating user identity or account logic
- Considered future extensibility when adding new health and habit areas
- Designed workflows around user context rather than a single universal dashboard

### Engineering and delivery

- Worked across frontend and backend product implementation
- Managed authentication and permission considerations
- Tested validation, error states and critical user paths
- Used staging and production-oriented workflows
- Debugged issues across interface, application logic, data and integrations
- Structured documentation for continued product development

## High-level architecture

```text
User onboarding and profile
          ↓
Module activation and personalised experience
          ↓
Tracking, planning and community workflows
          ↓
Application services and validation
          ↓
Relational data and external integrations
```

The central architectural concern is keeping a shared user and profile model while allowing modules to evolve independently.

## Data concepts

The private implementation contains more detail, but the product can be understood through these domain concepts:

- User
- Profile and health context
- Enabled module
- Tracking record
- Goal or target
- Meal, pantry and shopping information
- Medication and appointment records
- Community group
- Challenge
- Achievement and points activity

Important considerations include historical records, module ownership, profile-driven behaviour and consistent user access.

## Core workflow example

```text
User creates account
      ↓
Completes context-based onboarding
      ↓
System establishes profile and initial modules
      ↓
User records or plans an activity
      ↓
Input is validated and stored
      ↓
Interface updates progress and related insights
```

## Testing focus

- Account creation and authentication
- Onboarding variations
- Module activation and deactivation
- Data-entry validation
- Empty, loading and failure states
- Permissions and record ownership
- Responsive behaviour
- Regression testing after module changes
- Staging verification before production updates

## Product evolution challenge

The most important challenge has been evolving the product without keeping it conceptually trapped in its origin.

The solution required more than renaming the interface. It involved rethinking:

- The product category
- User onboarding
- Module boundaries
- Navigation
- Data relationships
- Language and positioning
- Future feature compatibility

## Current documentation priorities

The next documentation layer should include:

1. Current architecture map
2. Confirmed production technology stack
3. Data-model diagram
4. Authentication and permissions matrix
5. Module lifecycle
6. Integration inventory
7. Testing checklist
8. Deployment and rollback process
9. Product analytics and active-user metrics
10. Decision log for the transition from Glucosa Fácil to Consta

## Confidentiality note

This case study describes product and engineering responsibilities without publishing private source code, health-related user data, credentials or production infrastructure details.
