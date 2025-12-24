# DeepRead Messaging Guide

**Principle:** Engineers don't read. They scan. Make every word count.

---

## Core Value Prop (Pick One)

### Option A: The Complexity Bomb
**"Production OCR: 40,000 lines of code. You don't have to write them."**

### Option B: The Time Saver
**"6 weeks to build. 10 hours/month to maintain. Or: Use ours, ship today."**

### Option C: The Model Churn
**"Models change every quarter. Your pipeline needs constant re-optimization. We handle it."**

### Option D: The Honest One (Recommended)
**"Yes, you can build this. It's 6 weeks + ongoing maintenance. Or use ours."**

---

## Homepage Messaging

### Hero Section

**Headline:**
"Production OCR infrastructure for developers"

**Subhead:**
"Multi-model consensus, automatic optimization, continuous model updates. The 40K-line pipeline you'd build, already built."

**CTA:**
[Try on your documents] [See the architecture]

---

### Above the Fold

**3 Bullet Points (max):**

✓ **Multi-model consensus** - 6-8 specialized steps, not one API call
✓ **Auto-optimization** - Stay current as GPT-5, Gemini, Claude improve
✓ **Ship today** - 6 weeks of build time, gone

---

## The "Why Not DIY?" Section

### Headline
**"What you'd build"**

### Visual: The Pipeline Complexity

```
What you think you need:
┌──────────────┐
│ PDF Document │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│  GPT-4V OCR  │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│     Text     │
└──────────────┘


What you actually need:
┌──────────────┐
│ PDF Document │
└──────┬───────┘
       │
       ▼
┌───────────────────┐
│ Convert to Images │ ← Gemini Lite
│   + Fix Rotation  │
└─────────┬─────────┘
          │
    ┌─────┴─────┐
    ▼           ▼
┌────────┐  ┌─────────┐
│ GPT-5  │  │ Gemini  │ ← Parallel OCR
│  Mini  │  │  Flash  │
└───┬────┘  └────┬────┘
    │            │
    └─────┬──────┘
          ▼
   ┌──────────────┐
   │ Consensus    │ ← Gemini Flash (Judge)
   │ Voting       │
   └──────┬───────┘
          │
          ▼
   ┌──────────────┐
   │ Resolve      │ ← GPT-5 Mini (if disagree)
   │ Discrepancy  │
   └──────┬───────┘
          │
          ▼
   ┌──────────────┐
   │ Extract      │ ← GPT-5 (high accuracy)
   │ Structured   │
   └──────┬───────┘
          │
          ▼
   ┌──────────────┐
   │ Quality      │ ← GPT-5 Mini
   │ Review       │
   └──────┬───────┘
          │
          ▼
   ┌──────────────┐
   │ Final Result │
   │ + Confidence │
   └──────────────┘

6-8 steps. 5 different models. Parallel execution. Cost tracking.
```

### Body (Short bullets)

**The Pipeline:**
- Primary OCR (GPT-5 Mini)
- Secondary OCR (Gemini Flash)
- Consensus judge (LLM voting)
- Discrepancy resolution
- Structured extraction
- Quality review & flagging

**The Maintenance:**
- Re-benchmark every model release (quarterly)
- Optimize routing as prices change
- A/B test config changes
- Debug accuracy regressions
- Update for new model capabilities

**The Code:**
- 40,000+ lines of Python
- LangGraph orchestration
- 8 different model configs
- Iterative optimizer (12K LOC)
- Cost tracking & monitoring

**Your Time:**
- Build: 6-8 weeks
- Maintain: 10+ hours/month
- Opportunity cost: Not shipping features

**Or: Use DeepRead**

[Try it free] [See pricing]

---

## Social Media / HN / Twitter

### Version 1: The LOC Bomb
"Production OCR isn't 1 API call. It's 40,000 lines of multi-model consensus, optimization, and failover. We built it so you don't have to. [link]"

**Length:** 156 chars

---

### Version 2: The Maintenance Tax
"You'll build an LLM OCR pipeline in 2 weeks. Then spend 10 hours/month maintaining it as models change. Forever. [link]"

**Length:** 128 chars

---

### Version 3: The Model Churn
"GPT-5.5 drops next month. Will you re-benchmark your OCR pipeline? Re-optimize routing? Update consensus logic? We do. Full-time. [link]"

