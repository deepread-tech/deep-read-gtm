# Metrics & KPIs - Success Measurement Framework

## Overview

Track only what matters at each stage. Don't measure everything - measure what drives decisions.

---

## North Star Metric (Both Phases)

**Weekly Active API Keys with 10+ Successful Calls**

**Why:**
- Measures real value delivery (not vanity signups)
- Predicts revenue before it happens
- Simple to understand and act on

**Target Growth:**
- $0-1M ARR: 10-20% week-over-week
- $1-10M ARR: 5-10% week-over-week

---

## Phase 1: $0 to $1M ARR (5 Metrics That Matter)

### 1. Activation Rate: API Key → First Success

**Definition:** % of users who make ≥1 successful API call after creating key

**Target:** ≥40%

**Why it matters:** Low activation = broken onboarding or product

**How to measure:** PostHog funnel

**How to improve:**
- Better quick-start guide
- Simpler code samples
- Proactive support for errors
- Welcome email with working example

---

### 2. PQL Conversion Rate: PQL → Paid

**Definition:** % of Product Qualified Leads who become paying customers

**PQL Definition:** User who processed >100 pages in 7 days

**Target:** ≥8%

**Why it matters:** This is how you make money in self-serve

**How to measure:** HubSpot deal pipeline

**How to improve:**
- Better upgrade prompts (in-app + email)
- Pricing page clarity
- Remove friction in checkout
- Founder outreach to high-value PQLs

---

### 3. MRR Growth Rate

**Definition:** Month-over-month recurring revenue growth

**Target:** 15-20% per month

**Why it matters:** Primary measure of progress to $1M

**How to measure:** Stripe dashboard

**Calculation:**
```
MRR Growth % = ((This Month MRR - Last Month MRR) / Last Month MRR) × 100
```

---

### 4. Self-Serve CAC Payback

**Definition:** Months to recover cost of acquiring customer

**Target:** <3 months

**Why it matters:** Unit economics must work before scaling

**How to measure:**
```
CAC Payback = CAC / ARPU

Example:
- CAC: $100 (organic content)
- ARPU: $150/month
- Payback: 0.67 months (20 days) ✅

Example 2:
- CAC: $500 (paid ads)
- ARPU: $200/month
- Payback: 2.5 months ✅
```

**How to improve:**
- Lower CAC (better SEO, word-of-mouth)
- Increase ARPU (better pricing, upsells)

---

### 5. Weekly Retention Cohorts

**Definition:** % of users who return each week after signup

**Target:**
- Week 1: >60%
- Week 4: >40%
- Week 12: >30%

**Why it matters:** Retention curve must flatten (habit formation)

**How to measure:** PostHog retention chart

**Good vs Bad:**
```
Good retention (flattens):
Week 0: 100%
Week 1: 60%
Week 2: 50%
Week 4: 40%
Week 8: 35%
Week 12: 30% → Stabilizes here

Bad retention (keeps dropping):
Week 0: 100%
Week 1: 40%
Week 2: 25%
Week 4: 15%
Week 8: 8%
Week 12: 3% → No product-market fit
```

---

## Phase 1: What NOT to Track

