# GTM Overview - DeepRead

## Strategic Framework

### Market Positioning

**Category:** Developer Infrastructure - OCR Pipeline Automation

**Key Message:**
"Everyone knows LLMs are better at OCR, but building production pipelines takes weeks. DeepRead is the infrastructure for best-in-class OCR - so you can ship in hours, not months."

### Target Segments

**Primary:**
- Engineering teams building document processing features
- Product teams in fintech, legal tech, healthcare
- Companies processing >10K documents/month
- Teams currently evaluating OCR vendors or building in-house

**Secondary:**
- Agencies building client solutions
- Enterprises with compliance requirements
- Startups in document-heavy verticals

## GTM Philosophy

### Core Principles

1. **Product-Led First**
   - Value before friction
   - API key + docs before sales calls
   - Usage data drives everything

2. **Signal-Based Revenue**
   - Product behavior > demographics
   - Automation > manual qualification
   - Real-time triggers > batch campaigns

3. **Developer-Centric**
   - Documentation is marketing
   - Code samples are conversion assets
   - Technical accuracy > marketing polish

## The GTM Layers

DeepRead's GTM stack unifies product data with revenue workflows, aligning marketing, sales, and product operations under one system.

```
┌─────────────────────────────────────────────┐
│         PRODUCT ANALYTICS                   │
│    (PostHog/Mixpanel + Segment)            │
└──────────────┬──────────────────────────────┘
               │ Product Signals
               ↓
┌─────────────────────────────────────────────┐
│      CRM & REVENUE CORE                     │
│         (HubSpot/Salesmate)                 │
└──────────────┬──────────────────────────────┘
               │ Triggers
               ↓
┌─────────────────────────────────────────────┐
│    REVENUE ACTIONS                          │
│  • Marketing Automation (Brevo)             │
│  • Sales Engagement (Apollo)                │
│  • Customer Success (Gainsight)             │
└─────────────────────────────────────────────┘
```

### Why This Architecture Works

**Unified Data Flow:**
Product signals feed revenue workflows automatically - no manual data entry, no spreadsheet exports, no lag between user action and business response.

**Behavior Over Attributes:**
In developer markets, form fills are rare. This stack prioritizes usage signals (API calls, docs engagement, feature adoption) over static firmographics.

**Automation at Scale:**
As you grow from 100 → 10,000 users, automation maintains quality without linear headcount growth.

## Growth Stages

### Stage A: $0 to $1M ARR
**Focus:** Validate PMF + build predictable self-serve revenue

**Primary Motion:** Product-led acquisition
**Team Size:** 2-5 people
**Timeline:** 12-18 months

[→ Full Stage A Documentation](./02-stage-a-self-serve.md)

### Stage B: $1M to $10M ARR
**Focus:** Add sales motion while preserving PLG efficiency

**Primary Motion:** PLG + sales-assisted
**Team Size:** 8-20 people
**Timeline:** 18-36 months

[→ Full Stage B Documentation](./03-stage-b-plg-sales.md)

## Critical Success Factors

### Must-Have from Day 1

1. **Product Analytics Integration**
   - Track: API key creation, first success, volume usage
   - Route signals to CRM automatically
   - Enable cohort analysis

2. **Documentation as Acquisition**
   - SEO-optimized technical docs
   - Working code samples
   - Use-case tutorials
   - Performance benchmarks

3. **Self-Serve Pricing**
   - Free tier with clear limits
   - Transparent usage-based pricing
   - Frictionless upgrade path

### Common Pitfalls to Avoid

❌ **Over-gating early value** - Don't require form fills before API access
❌ **Manual lead scoring** - Automate qualification based on product signals
❌ **Generic messaging** - Speak technical specifics, not vague benefits
❌ **Premature sales hiring** - Validate self-serve first, then add sales
❌ **Ignoring activation** - API key ≠ success; track first meaningful outcome

## Next Steps

1. Review your current stage ([Stage A](./02-stage-a-self-serve.md) or [Stage B](./03-stage-b-plg-sales.md))
2. Implement the [Tech Stack](./04-tech-stack.md) components
3. Set up [Revenue Flows](./05-revenue-flows.md) automation
4. Track [Metrics](./06-metrics-kpis.md) religiously
5. Execute using [Playbooks](./07-playbooks/)

---

**Key Principle:** In developer infrastructure, the product IS the marketing. Every API call, every doc page, every code sample is part of your GTM motion.
