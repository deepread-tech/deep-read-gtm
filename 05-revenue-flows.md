# Revenue Flows - Product-to-Revenue Automation

## Overview

Product signals should automatically trigger revenue actions. No manual work, no lag.

---

## Phase 1: $0 to $1M ARR (Self-Serve Flow)

### The Simple Path: Product → Revenue

```
Visitor → Docs → API Key → First Success → Recurring Use → Upgrade → $$$
```

### Detailed Flow

```
DISCOVERY
│
│ Visitor arrives (SEO, HN, word-of-mouth)
│ Lands on: docs or use-case tutorial
↓
[Track: page view, source]

ACTIVATION
│
│ User clicks: "Get API Key"
│ Form: Email only (no friction)
↓
[Event: api_key_created]
[Action: Create contact in HubSpot]
[Action: Enroll in Brevo: Welcome email]
│
│ Email: API key + quick-start code sample
│ User makes first API call
↓
[Event: first_ocr_success]
[Action: Update HubSpot: activation_status = "first_success"]
[Action: Send congrats email]

HABIT FORMATION
│
│ User returns 3+ days/week
│ Processes more documents
↓
[Event: recurring_usage]
[Action: Tag as "active_user"]
[Action: Calculate PQL score]
│
│ If PQL score >50:
│   → Tag "product_qualified_lead"
│   → Slack alert to founder
↓

MONETIZATION
│
│ User hits 80% of free tier (80 pages)
↓
[Trigger: usage_threshold]
[Action: Email: "You're approaching limit"]
[Action: Show in-app banner]
│
│ Wait 3 days
│ User still not upgraded
↓
[Action: Email: "Upgrade to keep processing"]
[Action: Include pricing calculator]
│
│ User clicks "Upgrade"
│ Stripe checkout
↓
[Event: subscription_created]
[Action: Create deal in HubSpot: "Customer"]
[Action: Send welcome email for paid users]
[Action: Slack: "New customer! 🎉"]

✅ REVENUE GENERATED
```

### Key Conversion Points

| Stage | Conversion Target | Avg Time |
|-------|------------------|----------|
| Visitor → API key | 5-10% | N/A |
| API key → First success | **≥40%** | <24 hours |
| First success → Recurring use | 60-70% | 7 days |
| Recurring use → PQL | 40-50% | 14 days |
| PQL → Paid | **≥8%** | 30 days |

### Automation Triggers (Phase 1)

**Trigger 1: api_key_created**
```
Actions:
1. Create contact in HubSpot
2. Set activation_status = "api_key_created"
3. Enroll in Brevo: "Onboarding Day 0"
4. If @enterprise-domain.com: Tag "high_priority" + Slack alert
```

**Trigger 2: first_ocr_success**
```
Actions:
1. Set activation_status = "first_success"
2. Set first_api_call_date = today
3. Send email: "Nice! Here's what to try next"
```

**Trigger 3: recurring_usage (3+ calls in 7 days)**
```
Actions:
1. Set activation_status = "recurring_user"
2. Calculate PQL score
3. If score >50: Tag "pql" + create task for founder
```

**Trigger 4: usage >80 pages (approaching limit)**
```
Actions:
1. Email: "You're approaching your 100 page limit"
2. Show in-app upgrade banner
3. Wait 3 days
4. If not upgraded: Email with pricing + ROI calculator
```

**Trigger 5: subscription_created**
```
Actions:
1. Create deal: "Self-Serve Customer" (Closed-Won)
2. Set lifecycle_stage = "customer"
3. Send welcome email (priority support info)
4. Slack: "New customer! $X MRR"
```

### Phase 1: Email Sequences (Brevo)

**Onboarding Sequence**
```
Day 0: Welcome + API key + quick start (5 min setup)
Day 1: "Hit any issues?" (surface blockers)
Day 3: Use case examples (inspire adoption)
Day 7: Power features (education)
Day 14: Customer story (social proof)
```

**Activation Nudge** (no API call in 48hrs)
```
Subject: "Stuck? Here's a working code sample"
Content: Copy-paste Python/Node.js example
CTA: "Get this working in 2 minutes"
```

**Upsell Sequence** (approaching limits)
```
Email 1 (at 80 pages): "You're crushing it! Here's what's next"
Email 2 (+3 days): Pricing calculator + "Save X hours/month"
Email 3 (+7 days): "Upgrade now" (urgency)
```

---

## Phase 2: $1M to $10M ARR (PLG + Sales-Assisted)

### Two Parallel Flows

**70% of customers:** Self-serve (same as Phase 1)
**30% of customers:** Sales-assisted (high-value accounts)

### Sales-Assisted Flow

