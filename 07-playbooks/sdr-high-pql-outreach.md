# SDR Playbook: High-PQL Outreach

## When to Use This Playbook

**Trigger:** Contact tagged as "high-value PQL" in HubSpot

**Criteria for High-Value PQL:**
- Processed >5,000 pages in last 7 days, OR
- 3+ users from same company domain, OR
- Company size >200 employees (from enrichment), OR
- Enterprise email domain (not @gmail.com)

**Goal:** Get the prospect on a call with AE within 7 days

---

## Prerequisites

Before outreach, ensure you have:
- [x] Contact enriched (Apollo ran, company data populated)
- [x] Product usage data reviewed (pages processed, features used)
- [x] LinkedIn profile identified (for personalization)
- [x] Recent company news checked (funding, hiring, product launches)

---

## Step-by-Step Process

### Step 1: Research (5-10 minutes)

**Check in HubSpot:**
- Total pages processed
- Days since signup
- Features used (basic vs. advanced)
- Error rate (if high, mention support offer)

**Check LinkedIn:**
- Job title (focus: Engineering Manager, VP Eng, CTO, Head of Product)
- Recent posts or activity (for personalization hook)
- Mutual connections (warm intro opportunity)

**Check Company News:**
- Recent funding round? → "Congrats on Series B!"
- Hiring engineers? → "Saw you're expanding the team..."
- Product launch? → "Just saw [product] go live..."

### Step 2: Craft Personalized Email (Day 0)

**Template (customize with research):**

```
Subject: Quick question about your DeepRead usage

Hi [First Name],

I noticed your team at [Company] processed [X,XXX] pages with DeepRead
over the last few days. That's awesome!

Most teams at that volume typically need [relevant feature: e.g., batch
processing / dedicated infrastructure / SLA guarantees].

Quick question: are you hitting any bottlenecks as you scale, or is
everything running smoothly?

Worth a 15-min chat to make sure you're set up for success?

Best,
[Your Name]

P.S. [Personal touch based on research: "Congrats on the Series B!" /
"Saw your post about document processing challenges - totally resonates"]
```

