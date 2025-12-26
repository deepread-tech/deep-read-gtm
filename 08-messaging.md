# DeepRead Messaging Guide

**Principle:** Engineers don't read. They scan. Make every word count.

---

## Core Value Prop (Pick One)

### Option A: Optimizer-First (RECOMMENDED)
**"Self-optimizing OCR for structured extraction"**

Subhead: "Multi-model consensus + AI that auto-improves prompts. 95% accuracy in 3 iterations, not 3 weeks."

### Option B: Engineer Problem-Focused
**"Stop tweaking OCR prompts. Let AI do it."**

Subhead: "Automated schema optimization: 68% → 95% in 3-5 iterations. Vision-based failure analysis, cross-document generalization, production-ready output."

### Option C: The Infrastructure + AI Angle
**"OCR infrastructure that optimizes itself"**

Subhead: "50K lines of pipeline code + 12K lines of auto-optimization. Upload docs, get 95% accuracy, ship your product."

### Option D: The Honest One
**"Yes, you can build this. It's 6 weeks + ongoing maintenance. Or use ours."**

---

## Homepage Messaging

### Hero Section

**Headline:**
"Self-optimizing OCR for structured extraction"

**Subhead:**
"Multi-model consensus + AI that auto-improves prompts. 95% accuracy in 3 iterations, not 3 weeks."

**CTA:**
[Upload your eval set] [See how it works]

---

### Above the Fold

**3 Bullet Points (max):**

✓ **Auto-optimizing schemas** - AI analyzes failures, generates better prompts (68% → 95% in hours)
✓ **Multi-model consensus** - 6-8 specialized steps with LLM-judge voting
✓ **10x throughput** - Flag 5-10% for human review, auto-process 90-95%

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

## The Optimizer Pitch (Primary Differentiator)

### Headline
**"Stop tweaking prompts. Let AI do it."**

### Visual: Manual vs Automated

```
Manual Prompt Engineering:
─────────────────────────────────────────────────────
Week 1: Write schema
       → Run extraction → 68% accuracy
       → Analyze failures manually
       → Guess what's wrong

Week 2: Update prompts
       → Re-run extraction → 75% accuracy
       → More manual analysis
       → More guessing

Week 3: Keep tweaking
       → Re-run extraction → 82% accuracy
       → Frustrated, ship it

Total: 3 weeks, 82% accuracy, lots of guessing
─────────────────────────────────────────────────────


DeepRead Schema Optimizer:
─────────────────────────────────────────────────────
Hour 1: Upload 20 documents + ground truth

Hour 2-4: Optimizer runs automatically:
         → Iteration 1: 68% → GPT-5 vision analyzes failures
         → Iteration 2: 78% → Auto-generates better prompts
         → Iteration 3: 89% → Tests on held-out validation
         → Iteration 4: 95% → Converged

Total: 4 hours, 95% accuracy, zero guessing
─────────────────────────────────────────────────────

Difference: 3 weeks vs 4 hours. 82% vs 95%.
```

### How It Works

**1. Vision-Based Failure Analysis**
```
Traditional: "Field 'invoice_date' extracted wrong. Why?"
You: Stare at the PDF, guess what went wrong

DeepRead Optimizer:
→ GPT-5 vision examines the actual PDF
→ "The date is in MM/DD/YYYY format, but your schema expects YYYY-MM-DD"
→ "The label says 'Date' not 'Invoice Date'"
→ Auto-generates improved prompt with location hints
```

**2. Cross-Document Generalization**
```
Traditional: Optimize on one vendor's invoices
Result: Works great for Vendor A, fails on Vendor B

DeepRead Optimizer:
→ Trains on 20 mixed-source documents
→ Validates on held-out test set
→ Generates prompts that handle variations
Result: Works across all vendors
```

**3. Iterative Improvement Loop**
```
Start: Basic schema (vendor, date, total)
↓
Iteration 1: Extract → Accuracy 68%
           → Vision analysis identifies failures
           → "Date field: Add format hint, common labels"
↓
Iteration 2: Re-extract with improved prompts → 78%
           → "Total field: Look near 'Amount Due', 'Balance'"
↓
Iteration 3: Re-extract → 89%
           → "Vendor: Check header AND footer"
↓
Iteration 4: Re-extract → 95%
           → Converged (improvement <2%)
↓
Done: Production-ready schema
```

### What You Get

**Optimized Schema:**
```json
{
  "invoice_date": {
    "type": "string",
    "format": "date",
    "description": "Invoice date in YYYY-MM-DD format. Common labels: 'Invoice Date', 'Date', 'Billing Date'. Usually in header near invoice number. Formats vary: MM/DD/YYYY, DD/MM/YYYY, spelled out."
  },
  "vendor_name": {
    "type": "string",
    "description": "Vendor/company name. Check: Header (top-left or center), footer, remittance section. May include legal suffixes (LLC, Inc). Ignore 'Bill To' or customer names."
  }
}
```

