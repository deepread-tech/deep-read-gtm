# Stage A: $0 to $1M ARR (Self-Serve First)

## Objective

Validate product-market fit and build predictable self-serve revenue motion.

**Timeline:** 12-18 months
**Team Size:** 2-5 people
**Primary Focus:** Activation rate, usage growth, self-serve conversion

---

## 1. Product-Led Acquisition

### Goal
Convert visitors → API key → first success → recurring usage

### Critical Events to Track

| Event | Definition | Why It Matters |
|-------|-----------|----------------|
| `api_key_created` | User generates API key | Top-of-funnel activation |
| `first_ocr_success` | First successful OCR call | Aha moment - experienced value |
| `docs_to_api_transition` | Docs view → API usage <24hrs | Intent-to-action speed |
| `volume_threshold` | Pages processed/day | Usage intensity (PQL signal) |
| `feature_adoption` | Advanced features used | Power user indicator |

### Activation Funnel

```
Website Visit
    ↓ (40-60% of qualified traffic)
Docs Engagement
    ↓ (20-30%)
API Key Created
    ↓ (TARGET: ≥40%)
First Successful OCR Call
    ↓ (60-70% within 7 days)
Recurring Usage (3+ days/week)
    ↓ (TARGET: ≥8%)
Paid Conversion
```

### Tools Required

**Product Analytics:**
- **PostHog** or **Mixpanel** - event tracking, funnel analysis, cohort retention
- Custom dashboards for: activation rate, time-to-value, usage trends

**Event Unification:**
- **Segment** (optional but recommended) - pipes product events to CRM, marketing tools
- Alternative: Direct integrations if budget-constrained

**Central Data Store:**
- **Snowflake** or **BigQuery** - store product events, enable SQL analysis
- Needed when you want to join product data with CRM/revenue data

### Implementation Steps

1. **Week 1-2:** Instrument key events (API key, first call, volume)
2. **Week 3:** Set up PostHog/Mixpanel dashboards
3. **Week 4:** Connect events to CRM (via Segment or native integration)
4. **Ongoing:** Add new events as you discover PQL patterns

---

## 2. Lead Capture & Enrichment

### Strategy: Value Before Friction

**Don't gate:**
- Documentation access
- API key generation
- First 100 API calls

**Do capture:**
- Email (after first successful OCR call)
- Company name (optional at signup)
- Use case (post-activation survey)

### Lead Enrichment Stack

**Tools:**
- **Apollo** or **Cognism** - enrich email → company data, employee count, tech stack
- **Visitor ID tools** (e.g., Clearbit Reveal, 6sense) - convert anonymous traffic to companies

**Enrichment Workflow:**

```
User signs up (email only)
    ↓
Trigger: Apollo enrichment API
    ↓
Add to CRM with:
  - Company name
  - Industry
  - Employee count
  - LinkedIn profile
    ↓
Apply PQL scoring model
```

### Signal-Based Lead Triggers

Use **Tactic** or similar tools to create real-time triggers:

| Trigger | Action |
|---------|--------|
| API key created + Fortune 500 company | Alert sales, high priority |
| 5+ successful calls in 24hrs | Add to "hot leads" sequence |
| Docs visit depth >5 pages | Tag as high-intent, nurture campaign |
| Error rate >30% | Trigger support outreach (prevent churn) |

### Best Practices

✅ Avoid mandatory forms before first value delivery
✅ Capture email *after* user experiences the aha moment
✅ Use enrichment to score, not to gate
✅ Respect developer preferences - never spam

---

## 3. CRM & Revenue Core

### Recommended: HubSpot CRM

**Why HubSpot:**
- Native marketing automation
- Strong API for product data sync
- Workflow automation for PQL routing
- Scales from Stage A → Stage B

**Core Setup:**

**Contact Properties:**
- `first_api_call_date`
- `total_pages_processed`
- `average_daily_volume`
- `error_rate`
- `feature_flags` (JSON of features used)
- `pql_score` (calculated)

**Deal Pipeline Stages:**
1. Self-Serve Trial
2. Active Free User
3. PQL (Product Qualified Lead)
4. Self-Serve Customer
5. Expansion Opportunity

**Automation Examples:**
- API key created → Create contact → Enrich → Score
- PQL threshold met → Create deal → Assign to founder/SDR
- 7 days no activity → Re-engagement email

### Alternative: Salesmate

**Why Salesmate:**
- Lower cost ($15-30/user vs. $50-100 for HubSpot)
- Built-in email sequences
- Sandy AI for outreach automation
- Good for lean teams

**Trade-off:** Less robust marketing automation, may need separate tool (Brevo)

### Implementation Checklist

- [ ] Set up contact/company properties for product signals
- [ ] Create deal pipeline with clear stage definitions
- [ ] Build automation: product event → CRM action
- [ ] Configure PQL scoring model
- [ ] Set up internal notifications (Slack/email) for hot leads

---

## 4. Marketing Automation

### Primary Tool: Brevo (Sendinblue)

**Why Brevo:**
- Affordable ($25-65/mo for startup scale)
- Email workflows + SMS
- Behavior-triggered campaigns
- Good deliverability

### Email Campaigns to Build

**1. Onboarding Sequence (Triggered: API key created)**

| Day | Subject | Goal |
|-----|---------|------|
| 0 | Welcome + Quick Start Guide | Drive first API call |
| 1 | "Did you hit any issues?" | Surface blockers |
| 3 | Use case examples | Inspiration for adoption |
| 7 | Power features you're missing | Feature awareness |
| 14 | How [Company X] processes 10K docs/day | Social proof + volume |

**2. Activation Nudge (Triggered: API key created, no API call in 48hrs)**

