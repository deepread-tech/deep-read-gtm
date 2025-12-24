# AE Playbook: Product Demo

## When to Use This Playbook

**Trigger:** SDR books a meeting, or inbound request for demo

**Goal:** Convert demo → proposal sent with 60-70% success rate

**Typical Audience:**
- Engineering Managers (technical, hands-on)
- VPs/CTOs (strategic, ROI-focused)
- Product Managers (user experience, time-to-market)

---

## Pre-Demo Preparation (Do This 24hrs Before)

### 1. Review Context (15 minutes)

**Check HubSpot:**
- Company background (size, industry, funding stage)
- Product usage data (pages processed, features used, frequency)
- SDR notes (pain points mentioned, questions asked)
- Previous interactions (emails, meetings)

**Check LinkedIn:**
- Attendee profiles (titles, backgrounds)
- Company updates (hiring, product launches, funding)

**Check Product Analytics (PostHog):**
- Usage patterns (what features are they using?)
- Error patterns (are they struggling with anything?)
- Volume trends (growing, flat, declining?)

### 2. Prepare Custom Demo Environment (10 minutes)

**Upload Sample Documents:**
- Use documents similar to their use case (if known)
- Examples: Invoices (fintech), Legal contracts (legal tech), Medical records (healthcare)

**Pre-run API Calls:**
- Show results instantly instead of waiting during demo
- Have code samples ready to share

**Prepare ROI Slide:**
- Estimate their volume (from product data or ask)
- Calculate: DeepRead cost vs. "Build in-house" cost
- Show time saved (engineering hours)

### 3. Set Up Demo Flow (5 minutes)

