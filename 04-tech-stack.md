# Tech Stack - Complete Martech Architecture

## Stack Overview

This document details the GTM technology stack for DeepRead, organized by revenue phase.

**Principle:** Start minimal, add tools only when needed. Don't over-engineer early.

---

## Phase 1: $0 to $1M ARR (Self-Serve Focus)

### Essential Stack (Must Have)

| Tool | Purpose | Monthly Cost | When to Add |
|------|---------|--------------|-------------|
| **PostHog** | Product analytics, event tracking | $0-200 | Week 1 |
| **HubSpot CRM** (Free) | Contact management, basic workflows | $0 | Week 1 |
| **Brevo** | Email automation | $25-65 | Week 2 |
| **Stripe** | Payment processing | 2.9% + 30¢ | Week 1 |

**Total Monthly Cost: $25-265**

### Nice-to-Have (Add as you grow)

| Tool | Purpose | Monthly Cost | When to Add |
|------|---------|--------------|-------------|
| **Apollo** (Basic) | Email enrichment | $49 | Month 2-3 |
| **Segment** | Event routing (optional) | $120 | Month 3-6 (or skip) |
| **Cal.com** | Meeting booking | $0-12 | Month 1 |

**Total with Nice-to-Haves: $194-446/mo**

### What You DON'T Need ($0-1M)

❌ Salesforce (overkill, expensive)
❌ Marketo/Pardot (too complex)
❌ LinkedIn Sales Navigator (no outbound sales yet)
❌ Gainsight/ChurnZero (too early for dedicated CS platform)
❌ Data warehouse (PostHog analytics is enough)
❌ Gong/Chorus (no sales team yet)

---

## Phase 2: $1M to $10M ARR (PLG + Sales)

### Core Stack (Essential)

| Tool | Purpose | Monthly Cost | When to Add |
|------|---------|--------------|-------------|
| **PostHog** | Product analytics | $200-500 | Already have |
| **HubSpot Sales Hub** | CRM + sales automation | $500-1,500 | $1M ARR |
| **Brevo** | Email automation | $65-150 | Already have |
| **Apollo** (Professional) | Enrichment + sales sequences | $149/user × 3 | $1M ARR |
| **Stripe** | Payments | 2.9% + 30¢ | Already have |
| **LinkedIn Sales Nav** | Sales intelligence | $135/user × 2 | $1.5M ARR |
| **Cal.com or Calendly** | Meeting booking | $12-16/user | Already have |

**Total Monthly Cost: $1,500-3,000**

### Advanced (Add at $3M+ ARR)

| Tool | Purpose | Monthly Cost | When to Add |
|------|---------|--------------|-------------|
| **Snowflake/BigQuery** | Data warehouse | $500-2,000 | $3M ARR |
| **HubSpot Service Hub** | Customer success | $450-900 | $3M ARR |
| **Segment** | Event pipeline | $500-1,500 | $3M ARR (if needed) |
| **Gong** (optional) | Sales call intelligence | $1,200/user × 2 | $5M ARR |

**Total with Advanced: $4,150-8,600/mo**

### What You Still DON'T Need ($1-10M)

❌ Salesforce (HubSpot scales to $10M+)
❌ Gainsight (HubSpot Service Hub is enough until $10M)
❌ 6sense/Demandbase (ABM platforms - save for $10M+)

---

## Phase 1 Setup: $0 to $1M ARR

### Week 1: Core Foundation

**PostHog Setup**
```javascript
// Track key product events
posthog.capture('api_key_created', {
  user_id: user.id,
  email: user.email,
  source: 'docs'
});

posthog.capture('first_ocr_success', {
  user_id: user.id,
  pages_processed: 1,
  model: 'gpt-4v'
});

posthog.capture('volume_milestone', {
  user_id: user.id,
  total_pages: 100
});
```

**HubSpot CRM Setup**
- Free tier is enough for $0-1M
- Create custom properties:
  - `first_api_call_date`
  - `total_pages_processed`
  - `pql_score`
  - `activation_status`
- Simple deal pipeline:
  1. Trial
  2. Active Free
  3. PQL
  4. Customer

**Brevo Setup**
- Create 3 email sequences:
  1. Onboarding (Days 0, 1, 3, 7, 14)
  2. Activation nudge (No API call in 48hrs)
  3. Upsell (Approaching limits)

**Integration: PostHog → HubSpot**
```javascript
// Option 1: Webhook (free)
// Send PostHog events to HubSpot via webhook
// Configure in PostHog settings → Webhooks

// Option 2: Zapier (if you want no-code)
// PostHog → Zapier → HubSpot
// Cost: $20-50/mo
```

