# ROAD Ecosystem — Sanitised Case Study

## Snapshot

**Status:** Active, ongoing product and tooling development
**Type:** Owned product-and-services ecosystem (No-Code Studio, internal SaaS tooling, AI-assisted development lab)
**My role:** Founder / Ecosystem Lead / Technical Product Developer
**Code visibility:** Private
**Public site:** [joseroad.com](https://joseroad.com) — ROAD's own marketing site (Ecosistema, Easy ROAD, ROAD Studio, Lab). This is the brand's public site, not a personal portfolio — this GitHub repository is the up-to-date professional profile.
**Related documents:** [Road OS Documentation System](./ROAD_OS_DOCUMENTATION.md) · [Propertree](./PROPERTREE.md) · [Easy Road](./EASY_ROAD.md) · [Road Automation Workflows](./ROAD_AUTOMATION_WORKFLOWS.md)

## Executive summary

ROAD is not only the name of a role on my experience timeline — it is my own ecosystem of products, internal tooling and a no-code/AI-assisted studio practice. Client-facing work (Unknown Brand Consulting, PrimerizaRD, DIVEP) and my own products (Propertree, Easy Road, Consta) are built on top of a shared internal foundation: a documentation system (Road OS), a set of internal SaaS-style tools, and a standardised no-code/AI development workflow.

This case study documents that foundation. Individual products built on top of it have their own case studies; this document explains the ecosystem, tooling and operating model that supports them.

## Why an ecosystem instead of a single product

Building several products and running client work in parallel (as a very small, mostly solo operation) creates a real risk of reinventing the same infrastructure — auth patterns, dashboards, analytics, briefing formats — for every new project. ROAD exists to avoid that: a shared set of internal tools, conventions and documentation practices that every product and client engagement can reuse instead of starting from zero.

## How an idea becomes a product

This is the pipeline ROAD's own public site describes, and it matches how the ecosystem actually operates:

```text
Idea
  ↓
ROAD Lab — probamos (test the concept internally)
  ↓
Easy ROAD — empaquetamos (package it as a resource/offer)
  ↓
ROAD Studio — implementamos (build it properly for real use)
  ↓
Producto — lanzamos (launch it)
```

Not every idea completes the pipeline — many stay at the Lab stage as internal tooling (see Road Lab below) rather than becoming a packaged or launched product.

## Structure

### Road OS — Single Source of Truth

The documentation backbone of the whole ecosystem. It organises brand, product strategy, Studio operations, marketing, a tools directory and governance rules in one place, with a strict "Core wins on conflict" rule and context packs so AI agents (Lovable, Cursor, Claude) can load only the section they need instead of an entire undifferentiated knowledge base.

See the dedicated [Road OS Documentation System case study](./ROAD_OS_DOCUMENTATION.md) for the full methodology.

### Road Lab — internal tools

A set of internally built tools that support product and Studio work rather than being sold directly to end clients:

- **Road UI** — shared component/design-system layer reused across ROAD products
- **Road Flow** — internal workflow/process tooling
- **Road AI** — internal AI tooling and experimentation surface
- **Road Web Analytics** — internal analytics tracking used across owned products
- **Road Finances** — internal finance-tracking tool for the ecosystem's own operations
- **Road RSV** — SaaS product for managing residential rental properties (units, buildings, condominiums) — see [Product and Platform Portfolio](../PROJECTS.md#road-rsv) for its own entry
- **Road Brief** — structured briefing tool for new product/client work
- **Road Collect** — internal data-collection tooling
- **Road Launchpad** — tooling to support new-product launches
- **Road Academy** (private) and a published **Road Academy Template** (public, LMS starter built with React, TypeScript, Tailwind CSS and Supabase) — academy/learning-platform tooling, later generalised into a reusable open-source template
- **Memorykit** — a personal memory/context tool for AI-assisted development, in the same family as the publicly shared `codebase-memory-mcp` tool

These are internal-facing: they exist to make product and client delivery faster and more consistent, not as standalone commercial products (with the exception of the open-sourced Road Academy Template).

### Products built on ROAD

- **[Propertree](./PROPERTREE.md)** — real-estate portfolio/link-in-bio platform for agents and brokers in the Dominican Republic
- **[Easy Road](./EASY_ROAD.md)** — membership/resource portal for entrepreneurs and small businesses
- **[Road Automation Workflows](./ROAD_AUTOMATION_WORKFLOWS.md)** — n8n-based automation hub, deployed on a dedicated VPS, serving Road and UBC projects
- **Site Capture** — internal tool for capturing and archiving live Framer/no-code sites as static HTML, used to migrate or back up client sites (e.g. before a rebuild or platform change)
- **Agro Road** — agritech incident-reporting concept (documented in [Product and Platform Portfolio](../PROJECTS.md))

### Unknown Brand Consulting (UBC) tooling

Separate from ROAD, but built with the same practices, is a small set of internal tools for my consulting brand Unknown Brand Consulting: a social-hub tool, a unified client-portal hub and a content/generation hub used across UBC client engagements. These remain internal and are not documented as individual products.

## My contribution

- Defined the ecosystem structure itself: what belongs in shared tooling versus what belongs in a single product
- Authored the Road OS documentation system and its context-pack model for AI agents
- Designed, built and maintain the internal Road Lab tools listed above
- Set the standard workflow (`Plan → Patch → Pruebas → Docs`) used across ROAD and UBC repositories
- Made the build/deploy/hosting decisions per product (Vercel, Cloudflare Workers, Lovable Cloud/Supabase, a self-managed VPS for automation) based on each product's actual needs rather than a single default stack

## Architecture perspective

```text
Road OS (Single Source of Truth)
        │
        ├── Road Lab internal tools (UI, Flow, AI, Analytics, Finances, RSV, Brief, Collect, Launchpad, Academy, Memorykit)
        │
        ├── Owned products (Propertree, Easy Road, Consta, Agro Road)
        │
        ├── Automation layer (Road Automation Workflows — n8n on a dedicated VPS)
        │
        └── Client and partner work (Unknown Brand Consulting, PrimerizaRD, DIVEP)
```

Client work and owned products draw from the same Road OS documentation conventions and, where useful, the same internal tools — without forcing every project onto identical technology.

## Current documentation priorities

1. Public-facing map of which Road Lab tools are active versus experimental
2. Clear separation between ROAD-branded tooling and Unknown Brand Consulting tooling in internal docs
3. Versioned changelog per Road Lab tool
4. Decision log entries for major pivots (see [Road Automation Workflows](./ROAD_AUTOMATION_WORKFLOWS.md) for an example of this in practice)

## Confidentiality note

Internal tool source code, Road OS's private project-specific documents, and UBC's internal tooling remain private. This case study describes the shape of the ecosystem and my role in building it without exposing proprietary implementation details.
