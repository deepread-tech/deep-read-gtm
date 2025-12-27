# Stage B: $1M to $10M ARR (PLG + Sales Enabled)

## Objective

Scale PLG motion while adding sales-assisted expansion for mid-market and enterprise deals.

**Timeline:** 18-36 months
**Team Size:** 8-20 people
**Primary Focus:** Sales-assisted ACV, expansion revenue, enterprise pipeline

---

## Strategic Shift: PLG + Sales Hybrid

### What Changes from Stage A

**Stage A (Self-Serve Only):**
- All customers find you, sign up, upgrade themselves
- Founder handles high-touch requests ad-hoc
- Revenue from volume of small deals ($100-1K/month)

**Stage B (PLG + Sales):**
- Self-serve continues (>70% of logos)
- Sales layer for deals >$10K ACV
- Proactive outbound to high-signal accounts
- Customer success team for expansion/retention

### The Hybrid Model

```
┌─────────────────────────────────────────────┐
│         SELF-SERVE PLG (70% of logos)       │
│                                             │
│  Visitor → Docs → API → Paid ($100-2K/mo)  │
└─────────────────────────────────────────────┘
              ↓ High-signal accounts
┌─────────────────────────────────────────────┐
│       SALES-ASSISTED (30% of logos,         │
│             70% of revenue)                 │
│                                             │
│  PQL → SDR outreach → Demo → Contract      │
│                     ($10K-100K ACV)         │
└─────────────────────────────────────────────┘
```

**Key Principle:** Don't kill self-serve. Sales is an *addition*, not a replacement.

---

## 1. Sales & SDR Workflow (Signal-Driven)

### Primary Product Signals for Sales Qualification

| Signal | Threshold | Action |
|--------|-----------|--------|
| **High volume** | >5,000 pages/day for 3+ consecutive days | SDR outreach within 24hrs |
| **Team seats** | 3+ users from same company domain | Flag as expansion opportunity |
| **Advanced features** | Using enterprise features on free/low tier | Upsell conversation |
| **Error patterns** | High volume + errors | Support → sales handoff |
| **Repeat upgrades** | Self-serve customer upgrades 2+ times | CS introduces account executive |

### Sales Stack Components

**CRM: HubSpot Sales Hub**
- Deal stages, pipeline management
- Email tracking, meeting scheduling
- Automated task creation from PQL signals

**Sales Engagement: Apollo**
- Outbound sequences (email + LinkedIn)
- Contact enrichment at scale
- Intent data integration

**LinkedIn Sales Navigator**
- Target engineering leaders at PQL accounts
- Warm introductions via mutual connections
- Company news triggers (funding, hiring, expansion)

**Conversation Intelligence (Optional: Gong/Chorus)**
- Record sales calls
- Extract objection patterns, winning talk tracks
- Onboard new reps faster

### Signal-to-Action Automation

**Workflow Example: High-Volume User**

```
Product Event: User processes >5K pages in one day
    ↓
HubSpot automation:
  1. Create deal: "High-Volume PQL"
  2. Assign to: SDR (round-robin)
  3. Create task: "Outreach within 24hrs"
  4. Send Slack notification to #sales
    ↓
SDR receives task:
  - Pre-filled email template (usage stats, ROI estimate)
  - LinkedIn profile (via Apollo enrichment)
  - Recent company news (via LinkedIn Sales Nav)
    ↓
SDR sends personalized email:
  "I noticed you processed 8,000 pages yesterday.

   At that volume, most teams benefit from our Schema Optimizer
   to push accuracy from ~80% to 95%+ (saves weeks of manual
   prompt engineering).

   Worth a 15min chat to show you how it works?"
    ↓
Meeting booked → AE takes over → Demo → Contract
```

### SDR Playbooks

**Outbound Sequence for High-PQL Accounts**

