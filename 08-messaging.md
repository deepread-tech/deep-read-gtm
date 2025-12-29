# DeepRead Messaging Guide

**Principle:** Engineers don't read. They scan. Make every word count.

---

## Core Value Prop

**"Extract structured data from documents"**

Subhead: "95% accuracy. 5 minutes to integrate. Optimizes itself."

---

## Positioning

**Primary:** Developer-first OCR API with AI schema optimization

**One-liner:** "Managed OCR infrastructure that optimizes itself"

**What makes us different:**
The Schema Optimizer. Upload 20 docs → AI analyzes failures → generates better prompts → 95% accuracy on YOUR documents.

Competitors fix errors per-document or learn passively. We actively train on your data and create a reusable optimized schema.

---

## vs Competitors

| Feature | Reducto | Extend.ai | Rossum | DeepRead |
|---------|---------|-----------|--------|----------|
| **Approach** | Real-time self-correction per doc | Passive learning over time | Enterprise workflow platform | **Active schema optimization** |
| **Accuracy** | 99%+ | 99%+ | High | 90-97% (on YOUR docs) |
| **Developer API** | ✅ | ✅ | Limited | ✅ |
| **Custom Training** | ❌ | ✅ (passive) | ✅ (enterprise) | ✅ **Vision-based optimizer** |
| **Price** | API-first | API-first | $18K+/year | $0.08-0.15/page |
| **Best for** | Real-time accuracy | Passive improvement | Enterprise workflows | **Optimizing for your document types** |

**The Differentiator:**
- Reducto: Fixes each document individually (great for one-offs)
- Extend.ai: Learns passively as you use it (gradual improvement)
- Rossum: Full enterprise IDP platform (workflows, not just API)
- **DeepRead: Active optimizer trains on your eval set, creates reusable schema (95% in 4 hours)**

---

## Homepage Messaging

### Hero Section

**Headline:**
"Extract structured data from documents"

**Subhead:**
"95% accuracy. 5 minutes to integrate."

**Differentiator:**
Unlike Reducto or Extend.ai, trains an AI optimizer on YOUR docs to create a reusable schema.

**Code Sample (Show immediately):**
```bash
curl https://api.deepread.com/ocr \
  -H "Authorization: Bearer dr_xxx" \
  -F "file=@invoice.pdf"
```

**CTA:**
[Try it now] [View docs]

---

### Above the Fold

**3 Bullet Points (max):**

✓ **Automatic schema optimization** - 68% → 95% accuracy, no prompt tweaking
✓ **Production-ready infrastructure** - Multi-model consensus, cost routing included
✓ **Works on your documents** - Trains on your data, adapts to your formats

---

## What's Included

**Production OCR Infrastructure:**
- Multi-model consensus (GPT-5 + Gemini)
- Automatic cost optimization
- Per-field confidence scoring
- Quality flagging for human review

**AI Schema Optimizer:**
- Vision-based failure analysis
- Automatic prompt improvement
- Trains on your documents
- 68% → 95% accuracy in hours

**Always Updated:**
- New model releases integrated automatically
- Cost routing optimized as prices change
- No maintenance required

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

1. **Vision-based analysis** - Tight integration between vision models and extraction pipeline
2. **Cross-validation** - Proper train/test splits prevent overfitting
3. **Convergence detection** - Automatically know when to stop optimizing
4. **Prompt engineering patterns** - Automated discovery of what works across document types
5. **Production pipeline integration** - Optimized schemas work immediately, no translation needed

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

"OCR that optimizes itself. Upload docs → 95% accuracy in 4 hours. No prompt engineering. [link]"

**Length:** 95 chars

---

## Email Subject Lines

### Welcome Email
"Your DeepRead API key"

### Accuracy Report
"94% accuracy on your docs"

### Re-engagement (Inactive Users)
"Your context is still ready"

### Upsell (High Volume Users)
"8,000 pages this week – let's optimize"

### Model Update Announcement
"GPT-5.5 is live (already integrated)"

### Churn Prevention
"What can we improve?"

---

## Email Body Templates

### Welcome Email (Day 0)

**Subject:** Your DeepRead API key