**Length:** 148 chars

---

### Version 4: The Honest Approach
"Building OCR is 6 weeks. Maintaining it is 10 hours/month, forever. We built it. You can use ours or build your own. Both valid. [link]"

**Length:** 141 chars

---

### Version 5: HN-Specific (Technical)
"Our production OCR: 6-8 model calls per document (primary/secondary/judge/resolve/extract/review). LangGraph orchestration. 12K-line optimizer. Not claiming magic - just built the infra. [link]"

**Length:** 192 chars

---

## Email Subject Lines

### Welcome Email
"Your API key (skip 6 weeks of infrastructure work)"

### Accuracy Report
"94% on YOUR docs (vs 78% generic OCR)"

### Re-engagement (Inactive Users)
"Still building your own OCR pipeline?"

### Upsell (High Volume Users)
"8,000 pages this week. Here's what you need at scale."

### Model Update Announcement
"GPT-5.5 is live. Your pipeline is already updated."

### Churn Prevention
"Before you go: What would make DeepRead worth it?"

---

## Email Body Templates

### Welcome Email (Day 0)

**Subject:** Your API key (skip 6 weeks of infrastructure work)

**Body:**
```
Hi [Name],

Your DeepRead API key: [KEY]

Next: Upload 100 documents (your eval set).

We'll:
1. Build a custom context layer (train on 50)
2. Test accuracy (validate on 50)
3. Send you results in 15 minutes

Most teams waste 6 weeks building multi-model OCR pipelines.
You'll validate ours in 15 minutes.

[Upload eval set] ← CTA

Questions? Reply.

Best,
[Founder]
```

---

### Accuracy Report Email (THE MONEY EMAIL)

**Subject:** 94% on YOUR docs (vs 78% generic OCR)

**Body:**
```
Hi [Name],

Your custom context is ready.

Results:
→ DeepRead: 94% accurate
→ Generic OCR: 78% accurate
→ Improvement: +16 points

On YOUR document types. Tested on 50 of your files.

What this means:
Instead of 6 weeks building a pipeline, you tested ours in 15 minutes.

Next: Make your first production call.

```python
import deepread
result = deepread.ocr("invoice.pdf", context_id="ctx_abc123")
```

[Start processing] ← CTA

Not impressed? Reply and tell me why.

Best,
[Founder]

P.S. Your custom context uses:
- GPT-5 Mini (reasoning)
- Gemini Flash (vision)
- Consensus voting (when they disagree)
- Automatic quality flagging

You'd build the same thing. Just saved 6 weeks.
```

---

### Re-engagement Email (14 Days Inactive)

**Subject:** Still building your own OCR pipeline?

**Body:**
```
Hi [Name],

Haven't seen you in 2 weeks.

Quick question: Did you end up building your own LLM OCR pipeline?

If so, curious how long it took. Most teams say 4-6 weeks.

If not, what blocked you from trying DeepRead?

Reply - genuinely want to know.

Best,
[Founder]

P.S. If you're still interested: [Your custom context is still live]
```

---

## Website Copy Blocks

### Comparison Table: DIY vs DeepRead

### Visual: Time Investment Over 1 Year

```
DIY Timeline:
──────────────────────────────────────────────────────────────────

Month 1-2: Build [████████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░] 6 weeks

Month 3: GPT-5.5 released [████░░░] 20 hours (re-benchmark)

Month 5: Costs spike [██░░] 8 hours (debug & optimize)

Month 6: Gemini update [████░░] 18 hours (re-test & route)

Month 9: Claude vision [████░░░] 22 hours (evaluate & integrate)

Month 12: Llama 4 free [███░░] 16 hours (cost optimization)

Total Year 1: 6 weeks + 84 hours = 324 hours (~$24K eng time)
──────────────────────────────────────────────────────────────────

DeepRead Timeline:
──────────────────────────────────────────────────────────────────

Day 1: Upload eval set [█] 15 minutes

All model updates: [✓] Automatic (zero time)

Total Year 1: 15 minutes (~$0 eng time)
──────────────────────────────────────────────────────────────────
```

### Comparison Table