```
HIGH-SIGNAL DETECTION
│
│ User exhibits high-value behavior:
│  - Processes >5K pages in one day, OR
│  - 3+ users from same domain, OR
│  - Company >200 employees
↓
[Event: high_volume_usage]
[Trigger: PQL score calculation]
│
│ PQL score >70
↓
[Actions]
1. Create deal: "High-Value PQL"
2. Assign to SDR (round-robin)
3. Call Apollo API: Enrich contact
4. Slack alert: #sales channel
5. Add to Apollo outbound sequence

ENRICHMENT
│
│ Apollo returns:
│  - Full name, job title
│  - Company size, industry, funding
│  - LinkedIn profile
│  - Recent company news
↓
[Action: Update HubSpot with enrichment data]
│
│ SDR receives task:
│ "Outreach to [Name] at [Company] - 8K pages yesterday"

SDR OUTREACH
│
│ Day 0: Personalized email
│ "I noticed you processed X pages... worth a chat?"
↓
│ Day 2: LinkedIn connection request
↓
│ Day 4: Follow-up email + case study
↓
│ Day 7: LinkedIn message (if connected)
↓
│ Day 10: Breakup email
│ "Should I close your file?"

USER REPLIES
│
│ "Yes, let's chat"
↓
[Action: SDR sends calendar link]
[Action: Update deal stage: "Meeting Scheduled"]
[Action: Notify AE with prep doc]

DISCOVERY & DEMO
│
│ AE conducts discovery call:
│  - Current setup, pain points
│  - Volume projections
│  - Technical requirements
↓
│ AE gives demo:
│  - Focused on their use case
│  - Live API demo
│  - ROI calculation
↓
[Update: Deal stage → "Demo Complete"]

PROPOSAL
│
│ AE sends proposal:
│  - Pricing: $10K-100K/year
│  - SLA: 99.9% uptime
│  - Security docs (SOC 2, GDPR)
↓
[Update: Deal stage → "Proposal Sent"]
│
│ Negotiation (2-4 weeks)
│ Legal review, procurement
↓

CONTRACT SIGNED
↓
[Event: contract_signed]
[Actions]
1. Update deal: Closed-Won
2. Assign CSM
3. Send onboarding email
4. Slack: "Enterprise deal! $X ACV 🚀"

✅ REVENUE GENERATED
```

### Key Conversion Points (Phase 2)

| Stage | Conversion Target | Avg Time |
|-------|------------------|----------|
| PQL → Contacted | 100% (automated) | <24 hours |
| Contacted → Reply | 15-25% | 3-7 days |
| Reply → Meeting | 60%+ | 3-7 days |
| Demo → Proposal | 60-70% | <1 week |
| Proposal → Closed-Won | **20-30%** | 2-8 weeks |

### Automation Triggers (Phase 2)

**Trigger 1: High-PQL Detection**
```
Condition: PQL score >70 AND company_size >200

Actions:
1. Create deal: "High-Value PQL"
2. Enrich via Apollo API
3. Assign to SDR (round-robin)
4. Add to Apollo sequence: "High-PQL Outreach"
5. Slack: #sales channel with context
6. Pre-populate research doc for SDR
```

**Trigger 2: Meeting Booked**
```
Actions:
1. Update deal stage: "Meeting Scheduled"
2. Send prep email to AE:
   - Product usage stats
   - Company info (from Apollo)
   - Recent news (from LinkedIn)
3. Create follow-up task for +1 day after meeting
```

**Trigger 3: Demo Completed**
```
Actions:
1. Update deal stage: "Demo Complete"
2. Send follow-up email:
   - Thank you
   - Demo recording link
   - Next steps
3. Create task: "Send proposal within 48hrs"
```

**Trigger 4: Proposal Sent**
```
Actions:
1. Update deal stage: "Proposal Sent"
2. Set reminder: Follow up in 3 days
3. Track proposal opens (if using DocSend)
4. Alert AE if no engagement in 5 days
```

**Trigger 5: Contract Signed**
```
Actions:
1. Update deal: Closed-Won
2. Create customer record
3. Assign CSM from round-robin
4. Send to ops team: Provisioning checklist
5. Enroll in "Enterprise Onboarding" sequence
6. Slack + email: Team celebration
```

### SDR Email Sequence (Apollo/HubSpot)

**Day 0: Initial Outreach**
```
Subject: Quick question about [Company]'s DeepRead usage

Hi [Name],

I noticed your team at [Company] processed [X] pages with DeepRead
over the last few days.

Most teams at that volume typically need [feature]. Quick question:
are you hitting any bottlenecks as you scale?

Worth a 15-min chat?

Best,
[SDR Name]

P.S. [Personal touch: funding news, LinkedIn post, etc.]
```

**Day 4: Follow-up**
```
Subject: Re: Quick question about [Company]'s DeepRead usage

Hi [Name],

Wanted to share how [Similar Company] handles [X volume] with DeepRead.

Attached a quick case study. Key insight: they saved ~200 eng hours
by using [feature] vs. building in-house.

If you're curious, happy to do a quick screen share.

Best,
[SDR Name]
```

**Day 10: Breakup**
```
Subject: Closing your file

Hi [Name],

I haven't heard back, so assuming this isn't a priority right now.
No worries!

I'll close your file, but if you ever want to chat about scaling
your doc processing, just reply.

Best of luck!

[SDR Name]

P.S. If I'm reaching out to the wrong person, who should I contact?
```

