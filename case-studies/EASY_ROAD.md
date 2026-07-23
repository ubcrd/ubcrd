# Easy Road — Sanitised Product Case Study

## Snapshot

**Status:** Active development (portal-first, marketing site paused)
**Product type:** Membership portal — resources, discounts, community and progress tracking
**Industry:** Entrepreneurship / small-business enablement (Dominican Republic → LATAM)
**My role:** Founder, Product Architect and Technical Product Developer
**Code visibility:** Private
**Part of:** [ROAD Ecosystem](./ROAD_ECOSYSTEM.md)

## Executive summary

Easy Road is a membership platform for entrepreneurs and small businesses, built around a simple idea: give members a single portal to access curated resources, partner discounts, a community and a sense of progress, gated by subscription tier. The product was scoped in phases; the current build prioritises the portal and admin experience over the public marketing/checkout funnel, so the platform can be validated with real content and real members before investing further in acquisition.

## Product problem

Small businesses and independent entrepreneurs in the Dominican Republic and wider LATAM market often lack affordable, curated access to practical business resources, vetted discounts on tools they already need, and a community of peers — usually cobbling this together from scattered free content and personal networks.

## Users and roles

| Role | Main need | Main permissions |
|---|---|---|
| Member (Starter/Pro/Studio tier) | Access resources, discounts and community gated to their plan | Portal: dashboard, resources, discounts, community, profile, settings |
| Admin | Manage members, resources, discounts, events, community and tiers | Admin: users, resources, discounts, events, community, levels/achievements, settings |

## Scope

### Included (current build)

- Supabase Auth with middleware protecting `/portal/*` and `/admin/*`
- Member portal: dashboard, resource library, discount catalogue, community area, profile and settings
- Admin panel: user management, resources, discounts, events, community, levels/achievements and settings
- Manual plan/pause/status administration (payments handled outside automated billing for now)
- Levels, achievements and progress mechanics to support engagement

### Not included yet (deferred by design)

- Public marketing site and self-serve checkout flow (originally planned with Lemon Squeezy as the checkout/tax provider)
- Automated billing and plan changes (currently manual through admin)
- Semantic search, cohorts, assessments and a third-party marketplace — explicitly scoped out of the current phase

## My contribution

### Product

- Defined the phased scope: portal-and-admin first, public acquisition funnel deferred
- Designed the tier model (Starter / Pro / Studio, plus a limited-window Lifetime Founders option) with region-aware USD pricing and a referential DOP conversion
- Specified the resource, discount and onboarding-email flows (welcome → "quick win" follow-up → discount-redemption guidance) as a sequenced activation sequence rather than a single onboarding screen

### System and data design

- Modelled `user_profiles`, `resources`, `discounts`, `purchases`, `downloads` and `resource_views` as separate entities with row-level security tied to plan level (`studio > pro > starter > lifetime`)
- Designed signed-URL, time-limited downloads gated by plan and resource requirements rather than open file storage
- Kept a `settings` table (e.g. for the USD→DOP exchange rate) so operational values don't require redeploys

### Engineering and delivery

- **Next.js (App Router) + TypeScript + Tailwind CSS** on the frontend
- **Supabase** for Postgres, Auth, Storage and Row Level Security
- Planned **Lemon Squeezy** integration for checkout, licensing and tax handling (EU VAT, RD ITBIS) via verified webhooks, with **Resend** for the onboarding email sequence
- **Vercel** for deployment
- Defined explicit acceptance criteria for the checkout-to-role-assignment flow, plan-gated content visibility, signed-URL expiry (under 30 minutes) and onboarding email delivery — written before the corresponding phase was implemented, not after

## High-level architecture

```text
Public marketing/checkout (planned, currently paused)
                ↓
Auth + role/plan gating (Supabase Auth + middleware)
                ↓
Member portal  ──┬── Admin panel
                 │
        Resources · Discounts · Community · Levels
                 ↓
        Supabase (Postgres, RLS, Storage)
                 ↓
        Lemon Squeezy (planned) · Resend (email)
```

## Core workflow example

```text
Member authenticates
        ↓
Middleware checks role/plan for /portal or /admin
        ↓
Portal renders resources/discounts available at member's plan level
        ↓
Member requests a resource download
        ↓
Access re-checked against plan_required; signed URL issued (short expiry)
        ↓
Download logged for admin visibility
```

## Testing focus

- Auth middleware behaviour on `/portal/*` and `/admin/*`
- Plan-gated visibility of resources and discounts (RLS correctness)
- Signed-URL expiry and access revalidation
- Admin CRUD flows for resources, discounts and events
- Typecheck, lint, unit tests and build as a required validation gate before merging

## Product decision worth noting

The deliberate choice to build the portal and admin experience before the public marketing/checkout funnel is itself a product decision, not a shortcut: it lets the tier model, content and admin workflows be validated with real usage before spending effort on acquisition and billing integration — reducing the risk of building a paid funnel around a portal that still needs to prove its core value.

## Current documentation priorities

1. Decision log entry for pausing the public marketing funnel and its resumption criteria
2. Confirmed billing/automation roadmap (manual admin process today vs. Lemon Squeezy integration)
3. Member lifecycle and churn/pause handling once billing is automated
4. Community-feature scope definition (current build vs. future phases)

## Confidentiality note

This case study describes product and engineering responsibilities without publishing private source code, member data, credentials or production infrastructure details.