| Day | Channel | Message Focus |
|-----|---------|---------------|
| 0 | Email | "Noticed you're using DeepRead - how's it going?" |
| 2 | LinkedIn connection | Brief intro, no pitch |
| 4 | Email | Share relevant case study (similar company/use case) |
| 7 | LinkedIn message | "Saw [company news]. Might be relevant..." |
| 10 | Email | Breakup email: "Should I close your file?" |

**Conversion Rate Targets:**
- PQL → Meeting booked: 15-25%
- Meeting → Demo: 60%+
- Demo → Closed-Won: 20-30%

---

## 2. Mid-Market & Enterprise Motion

### What Mid-Market/Enterprise Buyers Need

**Beyond Self-Serve:**
- Security & compliance docs (SOC 2, GDPR, HIPAA)
- SLA commitments (99.9% uptime)
- Dedicated support (Slack channel, CSM)
- Custom contracts (MSA, DPA)
- Invoice/PO payment (not just credit card)
- Unlimited Schema Optimizer runs (vs. limited on lower tiers)
- White-glove optimization service for complex document types

### Packaging for Enterprise

**Enterprise Plan** ($5K-50K/month)
- Volume commitments (e.g., 500K pages/month)
- Dedicated infrastructure (optional)
- SSO (SAML, Okta)
- Advanced security (API key rotation, audit logs)
- SLA: 99.95% uptime, <24hr support response
- Quarterly business reviews (QBR)

### Outbound Motion for Enterprise

**Ideal Customer Profile (ICP):**
- Company size: 200-5,000 employees
- Funding: Series B+ or profitable
- Tech stack: Modern (Python/Node.js/cloud-native)
- Use case: Document-heavy workflows (legal, finance, healthcare)
- Buying signals: Job postings for ML/data engineers, recent funding

**Outbound Channels:**

1. **Targeted Email Campaigns**
   - Apollo sequences to engineering VPs, product leaders
   - Personalized first line (reference company news, tech stack)
   - ROI-focused messaging: "Save 200 engineering hours/month"

2. **LinkedIn Outbound**
   - Connect with target personas
   - Engage with their posts (genuine value-add comments)
   - InMail for high-priority accounts (use sparingly)

3. **Partner Channels**
   - AWS/GCP marketplace listings
   - Integration partnerships (workflow tools, data platforms)
   - Reseller agreements (system integrators in vertical markets)

### Content for Enterprise Buyers

**Required Assets:**

- **Security & Compliance One-Pager** - SOC 2, GDPR, data handling
- **ROI Calculator** - Interactive tool: "Input your volume → See cost vs. build"
- **Schema Optimizer Demo** - Before/after comparison showing 68% → 95% improvement in 3 iterations
- **Case Studies** - 3-5 stories from similar companies (anonymized if needed)
- **Comparison Battlecards** - DeepRead vs. AWS Textract, Google Document AI, build in-house (emphasize optimizer as unique differentiator)
- **Technical Architecture Doc** - How it works, multi-model consensus, vision-based failure analysis, integration patterns, performance benchmarks

**Distribution:**
- Gated on website (capture high-intent leads)
- Send proactively during sales conversations
- Include in outbound sequences

---

## 3. Account Expansion & Customer Success

### Why Expansion Matters in Stage B

**Target:** 30-40% of new ARR from existing customers

**Expansion Levers:**
1. **Volume growth** - customer processes more docs as they scale
2. **Feature upsell** - start with basic, upgrade to advanced models
3. **Seat expansion** - more team members using the platform
4. **New use cases** - initial use case succeeds, add more workflows

### Customer Success Structure

**At $1M ARR:** Founder/PM handles top 10 accounts
**At $3M ARR:** Hire first CSM (manages 20-30 accounts >$1K/month)
**At $5M ARR:** CSM team (1 CSM per $1.5M ARR)

### CS Tools

**HubSpot Service Hub**
- Ticketing, knowledge base
- Customer health scoring
- Renewal tracking
- Most cost-effective since you're already using HubSpot
- Sufficient until $10M+ ARR