**Have these tabs open:**
1. DeepRead Dashboard (live usage, if they're already using it)
2. API Playground (for live demo)
3. Code samples (Python/Node.js)
4. ROI Calculator
5. Case study (similar company/use case)

---

## Demo Structure (30-45 minutes)

### Part 1: Discovery (10 minutes)

**Goal:** Understand their needs before you pitch

**Questions to Ask:**

**Current Setup:**
- "What's your current document processing setup?"
  - DIY (open source libraries)?
  - Competitor (AWS Textract, Google Document AI)?
  - Manual (humans reviewing documents)?

**Pain Points:**
- "What's the biggest challenge you're facing right now?"
  - Accuracy issues?
  - Slow processing?
  - High maintenance burden?
  - Cost?

**Use Case:**
- "Walk me through a typical document you need to process."
  - What info do you extract?
  - How many pages?
  - How often (volume per day/month)?

**Decision Process:**
- "What does success look like for this project?"
- "Who else is involved in the decision?" (Identify stakeholders)
- "What's your timeline?" (Urgency indicator)

**Listen carefully and take notes.** The demo should address their specific pain points.

---

### Part 2: Live Demo (15-20 minutes)

**Start with Their Use Case:**

"Okay, so it sounds like you're processing [X type of documents] and the
main challenge is [pain point]. Let me show you exactly how DeepRead handles that."

**Show, Don't Tell:**

**Step 1: Upload Document (2 min)**
- Use a document similar to their use case
- Show the UI: "Here's a typical [invoice/contract/receipt]"

**Step 2: API Call (3 min)**
- Show code sample (their language: Python/Node.js/curl)
- Explain key parameters (model selection, options)
- Run the call live (if pre-run, show the response)

```python
import deepread

# Example: Extract structured data from invoice
response = deepread.process(
    file_path="invoice.pdf",
    model="gpt-4v",  # Optimized for tables and forms
    extract_tables=True
)

print(response.data)
# Show structured JSON output
```

**Step 3: Show Results (5 min)**
- Highlight accuracy: "Notice how it correctly extracted the table..."
- Compare to their pain point: "You mentioned accuracy issues with [competitor] -
  here's how we handle edge cases..."
- Show structured output (JSON, CSV, whatever they need)

**Step 4: Advanced Features (3 min)**
- **Batch Processing:** "If you're doing 10K+ pages/day, here's how you'd batch..."
- **Custom Models:** "For your specific use case, we can fine-tune the model to improve accuracy..."
- **Error Handling:** "Here's how you handle retries and failures..."

**Step 5: Integration (2 min)**
- "Integrating with your existing workflow is straightforward..."
- Show code sample: API call → their database/workflow tool

**Keep it interactive:**
- "Does this make sense so far?"
- "Is this similar to what you're doing now?"
- "What questions do you have?"

---

### Part 3: ROI & Differentiation (10 minutes)

**Show the Numbers:**

**Option A: Cost Savings (vs. Build In-House)**
```
Building in-house:
  - 2 engineers × 3 months = 6 eng-months ($60K-100K)
  - Ongoing maintenance = 1 engineer × 20% time ($20K/year)

DeepRead:
  - Your volume: 50K pages/month
  - Cost: ~$2,500/month ($30K/year)

Savings Year 1: $50K-70K
Savings Year 2+: $20K+/year (no maintenance burden)
```

**Option B: Speed to Market (vs. Build)**
- "You could start using DeepRead today vs. 3 months to build"
- "That's 3 months of revenue/value you'd be leaving on the table"

**Differentiation vs. Competitors:**

**If they mention AWS Textract:**
- "Textract is great for simple forms, but struggles with [complex tables/handwriting/multi-page context]"
- "We combine multiple LLMs (GPT-4V + Claude + Gemini) to achieve >95% accuracy on [their use case]"
- Show side-by-side comparison (if you have data)

**If they mention Google Document AI:**
- Similar positioning: "Great for specific use cases, but requires significant config"
- "DeepRead gives you the accuracy of Document AI with 1/10th the setup time"

**Your Unique Value:**
- "We're not building a proprietary LLM - we're building the *infrastructure* to combine
  the best LLMs for maximum accuracy"
- "Think of us as the 'Stripe for document processing' - you don't build payment infrastructure,
  you don't build OCR infrastructure"

---

### Part 4: Social Proof (3 minutes)

**Share a Case Study:**

"Let me show you how [Similar Company] uses DeepRead..."

**Key Elements:**
- **Similar use case:** Same industry or document type
- **Concrete results:** "They went from 85% accuracy to 98%"
- **ROI:** "Saved 200 engineering hours in first quarter"

**Testimonial (if you have one):**
```
"Before DeepRead, we spent 30% of our engineering time maintaining our
OCR pipeline. Now we spend 0% and get better accuracy."
- John Doe, VP Engineering at [Company]
```

**Customer Logos (if you have them):**
- Show well-known brands (if permissioned)

---

### Part 5: Next Steps (5 minutes)

**Summarize:**
- "So, to recap: you're processing [volume] of [document type]"
- "Main pain point is [accuracy/speed/maintenance]"
- "DeepRead solves that by [specific solution]"

**Address Concerns:**
- "Any concerns or questions before we move forward?"
- Handle objections (see section below)

**Propose Next Steps:**

**If they're ready:**
- "Great! I'll send over a proposal with pricing for [estimated volume]"
- "We can have you up and running within 48 hours"

**If they need more:**
- "Would it be helpful to do a pilot? Process 1,000 docs and compare results to [current solution]?"
- "Can I set up a technical deep-dive with your engineering team?"

**If there are other stakeholders:**
- "Who else needs to be involved in the decision?"
- "Would it be helpful if I present to [CTO/procurement/legal]?"

**Set a clear deadline:**
- "What's your timeline for making a decision?"
- "I'll send the proposal by [date]. Can we schedule a follow-up for [date] to discuss?"

---

## Handling Common Objections

### "It's too expensive"

**Diagnose the real issue:**
- "Too expensive compared to what?" (Current solution? Build in-house?)

**Response:**
```
I understand. Let me break down the ROI:

Your volume: [X pages/month]
DeepRead cost: $[Y]/month

Building in-house:
  - Dev time: $50K-100K upfront
  - Maintenance: $20K+/year
  - Opportunity cost: 3 months delay

Even if you're comparing to [cheaper competitor], remember accuracy
matters. If you're at 85% accuracy vs. our 98%, that's 15% of your
documents that need manual review.

What's the cost of manual review per document?
```

**Offer:**
- Annual discount (10-20% off for annual prepay)
- Pilot program (process 1K docs, prove ROI)

---

### "We're already using [Competitor]"

**Don't badmouth the competitor.**

**Response:**
```
[Competitor] is a solid choice for [what they're good at].

Where we see teams switch to DeepRead is when they need [your differentiator]:
  - Higher accuracy on [specific doc types]
  - Faster processing (we're 10x faster for [use case])
  - Less maintenance (no model training required)

Would it be worth running a head-to-head test? Send us 100 docs, we'll
process them, and you can compare results side-by-side.
```

**Offer:** Free pilot / proof of concept

---

### "We're building in-house"

**Respect the decision, but plant the seed:**

**Response:**
```
That makes sense - you want full control. A few things to consider:

1. How long will it take? (Usually 3-6 months for production-ready)
2. Who's maintaining it? (Ongoing burden as models evolve)
3. What's the opportunity cost? (Revenue you could generate in those 6 months)

A lot of teams start building, realize the complexity, and end up using
DeepRead. But if you want to build, I respect that.

One option: use DeepRead now to ship quickly, then replace it with your
in-house solution later. No lock-in, cancel anytime.

What do you think?
```

---

### "We need to talk to legal/procurement/security"

**This is normal for enterprise. Don't panic.**

**Response:**
```
Absolutely. Here's what I can provide to help:

For Legal:
  - MSA (Master Service Agreement)
  - DPA (Data Processing Agreement)
  - SLA (Service Level Agreement)

For Security:
  - SOC 2 Type II report
  - GDPR compliance docs
  - Data handling policy (we don't store your docs)

For Procurement:
  - Standard pricing sheet
  - Payment terms (Net 30/60)
  - Volume discounts

I can join a call with your legal/security team if that's helpful. Or
I can just send these docs over. What works best?
```

**Proactively send docs.** Don't wait for them to ask.

---

### "We need more time to evaluate"

**Understand the real blocker:**

**Questions to ask:**
- "What specifically do you need to evaluate?"
- "What would make you confident to move forward?"
- "Is there a specific concern I can address?"

**Response:**
```
Totally understand. To make sure you have what you need, let me suggest:

Option 1: Pilot Program
  - Process 1,000 docs with DeepRead (free)
  - Compare accuracy to your current solution
  - Make a decision based on real data

Option 2: Technical Deep-Dive
  - I'll bring our CTO/eng lead
  - Walk through architecture, security, integration
  - Answer any technical questions

Which would be more helpful?
```

**Set a deadline:**
- "When do you think you'll have an answer?"
- "Can I follow up on [date]?"

---

## After the Demo

### Immediately (within 1 hour):

**1. Send Follow-Up Email:**

```
Subject: Thanks for the demo - next steps

Hi [Name],

Great chatting with you today! To recap what we discussed:

Your Use Case:
  - Processing [X] [document type] per month
  - Main challenge: [pain point mentioned]

How DeepRead Helps:
  - [Solution 1]
  - [Solution 2]
  - [ROI estimate: $X saved per year]

Next Steps:
  - I'll send a formal proposal by [date]
  - [Any other commitments you made]

Attached:
  - Case study: [Similar Company]
  - Code samples (Python, Node.js)
  - Security docs (SOC 2, GDPR)

Let me know if you have any questions in the meantime!

Best,
[Your Name]
```

**2. Update HubSpot:**
- Move deal to "Demo Complete"
- Add detailed notes (pain points, objections, stakeholders, timeline)
- Set task: "Send proposal by [date]"

**3. Prepare Proposal:**
- Pricing based on their estimated volume
- Contract terms (monthly vs. annual)
- SLA and support level
- Implementation timeline

---

### Follow-Up Cadence:

**Day 1 (demo day):** Send recap email (above)
**Day 2:** Send proposal
**Day 4:** Check-in: "Did you have a chance to review the proposal?"
**Day 7:** If no response, call them
**Day 10:** "Is this still a priority? What can I do to help move this forward?"

**Stay persistent but respectful.** Enterprise deals take time (30-90 days).

---

## Success Criteria

**Good Demo:**
- Prospect engaged (asked questions, took notes)
- Addressed their specific pain points
- Clear next step defined (proposal, pilot, technical review)

**Great Demo:**
- Prospect said "this is exactly what we need"
- Verbal commitment to move forward
- Timeline discussed

**Demo → Proposal Rate:** Target 60-70%
**Proposal → Closed-Won Rate:** Target 20-30%

---

## Common Pitfalls

❌ **Don't:** Talk for 45 minutes straight
✅ **Do:** Make it a conversation (ask questions, listen)

❌ **Don't:** Show every feature
✅ **Do:** Focus on their specific use case

❌ **Don't:** Badmouth competitors
✅ **Do:** Respectfully differentiate ("Great for X, we excel at Y")

❌ **Don't:** Oversell ("We can do anything!")
✅ **Do:** Be honest about limitations, offer solutions

❌ **Don't:** End without a clear next step
✅ **Do:** Get commitment to next action (proposal review date, pilot start date)

---

[← Back to Playbooks](./README.md)
