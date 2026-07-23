# Road Automation Workflows — Sanitised Case Study

## Snapshot

**Former name:** ws-project (originally started as `whatsapp-agent-engine`)
**Status:** Active, in production use
**Type:** Automation hub for n8n workflows, serving Road and Unknown Brand Consulting (UBC) projects
**My role:** Automation Architect and Technical Product Developer
**Code visibility:** Private
**Infrastructure:** Self-managed VPS (Contabo)
**Part of:** [ROAD Ecosystem](./ROAD_ECOSYSTEM.md)

## Executive summary

This is the technical hub where automation workflows are designed, tested, versioned and documented for every project in the Road and UBC portfolio that needs it — not a single-client integration. It runs on a self-hosted n8n instance deployed to a dedicated VPS rather than a managed SaaS automation tool, which gives full control over credentials, retries, logging and cost as the number of automated workflows grows across projects.

## Product/technical problem

Business operations across Road and UBC projects (client onboarding, CRM lifecycle events, scheduling, notifications, cross-system data movement) generate a steady need for automation. Building a one-off integration per project does not scale: conventions drift, credentials get duplicated, and lessons learned on one project don't transfer to the next. This hub exists to centralise that work behind one set of conventions, one deployment, and one documented playbook.

## The pivot: from a custom TypeScript engine to n8n

The repository did not start as an automation hub. It began as `whatsapp-agent-engine`, a single TypeScript engine (`core/` + `adapters/`) meant to run multi-client WhatsApp conversational agents.

The first real production case — DIVEP's applicant and communication workflows — forced a decision. Building and maintaining a fully custom engine for every new automation need was slower than the business needs justified, so the project pivoted to **n8n** as the runtime, with the original TypeScript engine kept in the repository as a reference design rather than deleted. That decision is recorded in the repo's own decision log rather than left implicit.

Once the DIVEP case was live on n8n, it became clear that the conventions, testing discipline and n8n-specific gotchas learned there had value beyond WhatsApp or DIVEP specifically — which is what led to repositioning the whole repository as a general-purpose automation hub for any project in the portfolio, not a DIVEP-only or WhatsApp-only tool.

This is a concrete example of a technical decision made under real delivery pressure, documented at the time, and later generalised once its value became clear — rather than over-engineered upfront.

## My contribution

### Architecture and decisions

- Designed the "one hub, many projects" model: business logic and workflow exports live per project (`infra/n8n-workflows/{project_id}/`), while shared conventions and playbooks live centrally
- Made and documented the build vs. buy-style decision to pivot from a custom TypeScript runtime to n8n once real production pressure (DIVEP) made the trade-off clear
- Defined a mandatory workflow-spec template (`WORKFLOW_SPEC.md`) that every new workflow must have before being built, including a QA checklist and a record of results — applying the same discipline used for product specs elsewhere in the ecosystem
- Established the rule that new channels or automation patterns must first be documented as *evaluated* (viable or not, and why) before infrastructure is built for them — avoiding speculative infrastructure

### Engineering and delivery

- Deployed and operate a self-hosted **n8n** instance on a dedicated **VPS (Contabo)**, including deployment scripting (`infra/deploy-contabo.sh`) and container-based deployment (`docker compose`)
- Enforced that all sensitive configuration lives in environment variables, prefixed per project, never committed in versioned config or exported workflow files
- Kept the original TypeScript engine functional and documented as an escape hatch for any future case that needs more control than n8n can give (custom types, tests, complex auth logic) rather than treating the pivot as a one-way door

## Architecture overview

```text
Project-specific business context (clients/{project_id}/, historical design)
                ↓
n8n workflows, exported and versioned (infra/n8n-workflows/{project_id}/)
                ↓
Self-hosted n8n runtime (Docker, VPS via Contabo)
                ↓
External systems per project (WhatsApp, CRM, email, forms, etc.)
```

The original custom TypeScript engine (`core/`, `adapters/`) remains in the repository as a documented reference design, not as the active runtime for any project today.

## Workflow lifecycle

```text
Identify automation need in a project
        ↓
Evaluate channel/pattern feasibility (documented, not assumed)
        ↓
Write WORKFLOW_SPEC.md (purpose, QA checklist, expected results)
        ↓
Build the workflow in n8n
        ↓
Test against the spec's QA checklist
        ↓
Export, version and document in infra/n8n-workflows/{project_id}/
        ↓
Deploy / update on the VPS runtime
```

## Testing and quality focus

- Each workflow is validated against its own written QA checklist before being considered production-ready
- Credential and environment-variable handling is checked per project prefix to avoid cross-project leakage
- Real production case (DIVEP) used to validate n8n-specific behaviour and edge cases (retries, error paths, rate limits) before generalising conventions to other projects

## Current documentation priorities

1. Public-safe summary of which projects currently run active workflows on this hub
2. VPS capacity/scaling plan as the number of active workflows grows
3. Formal criteria for when a workflow should move from n8n back to custom TypeScript code
4. Incident/rollback playbook for automation failures in production

## Confidentiality note

Workflow exports, project-specific business logic, credentials and VPS infrastructure details remain private. This case study documents the architecture, the pivot decision and the operating discipline without exposing client data or automation internals.
