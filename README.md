# DeepRead GTM Strategy

## Overview

Complete go-to-market strategy for DeepRead - infrastructure for production-ready OCR pipelines.

**Philosophy:** Product-led growth first, then add sales. Keep it simple, measure what matters, scale only what works.

---

## The Two-Phase Framework

### Phase 1: $0 to $1M ARR (12-18 months)
**Focus:** Self-serve revenue + product-market fit
**Team:** 2-5 people
**Motion:** 100% product-led growth

### Phase 2: $1M to $10M ARR (18-36 months)
**Focus:** Scale PLG + add sales for enterprise
**Team:** 8-20 people
**Motion:** 70% self-serve + 30% sales-assisted

---

## Quick Value Prop

**The Problem:**
- LLMs are great at OCR, but production requires complex multi-LLM pipelines
- Teams waste weeks building and maintaining infrastructure
- Can't focus on core product

**Our Solution:**
Battle-tested infrastructure for best-in-class OCR pipelines. We don't claim magic - we built the infrastructure so you don't have to.

**Target:** Engineering teams at tech companies processing >10K documents/month

---

## What's Inside

### Core Strategy Docs

**[1. GTM Overview](./01-gtm-overview.md)**
Strategic framework, positioning, core principles

**[2. Phase 1: $0-1M ARR](./02-stage-a-self-serve.md)**
Self-serve playbook: activation, conversion, monetization

**[3. Phase 2: $1-10M ARR](./03-stage-b-plg-sales.md)**
Adding sales: SDR/AE motion, mid-market, enterprise

**[4. Tech Stack](./04-tech-stack.md)**
What tools you need at each phase (keep it minimal)

**[5. Revenue Flows](./05-revenue-flows.md)**
Product-to-revenue automation blueprints