### Expansion Playbooks

**Trigger: Usage grows 50% month-over-month**

1. CS sends email: "Congrats on growth! Let's optimize your setup"
2. Schedule check-in call
3. Review usage patterns, identify bottlenecks
4. Recommend: Upgrade to higher tier or add features
5. Offer: Annual contract (discount for commitment)

**Trigger: Customer uses 90% of plan limits**

1. Automated email: "You're approaching your limit - let's talk"
2. CSM reviews account, prepares upgrade proposal
3. Proactive outreach before they hit limit
4. Upgrade CTA with ROI justification

**Trigger: 30 days before renewal**

1. CSM sends renewal reminder + usage report
2. Offer: Upsell to annual (if on monthly) or higher tier
3. Address any objections/issues preemptively

### Customer Health Scoring

**Product Signals:**
- ✅ Green: API calls every day, low error rate, expanding usage
- ⚠️ Yellow: Flat usage, occasional errors, no new features adopted
- 🔴 Red: Declining usage, high error rate, no activity in 7 days

**Engagement Signals:**
- ✅ Green: Responds to emails, attends QBRs, engaged with support
- ⚠️ Yellow: Slow email response, skips optional meetings
- 🔴 Red: Ignores outreach, submits cancellation request

**Action by Health:**
- Green → Expansion play (upsell, case study request, referral ask)
- Yellow → Re-engagement (check-in call, feature education, offer help)
- Red → Save play (executive sponsor call, discount offer, identify root issue)

---

## 4. ABM & Paid Acquisition

### Account-Based Marketing (ABM) for Enterprise

**When to Start ABM:** >$3M ARR, clear ICP, sales team in place

**ABM Strategy:**

1. **Identify Target Accounts**
   - ICP fit (size, industry, tech stack)
   - Buying signals (funding, hiring, tech initiatives)
   - Build list of 50-100 "dream accounts"

2. **Multi-Channel Engagement**
   - LinkedIn ads to employees at target accounts
   - Retargeting to website visitors from target domains
   - Personalized direct mail (ROI reports, swag, event invites)

3. **Sales Alignment**
   - SDR assigned to each account
   - Coordinated outreach (marketing warms up, sales closes)

### Paid Channels

**LinkedIn Ads**
- **Audience:** Job titles (Engineering Manager, VP Product, CTO)
- **Creative:** Technical content (benchmarks, case studies)
- **Budget:** $3K-10K/month
- **Goal:** Drive to gated asset (whitepaper, ROI calc) → MQL

**Google Search Ads**
- **Keywords:** High-intent, long-tail
  - "enterprise ocr api"
  - "document processing automation"
  - "pdf extraction for python"
- **Budget:** $2K-5K/month
- **Goal:** Drive to docs or comparison page → self-serve trial

**Retargeting (Google Display/Facebook)**
- **Audience:** Website visitors who didn't sign up
- **Creative:** Social proof, customer logos, urgency ("Start free today")
- **Goal:** Bring back to trial signup

### Paid Acquisition Benchmarks

- **CAC (paid channels):** $500-1,500 for self-serve, $3K-10K for sales-assisted
- **LTV:CAC ratio:** Target 3:1 minimum
- **Payback period:** <12 months for enterprise, <6 months for self-serve

---

## 5. Organizational Structure for Stage B

### Team at $1M ARR

- **Founders (2):** Product + GTM
- **Engineer(s) (1-2):** Product development
- **Marketing (0.5-1):** Content, SEO, email campaigns
- **SDR (0.5):** Part-time or founder-led outbound

### Team at $5M ARR

- **Product/Eng (5-8):** Features, infrastructure, support
- **Marketing (2-3):** Content, demand gen, ops
- **Sales (3-5):** SDR (2), AE (2), Sales Manager (1)
- **Customer Success (1-2):** Onboarding, expansion, renewals
- **Operations (1):** RevOps, data, tooling