**Body:**
```
Your API key: dr_xxxxxx

Quick start:
curl https://api.deepread.com/ocr \
  -H "Authorization: Bearer dr_xxxxxx" \
  -F "file=@document.pdf"

Want 95% accuracy on YOUR docs?
Upload 20 samples → Get optimized schema in 4 hours
[Upload eval set]

Docs: deepread.com/docs
Questions? Hit reply.
```

---

### Accuracy Report Email (THE MONEY EMAIL)

**Subject:** 94% accuracy on your docs

**Body:**
```
Your context is ready: ctx_abc123

Results on YOUR documents:
→ 94% accurate (vs 78% generic OCR)
→ Tested on 50 of your files

Use it now:
curl https://api.deepread.com/process \
  -H "Authorization: Bearer dr_xxx" \
  -F "file=@invoice.pdf" \
  -F "context_id=ctx_abc123"

Want 97%+ accuracy?
Run the optimizer on 20 more docs → 4 hours
[Optimize further]

Questions? Hit reply.
```

---

### Re-engagement Email (14 Days Inactive)

**Subject:** Your context is still ready

**Body:**
```
Your context: ctx_abc123 (still active)

Ready when you are.

Questions? Hit reply.
```

---

## Website Copy Blocks

### Feature Comparison

| Feature | DeepRead |
|---------|----------|
| Multi-model consensus | ✅ GPT-5 + Gemini |
| AI schema optimizer | ✅ Vision-based failure analysis |
| Cost optimization | ✅ 6 configs ($0.02-$0.15/page) |
| Automatic updates | ✅ New models integrated automatically |
| Per-field confidence | ✅ LLM-judge scoring |
| Integration time | 5 minutes |
| Maintenance required | Zero |

---

### Developer OCR API Comparison

| Feature | Reducto | Extend.ai | DeepRead |
|---------|---------|-----------|----------|
| **Optimization** | Real-time per-doc | Passive learning | **Active schema training** |
| **Accuracy** | 99%+ | 99%+ | 90-97% (on YOUR docs) |
| **Training** | None | Automatic | **Upload eval set** |
| **Output** | Fixed per document | Improves over time | **Reusable optimized schema** |
| **Speed** | Real-time | Gradual | **95% in 4 hours** |
| **API** | ✅ | ✅ | ✅ |
| **Price** | API-first | API-first | $0.08-0.15/page |

**When to use:**
- **Reducto**: Need 99%+ on each document immediately
- **Extend.ai**: Passive improvement is fine, high volume
- **DeepRead**: Want to optimize for specific document types quickly

---

### The Technical Details Section

**Headline:** What's actually running

**Visual: One API Call = Complete Pipeline**

