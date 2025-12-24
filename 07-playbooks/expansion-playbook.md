# Expansion Playbook

## When to Use This Playbook

**Trigger:** Existing customer shows expansion signals

**Goal:** Grow revenue from existing customers (target: 30-40% of new ARR from expansion)

**Owner:** Customer Success Manager (with AE support for large expansions)

---

## Expansion Signals to Monitor

### Product Signals (Automated)

| Signal | Threshold | Action |
|--------|-----------|--------|
| **Volume Growth** | >50% MoM increase in pages processed | Proactive outreach: Upgrade recommendation |
| **Approaching Limits** | >90% of plan limit | Upgrade nudge (email + in-app) |
| **Feature Usage** | Using advanced features on low tier | Upsell to higher tier |
| **Team Growth** | 3+ new users added in 30 days | Team plan upsell |
| **Multiple Use Cases** | Processing different document types | Expand contract scope |

### Engagement Signals

| Signal | Meaning | Action |
|--------|---------|--------|
| **High NPS Score** | >9 rating on recent survey | Ask for referral + expansion conversation |
| **Positive Feedback** | Praise in support tickets or calls | Prime for upsell |
| **Frequent Contact** | Weekly engagement with CS | Strong relationship, good time to upsell |

### Business Signals (Research)

| Signal | Source | Action |
|--------|--------|--------|
| **Funding Round** | LinkedIn, TechCrunch | Congrats email + scale conversation |
| **Headcount Growth** | LinkedIn job postings | More users = more volume |
| **Product Launch** | Company blog, Twitter | New use cases likely |

---

## Expansion Types & Playbooks

### Type 1: Volume Expansion (Most Common)

**Signal:** Customer processing more documents month-over-month

**Opportunity:** Upgrade to higher tier or increase committed volume

---

#### Playbook: Volume-Based Upgrade

**Step 1: Detect Signal (Automated)**
```
Product event: monthly_volume_increase >50%
  → Tag customer: "expansion_opportunity_volume"
  → Alert CSM via Slack
```

**Step 2: Research (5 minutes)**
- Review volume trend (3-month chart)
- Current plan tier and limits
- Pricing: What would they pay at next tier?
- ROI: Cost per page at current vs. upgraded tier

**Step 3: Outreach (Email)**

```
Subject: Congrats on your growth! 📈

Hi [Name],

I noticed you've been processing a lot more documents with DeepRead
lately - [X]K pages last month, up from [Y]K the month before. That's
awesome!

Quick heads up: you're approaching your plan limit ([Z]K pages/month).

Rather than hitting overages, it might make sense to upgrade to the
[Next Tier] plan:
  - Current: $[A]/mo ([B] pages included, $[C] per additional page)
  - Upgraded: $[D]/mo ([E] pages included, $[F] per additional page)

At your current trajectory, you'd save ~$[G]/month by upgrading.

Want to hop on a quick call to discuss? Or I can just send the upgrade
link if you want to do it yourself.

Let me know!

Best,
[Your Name]
```

**Step 4: Follow-Up**

**If they reply positively:**
- Send upgrade link (self-serve) OR
- Process upgrade manually (for custom pricing)
- Confirm upgrade: "You're all set! New limits are live."

**If they hesitate:**
- Offer discount: "I can do 10% off if you commit to annual"
- Offer flexibility: "We can start with monthly and switch to annual later"

**If no reply after 3 days:**
- Send reminder: "Following up - did you have any questions about the upgrade?"

---

### Type 2: Feature Upsell

**Signal:** Customer using basic features, could benefit from advanced

**Opportunity:** Upsell to plan with advanced features

---

#### Playbook: Feature-Based Upgrade

**Step 1: Identify Gap**

Review customer usage:
- What features are they using? (basic OCR only?)
- What features would help them? (batch processing, custom models, priority support)

**Common Scenarios:**

**Scenario A: High Volume, No Batch Processing**
- They're making individual API calls for each document
- Batch API would be 2x faster + cheaper

**Scenario B: Using Standard Models, Could Use Custom**
- Accuracy is okay (90-95%) but could be better
- Custom model tuning would get them to 98%+

**Scenario C: Growing Team, Basic Support**
- They have questions but wait 24hrs for support
- Priority support (4hr response) would help

**Step 2: Outreach (Educational)**

```
Subject: Quick tip: Speed up your processing by 2x

Hi [Name],

I was reviewing your DeepRead setup and noticed you're processing
documents one-by-one via the standard API.

For teams processing [X] pages/day like you, the Batch API is usually
2x faster and ~30% cheaper per page.

Example:
  - Current: 1,000 docs × 2 sec each = 33 minutes
  - Batch: 1,000 docs in 8 minutes

Worth trying? I can send you a code sample, or we can do a quick
15-min screen share to set it up.

(Note: Batch API is included in the [Higher Tier] plan - $[price]/mo)

Let me know!

Best,
[Your Name]
```