---

## Expansion & Upsell (Phase 2)

### Expansion Triggers

| Trigger | Signal | Action |
|---------|--------|--------|
| **Usage Growth** | Volume +50% MoM | CS email: "Let's optimize for growth" |
| **Approaching Limits** | >90% of plan | Automated upgrade prompt |
| **Team Growth** | +3 users in 30 days | CS call: Team plan upsell |
| **Feature Interest** | Using enterprise features on free tier | Sales call |
| **Annual Renewal** | 30 days before renewal | CS sends renewal + upsell |

### Example: Usage Growth Flow

```
[Event: monthly_volume_increase]
  (Previous: 10K pages, Current: 18K pages, Growth: 80%)
↓
[Trigger: HubSpot workflow "Expansion Opportunity"]
  1. Tag: "expansion_opportunity"
  2. Create task for CSM
  3. Update health score: +10pts
↓
CSM sends email:
  "Congrats on 80% growth! Let's chat about optimizing your setup
   and making sure you're on the right plan."
↓
CS call:
  1. Celebrate success
  2. Review usage, pain points
  3. Recommend upgrade or annual commit
  4. Offer: 15% discount for annual prepay
↓
Customer agrees → Upgrade subscription
↓
[Event: subscription_upgraded]
↓
✅ EXPANSION REVENUE
```

---

## Churn Prevention (Both Phases)

### Re-Engagement Triggers

| Trigger | Action |
|---------|--------|
| 14 days no activity | Email: "We miss you! What's new?" |
| 30 days no activity | Email: "100 free pages to come back" |
| High error rate (>30%) | Support outreach (prevent churn) |
| User clicks "Cancel" | Save modal with offer |

### Save Flow: User Clicks Cancel

```
User clicks "Cancel subscription"
↓
[Show modal]
  "Before you go, can we help?"

  Options:
  - "I have a question" → Support chat
  - "Too expensive" → 20% discount offer
  - "Don't use enough" → Suggest lower tier
  - "Just canceling" → Proceed
↓
If selects "Too expensive":
  Modal: "How about 20% off for 3 months?"
  [Accept] [No thanks]
↓
If accepts → Apply discount, retain customer
If declines → CS exit interview call
↓
Log feedback → Product improvements
```

---

## Simple Automation Setup

### Phase 1: Minimal Stack

**Tools:**
- PostHog → HubSpot (webhook)
- HubSpot → Brevo (native integration)

**Setup Time:** 1 day

**Workflows to Build:**
1. New signup → Welcome email
2. PQL detection → Founder alert
3. Approaching limit → Upsell email

### Phase 2: Add Sales Automation

**Additional Tools:**
- Apollo (enrichment + sequences)
- LinkedIn Sales Navigator
- HubSpot Sales Hub

**Setup Time:** 1 week

**Workflows to Add:**
1. High-PQL → SDR assignment
2. Meeting booked → AE prep
3. Proposal sent → Follow-up reminders
4. Contract signed → CSM onboarding

---

## Metrics to Track

### Phase 1: Self-Serve Flow Metrics

**Funnel:**
- Visitor → API key: 5-10%
- API key → First success: ≥40%
- First success → Recurring: 60-70%
- PQL → Paid: ≥8%

**Speed:**
- Time to first API call: <24hrs
- Time to PQL: ~14 days
- Time to paid: ~30 days

### Phase 2: Sales Flow Metrics

**Funnel:**
- PQL → Contacted: 100%
- Contacted → Reply: 15-25%
- Reply → Meeting: 60%+
- Demo → Proposal: 60-70%
- Proposal → Won: 20-30%

**Speed:**
- PQL → First contact: <24hrs
- Reply → Meeting: 3-7 days
- Sales cycle: 30-60 days (mid-market), 60-90 days (enterprise)

---

## Common Automation Mistakes

### Don't:
❌ Over-automate early (keep it manual until you see patterns)
❌ Spam users with too many emails
❌ Auto-assign sales before enrichment completes
❌ Use generic templates without personalization
❌ Forget to test workflows before going live

### Do:
✅ Start with 3-5 core workflows, add more later
✅ Test emails yourself first
✅ Use Slack alerts for high-value events
✅ Review workflow performance weekly
✅ Talk to customers (automation ≠ ignore them)

---

## Quick Start Checklist

### Phase 1: First Week

- [ ] Connect PostHog → HubSpot (webhook)
- [ ] Build 3 email sequences in Brevo
- [ ] Set up PQL scoring in HubSpot
- [ ] Create Slack alert for high PQLs
- [ ] Test all workflows with dummy data

### Phase 2: At $1M ARR

- [ ] Upgrade to HubSpot Sales Hub
- [ ] Add Apollo integration
- [ ] Build SDR outbound sequences
- [ ] Create sales prep automation
- [ ] Train team on new workflows

---

[← Back to Tech Stack](./04-tech-stack.md) | [Next: Metrics & KPIs →](./06-metrics-kpis.md)