### Month 2-3: Add Enrichment

**Apollo Integration**
```javascript
// When user signs up, enrich via API
const enrichData = await apollo.enrich({
  email: user.email
});

// Update HubSpot with company data
hubspot.updateContact({
  email: user.email,
  company: enrichData.company,
  employee_count: enrichData.employee_count,
  industry: enrichData.industry
});
```

### Simple Automation Workflows

**Workflow 1: New Signup**
```
Trigger: api_key_created event from PostHog
↓
Actions:
1. Create contact in HubSpot
2. Enrich with Apollo
3. Enroll in Brevo onboarding sequence
4. If company >200 employees: Slack notification to founders
```

**Workflow 2: PQL Detection**
```
Trigger: total_pages_processed > 100 in 7 days
↓
Actions:
1. Tag as PQL in HubSpot
2. Send Slack alert
3. Create task: "Founder: reach out within 24hrs"
```

**Workflow 3: Approaching Limit**
```
Trigger: total_pages > 80 (free tier is 100)
↓
Actions:
1. Send email: "You're approaching your limit"
2. Wait 3 days
3. If not upgraded: Send upsell email
```

---

## Phase 2 Setup: $1M to $10M ARR

### What Changes at $1M

**Upgrade HubSpot to Sales Hub**
- Cost: ~$500-1,500/mo (Professional tier)
- Why: Better sales automation, sequences, reporting
- Features you'll use:
  - Sales sequences (email + task automation)
  - Pipeline reporting
  - Revenue forecasting
  - Team workflows

**Add Sales Tools**

**Apollo for SDRs**
- Cost: $149/user (3 SDRs = $447/mo)
- Use for:
  - Enriching high-PQL accounts
  - Building outbound lists
  - Email/LinkedIn sequences
  - Finding decision-makers

**LinkedIn Sales Navigator**
- Cost: $135/user (2 AEs = $270/mo)
- Use for:
  - Researching target accounts
  - Finding warm intro paths
  - Monitoring company updates
  - InMail for enterprise deals

### Sales Automation Workflows

**High-PQL Routing**
```
Trigger: PQL score > 70 + company_size > 200
↓
Actions:
1. Create deal: "High-Value PQL"
2. Assign to SDR (round-robin)
3. Enroll in Apollo sequence
4. Send Slack alert: #sales channel
5. Pre-populate research (Apollo data)
```

**Meeting Booked**
```
Trigger: Meeting scheduled
↓
Actions:
1. Update deal stage: "Meeting Scheduled"
2. Send prep email to AE with:
   - Product usage data
   - Company info
   - Recent company news
3. Create follow-up task for +1 day after meeting
```

### Customer Success Tools (Add at $3M ARR)

**HubSpot Service Hub**
- Ticketing system
- Customer health scoring
- NPS surveys
- Knowledge base

**Health Score Model**
```javascript
// Auto-calculate in HubSpot workflow
health_score =
  (daily_api_calls ? 20 : 0) +
  (volume_growing ? 15 : 0) +
  (error_rate < 5% ? 10 : 0) +
  (feature_adoption ? 5 : 0) +
  (email_responsive ? 15 : 0) +
  (payment_current ? 10 : 0)

// Total: 0-100
// Green: 80+, Yellow: 50-79, Red: <50
```

---

## Data Architecture

### Phase 1 ($0-1M): Keep It Simple

```
Product (API)
    ↓ events
PostHog
    ↓ webhook
HubSpot + Brevo
```

**No data warehouse needed.** PostHog has built-in analytics.

### Phase 2 ($1-10M): Add Warehouse at $3M+

```
Product (API)
    ↓ events
PostHog
    ↓
Segment (optional)
    ↓ routes to:
├─ HubSpot (CRM)
├─ Brevo (Email)
├─ Snowflake (Data Warehouse)
└─ BI Tool (Metabase/Looker)
```

**When to add warehouse:**
- You need to join product data + CRM data
- Complex cohort analysis
- Custom reports for board/investors
- Multiple data sources to unify

**Cost:** $500-2K/mo (Snowflake + BI tool)

---

## Tech Stack Budget Summary

### Phase 1: $0-1M ARR

**Month 1-3:**
- PostHog: $0 (free tier)
- HubSpot: $0 (free tier)
- Brevo: $25
- Stripe: % of revenue
- **Total: $25/mo**

**Month 4-12:**
- PostHog: $100
- HubSpot: $0
- Brevo: $65
- Apollo: $49
- Stripe: % of revenue
- **Total: $214/mo**