| Build It Yourself | DeepRead |
|-------------------|----------|
| Week 1-2: Build pipeline | **Day 1**: Working OCR |
| Week 3-4: Multi-model consensus | ✅ 6-8 model orchestration |
| Week 5-6: Build optimizer | ✅ 12K-line optimizer included |
| Ongoing: 10hrs/month maintenance | ✅ We maintain it |
| Model updates: Your problem | ✅ Always on latest models |
| **Total time:** 6-8 weeks + forever | **Total time:** 15 minutes |

**When to DIY:**
- You're building an OCR company
- You process >10M pages/month
- You need on-prem/air-gapped
- OCR is your core IP

**Otherwise:** Use DeepRead. Ship your product.

---

### The Technical Details Section

**Headline:** What's actually running

**Visual: One API Call = 40K Lines of Code**

```
Your code:
────────────────────────────────────────
result = deepread.ocr("invoice.pdf")
────────────────────────────────────────

What actually runs:
────────────────────────────────────────

┌─ Pre-processing (5K LOC)
│  ├─ PDF → Images (300 DPI)
│  ├─ Rotation Detection
│  └─ Optimization
│
├─ Multi-Model OCR (15K LOC)
│  ├─ Primary: GPT-5 Mini ────┐
│  ├─ Secondary: Gemini Flash ─┤
│  ├─ Consensus Judge ─────────┤→ Pick Best
│  └─ Resolve Discrepancy ─────┘
│
├─ Extraction (8K LOC)
│  ├─ Field Detection
│  ├─ Location Hints
│  ├─ Extraction (GPT-5)
│  └─ Cross-Validation
│
├─ Quality Review (5K LOC)
│  ├─ Confidence Scoring
│  ├─ Flag Uncertain Fields
│  └─ Human Review Queue
│
├─ Optimizer (12K LOC)
│  ├─ Failure Analysis
│  ├─ Prompt Improvement
│  ├─ Convergence Detection
│  └─ A/B Testing
│
└─ Infrastructure (5K LOC)
   ├─ LangGraph Orchestration
   ├─ Cost Tracking
   ├─ Retry Logic
   └─ Monitoring

Total: 50,000+ lines, 2 years of optimization
────────────────────────────────────────
```

**Body:**

Your one API call triggers:

**1. Pre-processing**
- PDF → 300 DPI images
- Rotation detection (Gemini Lite)
- Image optimization

**2. Multi-model OCR**
- Primary: GPT-5 Mini (reasoning)
- Secondary: Gemini Flash (vision)
- Judge: LLM consensus voting
- Resolve: Auto-fix discrepancies

**3. Structured Extraction**
- Field detection (GPT-5 Mini)
- Extraction (GPT-5)
- Validation & cross-check

**4. Quality Review**
- Confidence scoring
- Flag uncertain extractions
- Human review where needed

**5. Cost Optimization**
- Track spend per component
- Auto-route to cheaper models
- A/B test configurations

**Total:** 50,000+ lines of Python, optimized over 2 years.

You can build this. **Or use ours.**

---

## Landing Page Variations

### For "Build vs Buy" Decision-Makers

**Headline:**
"Build your OCR pipeline. Or use ours. Both valid."

**Subhead:**
We're not claiming you can't build it. We're saying: We already did. You can use it while you ship your actual product.

**Body (3 columns):**

**Build It**
- Full control
- Custom optimizations
- Learning experience
- 6-8 weeks build
- 10+ hrs/month maintain

**Use DeepRead**
- Ship in 15 minutes
- Always updated
- Focus on product
- $0.08-0.15/page
- Zero maintenance

**Hybrid**
- Use ours now
- Build yours later
- No lock-in
- Standard API
- Migrate anytime

---

### For Technical Evaluators

**Headline:**
"The OCR pipeline we built (so you don't have to)"

**Visual: Pipeline Configs (Cost vs Accuracy Trade-offs)**