**Step 3: Demo (If Interested)**

- Show feature in action (live demo or Loom video)
- Quantify benefit: Time saved, cost saved, accuracy improvement
- Make upgrade easy: "Click here to upgrade, feature is live immediately"

**Step 4: Close**

- If they upgrade: Onboard them to the new feature
- If they don't: Add to nurture sequence (send case studies, remind in 30 days)

---

### Type 3: Seat/User Expansion

**Signal:** Multiple users from same company using DeepRead

**Opportunity:** Upgrade to team plan with multi-user management

---

#### Playbook: Team Plan Upsell

**Step 1: Detect Signal**
```
Product event: 3+ API keys from same company domain
  → Tag: "team_expansion_opportunity"
  → Alert CSM
```

**Step 2: Outreach**

```
Subject: Time for a team plan?

Hi [Name],

I noticed you now have [X] people at [Company] using DeepRead - that's
great to see adoption growing!

You're currently on individual plans, which is fine, but you might save
money (and get better features) with a Team plan:

Individual Plans:
  - [X] users × $[Y]/mo = $[Z]/mo total
  - Separate API keys, no centralized billing

Team Plan:
  - $[A]/mo for up to [B] users
  - Centralized billing and user management
  - Shared usage pool (more flexible)
  - Priority support

You'd save ~$[C]/month + get better features.

Want to switch? I can migrate you over in <24hrs.

Let me know!

Best,
[Your Name]
```

**Step 3: Migration**

- If they agree: Handle migration (move all users to team account)
- Ensure no downtime (API keys stay active)
- Send welcome email to all team members

---

### Type 4: New Use Case Expansion

**Signal:** Customer mentions new project or document type in conversation

**Opportunity:** Expand contract scope, add volume, or cross-sell

---

#### Playbook: Use Case Expansion

**Step 1: Listen for Signals**

During regular check-ins, ask:
- "Are there other document types you're thinking about processing?"
- "Any new projects coming up that might need document processing?"
- "Other teams at [Company] who could benefit from DeepRead?"

**Step 2: Explore Opportunity**

If they mention a new use case:
- "Tell me more about that. What documents? What data do you need to extract?"
- "What's the volume?"
- "What's your timeline?"

**Step 3: Position Solution**

```
"Okay, so you're looking to process [new document type] at [volume].
 DeepRead handles that really well - we have several customers doing
 similar things.

Let me show you: [demo or case study]

In terms of adding this to your account:
  - Option 1: Add to your current plan (just increase volume commitment)
  - Option 2: Separate contract for [new team/department]

Which makes more sense for you?"
```

**Step 4: Expand Contract**

- If they agree: Create amendment to contract (add volume/use case)
- Update account in HubSpot (new ARR, expansion date)
- Celebrate: "Awesome! I'll get this set up for you."

---

### Type 5: Annual Commitment (from Monthly)

**Signal:** Customer has been on monthly plan for 6+ months, stable usage

**Opportunity:** Convert to annual (more predictable revenue, lower churn risk)

---

#### Playbook: Monthly → Annual Conversion

**Step 1: Timing**

Best time to propose annual:
- After 6 months of consistent usage
- Around renewal time (before monthly charge processes)
- After positive QBR or NPS survey

**Step 2: Pitch**

```
Subject: Save [X]% with annual plan

Hi [Name],

You've been using DeepRead for [X] months now - thanks for being a great
customer!

I wanted to mention: you're currently on a monthly plan ($[Y]/mo), but
most customers at your stage switch to annual to save money.

Here's the math:
  - Monthly: $[Y]/mo × 12 = $[Z]/year
  - Annual: $[A]/year (save $[B] = [C]% discount)

Plus, you get:
  - Price lock (no increases for 12 months)
  - Quarterly business reviews (we don't do these for monthly)
  - [Other perks: dedicated CSM, priority roadmap input, etc.]

Want to switch? I can apply the discount today and your next charge
will be the annual rate.

Let me know!

Best,
[Your Name]
```

**Step 3: Address Objections**

**"What if we don't use it for the full year?"**
- "Totally fair concern. Based on your usage ([X] pages/month for [Y] months),
   you're on a great trajectory. But I understand. How about this: let's do a
   6-month commit instead? You still save [Z]%, just less than the annual discount."

**"We might need to scale down"**
- "If your usage decreases, we can adjust the contract at renewal. But given your
   growth trend, I'd be surprised if you scale down. Want to start with a lower
   annual commitment and add on if you grow?"