```
Your code:
────────────────────────────────────────
result = deepread.ocr("invoice.pdf")
────────────────────────────────────────

What actually runs:
────────────────────────────────────────

┌─ Pre-processing
│  ├─ PDF → Images (300 DPI)
│  ├─ Rotation Detection
│  └─ Optimization
│
├─ Multi-Model OCR
│  ├─ Primary: GPT-5 Mini ────┐
│  ├─ Secondary: Gemini Flash ─┤
│  ├─ Consensus Judge ─────────┤→ Pick Best
│  └─ Resolve Discrepancy ─────┘
│
├─ Extraction
│  ├─ Field Detection
│  ├─ Location Hints
│  ├─ Extraction (GPT-5)
│  └─ Cross-Validation
│
├─ Quality Review
│  ├─ Confidence Scoring
│  ├─ Flag Uncertain Fields
│  └─ Human Review Queue
│
├─ AI Optimizer
│  ├─ Vision-Based Failure Analysis
│  ├─ Automated Prompt Improvement
│  ├─ Convergence Detection
│  └─ Cross-Document Validation
│
└─ Infrastructure
   ├─ LangGraph Orchestration
   ├─ Cost Tracking & Routing
   ├─ Retry Logic
   └─ Monitoring

6 integrated systems, battle-tested in production
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

**Total:** 6 integrated systems, production-ready.

---

## Landing Page Variations

### For Technical Evaluators

**Headline:**
"Production OCR infrastructure"

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

## FAQ

### "Can I self-host?"

Enterprise plan includes deployment to your VPC. Otherwise, we're fully managed.

---

### "What's the pricing?"

$0.08-0.15/page depending on accuracy tier. Free tier: 100 pages/month.

See full pricing: deepread.com/pricing

---

### "Is there lock-in?"

Standard REST API. Export your optimized schemas anytime.

---

### "How is this different from AWS Textract?"

**Textract:** Fixed prompts, no optimization
**DeepRead:** AI optimizer that improves accuracy on your documents automatically

---

## Pricing Page Messaging

### Headline
"Pay for pages, not infrastructure"

### Subhead
No setup fees. No maintenance costs. No engineer time wasted.

### Pricing Grid

| Plan | Price | Pages/mo | Schema Optimizer | Pipelines |
|------|-------|----------|------------------|-----------|
| **Free** | $0 | 100 | 1 run (3 iterations) | Standard only |
| **Starter** | $99/mo | 1,000 | 3 runs/month | Standard + Searchable |
| **Growth** | $499/mo | 5,000 | **Unlimited** | All pipelines + configs |
| **Scale** | $1,999/mo | 25,000 | **Unlimited** | All + priority support |
| **Enterprise** | Custom | Unlimited | **Unlimited** | Dedicated infra |

**All plans include:**
✓ **AI Schema Optimizer** (vision-based failure analysis)
✓ Multi-model consensus (GPT-5 + Gemini)
✓ Per-field confidence scoring
✓ Model updates (GPT-5, Gemini, Claude)
✓ Custom contexts
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

### Pricing Details

**What's included:**
- Pages processed
- AI schema optimizer
- Multi-model pipeline
- Automatic updates
- No maintenance required

---

## FAQ

**Q: How is this different from Reducto/Extend.ai?**
A: They fix errors per-document (Reducto) or learn passively (Extend.ai). We actively train an optimizer on your eval set to create a reusable schema. 95% accuracy in 4 hours.

**Q: What models do you use?**
A: GPT-5, GPT-5 Mini, Gemini 2.5 Flash, Gemini Lite. Automatically updated when new models release.

**Q: How accurate is it?**
A: 90-97% typical. Upload your documents and we'll tell you exactly.

**Q: On-premise deployment?**
A: Available on Enterprise plan. We deploy to your VPC.

**Q: How long to integrate?**
A: 5 minutes. Standard REST API.

**Q: Is there lock-in?**
A: No. Export your optimized schemas anytime.

**Q: SLA?**
A: Growth+: 99.9% uptime. Enterprise: 99.95% + dedicated support.

---

## Key Messaging Rules

### DO:
✅ Be specific (95% accuracy, 4 hours, 5 minutes to integrate)
✅ Show code immediately (curl examples, not paragraphs)
✅ Lead with outcomes, not how it works
✅ Use concrete numbers over explanations
✅ Show technical depth when asked (model names, architecture)
✅ Make trying it frictionless

### DON'T:
❌ Defend why they shouldn't build it themselves
❌ Use marketing buzzwords ("revolutionary," "game-changing")
❌ Explain complexity to justify value
❌ Write long paragraphs (engineers scan, not read)
❌ Talk about "lines of code"
❌ Be defensive about alternatives

---

## A/B Test Variations

### Recommended Headline
"Production OCR infrastructure"

**Alternative:** "Extract structured data from documents"

### Recommended CTA
[Try it now] or [Test on your documents]

### Recommended Social Post
"OCR that optimizes itself. 95% accuracy in 4 hours. No prompt engineering. [link]"

---

## Launch Messaging (HN Post)

**Title:**
"DeepRead – OCR that optimizes itself"

**Post:**
```
Hey HN,

I got tired of manually tweaking OCR extraction prompts for weeks to hit 80% accuracy.

So we built an AI optimizer that does it automatically.

Upload 20 documents → GPT-5 vision analyzes why extractions fail →
Auto-generates better prompts → 95% accuracy in 4 hours.

How it's different:
- Reducto: Fixes errors per-document in real-time (great for one-offs)
- Extend.ai: Learns passively as you use it (gradual)
- DeepRead: Actively trains on your eval set, creates reusable schema (95% in 4 hours)

Also includes production pipeline: multi-model consensus (GPT-5 + Gemini),
cost routing, confidence scoring.

Try it: [link]
Docs: [link]

What document types are you extracting from?
```

**Length:** ~750 chars

---

**Last Updated:** 2025-12-29