```
We maintain 6 production configs:

Config              Cost/Page    Accuracy    Use Case
──────────────────────────────────────────────────────────────
Ultra Cheap         $0.02        87%         High volume, simple docs
├─ OCR: Gemini Lite
├─ Judge: Gemini Lite
└─ Extract: Gemini Lite

Cost Optimized      $0.04        91%         Balanced approach
├─ OCR: GPT-4o Mini
├─ Judge: Gemini Lite
└─ Extract: GPT-4o Mini

Baseline            $0.08        94%         Production default
├─ OCR: GPT-5 Mini + Gemini Flash
├─ Judge: Gemini Flash
└─ Extract: GPT-5

Accuracy Focused    $0.15        97%         Critical documents
├─ OCR: Gemini Flash + GPT-5
├─ Judge: GPT-5 Mini
└─ Extract: GPT-5

Custom              Variable     Variable    Your docs, optimized
└─ Trained on your eval set

All configs use same infrastructure, just different model routing
──────────────────────────────────────────────────────────────
```

**Specs:**

**Models:**
- 8 different roles, optimized individually
- GPT-5, GPT-5 Mini, Gemini 2.5 Flash, Gemini Lite
- Automatic model selection based on document type

**Architecture:**
- LangGraph state machines
- Parallel execution (Send API)
- Type-safe with TypedDict
- Checkpointing & recovery

**Optimizer:**
- Iterative prompt improvement
- Vision-based failure analysis
- Convergence detection
- Per-document-type tuning

**Cost:**
- Baseline: $0.08/page (94% accuracy)
- Ultra Cheap: $0.02/page (87% accuracy)
- Accuracy Focused: $0.15/page (97% accuracy)
- Custom: Optimized for your docs

**Not magic. Just infrastructure.**

[Try it] [See docs] [GitHub (coming soon)]

---

## Objection Handlers

### "I can build this myself"

**Response:**
"Absolutely. Most engineers can. Question is: Should you? 6 weeks of build time + 10 hours/month maintaining as models change. If OCR is core to your business, build it. If it's infrastructure, use ours and ship your product."

---

### "This seems expensive"

**Response:**
"Let's compare:

**Visual: Cost Breakdown (100K pages/year)**

```
DIY Costs (Year 1):
─────────────────────────────────────────
Build Time:     $12,000 ████████████
Maintenance:    $ 9,000 █████████
LLM APIs:       $ 5,000 █████
─────────────────────────────────────────
Total:          $26,000

Plus: Ongoing maintenance every year


DeepRead Costs (Year 1):
─────────────────────────────────────────
Build Time:     $     0
Maintenance:    $     0
All-in:         $10,000 ██████████
─────────────────────────────────────────
Total:          $10,000

Break-even: ~300K pages/year
Below that: We're cheaper + faster
```

**DIY total cost (Year 1):**
- Build time: 160 hours × $75/hr = $12K
- Maintenance: 120 hours × $75/hr = $9K
- LLM API costs: ~$0.05/page
- Total: $21K + API costs

**DeepRead (Year 1):**
- Build time: $0
- Maintenance: $0
- All-in cost: $0.08-0.15/page
- Total: Just usage

Break-even: ~300K pages. Below that, we're cheaper + faster."

---

### "What if you shut down?"

**Response:**
"Fair concern. Two things:

1. **No lock-in:** Standard REST API. Migrate in days, not weeks.
2. **Transparent architecture:** We document exactly what we built. You can replicate it.

Use us to ship fast. Build your own when it makes sense. Both valid strategies."

---

### "How is this different from [competitor]?"

**Response:**
"Most OCR APIs are single-model calls with markup.

We're multi-model consensus with continuous optimization:
- Not 1 model. 6-8 models per document.
- Not static. Re-optimized every model release.
- Not black box. You see the architecture.

Different category. We're infrastructure, not an API wrapper."

---

## Pricing Page Messaging

### Headline
"Pay for pages, not infrastructure"

### Subhead
No setup fees. No maintenance costs. No engineer time wasted.

### Pricing Grid

| Plan | Price | Includes |
|------|-------|----------|
| **Free** | $0 | 1 custom context, 50 pages |
| **Starter** | $99/mo | 1,000 pages, standard pipeline |
| **Growth** | $499/mo | 5,000 pages, premium pipeline |
| **Scale** | $1,999/mo | 25,000 pages, custom optimization |
| **Enterprise** | Custom | Unlimited, dedicated infra |

**All plans include:**
✓ Multi-model consensus
✓ Automatic optimization
✓ Model updates (GPT-5, Gemini, etc.)
✓ Custom context layers
✓ Quality review & flagging

### Below Pricing