**Improvement Report:**
```
Baseline Accuracy: 68%
Final Accuracy: 95%
Improvement: +27 percentage points

Field-Level Improvements:
- invoice_date: 0% → 100% (+100%) - Added format hints and label variations
- vendor_name: 40% → 90% (+50%) - Added location hints (header/footer)
- total_amount: 80% → 100% (+20%) - Added nearby label context
- account_number: 90% → 95% (+5%) - Added OCR error handling

Iterations: 4
Time: 3.2 hours
Cost: $8.40
```

### The Moat

**Why competitors can't copy this:**

1. **Vision-based analysis** - Requires tight integration between vision models and extraction pipeline
2. **Cross-validation** - Need held-out test sets, proper train/test splits
3. **Convergence detection** - Know when to stop (avoid overfitting)
4. **Prompt engineering expertise** - Codified 2 years of learnings
5. **Production pipeline integration** - Optimized schemas work in production immediately

**AWS Textract:** No optimization (fixed prompts)
**OpenAI wrappers:** Manual prompt tweaking only
**DeepRead:** Automated optimization with vision-based failure analysis

### Use Cases

**1. New Document Type**
- Upload 20 examples → Get 95% schema in hours
- No manual prompt engineering
- Production-ready immediately

**2. Accuracy Below Target**
- Current schema: 82% accurate
- Run optimizer → 95% in 3-4 iterations
- Learn which prompts work

**3. Multi-Vendor Documents**
- Invoices from 10 different vendors
- Train on mixed set → General schema that handles all
- No per-vendor customization needed

### CTA

[Upload your eval set] [See example improvements]

---

## Social Media / HN / Twitter

### Version 1: Optimizer-First (RECOMMENDED)
"Stop manually tweaking OCR prompts. We built AI that optimizes them automatically. 68% → 95% accuracy in 4 hours using GPT-5 vision-based failure analysis. [link]"

**Length:** 167 chars

---

### Version 2: Problem-Focused
"You: Stare at PDFs, guess why extraction failed, tweak prompts, repeat for weeks. DeepRead Optimizer: GPT-5 vision analyzes failures, auto-generates better prompts. 95% in hours. [link]"

**Length:** 188 chars

---

### Version 3: Time Savings
"Manual prompt engineering: 3 weeks to hit 82% extraction accuracy. DeepRead Optimizer: 4 hours to hit 95%. Vision-based failure analysis, cross-document generalization. [link]"

**Length:** 178 chars

---

### Version 4: The Moat
"AWS Textract: Fixed prompts. OpenAI wrappers: Manual tweaking. DeepRead: AI optimizer that uses GPT-5 vision to analyze extraction failures and auto-generate better prompts. [link]"

**Length:** 182 chars

---

### Version 5: HN-Specific (Technical)
"Built an AI optimizer for OCR extraction schemas. Uses GPT-5 vision to analyze why extractions fail, auto-generates improved prompts with location hints/format rules. 68%→95% in 3-4 iterations. Plus the 50K-line multi-model consensus pipeline. [link]"

**Length:** 250 chars

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

────────────────────────────────────────

Want to push to 97-98%?

Run the Schema Optimizer:
→ Upload 20 representative documents + ground truth
→ AI analyzes extraction failures with GPT-5 vision
→ Auto-generates improved prompts (location hints, format rules)
→ Get 95-98% accuracy in 3-4 iterations (4 hours, not 3 weeks)

[Run Optimizer] ← Primary CTA
[Use Current Context (94%)] ← Secondary CTA

────────────────────────────────────────

Or start with what you have:

```python
import deepread
result = deepread.ocr("invoice.pdf", context_id="ctx_abc123")
```

Questions? Reply to this email.

Best,
[Founder]

P.S. The optimizer uses GPT-5 vision to understand WHY extractions fail
(wrong format? label variations? OCR errors?) and automatically
generates better prompts. It's like having an ML engineer optimize
your schema for you.
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
| Week 5-6: Build optimizer | ✅ AI optimizer included |
| Weeks 7+: Manual prompt tweaking | ✅ Automated optimization |
| Ongoing: 10hrs/month maintenance | ✅ We maintain it |
| Model updates: Your problem | ✅ Always on latest models |
| **Total time:** 8+ weeks + forever | **Total time:** 4 hours |

**When to DIY:**
- You're building an OCR company
- You process >10M pages/month
- You need on-prem/air-gapped
- OCR is your core IP