❌ Total signups (vanity metric)
❌ Website traffic (unless converting)
❌ Social media followers
❌ Email open rates (focus on conversions)
❌ Sales pipeline (you don't have sales yet)
❌ NPS (too early, not enough customers)

**Focus on:** Activation, Conversion, Revenue, Retention

---

## Phase 1: Dashboard Setup

### Weekly Review (Every Monday)

**5-Minute Dashboard:**
1. North Star: Weekly active users (trend)
2. Activation rate (this week)
3. New paying customers (this week)
4. MRR (current + growth %)
5. Top 3 PQLs (who to reach out to)

**Tool:** PostHog + HubSpot

### Monthly Review (First of Month)

**15-Minute Review:**
1. All 5 core metrics (vs. targets)
2. Cohort retention (is it getting better?)
3. CAC by channel (what's working?)
4. Churn (who left and why?)
5. Pipeline: How many PQLs? Conversion rate?

---

## Phase 2: $1M to $10M ARR (8 Metrics That Matter)

### Core 5 from Phase 1 (Still Important)
1. Activation rate (≥40%)
2. PQL → Paid conversion (≥10% - higher with sales)
3. MRR/ARR growth (15-25% QoQ)
4. CAC payback (<12 months blended)
5. Weekly retention cohorts

### Plus 3 New Metrics for Sales & Expansion

---

### 6. Sales Win Rate

**Definition:** % of qualified sales opportunities that close

**Target:** >25%

**Why it matters:** Validates sales process is working

**How to measure:** HubSpot sales pipeline

**Stages:**
```
Qualified Opp → Demo → Proposal → Closed-Won

Calculate:
Closed-Won / Total Qualified Opps = Win Rate

Example:
- 40 qualified opps
- 10 closed-won
- Win rate: 25% ✅
```

**How to improve:**
- Better qualification (only pursue good fits)
- Stronger discovery calls
- Clearer value prop
- Competitive positioning

---

### 7. Net Dollar Retention (NDR)

**Definition:** Revenue retained + expanded from a cohort over 12 months

**Target:** >110% (ideal: >120%)

**Why it matters:** Shows if customers grow with you or churn

**How to measure:**
```
NDR = (Starting ARR - Churned ARR + Expansion ARR) / Starting ARR × 100

Example (Good):
Jan 2024 cohort: $100K ARR
Jan 2025:
  - $10K churned
  - $30K expansion
  - Net: $120K

NDR = $120K / $100K = 120% ✅

Example (Bad):
Jan 2024 cohort: $100K ARR
Jan 2025:
  - $25K churned
  - $10K expansion
  - Net: $85K

NDR = $85K / $100K = 85% ❌ (churn problem)
```

**How to improve:**
- Reduce churn (better onboarding, CS touch)
- Increase expansion (upsells, usage growth)

---

### 8. Magic Number (Sales Efficiency)

**Definition:** How efficiently you turn S&M spend into ARR

**Target:** >0.75 (ideal: >1.0)

**Why it matters:** Tells you if you can afford to scale sales

**How to measure:**
```
Magic Number = Net New ARR This Quarter / S&M Spend Last Quarter

Example (Good):
- Q2 new ARR: $500K
- Q1 S&M spend: $400K
- Magic Number: 1.25 ✅ (Scale aggressively!)

Example (Okay):
- Q2 new ARR: $300K
- Q1 S&M spend: $400K
- Magic Number: 0.75 (Acceptable, optimize)

Example (Bad):
- Q2 new ARR: $200K
- Q1 S&M spend: $500K
- Magic Number: 0.4 ❌ (Fix sales or product)
```

**What to do:**
- <0.5: Stop scaling, fix fundamentals
- 0.5-0.75: Optimize before scaling
- 0.75-1.0: Scale cautiously
- >1.0: Scale aggressively

---

## Phase 2: What NOT to Track

❌ Vanity metrics (total users, page views)
❌ 50 different KPIs (pick 8, stick to them)
❌ Metrics you can't act on
❌ Metrics that don't connect to revenue

---

## Phase 2: Dashboard Setup

### Daily Review (5 min)

**Sales Team:**
- New PQLs today
- Meetings booked this week
- Deals closing this month

**CS Team:**
- Customer health changes (red flags)
- Churn risk alerts
- Expansion opportunities

### Weekly Review (30 min)

**Exec Team Reviews:**
1. North Star (weekly active users)
2. ARR + growth rate
3. Sales pipeline (value + coverage)
4. Win rate
5. NDR
6. Magic Number
7. CAC payback
8. Activation rate

### Monthly Review (1 hour)

**Full Team + Board:**
- All 8 core metrics (vs. targets)
- Cohort analysis (retention trends)
- Win/loss analysis (why deals close/don't)
- Channel performance (what's working)
- Forecast (next 3 months)

---

## Metric Definitions & Calculations

### Revenue Metrics

**MRR (Monthly Recurring Revenue):**
```
Sum of all active subscriptions (monthly value)
```

**ARR (Annual Recurring Revenue):**
```
MRR × 12
or
Sum of all annual contracts
```

**Net New ARR:**
```
New ARR + Expansion ARR - Churned ARR - Contraction ARR
```

### Customer Acquisition

**CAC (Customer Acquisition Cost):**
```
Total Sales & Marketing Spend / New Customers Acquired

Phase 1 (Organic): $50-100
Phase 1 (Paid): $200-500
Phase 2 (Self-serve): $200-500
Phase 2 (Sales-assisted): $1K-3K
```

**LTV (Lifetime Value):**
```
ARPU × Gross Margin % × (1 / Monthly Churn Rate)

Example:
ARPU: $200
Gross Margin: 80%
Churn: 5%/month

LTV = $200 × 0.80 × 20 = $3,200
```

**LTV:CAC Ratio:**
```
Target: >3:1

Example:
LTV: $3,200
CAC: $500
Ratio: 6.4:1 ✅
```

### Conversion Rates

**Activation Rate:**
```
(Users with ≥1 successful API call / Total API keys created) × 100
Target: ≥40%
```

**PQL Rate:**
```
(Users who processed >100 pages / Total users) × 100
```

**PQL → Paid:**
```
(Paid customers / PQLs) × 100
Target Phase 1: ≥8%
Target Phase 2: ≥10% (with sales help)
```

### Retention & Churn

**Logo Churn (Monthly):**
```
(Customers Lost / Total Customers at Start) × 100
Target: <5% per month
```

**Revenue Churn (Monthly):**
```
(MRR Lost / Total MRR at Start) × 100
Target: <5% per month
```

**Gross Dollar Retention:**
```
(Retained MRR / Starting MRR) × 100
Target: >85%
Excludes expansion, only retention
```

**Net Dollar Retention:**
```
((Retained MRR + Expansion MRR) / Starting MRR) × 100
Target Phase 2: >110%
```

---

## Metric Red Flags

### Phase 1 Red Flags

🚨 **Activation rate <30%**
- Action: Fix onboarding immediately
- Likely cause: Product too complex, docs unclear

🚨 **PQL → Paid <5%**
- Action: Improve pricing page, upgrade flow
- Likely cause: Pricing unclear or too expensive

🚨 **MRR growth <10%/month**
- Action: Check activation AND conversion
- Likely cause: Top of funnel or activation broken

🚨 **Retention drops continuously (doesn't flatten)**
- Action: Talk to churned users, fix core value
- Likely cause: No product-market fit

🚨 **CAC payback >6 months**
- Action: Reduce CAC or increase ARPU
- Likely cause: Wrong channels or pricing too low

### Phase 2 Red Flags

🚨 **Win rate <20%**
- Action: Better qualification or sales training
- Likely cause: Chasing wrong deals or weak positioning

🚨 **NDR <100%**
- Action: Stop new sales, fix churn first
- Likely cause: Bad onboarding or product gaps

🚨 **Magic Number <0.5**
- Action: Stop scaling, fix unit economics
- Likely cause: Sales too expensive or product not ready

🚨 **Sales cycle >90 days (mid-market)**
- Action: Simplify sales process or pricing
- Likely cause: Too much complexity or wrong buyers

---

## Metrics Review Cadence

### Phase 1 ($0-1M ARR)

**Daily:** Check Slack alerts for high PQLs

**Weekly (15 min):**
- 5 core metrics
- Top PQLs to reach out to

**Monthly (30 min):**
- All metrics vs. targets
- Cohort analysis
- Channel performance

**Quarterly (1 hour):**
- Deep dive on what's working/not
- Update strategy based on data

### Phase 2 ($1-10M ARR)

**Daily:** Sales + CS teams check their metrics

**Weekly (30 min):**
- Exec team: All 8 metrics
- Pipeline review
- Blockers discussion

**Monthly (1-2 hours):**
- Board-level review
- Win/loss analysis
- Forecast next quarter

**Quarterly (half day):**
- Strategy review
- Goal setting (OKRs)
- Budget allocation

---

## Metrics Integrity: Don't Game the System

### Bad Practices

❌ Lowering PQL threshold to hit "more PQLs" target
❌ Counting low-quality leads as "MQLs"
❌ Hiding churned revenue in ARR reporting
❌ Cherry-picking time periods to look good
❌ Changing definitions mid-quarter

### Good Practices

✅ Keep definitions consistent
✅ Report both good and bad news
✅ Track trends, not just point-in-time
✅ Share context (why did metric change?)
✅ Focus on actions, not excuses

---

## Simple Tracking Setup

### Phase 1: Tools You Need

**PostHog:**
- Activation funnel
- Retention cohorts
- Feature adoption

**HubSpot:**
- Deals (PQL → Paid funnel)
- Contact properties (PQL score)

**Stripe:**
- MRR dashboard
- Churn reports

**Google Sheet:**
- Weekly snapshot of 5 core metrics
- Month-over-month trends

**Total cost:** $0-100/mo

### Phase 2: Add These

**HubSpot Sales Hub:**
- Pipeline reports
- Win/loss tracking
- Sales cycle analysis

**Snowflake + Metabase** (optional at $3M+):
- Join product + revenue data
- Custom reports

---

## Example: Weekly Metrics Email

**Subject: DeepRead Metrics - Week of Dec 21**

**North Star:**
- Weekly active users: 247 (↑12% vs last week)

**Phase 1 Core 5:**
1. Activation rate: 43% (target: ≥40%) ✅
2. PQL → Paid: 9.2% (target: ≥8%) ✅
3. MRR: $47K (↑18% MoM) ✅
4. CAC payback: 2.1 months (target: <3) ✅
5. Week 4 retention: 44% (target: >40%) ✅

**🎯 What's Working:**
- Activation rate up (new quick-start guide working)
- MRR growth strong

**⚠️ What Needs Attention:**
- Week 1 retention dropped to 55% (was 62% last month)
- Need to investigate: recent cohort quality?

**🔥 Top 3 PQLs to Contact:**
1. Acme Corp - 8,200 pages, Series B funded
2. Beta Inc - 5,500 pages, 3 users same domain
3. Gamma LLC - 4,100 pages, enterprise email

**Action Items:**
- [ ] Founder: Reach out to top 3 PQLs
- [ ] Product: Investigate Week 1 retention drop
- [ ] Marketing: Double down on content (driving good activation)

---

[← Back to Revenue Flows](./05-revenue-flows.md) | [Next: Playbooks →](./07-playbooks/)