**At $1M ARR:**
- PostHog: $200
- HubSpot: $100 (Starter)
- Brevo: $65
- Apollo: $99
- Cal.com: $12
- **Total: ~$476/mo**

### Phase 2: $1-10M ARR

**At $1M ARR:**
- Core stack: ~$1,500/mo
- Team size: 3-5 people

**At $3M ARR:**
- Core + Advanced: ~$3,000/mo
- Team size: 10-15 people

**At $5M ARR:**
- Full stack: ~$5,000/mo
- Team size: 15-20 people

**At $10M ARR:**
- Complete stack: ~$8,000-10,000/mo
- Team size: 25-35 people

---

## Decision Framework: When to Add Tools

### Before Adding Any Tool, Ask:

1. **What manual process is this replacing?**
   - If no manual process exists, you don't need the tool yet

2. **What's the cost of NOT having this tool?**
   - Lost deals? Slow response time? Bad customer experience?

3. **Can we survive without it for 3 more months?**
   - If yes, wait

4. **Will this tool 2x something important?**
   - 2x conversion rate? 2x team efficiency? 2x customer satisfaction?
   - If not, skip it

### Red Flags (Don't Buy)

❌ "This will be useful later" (buy it later then)
❌ "Everyone uses this tool" (not everyone is at your stage)
❌ "We got a good deal on annual contract" (flexibility > savings early)
❌ "It does so many things" (you need focus, not features)

### Green Lights (Buy Now)

✅ Current process is breaking (manual work can't scale)
✅ Clear ROI (will pay for itself in <3 months)
✅ Blocking revenue (can't close deals without it)
✅ Team is spending >10hrs/week on manual work this tool eliminates

---

## Tool Alternatives by Budget

### Tight Budget ($0-1M ARR)

| Need | Expensive Option | Budget Option |
|------|-----------------|---------------|
| CRM | Salesforce ($150/user) | HubSpot Free → Starter ($50/user) |
| Email | Marketo ($1,000+/mo) | Brevo ($25/mo) |
| Analytics | Amplitude ($500+/mo) | PostHog Free → $200/mo |
| Enrichment | ZoomInfo ($15K/yr) | Apollo ($49/mo) |
| Meetings | Calendly Teams ($16/user) | Cal.com ($12/user or self-host free) |
| Forms | Typeform ($35/mo) | Tally (free) |

### More Budget ($1-10M ARR)

You can afford better tools, but still be intentional:

| Need | Good Enough | Premium |
|------|-------------|---------|
| CRM | HubSpot ($500-1.5K/mo) | Salesforce ($3K+/mo) |
| CS Platform | HubSpot Service Hub ($450/mo) | Gainsight ($2K+/mo) |
| Sales Intel | Apollo ($149/user) | ZoomInfo ($300+/user) |
| Analytics | PostHog ($500/mo) | Amplitude ($2K+/mo) |

**Most companies should stick with "Good Enough" until $10M+ ARR.**

---

## Implementation Checklist

### Phase 1: First 90 Days ($0-1M)

**Week 1:**
- [ ] Set up PostHog, instrument 5 key events
- [ ] Create HubSpot free account
- [ ] Set up Brevo, import first contacts
- [ ] Configure Stripe

**Week 2-4:**
- [ ] Connect PostHog → HubSpot (webhook or Zapier)
- [ ] Build 3 email sequences in Brevo
- [ ] Create PQL scoring model
- [ ] Set up Slack alerts for high PQLs

**Month 2-3:**
- [ ] Add Apollo for enrichment
- [ ] Build automation workflows
- [ ] Create dashboards in PostHog
- [ ] Weekly metrics review cadence

### Phase 2: At $1M ARR

**Month 1:**
- [ ] Upgrade to HubSpot Sales Hub
- [ ] Add Apollo for SDR team
- [ ] Add LinkedIn Sales Navigator for AEs
- [ ] Build sales automation workflows

**Month 2-3:**
- [ ] Hire first SDR, onboard to tools
- [ ] Create sales sequences in Apollo
- [ ] Build pipeline dashboards
- [ ] Implement sales-assisted playbooks

**At $3M ARR:**
- [ ] Add data warehouse (Snowflake/BigQuery)
- [ ] Implement HubSpot Service Hub
- [ ] Build customer health scoring
- [ ] Advanced reporting setup

---

[← Back to Stage B](./03-stage-b-plg-sales.md) | [Next: Revenue Flows →](./05-revenue-flows.md)