**[6. Metrics & KPIs](./06-metrics-kpis.md)**
5 metrics for Phase 1, 8 for Phase 2 (don't track more)

**[7. Playbooks](./07-playbooks/)**
Tactical execution guides (SDR outreach, demos, expansion, etc.)

**[8. Messaging](./08-messaging.md)**
Short, hard-hitting messaging for engineers (homepage, emails, social, HN)

---

## Phase 1: $0 to $1M ARR

### Goals
- Validate product-market fit
- Build predictable self-serve revenue
- Hit $1M ARR with minimal team

### The 5 Metrics That Matter
1. **Activation Rate:** API key → First success (**≥40%**)
2. **PQL Conversion:** PQL → Paid (**≥8%**)
3. **MRR Growth:** Month-over-month (**15-20%**)
4. **CAC Payback:** Months to recover cost (**<3 months**)
5. **Retention:** Week 4 retention (**>40%**)

### Minimal Tech Stack
- **PostHog** (analytics): $0-200/mo
- **HubSpot** (CRM): Free
- **Brevo** (email): $25-65/mo
- **Stripe** (payments): % of revenue

**Total:** ~$25-265/mo

### First 90 Days Checklist
- [ ] Week 1: Set up PostHog, HubSpot, Brevo
- [ ] Week 2-4: Connect tools, build 3 email sequences
- [ ] Month 2-3: Add Apollo for enrichment, automate PQL alerts
- [ ] Month 3+: Weekly metrics review, optimize conversion

### Success Criteria (Ready for Phase 2)
✅ $50K+ MRR with self-serve
✅ PQL → Paid ≥8% consistently
✅ 10+ customers paying >$500/month
✅ Clear who your best customers are
✅ Customers asking for enterprise features

---

## Phase 2: $1M to $10M ARR

### Goals
- Scale self-serve (still 70% of logos)
- Add sales for high-value accounts (30% of logos, 70% of revenue)
- Build repeatable expansion motion

### The 8 Metrics That Matter
*Keep Phase 1's 5 metrics, plus:*

6. **Sales Win Rate:** >25%
7. **Net Dollar Retention (NDR):** >110%
8. **Magic Number:** >0.75 (sales efficiency)

### Tech Stack Additions
- **HubSpot Sales Hub:** $500-1,500/mo
- **Apollo** (sales): $149/user × 3 SDRs
- **LinkedIn Sales Nav:** $135/user × 2 AEs

**Total:** ~$1,500-3,000/mo

### Team Evolution

**At $1M ARR:**
- Founders (2)
- Engineers (2-3)
- First AE (1)
- Marketing (0.5-1)

**At $5M ARR:**
- Product/Eng (5-8)
- Sales (3-5): SDRs + AEs
- Marketing (2-3)
- Customer Success (1-2)
- Ops (1)

### Success Criteria (Ready for $10M+)
✅ $10M ARR
✅ Repeatable sales process (new AEs can close)
✅ NDR >115%
✅ Magic Number >1
✅ 10+ customers >$50K ACV

---

## Revenue Model

### Pricing Tiers

| Plan | Price | Target |
|------|-------|--------|
| **Free** | $0 | Hobbyists, validation |
| **Starter** | $99/mo | Individuals, small teams |
| **Growth** | $499/mo | Growing startups |
| **Team** | $999/mo | Established teams |
| **Enterprise** | Custom | Large orgs (annual contracts) |

### Monetization Strategy

**Phase 1:** Free tier → usage-based pricing → self-serve checkout

**Phase 2:** Same + sales-assisted for >$10K ACV deals

---

## GTM Motions Explained

### Phase 1: Product-Led Growth

```
Traffic (SEO, HN, word-of-mouth)
    ↓
Docs Engagement
    ↓
API Key Created
    ↓ (Target: ≥40%)
First Successful API Call
    ↓
Recurring Usage (3+ days/week)
    ↓ (Target: ≥8%)
Self-Serve Upgrade
```

**Key:** Value before friction. No forms until after first API call.

### Phase 2: Add Sales Layer

```
Self-Serve Path (70% of logos)
    [Same as Phase 1]

+

Sales-Assisted Path (30% of logos, 70% of revenue)
    High-Value PQL (>5K pages/day or enterprise domain)
        ↓
    SDR Outreach (email + LinkedIn sequence)
        ↓
    AE Demo
        ↓
    Proposal (>$10K ACV)
        ↓
    Contract Signed
```

**Key:** Don't kill self-serve. Sales is an *addition*, not replacement.

---

## Critical Success Factors

### Must-Have from Day 1

1. **Product analytics integration**
   - Track: API key, first success, volume
   - Feed signals to CRM automatically

2. **Documentation as marketing**
   - SEO-optimized technical docs
   - Working code samples
   - Use-case tutorials

3. **Self-serve pricing**
   - Free tier with clear limits
   - Transparent usage pricing
   - Frictionless checkout

### Common Pitfalls to Avoid

❌ **Over-gating early value** - Don't require forms before API access
❌ **Manual lead scoring** - Automate based on product signals
❌ **Generic messaging** - Speak technical specifics
❌ **Premature sales hiring** - Validate self-serve first
❌ **Ignoring activation** - API key ≠ success; track first call
❌ **Too many tools** - Start minimal, add only when needed
❌ **Too many metrics** - 5 metrics in Phase 1, 8 in Phase 2

---

## Getting Started

### If You're Pre-Launch
1. Read [GTM Overview](./01-gtm-overview.md)
2. Focus on [Phase 1](./02-stage-a-self-serve.md)
3. Set up [Tech Stack](./04-tech-stack.md) (minimal version)
4. Track the [5 core metrics](./06-metrics-kpis.md)

### If You're at $0-500K ARR
1. Review [Phase 1](./02-stage-a-self-serve.md) entirely
2. Fix activation if <40% (docs, onboarding, quick-start)
3. Fix conversion if <8% (pricing page, upgrade flow)
4. Don't hire sales yet - optimize self-serve first

### If You're at $500K-1M ARR
1. Prepare for [Phase 2](./03-stage-b-plg-sales.md)
2. Hire first AE (founder does sales until clear PMF)
3. Upgrade [Tech Stack](./04-tech-stack.md) (HubSpot Sales Hub, Apollo)
4. Build [SDR playbooks](./07-playbooks/sdr-high-pql-outreach.md)

### If You're at $1M+ ARR
1. Execute [Phase 2](./03-stage-b-plg-sales.md)
2. Don't kill self-serve - scale it alongside sales
3. Track [all 8 metrics](./06-metrics-kpis.md)
4. Focus on NDR (expansion > new logos at this stage)

---

## Key Principles

**1. Product-Led First**
Value before friction. Let users experience the product before asking for anything.

**2. Signal-Based Everything**
Product behavior > demographics. Automate actions based on usage patterns.

**3. Developer-Centric**
Docs are marketing. Code samples are conversion assets. No marketing fluff.

**4. Keep It Simple**
- Phase 1: 5 metrics, 3-4 tools, <$300/mo
- Phase 2: 8 metrics, 6-8 tools, <$3K/mo
- Don't over-engineer

**5. Measure What Matters**
Track only metrics that drive decisions. Ignore vanity metrics.

**6. Scale What Works**
Don't add sales until self-serve works. Don't add tools until manual process breaks.

---

## Success Benchmarks

### Phase 1 ($0-1M ARR)
- **Time to $1M:** 12-18 months
- **Team size:** 2-5 people
- **Key metric:** Activation rate ≥40%, PQL conversion ≥8%
- **Economics:** CAC <$500, payback <3 months

### Phase 2 ($1M-10M ARR)
- **Time to $10M:** 18-36 months from $1M
- **Team size:** 8-20 people
- **Key metrics:** Win rate >25%, NDR >110%, Magic Number >0.75
- **Economics:** Self-serve CAC <$500, sales CAC <$3K, blended payback <12 months

---

## Budget Overview

### Phase 1 ($0-1M ARR)

**Month 1-3:** ~$25/mo
- PostHog (free tier)
- HubSpot (free tier)
- Brevo ($25)

**Month 4-12:** ~$214/mo
- PostHog ($100)
- HubSpot (free)
- Brevo ($65)
- Apollo ($49)

**At $1M ARR:** ~$476/mo
- PostHog ($200)
- HubSpot Starter ($100)
- Brevo ($65)
- Apollo ($99)
- Cal.com ($12)

### Phase 2 ($1M-10M ARR)

**At $1M ARR:** ~$1,500/mo

**At $3M ARR:** ~$3,000/mo

**At $5M ARR:** ~$5,000/mo

**At $10M ARR:** ~$8,000-10,000/mo

---

## FAQ

**Q: When should I hire my first salesperson?**
A: When you have ≥20 sales-qualified PQLs/month and self-serve conversion is ≥8%. Usually around $1M ARR.

**Q: Can I skip self-serve and go straight to sales?**
A: No. You need self-serve for product validation, feedback loops, and to understand your ICP. Sales comes after.

**Q: What if my activation rate is <40%?**
A: This is your #1 priority. Fix it before anything else. Better docs, simpler onboarding, proactive support.

**Q: Should I use Salesforce or HubSpot?**
A: HubSpot. It's cheaper, simpler, and scales to $10M+ ARR easily. Salesforce is overkill until $50M+.

**Q: When do I need a data warehouse?**
A: Not until $3M+ ARR. PostHog analytics + HubSpot reporting is enough before that.

**Q: How do I know if I have product-market fit?**
A: Retention curve flattens (Week 12 ≥30%), customers asking for more features, word-of-mouth growth, PQL → Paid ≥8%.

**Q: What's the fastest way to $1M ARR?**
A: Nail activation (≥40%), optimize self-serve conversion (≥8%), create SEO content, talk to every customer, iterate fast.

---

**Last Updated:** 2025-12-21

**Questions?** This is a living document. Update it as you learn what works for your business.