- Subject: "Stuck? Here's a working code sample"
- Include: Copy-paste code, troubleshooting guide

**3. Upsell Nurture (Triggered: Approaching free tier limits)**

- Subject: "You're crushing it! Here's what happens next"
- Content: Usage stats, pricing calculator, upgrade CTA

**4. Re-engagement (Triggered: 14 days inactive)**

- Subject: "We just shipped [feature] for [use case]"
- Content: Feature release, customer story, "welcome back" offer

### Interactive Funnels: involve.me

Use for:
- Use case qualifier → personalized demo
- ROI calculator → "Calculate your savings vs. building in-house"
- Technical requirements checker → "Is DeepRead right for you?"

**Benefit:** Qualify intent without manual sales calls

---

## 5. Content & SEO (Long-Term Acquisition)

### Documentation as Marketing

**Principle:** Developer docs should rank for high-intent queries

**Key Pages to Build:**

1. **Use Case Tutorials**
   - "How to extract tables from PDFs with Python"
   - "Processing invoices at scale with Node.js"
   - "Building a document search pipeline"

2. **Comparison Content**
   - "DeepRead vs. AWS Textract"
   - "DeepRead vs. Google Document AI"
   - "Open source OCR vs. managed pipelines"

3. **Technical Deep Dives**
   - "How we combine GPT-4V and Claude for 99% accuracy"
   - "Benchmarking OCR APIs: accuracy vs. speed vs. cost"
   - "Handling edge cases in document processing"

### SEO Strategy

**Target Keywords:**
- `ocr api for developers`
- `document processing pipeline`
- `pdf to text api`
- `llm ocr accuracy`
- `[specific use case] + ocr solution`

**Content Format:**
- Working code samples (GitHub Gist embeds)
- Performance benchmarks (tables, charts)
- Clear pricing comparisons
- Video walkthroughs (embedded)

**Distribution:**
- Dev.to, Medium (canonical link to your docs)
- Hacker News (sparingly, only genuinely useful content)
- Reddit (r/MachineLearning, r/LearnProgramming)
- GitHub discussions, Stack Overflow answers

---

## 6. Monetization Model

### Pricing Tiers

**Free Tier**
- 100 pages/month
- Standard accuracy model
- Community support (docs + Discord/Slack)
- API key rate limit: 10 requests/min

**Pay-as-You-Go**
- $0.05/page (or appropriate rate)
- All features unlocked
- Email support (24hr SLA)
- Rate limit: 100 requests/min

**Team Plan** ($299-999/month)
- Included volume (e.g., 10K pages)
- Overage: $0.03/page
- Multiple API keys
- Priority support
- Custom models (if applicable)

### Upgrade Triggers

**In-Product:**
- Banner when user hits 80% of free tier
- Modal when limit exceeded: "Upgrade now or wait until next month"
- Dashboard widget: "You've saved X hours this month - unlock more"

**Email:**
- 7 days before limit: "You're on track to hit your limit"
- At limit: "Upgrade to keep processing"
- 3 days after limit: "You're missing out on X pages processed by similar customers"

### Self-Serve Checkout

**Must-have features:**
- Credit card → instant activation (Stripe)
- Pricing calculator (estimate monthly cost)
- Annual discount option (2 months free)
- Transparent overage pricing

---

## 7. Key Metrics for Stage A

### North Star Metric
**Weekly Active API Keys with 10+ successful calls**

### Funnel Metrics

| Metric | Target | How to Improve |
|--------|--------|----------------|
| **Visitor → API key** | 5-10% | Better CTAs, clearer value prop |
| **API key → First success** | ≥40% | Improve docs, onboarding emails, reduce errors |
| **First success → Recurring usage** | 60-70% | Feature education, use case inspiration |
| **PQL → Paid conversion** | ≥8% | Pricing clarity, upgrade prompts, sales touch |

### Economic Metrics

- **Self-serve CAC:** <$100 (organic) to <$500 (paid)
- **CAC payback period:** <3 months
- **Average MRR per customer:** $150-500
- **Gross retention:** >85%

### Leading Indicators

- Week-over-week API call growth
- Docs engagement rate (% of visitors who view docs)
- Time to first API call (should decrease over time)
- Support ticket rate (should decrease as docs improve)

---

## Stage A Success Criteria

You're ready for Stage B when:

✅ **$50K+ MRR** with self-serve motion
✅ **PQL → Paid conversion ≥8%** consistently
✅ **10+ customers** paying >$500/month
✅ **Clear ICP pattern** - you know exactly who your best customers are
✅ **Repeatable activation** - can articulate the path to aha moment
✅ **Inbound signals** - customers asking for enterprise features, SSO, contracts

---

## Quick Win Checklist (First 90 Days)

**Week 1-2: Foundation**
- [ ] Set up PostHog/Mixpanel with core events
- [ ] Implement API key creation tracking
- [ ] Create HubSpot account, configure properties

**Week 3-4: Automation**
- [ ] Connect product events to HubSpot (via Segment or webhook)
- [ ] Build PQL scoring model (simple: volume + frequency)
- [ ] Set up welcome email sequence in Brevo

**Week 5-8: Content**
- [ ] Write 3 use-case tutorials (target high-intent keywords)
- [ ] Create comparison page vs. top 2 competitors
- [ ] Build interactive ROI calculator

**Week 9-12: Optimization**
- [ ] Analyze activation funnel, identify drop-off points
- [ ] A/B test onboarding email timing
- [ ] Implement upgrade nudges (in-product + email)

---

[← Back to Overview](./01-gtm-overview.md) | [Next: Stage B →](./03-stage-b-plg-sales.md)