**"What you're NOT paying for:**
- 6 weeks of engineering time ($12K+)
- Monthly maintenance (10 hrs × $75/hr = $750/mo)
- Model benchmarking & re-optimization
- LangGraph infrastructure code
- Optimizer development & tuning

**What you ARE paying for:**
- Pages processed. That's it."

---

## FAQ (Short Answers Only)

**Q: Can I build this myself?**
A: Yes. 6-8 weeks + ongoing maintenance. If OCR is your core business, you should. If not, use ours.

**Q: What models do you use?**
A: GPT-5, GPT-5 Mini, Gemini 2.5 Flash, Gemini Lite. Optimized per role (OCR, consensus, extraction, etc.). Updated as new models release.

**Q: How accurate is it?**
A: Depends on your documents. Upload an eval set, we'll tell you exactly. Typical: 90-97%.

**Q: What if I need on-prem?**
A: Enterprise plan. We deploy to your VPC. Or: Build it yourself (we're not the right fit).

**Q: How long to set up?**
A: 15 minutes. Upload eval set → get custom context → make first API call.

**Q: Can I migrate away?**
A: Yes. Standard REST API. No lock-in. Export your data anytime.

**Q: Do you have an SLA?**
A: Growth+: 99.9% uptime. Enterprise: 99.95% + dedicated support.

---

## Key Messaging Rules

### DO:
✅ Be specific (40,000 lines, 6 weeks, 10 hrs/month)
✅ Lead with time savings, not money
✅ Acknowledge they CAN build it
✅ Focus on ongoing maintenance burden
✅ Show technical depth (model names, architecture)
✅ Use "we" not "I" (sounds more established)
✅ Give them an out (when to DIY)

### DON'T:
❌ Claim proprietary magic
❌ Say "revolutionary" or "game-changing"
❌ Hide complexity (show it, then show you solved it)
❌ Use vague benefits ("better accuracy")
❌ Write long paragraphs (bullets only)
❌ Oversell (engineers hate that)
❌ Pretend it's impossible to build

---

## A/B Test Variations

### Headline Test

**A:** "Production OCR infrastructure for developers"
**B:** "The 40,000-line OCR pipeline you'd build, already built"
**C:** "6 weeks to build. Or: Use ours, ship today"
**D:** "Multi-model OCR consensus. Zero maintenance."

**Hypothesis:** B or C will win (most specific)

---

### CTA Test

**A:** [Try it free]
**B:** [Test on your documents]
**C:** [Upload eval set]
**D:** [See the architecture]

**Hypothesis:** B will win (specific action, immediate value)

---

### Social Post Test

**A:** "Production OCR: 40,000 lines of code. You don't have to write them. [link]"
**B:** "You'll build your OCR pipeline in 2 weeks. Then maintain it forever. [link]"
**C:** "Models change quarterly. Your OCR pipeline needs constant re-optimization. We handle it. [link]"

**Hypothesis:** A will win (most concrete)

---

## Launch Messaging (HN Post)

**Title:**
"DeepRead - Production OCR infrastructure (we built the 40K-line pipeline so you don't have to)"

**Post:**
```
Hey HN,

I've watched a dozen teams build the same LLM OCR pipeline:

Week 1: GPT-4V works great
Week 2: Add Gemini for comparison
Week 3: Build consensus logic (which result to trust?)
Week 4: Optimize costs (40% cheaper with smart routing)
Week 5-6: Build optimizer (iterate prompts to 95% accuracy)

Then: Maintain it forever as models change.

We built DeepRead to skip this.

What it is:
- Multi-model consensus (6-8 steps, not 1 API call)
- Automatic optimization (stay current as GPT-5, Gemini improve)
- 40,000 lines of Python (LangGraph, type-safe, tested)

What it's not:
- Proprietary models (we use GPT-5, Gemini, etc.)
- Magic (same LLMs you have access to)
- Lock-in (standard API, migrate anytime)

Use case: You need production OCR but don't want to spend 6 weeks building infrastructure.

Try it: [link]
Architecture: [link]
Questions: Ask here or email [email]

Not for everyone. If you're building an OCR company, you should build this. If OCR is infrastructure for your product, we built it so you don't have to.

Feedback welcome.
```

**Length:** ~1200 chars (HN sweet spot)

---

**Last Updated:** 2025-12-25
