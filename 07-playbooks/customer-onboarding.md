# Customer Onboarding Playbook

## When to Use This Playbook

**Trigger:** Contract signed, customer payment processed

**Goal:** Get customer to first production use within 14 days, establish foundation for long-term success

**Owner:** Customer Success Manager (or founder in early stage)

---

## Overview: The First 30 Days

```
Day 0-7: Technical Setup & First Success
  → Goal: Production API call

Day 8-14: Volume Ramp & Optimization
  → Goal: Processing meaningful volume

Day 15-30: Feature Adoption & Business Review
  → Goal: Expand use cases, confirm ROI
```

---

## Pre-Onboarding Prep (Before Kickoff Call)

### 1. Review Customer Context (15 minutes)

**From Sales Handoff:**
- Use case (what documents, what data to extract)
- Volume commitments (pages/month)
- Technical stack (Python, Node.js, etc.)
- Key stakeholders (who signed, who will use it)
- Pain points that led them to buy
- Contract terms (annual vs. monthly, SLA level)

**Check Product Usage (if they were already trialing):**
- Current usage patterns
- Error rates
- Features already adopted

### 2. Prepare Onboarding Materials

**Customize for their use case:**
- Code samples in their language
- Sample documents (similar to what they'll process)
- Integration guide for their stack (if applicable)

**Standard docs to send:**
- API documentation
- Best practices guide
- Support contact info (Slack channel, email, phone)

---

## Day 0: Kickoff Call (30-45 minutes)

### Agenda

**1. Introductions (5 min)**
- Introduce yourself as their CSM
- "I'm your main point of contact for success with DeepRead"
- Introduce any others (support engineer, account exec)

**2. Set Expectations (5 min)**
- "Our goal: get you processing documents in production within 7 days"
- "I'll check in weekly for the first month, then monthly QBRs"
- "You have [Slack channel / priority email] for support - we respond within [SLA time]"

**3. Confirm Use Case & Goals (10 min)**

Ask:
- "Walk me through exactly what you want to accomplish with DeepRead"
- "What does success look like in 30/60/90 days?"
- "What volume are you planning to process?"
- "Any specific deadlines or milestones?"

**Take detailed notes.** This becomes your success plan.

**4. Technical Review (10 min)**
- "What's your tech stack?"
- "How will DeepRead integrate with your existing workflow?"
- "Do you have sample documents you want to test with?"

**5. Assign Action Items (5 min)**

**Your action items:**
- Send API keys + credentials (if not already done)
- Share custom code samples
- Set up support Slack channel
- Schedule next check-in (3 days)

**Their action items:**
- Make first test API call
- Send sample documents for testing
- Identify any integration needs

**6. Questions (5 min)**
- "What questions do you have?"
- "Any concerns before we get started?"

### Follow-Up (Same Day)

**Send recap email:**
```
Subject: DeepRead Onboarding - Kickoff Recap & Next Steps

Hi [Name],

Great to meet you today! Here's a quick recap of our kickoff:

Your Goal:
  - [Use case: e.g., "Process 10K invoices/month, extract line items"]
  - Success = [metric: e.g., ">95% accuracy, <2 sec latency"]

Action Items:
  ✓ Me: API keys (sent), code samples (attached), Slack channel (invite sent)
  ✓ You: First test API call, send sample docs for testing

Resources:
  - API Docs: [link]
  - Code Samples: [link to GitHub]
  - Support: [Slack channel / email]

Next Check-In: [Date, 3 days from now]

Let me know if you hit any blockers!

Best,
[Your Name]
```

---

## Day 1-7: First Success Sprint

### Goal: Production API Call

### Day 1: Monitor First API Call

**Check Product Analytics:**
- Did they make first API call?
- Success or errors?
- Volume (testing or production-scale)?

**If Success:**
- Send congratulations email:
  ```
  "Awesome! I see you made your first API call and processed [X] documents.
   How did it go? Any issues with accuracy or integration?"
  ```

**If Errors:**
- Proactive outreach (don't wait for them to ask for help):
  ```
  "I noticed you hit an error on your first API call. Let me help debug.
   Can you share the error message or code snippet?"
  ```

### Day 3: Check-In Call (15 minutes)

**Questions to ask:**
- "How's the integration going?"
- "Have you been able to test with your actual documents?"
- "Any surprises (good or bad)?"
- "What's blocking you from going to production?"

**Common Blockers:**
- **Accuracy issues:** Offer to tune model for their use case
- **Integration complexity:** Pair with support engineer for setup
- **Volume/performance:** Optimize API usage (batching, caching)

**Action Items:**
- Address any blockers immediately
- Set goal: "Can we get to production by Day 7?"

### Day 7: Production Milestone

**Check:**
- Are they processing production volume (not just tests)?
- Success rate >95%?
- Any outstanding issues?

**If in production:**
- **Celebrate!**
  ```
  "Congrats on going live! I see you're processing [X] pages/day.
   How's it performing? Meeting your expectations?"
  ```
- Send small gift (swag, company merch, handwritten note)

**If not in production yet:**
- Escalate: "What's blocking you? Let's get on a call and solve it together."
- Involve technical resources if needed

---

## Day 8-14: Volume Ramp & Optimization

### Goal: Reach Contracted Volume, Optimize Performance

### Day 10: Usage Review

**Analyze their usage:**
- Current volume vs. contracted volume
- Error patterns (any recurring failures?)
- Latency (meeting SLA?)
- Feature usage (basic vs. advanced)

**Proactive Recommendations:**

**If volume is low:**
- "I see you're at [X] pages/day. Are you planning to ramp up? Anything blocking you?"

**If errors are high (>10%):**
- "I noticed [Y]% error rate on [document type]. Let's debug - can you send a sample doc?"

**If latency is slow:**
- "You're seeing [Z] sec latency. Most teams at your volume see <2 sec. Let me help optimize."

### Day 14: Optimization Call (30 minutes)

**Agenda:**
1. Review first 2 weeks (wins, challenges)
2. Optimize setup:
   - Batch processing (if high volume)
   - Model selection (accuracy vs. speed trade-offs)
   - Error handling (retries, fallbacks)
3. Discuss expanding use cases
4. Set goals for next 2 weeks

---

## Day 15-30: Feature Adoption & Business Review

### Goal: Expand Use Cases, Confirm ROI

### Day 21: Feature Education

**Introduce advanced features:**

**Email:**
```
Subject: 3 DeepRead features you're not using (yet)

Hi [Name],

You've been using DeepRead for a few weeks now - awesome!

I noticed you're mostly using [basic feature]. Wanted to highlight 3
features that could help:

1. [Feature X]: Saves time by [benefit]
2. [Feature Y]: Improves accuracy for [use case]
3. [Feature Z]: Enables [new capability]

Want a quick 15-min walkthrough? Or I can just send docs.

Let me know!

Best,
[Your Name]
```

**Goal:** Increase feature adoption (stickiness) and expand use cases (expansion revenue)

### Day 30: First Business Review (30-45 minutes)

**Agenda:**

**1. Review Success Metrics (10 min)**
- Volume processed (vs. goal)
- Accuracy achieved (vs. target)
- Time saved (engineering hours)
- Cost savings (vs. build in-house or previous solution)

**Prepare a simple report:**
```
DeepRead - 30-Day Review: [Customer Name]

Usage:
  - Pages processed: [X] (Goal: [Y])
  - Accuracy: [A]% (Target: [B]%)
  - Uptime: [C]% (SLA: 99.9%)

Business Impact:
  - Est. engineering hours saved: [D] hours
  - Cost vs. build in-house: $[E] saved
  - Documents processed [F]% faster than before

What's Working:
  - [Positive feedback from team]
  - [Specific use case success]

Opportunities:
  - [Feature they should adopt]
  - [New use case to explore]

Next 30 Days:
  - [Goal 1: e.g., "Scale to 50K pages/month"]
  - [Goal 2: e.g., "Expand to [new document type]"]
```

**2. Gather Feedback (10 min)**
- "What's working well?"
- "What could be better?"
- "Any features you wish we had?"
- "How's the support experience?"

**Document feedback.** Share with product team.

**3. Identify Expansion Opportunities (10 min)**
- "Are there other document types you could process with DeepRead?"
- "Other teams at [Company] who could benefit?"
- "As you scale, have you thought about [enterprise features]?"

**4. Set Goals for Next Quarter (5 min)**
- "What's your target volume in 90 days?"
- "Any new use cases or projects coming up?"

**5. Address Concerns (5 min)**
- "Any concerns or issues I should know about?"
- "What would make you consider churning?" (ask directly!)

---

## Ongoing: Monthly Touchpoints (After Day 30)

### Monthly Check-In (15-30 minutes)

**Cadence:** First week of each month

**Agenda:**
1. Usage review (volume, accuracy, errors)
2. Business impact update (ROI, time saved)
3. New feature announcements
4. Expansion discussion
5. Feedback & concerns

**Prepare Monthly Report (automated if possible):**
```
[Customer Name] - Monthly Report

Usage This Month:
  - Pages: [X] (↑↓ Y% vs. last month)
  - Accuracy: [A]%
  - Errors: [B] (down from [C] last month)

Year-to-Date:
  - Total pages: [D]
  - Est. cost savings: $[E]

Feature Spotlight:
  - [New feature] - [benefit for their use case]

Action Items:
  - [Any follow-ups]
```

---

## Red Flags: When to Escalate

### Usage Red Flags

🚨 **Volume declining >20% MoM** → Call immediately, understand why
🚨 **No usage in 7 days** → High churn risk, proactive outreach
🚨 **Error rate >20%** → Product issue, escalate to engineering
🚨 **Not using advanced features after 60 days** → Low stickiness, educate or risk churn

### Engagement Red Flags

🚨 **Skipped last 2 monthly check-ins** → Disengaged, risk of churn
🚨 **Slow to respond to emails (>3 days)** → Losing interest or deprioritized
🚨 **Negative feedback in support tickets** → Dissatisfaction building

### Commercial Red Flags

🚨 **Downgraded plan** → Understand why, prevent churn
🚨 **Mentioned competitor** → Proactive competitive response
🚨 **Requested cancellation** → Save play (see churn prevention playbook)

**Action:** Escalate to manager, loop in AE for save/expansion play

---

## Success Criteria

### Week 1:
✅ First production API call
✅ Customer satisfied with initial results

### Week 2:
✅ Processing meaningful volume (>10% of contract commitment)
✅ Error rate <10%

### Month 1:
✅ At or above contracted volume
✅ Customer reports ROI (time/cost savings)
✅ Identified expansion opportunity (new use case, features, or volume)

### Month 3:
✅ Customer is a reference (willing to do case study or referral)
✅ High health score (>80)
✅ Expansion revenue captured or in pipeline

---

## Onboarding Checklist Template

**Copy this for each new customer:**

```
[ ] Pre-Kickoff: Review customer context (sales notes, usage data)
[ ] Pre-Kickoff: Prepare custom materials (code samples, docs)
[ ] Day 0: Kickoff call completed
[ ] Day 0: Send recap email + resources
[ ] Day 0: Set up support Slack channel
[ ] Day 1: Monitor first API call
[ ] Day 3: Check-in call (address blockers)
[ ] Day 7: Production milestone achieved
[ ] Day 10: Usage review (optimize performance)
[ ] Day 14: Optimization call
[ ] Day 21: Feature education email
[ ] Day 30: First business review (QBR)
[ ] Day 30: Identify expansion opportunity
[ ] Ongoing: Monthly check-ins scheduled
```

---

[← Back to Playbooks](./README.md)