**Key Elements:**
- Specific usage stat (shows you're paying attention)
- Genuine value offer (not just "buy more")
- Easy ask (15 min, not "demo" which sounds sales-y)
- Personal touch (reference LinkedIn/news)

### Step 3: LinkedIn Connection (Day 2)

**If no email reply by Day 2:**

Send LinkedIn connection request with personalized note:

```
Hi [First Name], we're connected via DeepRead (I noticed your team's
using it for document processing). Would love to connect and share a
relevant case study from [similar company].
```

**Rules:**
- Keep it short (<300 chars)
- Don't pitch, just connect
- Mention DeepRead (context)

### Step 4: Follow-Up Email (Day 4)

**If still no reply:**

```
Subject: Re: Quick question about your DeepRead usage

Hi [First Name],

Following up on my note below. I don't want to be a pest, but wanted
to share how [Similar Company] handled scaling to [X volume] with
DeepRead.

Attached a quick 2-page case study. Key takeaway: they saved ~200
engineering hours by using [feature] instead of building it in-house.

If you're curious about their setup, happy to do a quick screen share.

Best,
[Your Name]
```

**Attachments:**
- Case study PDF (1-2 pages max)
- Optional: ROI calculator ("plug in your volume, see estimated savings")

### Step 5: LinkedIn Message (Day 7 - if connected)

**If they accepted connection but no email reply:**

```
Hey [First Name], thanks for connecting!

Wanted to share this quickly: [link to case study or relevant blog post]

[Similar Company] had a similar use case to yours and found [specific
insight].

Let me know if you'd like to chat about how they set it up - no pressure!
```

### Step 6: Breakup Email (Day 10)

**Final attempt:**

```
Subject: Closing your file

Hi [First Name],

I haven't heard back, so I'm assuming this isn't a priority right now.
No worries at all!

I'll close your file, but if you ever want to chat about scaling your
document processing, just reply to this email.

Best of luck with [Company]!

[Your Name]

P.S. If I'm reaching out to the wrong person, who should I talk to?
```

**Why this works:**
- Creates urgency ("closing your file")
- No pressure ("no worries")
- Gives an out ("wrong person?") → might forward internally

---

## Success Criteria

**Email Performance Benchmarks:**
- **Open rate:** >40% (if lower, improve subject line)
- **Reply rate:** >15% (if lower, improve personalization)
- **Meeting booked rate:** >5% (if lower, adjust value prop or timing)

**Desired Outcome:**
- Meeting booked with prospect within 10 days
- Hand off to AE with context (research, usage data, pain points mentioned)

---

## Common Pitfalls

### ❌ Don't: Generic Copy-Paste
**Why it fails:** Prospects can smell templated emails
**Fix:** Always customize first line with specific detail (usage stat, LinkedIn post, company news)

### ❌ Don't: Lead with Pricing/Demo
**Why it fails:** Too sales-y, triggers resistance
**Fix:** Lead with curiosity ("Are you hitting bottlenecks?") or value ("Most teams at your scale need X")

### ❌ Don't: Overwhelm with Info
**Why it fails:** Long emails don't get read
**Fix:** Keep emails <100 words. One clear CTA.

### ❌ Don't: Give Up After One Email
**Why it fails:** People are busy, might miss your first email
**Fix:** Follow the 10-day sequence. Persistence wins.

### ❌ Don't: Ignore Product Signals
**Why it fails:** You miss golden opportunities (e.g., high error rate = support issue)
**Fix:** Always check product data before reaching out

---

## Email Variants by Persona

### For Engineering Managers
**Focus:** Technical efficiency, team productivity
```
Hi [Name],

Saw your team processed [X] pages with DeepRead. Quick question: are
you handling retries and error handling manually, or using our batch API?

Most eng teams at your scale save ~20 hours/week by switching to batch
mode. Worth a quick screen share to show the setup?
```

### For VPs/CTOs
**Focus:** Strategic value, ROI, scale
```
Hi [Name],

Noticed [Company] is processing serious volume with DeepRead ([X] pages
last week). Congrats on the growth!

As you scale, have you thought about SLA guarantees and dedicated
infrastructure? We typically see this become critical at [threshold] volume.

Worth a 15-min chat to walk through options?
```

### For Product Managers
**Focus:** User experience, time-to-market
```
Hi [Name],

I see you're using DeepRead for [use case]. How's the accuracy holding
up for your users?

Most product teams at [Company Stage] end up needing custom model tuning
to hit >98% accuracy. Happy to show you what that looks like if useful.
```

---

## Handling Common Objections

### "We're happy with the free tier"
**Response:**
```
That's great! Just wanted to make sure you're aware of [feature X] which
could save you [specific benefit]. No pressure to upgrade - just don't
want you to miss something valuable.

If you ever hit [specific pain point], let me know and I can help.
```

### "We're evaluating other solutions"
**Response:**
```
Smart move to compare options. Would you find it helpful to see a
side-by-side comparison of DeepRead vs. [competitor]?

Most teams are surprised by [specific differentiator: e.g., "our accuracy
on tables" or "our 10x faster processing time"].

No sales pitch - just data.
```

### "Not the right time"
**Response:**
```
Totally understand. When would be a better time? I'll follow up then.

In the meantime, here's a resource that might be useful: [case study/guide].
```

### "Send me some info"
**Response (don't just send and ghost):**
```
Absolutely. To make sure I send the most relevant info, quick question:

What's the main challenge you're trying to solve?
[Options: Accuracy / Speed / Cost / Maintenance burden]

I'll send over exactly what you need.
```

**Then:** Send info + suggest a brief call to answer questions

---

## After Meeting is Booked

### Immediately (within 1 hour):
1. **Send calendar invite** (include Zoom link)
2. **Send prep email:**
   ```
   Hi [Name],

   Looking forward to our chat on [Day/Time]!

   To make best use of our 15 minutes, would you mind sharing:
   1. Your main use case for document processing?
   2. Rough volume you're handling (pages/month)?
   3. Biggest pain point right now?

   This way I can come prepared with relevant examples.

   See you [Day]!
   ```

3. **Update HubSpot:**
   - Move deal to "Meeting Scheduled"
   - Add notes from email exchange
   - Tag with pain points mentioned

4. **Brief the AE:**
   - Send Slack message or email with context:
     - Company background (size, industry, funding)
     - Product usage (volume, features, engagement)
     - Pain points mentioned in conversation
     - Suggested talking points

### Day Before Meeting:
- **Send reminder:**
  ```
  Hi [Name], looking forward to our call tomorrow at [Time]!

  Zoom link: [Link]

  See you then!
  ```

### After the Meeting (AE's responsibility, but SDR should follow up):
- Check-in with AE: Did they show? What's next step?
- If no-show: SDR sends reschedule email
- If successful: SDR marks deal as "Demo Complete" and lets AE take over

---

## Performance Tracking

### Track Your Outreach Performance

**Weekly Review:**
- How many high PQLs did you contact?
- Reply rate by email (Day 0, Day 4, Day 10)?
- Meeting booked rate?
- Show rate for booked meetings?

**Continuous Improvement:**
- A/B test subject lines (track open rates)
- Try different personalization hooks (usage stats vs. company news vs. pain points)
- Experiment with CTA (e.g., "15-min chat" vs. "quick screen share" vs. "send you a case study")

**Share with team:**
- What email variants worked best?
- Which objections are you hearing repeatedly? (Product team should know)
- Patterns in who converts (so you can refine PQL scoring)

---

## Example: Full Outreach Sequence (Real Scenario)

**Prospect:** Jane Doe, Engineering Manager at Acme Corp
**PQL Trigger:** Processed 8,200 pages in 3 days
**Enrichment Data:** 300-person company, Series B funded, hiring ML engineers

---

**Day 0 Email:**
```
Subject: Quick question about Acme's DeepRead usage

Hi Jane,

I noticed your team at Acme processed over 8,000 pages with DeepRead in
the last few days - that's some serious volume!

Most teams scaling past 5K pages/day start running into rate limits or
need batch processing to keep costs down.

Quick question: are you handling documents one-by-one, or have you looked
into our batch API?

Would love to share how similar teams (like [Competitor] in fintech)
optimized their setup. Worth a 15-min chat?

Best,
Alex

P.S. Congrats on the Series B! Saw the news on TechCrunch.
```

---

**Day 2 LinkedIn Connection:**
```
Hi Jane, saw your team's using DeepRead for document processing at Acme.
Would love to connect and share a relevant case study.
```

---

**Day 4 Email (Jane opened but didn't reply):**
```
Subject: Re: Quick question about Acme's DeepRead usage

Hi Jane,

Following up on my note below. Don't want to bug you, but wanted to
share a quick case study from a similar fintech company.

They were processing ~10K docs/day and cut processing time by 60% by
switching to batch mode. Thought it might be relevant for Acme.

Attached the 1-pager. If you're curious how they set it up, happy to
do a 10-min screen share. No pressure!

Best,
Alex
```

---

**Day 7 LinkedIn Message (Jane accepted connection):**
```
Hey Jane, thanks for connecting!

Quick share: [Case Study Link]

[Company] had a similar doc processing challenge and found our batch
API saved them ~100 hours/month in maintenance.

Let me know if you'd like to see their setup - always happy to chat!
```

---

**Day 10 Breakup Email:**
```
Subject: Closing your file

Hi Jane,

I haven't heard back, so I'm guessing this isn't a priority right now.
Totally understand!

I'll close your file, but if you ever want to chat about scaling Acme's
document processing, just reply to this email.

Best of luck with everything at Acme!

Alex

P.S. If I'm reaching out to the wrong person, who should I talk to about
our document processing infrastructure?
```

---

**Result:** Jane replies on Day 11:
```
"Hey Alex, sorry for the delay! We've been slammed. Yes, we're definitely
hitting some rate limits. Would love to learn about batch processing. Can
we do a call next Tuesday?"
```

✅ **Success!** Meeting booked, hand off to AE.

---

[← Back to Playbooks](./README.md)
