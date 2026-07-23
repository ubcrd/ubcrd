# Propertree — Sanitised Product Case Study

## Snapshot

**Status:** Pre-beta (soft launch with first invited agents)
**Product type:** Mobile-first real-estate portfolio and lead-generation platform
**Industry:** Real estate (Dominican Republic)
**My role:** Founder, Product Architect and Technical Product Developer
**Code visibility:** Private
**Domain:** propertreedr.com
**Part of:** [ROAD Ecosystem](./ROAD_ECOSYSTEM.md)

## Executive summary

Real-estate agents in the Dominican Republic typically share their listings by sending loose photos, voice notes and PDFs over WhatsApp — there is no single professional link a client can open to see an agent's full portfolio. Propertree replaces that with one public link per agent: a branded portfolio page, an individual page per property with gallery, pricing in both US$ and RD$, and a direct WhatsApp call-to-action, plus a dashboard for the agent to create, order, publish and measure their own listings.

## Product problem

- Listings are scattered across chat threads, images and PDFs with no persistent, shareable format
- Agents have no simple way to present a coherent, branded portfolio
- There is no lead-capture path from a shared listing back to the agent
- Pricing needs to work in both USD and DOP for the local market

## Users and roles

| Role | Main need |
|---|---|
| Real-estate agent / broker | Publish and manage listings, share one link instead of loose media, receive leads |
| Prospective buyer/renter | Browse an agent's portfolio or a single property page, contact the agent directly on WhatsApp |
| Platform admin (me) | Onboard agents, monitor usage, manage platform-wide settings |

## Scope

### Included (current pre-beta)

- Public agent portfolio page (`/a/{handle}`) with branding, zones and properties
- Public property page (`/p/{slug}`) with gallery, USD/DOP pricing, metrics and a WhatsApp CTA
- Agent dashboard to create, order, publish and measure properties
- Direct lead capture from the public page into the agent's inbox
- Role-based access separating public, agent and admin experiences

### Not included yet

- Public marketing/self-serve signup (currently invite-based soft launch)
- Payment or subscription billing
- Multi-agency/brokerage-level accounts

## My contribution

### Product

- Identified the "one link instead of loose photos" problem directly from how agents in the Dominican Republic actually share listings today
- Defined the agent-portfolio and single-property-page product model
- Set the local-market constraints: USD/DOP dual pricing, Dominican zones (Piantini, Naco, Cap Cana, Punta Cana, Santiago, etc.), no Mexican market references or currency
- Positioned the WhatsApp CTA as the primary conversion action, matching how agents already close deals locally

### System and data design

- Modelled agents, properties, agent-to-property ownership and public lead events as separate concerns
- Kept authentication and role checks (`user_roles` table with a `has_role()` security-definer function) decoupled from the public profile data
- Designed public routes, agent-authenticated routes and admin routes as clearly separated route groups

### Engineering and delivery

- Built on **TanStack Start v1** (React 19 + Vite 7) with server-side rendering
- **Tailwind CSS v4 + shadcn/ui**, with design tokens centralised in a single stylesheet rather than hardcoded per component
- **Lovable Cloud (Supabase)** for backend, database, auth and storage
- **Cloudflare Workers** for edge SSR hosting
- **Resend** for transactional email on a dedicated subdomain
- A first-party event tracker (`property_events`) combined with **GA4** and **Microsoft Clarity** for behavioural analytics
- TypeScript throughout with strict typing (no `any`), enforced lint/format tooling
- Mobile-first implementation (360–430px breakpoint first), with a minimum 44px touch-target rule given the WhatsApp-first, phone-based usage pattern of the target users

## High-level architecture

```text
Public portfolio & property pages (SSR, Cloudflare Workers)
                ↓
Agent dashboard (authenticated, role-gated)
                ↓
Server functions (TanStack) — no Supabase edge functions
                ↓
Supabase (Postgres, Auth, Storage, RLS)
                ↓
Resend (email) · GA4 / Clarity / first-party events (analytics)
```

## Core workflow example

```text
Agent creates account and portfolio
        ↓
Agent adds properties (photos, price, zone, description)
        ↓
Agent publishes portfolio/property links
        ↓
Prospect opens the public link and browses
        ↓
Prospect taps the WhatsApp CTA
        ↓
Lead reaches the agent directly; view/interaction is logged
```

## Product positioning

Propertree is deliberately scoped as an agent-facing portfolio and lead-sharing tool, not a property-management SaaS. It does not attempt to manage rental operations, tenants, buildings or condominium administration — its entire value is giving an individual agent one professional link to present and share their listings. This narrow scope is what keeps onboarding and the product story simple for agents who are used to WhatsApp, not software.

## Testing focus

- Public page rendering and SSR correctness across devices
- Auth gating between public, agent and admin routes
- Role-based data access (RLS) for property ownership
- Lead-capture path from public page to agent inbox
- Responsive behaviour at small mobile breakpoints
- Regression testing when shared components (cards, layouts) change

## Current documentation priorities

The next documentation layer should include:

1. Confirmed beta-to-launch criteria and rollout plan
2. Agent-onboarding funnel metrics (from GA4/Clarity, once broader usage data is available)
3. Lead-conversion tracking from public page to WhatsApp contact
4. Public marketing/self-serve signup scope definition
5. Data-model diagram for agents, properties and events

## Confidentiality note

This case study describes product and engineering responsibilities without publishing private source code, agent data, leads, credentials or production infrastructure details.