**Step 4: Close**

- If they commit: Process annual contract
- If they don't: Revisit in 3 months

---

## Expansion Pricing & Negotiation

### Discounting Guidelines

**When to Discount:**
- Annual commitment (10-20% off)
- Volume commitment (>2x current usage)
- Multi-year deal (15-25% off)

**When NOT to Discount:**
- Monthly plan (keep pricing firm)
- Low commitment (don't discount just for asking)
- If they're already getting great ROI (don't train them to negotiate)

**How to Frame Discounts:**
```
"I can offer [X]% off if you commit to [annual / higher volume / multi-year].
 That brings your price to $[Y]/month, which is a great deal for what you're
 getting. Sound good?"
```

### Pricing Strategy

**Expansion vs. New Customer:**
- **New customer:** Strict pricing (establish value perception)
- **Expansion:** Flexible (retain customer, grow ARR)

**Avoid:**
- Giving existing customers worse pricing than new customers (they'll churn)
- Large discounts without commitment (you're leaving money on the table)

---

## Tracking Expansion Performance

### Expansion Metrics to Track

| Metric | Target | Measurement |
|--------|--------|-------------|
| **Expansion Rate** | >25% of customers expand in 12mo | HubSpot |
| **Expansion Revenue** | 30-40% of new ARR | HubSpot ARR waterfall |
| **Average Expansion $** | Increasing over time | HubSpot custom report |
| **Time to Expansion** | <6 months from signup | HubSpot |
| **Expansion Conversion Rate** | >50% of opps close | HubSpot deals |

### Dashboard View

**Build in HubSpot or BI Tool:**

```
Expansion Pipeline:
  - Volume expansion opps: [X] ($[Y] potential ARR)
  - Feature upsells: [A] ($[B] potential ARR)
  - Team plan expansions: [C] ($[D] potential ARR)
  - Annual conversions: [E] ($[F] potential ARR)

Total Expansion Pipeline: $[Total] (vs. target: $[Target])

This Quarter Closed:
  - Expansion deals closed: [N]
  - Expansion ARR added: $[M]
  - % of new ARR from expansion: [P]%
```

---

## Expansion Email Templates

### Template 1: Volume Growth
```
Subject: Your volume is growing! Let's optimize your plan

Hi [Name],

Great news: I see your DeepRead usage is growing ([X]% increase last month).

You're currently on the [Current Plan] ($[Y]/mo for [Z] pages). At your
current pace, you'll hit the limit by [Date].

I'd recommend upgrading to [Next Plan] ($[A]/mo for [B] pages) to:
  1. Avoid overage charges ($[C] per extra page)
  2. Get better per-page pricing ($[D] vs. $[E])
  3. Unlock [feature]

Math:
  - Current plan + overages = $[F]/mo
  - Upgraded plan = $[G]/mo
  - Savings = $[H]/mo

Want to upgrade? Reply and I'll get you set up today.

Best,
[Your Name]
```

### Template 2: Feature Unlock
```
Subject: Unlock [Feature] to [Benefit]

Hi [Name],

Quick question: have you tried [Feature] yet?

I noticed you're [current behavior, e.g., "processing docs one-by-one"],
and [Feature] could [benefit, e.g., "speed that up by 3x"].

Here's how [Similar Customer] uses it: [link to case study]

[Feature] is included in the [Higher Plan] ($[X]/mo). If you want to
try it out, I can upgrade you for a month (no commitment) to see if
it's worth it.

Interested?

Best,
[Your Name]
```

### Template 3: Annual Conversion
```
Subject: Lock in your rate + save [X]%

Hi [Name],

You've been on DeepRead for [X] months - time flies!

Wanted to check: are you open to switching to an annual plan? You'd save
[Y]% ($[Z]) and lock in your current rate (we're raising prices in [Q]).

Annual Plan Benefits:
  - [Y]% discount ($[Z] savings)
  - Price lock for 12 months
  - Quarterly strategy calls with our team
  - [Other perks]

I can apply this to your account today if you're interested. Let me know!

Best,
[Your Name]
```

---

## Success Criteria

**Good Expansion Motion:**
- >20% of customers expand within 12 months
- Expansion revenue = 20-30% of new ARR

**Great Expansion Motion:**
- >30% of customers expand within 12 months
- Expansion revenue = 30-40% of new ARR
- NDR (Net Dollar Retention) >110%

**World-Class Expansion:**
- >40% of customers expand within 12 months
- Expansion revenue = >40% of new ARR
- NDR >120%

---

[← Back to Playbooks](./README.md)