### Key Hires by Priority

**Hire #1: Founding AE** (at $1M ARR or 20+ sales-qualified PQLs/month)
- Takes over high-touch deals from founder
- Builds sales process, playbooks
- Trains future reps

**Hire #2: Demand Gen Marketer** (at $1.5M ARR)
- Owns paid acquisition, SEO, content
- Frees up founder to focus on product/strategy

**Hire #3: CSM** (at $2M ARR or 30+ paying customers >$500/mo)
- Owns retention, expansion
- Builds CS playbooks

**Hire #4: SDR** (when AE has >40 leads/month, can't keep up)
- Qualifies inbound leads
- Runs outbound sequences to PQLs

---

## 6. Revenue Model Refinement

### Pricing Evolution

**Add Mid-Tier Plan:**

| Plan | Price | Target Customer |
|------|-------|-----------------|
| Free | $0 | Hobbyists, POCs |
| Starter | $99/mo | Individuals, small teams |
| **Growth** | **$499/mo** | **Growing startups** |
| Team | $999/mo | Established teams |
| Enterprise | Custom | Large orgs |

**Growth Plan Features:**
- 50K pages/month included
- Priority support (4hr response)
- 5 API keys
- Advanced models

**Why Add This Tier:**
- Capture customers who outgrow Starter but aren't ready for Team
- Reduce friction in upgrade path
- Increases ARPU

### Enterprise Pricing

**Shift to Annual Contracts:**
- Minimum: $50K ACV
- Payment: Invoice/PO (Net 30)
- Contract: MSA + Order Form
- Commitment: Volume + features + SLA

**Negotiation Guidelines:**
- Discount range: 10-20% for annual prepay
- Don't discount >20% without exec approval
- Tie discounts to commitments (volume, term, case study)

---

## 7. Key Metrics for Stage B

### North Star Metric
**ARR growth rate** (target: 15-25% quarter-over-quarter)

### Funnel Metrics

| Metric | Target | Note |
|--------|--------|------|
| **Self-Serve Conversion** | ≥10% | PQL → Paid (self-serve) |
| **Sales Conversion** | 20-30% | Demo → Closed-Won |
| **Sales Cycle** | 30-60 days | First touch → contract |
| **ACV (Sales-Assisted)** | >$10K | Average annual contract value |

### Expansion Metrics

- **Net Dollar Retention (NDR):** >110% (target: 120%+)
- **Expansion Revenue:** 30-40% of new ARR
- **Upsell Rate:** >25% of customers upgrade within 12 months
- **Logo Churn:** <10% annually

### Sales Efficiency

- **CAC Payback:** <12 months
- **Magic Number:** >0.75 (ideal: >1)
  - Formula: (Net New ARR in Quarter) / (Sales & Marketing Spend in Prior Quarter)
- **Win Rate:** >25% of qualified opportunities

---

## Stage B Success Criteria

You're ready for Stage C (scaling to $10M+) when:

✅ **$10M ARR** with predictable growth
✅ **Repeatable sales process** - new AEs can close deals
✅ **NDR >115%** - customers are expanding
✅ **Magic Number >1** - efficient growth
✅ **Clear enterprise motion** - 10+ customers >$50K ACV
✅ **Team scaled** - 15-25 people across product, sales, marketing, CS

---

## Common Pitfalls in Stage B

❌ **Killing self-serve for sales** - Keep both, optimize both
❌ **Hiring AEs before PMF** - Need clear ICP and repeatable wins first
❌ **Ignoring churn** - Expansion can't outpace churn indefinitely
❌ **Over-customizing product** - One-off features for deals kill velocity
❌ **Weak onboarding** - Sales closes deal, CS can't retain them

---

[← Back to Stage A](./02-stage-a-self-serve.md) | [Next: Tech Stack →](./04-tech-stack.md)