**Otherwise:** Use DeepRead. Ship your product.

---

### Competitive Positioning Matrix

| Feature | AWS Textract | OpenAI Wrapper | DeepRead |
|---------|--------------|----------------|----------|
| **Schema Optimization** | ❌ Manual only | ❌ Manual only | ✅ **Automated AI optimizer** |
| **Vision-based Failure Analysis** | ❌ | ❌ | ✅ GPT-5 analyzes PDFs |
| **Multi-model Consensus** | ❌ Single model | ❌ Single model | ✅ 2-3 models + judge |
| **Per-field Confidence** | ✅ Basic scores | ❌ None | ✅ LLM-judge flags |
| **Cost Optimization** | ❌ Fixed pricing | ❌ Fixed markup | ✅ 6 configs ($0.02-$0.15) |
| **Searchable PDFs** | ❌ | ❌ | ✅ OCR + text layer |
| **10x Throughput** | ❌ | ❌ | ✅ Flag 5-10%, auto-process 90% |

**Key Differentiator:**
Only DeepRead has automated schema optimization with vision-based failure analysis. Saves 3 weeks of manual prompt engineering per document type.

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

| Plan | Price | Pages/mo | Schema Optimizer | Pipelines |
|------|-------|----------|------------------|-----------|
| **Free** | $0 | 50 | 1 run (3 iterations) | Standard only |
| **Starter** | $99/mo | 1,000 | 3 runs/month | Standard + Searchable |
| **Growth** | $499/mo | 5,000 | **Unlimited** | All pipelines + configs |
| **Scale** | $1,999/mo | 25,000 | **Unlimited** | All + priority support |
| **Enterprise** | Custom | Unlimited | **Unlimited** | Dedicated infra |

**All plans include:**
✓ **AI Schema Optimizer** (vision-based failure analysis)
✓ Multi-model consensus (GPT-5 + Gemini)
✓ Per-field confidence scoring
✓ Model updates (GPT-5, Gemini, Claude)
✓ Custom context layers
✓ 10x throughput (flag 5-10% for human review)

### Feature Breakdown by Plan

**Free:**
- Test the optimizer (1 run, max 3 iterations)
- Evaluate on your documents
- Export optimized schema

**Starter ($99/mo):**
- Limited optimizer runs (3/month)
- Good for 1-2 document types
- Production-ready extraction

**Growth ($499/mo):**
- **Unlimited optimizer runs** ← Most popular
- Multiple document types
- All 6 cost/accuracy configs
- Searchable PDF creation

**Scale/Enterprise:**
- Everything in Growth
- Higher volume
- Priority support
- Custom SLAs

### Below Pricing

**"What you're NOT paying for:**
- 3 weeks per document type (manual prompt engineering)
- 6 weeks of pipeline development ($12K+)
- Monthly maintenance (10 hrs × $75/hr = $750/mo)
- Model benchmarking & re-optimization
- ML engineer to tune your schemas

**What you ARE paying for:**
- Pages processed
- Schema optimization runs
- That's it."

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
"DeepRead - AI that optimizes OCR extraction schemas automatically (vision-based failure analysis)"

**Post:**
```
Hey HN,

I've watched a dozen teams waste weeks manually optimizing OCR extraction prompts.

The problem:
- You write a schema → 68% extraction accuracy
- You stare at PDFs, guess why it failed
- You tweak prompts, re-run → 75%
- Repeat for 2-3 weeks → Ship at 82%

We built an AI optimizer that does this automatically.

How it works:
1. Upload 20 documents + ground truth
2. GPT-5 vision analyzes extraction failures on the actual PDFs
   ("Date is MM/DD/YYYY but schema expects YYYY-MM-DD")
3. Auto-generates improved prompts with location hints, format rules
4. Validates on held-out test set (cross-document generalization)
5. Repeats until convergence (3-5 iterations)

Result: 68% → 95% in 4 hours, not 3 weeks.

Plus we built the 50K-line multi-model consensus pipeline (GPT-5 + Gemini,
LLM-judge voting, per-field confidence, 6 cost/accuracy configs).

What it's not:
- Fine-tuning (we optimize prompts, not model weights)
- Proprietary models (same LLMs you have access to)
- Lock-in (export optimized schemas, use anywhere)

The optimizer is the differentiator. AWS Textract doesn't have it. OpenAI
wrappers don't have it. It saves 3 weeks of manual work per document type.

Try it: [link]
Optimizer docs: [link]
Questions: Ask here or email [email]

Feedback welcome - especially interested in what document types you're
struggling with.
```

**Length:** ~1400 chars

---

**Last Updated:** 2025-12-25
