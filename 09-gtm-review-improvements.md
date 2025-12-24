# GTM Plan Deep Review & Improvements

**Review Date:** 2025-12-25
**Reviewer:** Analysis of codebase vs GTM documentation

---

## Executive Summary

The GTM plan is solid but **undersells the product**. After reviewing the codebase, there are critical differentiators not adequately emphasized in the marketing.

**Key Gap:** The **Schema Optimizer** is a massive competitive advantage but barely mentioned in GTM docs.

**Overall Grade:** B+ (execution-ready but missing killer positioning)

---

## Critical Gaps: What's Built But Not Marketed

### 1. The Schema Optimizer (HUGE MISS)

**What It Is:**
Iterative, AI-powered schema/prompt optimization that automatically improves extraction accuracy by 20-30% in 3-5 iterations.

**How It Works:**
```
User uploads 15-20 documents + ground truth
↓
Optimizer runs extraction → analyzes failures with GPT-5 vision
↓
Generates improved prompts with location hints, format rules, edge cases
↓
Re-tests on held-out validation set
↓
Repeats until convergence (95%+ accuracy)
```

**Why It's a Killer Feature:**
- **Saves weeks of manual prompt engineering**
- **Cross-document generalization** (works on mixed sources, not overfitted)
- **Vision-based failure analysis** (understands WHY extraction failed)
- **Excel reports** showing iteration history and field-level improvements
- **Production-ready output** (optimized schema you can use immediately)

**Current GTM Mention:** Barely touched. One sentence in messaging doc: "12K-line optimizer."

**Recommended Fix:** Make this a **primary value prop**, not a technical detail.

---

### 2. Searchable PDF Creation

**What It Is:**
OCR + embedded text layer → searchable PDFs (like Adobe Acrobat's OCR but with LLMs).

**Current GTM Mention:** Zero. Not in positioning, messaging, or use cases.

**Who Cares:**
- Legal teams (search depositions, contracts)
- Compliance (search audit documents)
- Research (search scanned academic papers)

**Recommended Fix:** Add as a secondary use case. "OCR for extraction + searchable PDFs for archival."

---

### 3. Per-Field Confidence Scoring

**What It Is:**
Every extracted field includes:
```json
{
  "vendor": {
    "value": "Acme Corp",
    "human_review": false
  },
  "date": {
    "value": "2024-10-??",
    "human_review": true,
    "reason": "Date partially obscured"
  }
}
```

**Why It Matters:**
- **10x throughput improvement** (90-95% auto-processed, 5-10% human review)
- **Risk management** (flag uncertain extractions, not blind trust)
- **Compliance-friendly** (audit trail of what was reviewed)

**Current GTM Mention:** Mentioned in value prop but not emphasized as a differentiator.

**Recommended Fix:** Lead with "10x throughput" (humans review 5-10%, not 100%).

---

### 4. Multiple Pipeline Configs

**What Exists:**
6 production configs optimized for different cost/accuracy trade-offs:
- Ultra Cheap: $0.02/page, 87% accuracy
- Cost Optimized: $0.04/page, 91% accuracy
- Baseline: $0.08/page, 94% accuracy
- Accuracy Focused: $0.15/page, 97% accuracy
- Custom: Optimized per customer

**Current GTM Mention:** Mentioned in messaging but not in core positioning.

**Recommended Fix:** Emphasize **flexibility** - "One pipeline, 6 configs. Choose cost or accuracy for each job."

---

## What's Documented Well

✅ **Two-phase framework ($0-1M, $1-10M)** - Clear, actionable
✅ **Metrics (5 for Phase 1, 8 for Phase 2)** - Specific, measurable
✅ **Tech stack simplicity** - Start with $25/mo, scale to $3K/mo
✅ **Revenue flows** - Product signals → automation is well-mapped
✅ **Messaging for engineers** - Short, hard-hitting, visual diagrams
✅ **Email templates** - Accuracy report email is solid

---

## Positioning Gaps

### Gap 1: "OCR Infrastructure" Is Too Generic

**Current:**
"Production OCR infrastructure for developers"

**Problem:** Sounds like AWS Textract with extra steps.

**Recommended:**
"Multi-model OCR consensus with auto-optimizing schemas"

**Why Better:**
- **Multi-model consensus** → explains complexity
- **Auto-optimizing** → highlights the optimizer
- **Schemas** → structured extraction, not just text

---

### Gap 2: Missing the "Self-Improving" Angle

**Current Pitch:**
"We built the 50K-line pipeline so you don't have to."

**Missing Opportunity:**
"We built the pipeline AND the AI that continuously improves it."

**The Optimizer Is Self-Improving ML:**
- Analyzes failures with vision models
- Generates better prompts automatically
- Validates on held-out data
- Converges to 95%+ accuracy

**This is AGENTIC AI, not just LLM plumbing.**

---

### Gap 3: Not Positioned Against Manual Prompt Engineering

**Current Competitor:**
Framed as "DIY pipeline" (developers building their own)

**Real Competitor:**
- Developers manually tweaking prompts for weeks
- Teams hiring ML engineers to fine-tune extraction
- Companies building "AI teams" for document processing

**Recommended:**
"Replaces weeks of manual prompt engineering with automated optimization."

---

## Messaging Improvements

### Current Homepage Hero (From 08-messaging.md)
"Production OCR infrastructure for developers"

### Recommended Version 1 (Optimizer-First)
**"Self-optimizing OCR for structured extraction"**

Subhead: "Multi-model consensus + AI that auto-improves prompts. 95% accuracy in 3 iterations, not 3 weeks."

---

### Recommended Version 2 (Engineer-Friendly)
**"OCR infrastructure that optimizes itself"**

Subhead: "50K lines of pipeline code + 12K lines of auto-optimization. Upload docs, get 95% accuracy, ship your product."

---

### Recommended Version 3 (Problem-First)
**"Stop tweaking OCR prompts. Let AI do it."**

Subhead: "Automated schema optimization: 68% → 95% accuracy in 3-5 iterations. Vision-based failure analysis, cross-document generalization, production-ready output."

---

## Updated Value Prop (Recommended)

### Current (From GTM docs):
"Battle-tested infrastructure for best-in-class OCR pipelines. We don't claim magic - we built the infrastructure so you don't have to."

### Recommended:
"Multi-model OCR consensus with auto-optimizing schemas. The 50K-line pipeline you'd build + the AI that continuously improves it."

**Why Better:**
- **Multi-model consensus** → explains the complexity
- **Auto-optimizing schemas** → highlights the killer feature
- **50K lines** → concrete, impressive
- **AI that improves it** → self-improving, not static

---

## New Use Cases to Add

### Use Case 1: Automated Prompt Engineering
**Who:** ML teams spending weeks optimizing extraction prompts
**Problem:** Manual iteration is slow, doesn't generalize across document sources
**Solution:** Upload 20 mixed examples → get optimized schema in hours, not weeks

### Use Case 2: Document Archival (Searchable PDFs)
**Who:** Legal, compliance, research teams
**Problem:** Scanned documents aren't searchable
**Solution:** OCR + embedded text layer → fully searchable PDFs

### Use Case 3: Human-in-the-Loop Workflows
**Who:** Teams that need 99.9% accuracy but can't review 100% of docs
**Problem:** Traditional OCR requires full manual review
**Solution:** Per-field confidence → flag 5-10% for human review, auto-process 90-95%

---

## Competitive Positioning Updates

### Current Framing (From Messaging Doc)
"DeepRead vs DIY" (build it yourself vs use ours)

### Missing Competitive Set

**Real Competitors:**
1. **AWS Textract / Google Document AI** (single-model OCR APIs)
2. **Manual prompt engineering** (internal ML teams)
3. **OCR wrappers** (startups reselling OpenAI Vision with markup)

### Recommended Competitive Matrix

| Feature | AWS Textract | OpenAI Wrapper | DeepRead |
|---------|--------------|----------------|----------|
| Multi-model consensus | ❌ | ❌ | ✅ 2-3 models |
| Auto-optimization | ❌ | ❌ | ✅ 12K LOC optimizer |
| Per-field confidence | ✅ (basic) | ❌ | ✅ (LLM-judge) |
| Custom schemas | ❌ | Manual only | ✅ Auto-optimized |
| Cost optimization | Fixed | Fixed | ✅ 6 configs |
| Searchable PDFs | ❌ | ❌ | ✅ |

**Key Differentiators:**
- **Only DeepRead:** Auto-optimizing schemas (saves weeks)
- **Only DeepRead:** Multi-model consensus with LLM judge
- **Only DeepRead:** 6 cost/accuracy configs (flexible pricing)

---

## Phase 1 Adjustments

### Activation Funnel Update

**Current Flow (From GTM docs):**
```
API Key → Eval Set Upload → Context Built → Accuracy Report → Production Call
```

**Recommended Addition:**
After "Accuracy Report," add optional step:

```
→ Run Optimizer (optional) → Improved Schema → Production Call
```

**Why:**
- Optimizer can be a **conversion driver** ("Your custom schema is 94% accurate. Run optimizer to get to 97%?")
- **Upsell opportunity** (free tier: 1 context, paid tier: unlimited optimizer runs)
- **Retention hook** (users who run optimizer are more invested)

---

### Pricing Updates

**Current Free Tier:**
- 1 custom context
- 50 production API calls

**Recommended Addition:**
- **1 free optimizer run** (limited to 3 iterations, not 5)

**Why:**
- Lets users experience the killer feature
- Creates clear upgrade path ("Need 5 iterations? Upgrade to Pro")
- Differentiates from competitors (no one else has this)

---

## Messaging Document Updates

### Add New Section: "The Optimizer Pitch"

**Headline:**
"Stop tweaking prompts. Let AI do it."

**Visual:**

```
Manual Prompt Engineering:
────────────────────────────────────
Week 1: Write schema → 68% accuracy
Week 2: Analyze failures, guess fixes → 75%
Week 3: More tweaking → 82%
Week 4: Frustrated, ship at 82%
────────────────────────────────────
Total: 4 weeks, 82% accuracy


DeepRead Optimizer:
────────────────────────────────────
Day 1: Upload 20 docs + ground truth
     → Optimizer runs 3-5 iterations
     → Vision-based failure analysis
     → Auto-generated prompt improvements
     → 95% accuracy

Total: 4 hours, 95% accuracy
────────────────────────────────────
```

**CTA:** [Upload your eval set]

---

### Add FAQ: "How is this different from fine-tuning?"

**Q:** Can't I just fine-tune GPT-4 on my documents?

**A:**
Fine-tuning optimizes model weights (expensive, slow, requires ML expertise).

DeepRead optimizer optimizes **prompts** (fast, cheap, no ML expertise needed).

| Approach | Cost | Time | Accuracy Gain | Requires ML Team |
|----------|------|------|---------------|------------------|
| Fine-tuning | $500-5K | Weeks | +5-15% | Yes |
| DeepRead Optimizer | $5-50 | Hours | +20-30% | No |

**Plus:** Prompt optimization transfers across models. Fine-tuning locks you to one model.

---

## Social Media / Launch Updates

### Current HN Post (From Messaging Doc)
"Hey HN, I've watched a dozen teams build the same LLM OCR pipeline..."

### Recommended Revised Opening
"Hey HN, I've watched a dozen teams waste weeks manually optimizing OCR prompts..."

**Why:**
- Leads with the **optimizer** (the differentiator)
- More specific pain point (prompt engineering vs infrastructure)
- Sets up the optimizer as the solution

### Add This Paragraph
"The real insight: extraction accuracy isn't about the model (GPT-5 vs Gemini). It's about the prompts. We built an optimizer that uses GPT-5 vision to analyze extraction failures and automatically generates better prompts. 68% → 95% in 3-5 iterations. Works for any document type."

---

## Email Template Updates

### Accuracy Report Email (THE MONEY EMAIL)

**Current:**
```
Your custom context is ready.

Results:
→ DeepRead: 94% accurate
→ Generic OCR: 78% accurate

Next: Make your first production call.
```

**Recommended Addition:**
```
Want to improve to 97%?

Run the Optimizer:
→ Upload 20 representative documents
→ We'll analyze failures with GPT-5 vision
→ Auto-generate improved prompts
→ Get 95-97% accuracy in 3-5 iterations

[Run Optimizer] ← New CTA
[Use Current Schema] ← Existing CTA
```

**Why:**
- Introduces the optimizer at high-engagement moment
- Creates upsell path ("Optimizer requires Pro plan")
- Positions DeepRead as more than infrastructure

---

## Technical Documentation Gaps

### Gap 1: No Public Optimizer Docs

**Issue:** Optimizer is internal-only documented. Customers can't learn about it.

**Recommended:** Create `docs/optimizer-guide.md` with:
- What it is, how it works
- Step-by-step tutorial
- Example improvements (before/after prompts)
- Best practices (how many docs to upload, ground truth format)

---

### Gap 2: Benchmarking Results Not Shared

**Issue:** You have benchmark data (small/medium/large test sets) but don't publish results.

**Recommended:** Create public benchmarks page:
- Invoice benchmark: 94% accuracy (10 models tested)
- Receipt benchmark: 91% accuracy
- Medical forms: 89% accuracy
- Show model comparisons (GPT-5 vs Gemini vs Claude)

**Why:**
- **Trust:** Engineers trust data more than claims
- **SEO:** "OCR accuracy benchmark" searches
- **Content marketing:** "We benchmarked 10 OCR models. Here's what we found."

---

## Key Metrics Updates

### Add Optimizer Metrics (Phase 1)

**New Metric:** Optimizer Adoption Rate
- **Definition:** % of users who run optimizer after first production call
- **Target:** ≥20%
- **Why it matters:** Optimizer users have higher retention + ARPU

**New Metric:** Optimizer NPS
- **Definition:** "How likely are you to recommend the optimizer?"
- **Target:** ≥50
- **Why it matters:** If optimizer NPS > product NPS, make it the hero

---

## Roadmap Suggestions (Not GTM, But Affects Messaging)

### Feature 1: Optimizer as a Service
**Idea:** Let users run optimizer via API, not just dashboard
**Why:** Enables programmatic optimization in CI/CD pipelines
**Messaging Impact:** "Optimization in your deployment pipeline"

### Feature 2: Optimizer Marketplace
**Idea:** Share optimized schemas for common document types (invoices, receipts, W2s)
**Why:** Instant value, network effects
**Messaging Impact:** "Pre-optimized schemas for 50+ document types"

### Feature 3: Optimizer Analytics
**Idea:** Track which prompt changes had biggest accuracy impact
**Why:** Helps users understand what works
**Messaging Impact:** "Learn which prompt patterns improve accuracy"

---

## Action Items (Prioritized)

### High Priority (Do This Week)

1. **Update homepage hero to mention optimizer**
   - Current: "Production OCR infrastructure"
   - New: "Self-optimizing OCR for structured extraction"

2. **Add optimizer section to messaging doc**
   - Include visual diagram (manual vs automated)
   - Add to pricing tiers (free tier: 1 run, paid: unlimited)

3. **Update accuracy report email**
   - Add optimizer CTA after showing results
   - Position as upgrade path

4. **Create public optimizer docs**
   - Tutorial: "Optimize your schema in 15 minutes"
   - Include before/after prompt examples

---

### Medium Priority (Next 2 Weeks)

5. **Add optimizer to core value prop**
   - Update all GTM docs to emphasize it

6. **Create competitive matrix**
   - DeepRead vs AWS Textract vs OpenAI wrappers
   - Highlight optimizer as unique differentiator

7. **Add searchable PDF use case**
   - Legal/compliance positioning
   - Example: "Search 10K scanned contracts in seconds"

8. **Publish benchmark results**
   - Invoice, receipt, medical form accuracy
   - Model comparisons (GPT-5 vs Gemini vs Claude)

---

### Low Priority (Next Month)

9. **Create optimizer case study**
   - "How [Company] improved extraction from 72% to 96% in 3 hours"

10. **Add optimizer to free tier**
    - 1 free run (3 iterations max)
    - Clear upgrade path for more runs

11. **Update demo video**
    - Show optimizer in action
    - Before/after prompt comparison

12. **Create HN launch post v2**
    - Lead with optimizer, not infrastructure
    - Include benchmark data

---

## Conclusion

**What's Working:**
- Two-phase framework is clear
- Metrics are specific and actionable
- Tech stack guidance prevents over-engineering
- Messaging for engineers is honest and technical

**What's Missing:**
- **Optimizer not positioned as killer feature** (it should be #1 differentiator)
- Searchable PDF capability not marketed
- Per-field confidence not emphasized enough
- Competitive positioning too narrow (DIY only, not AWS/OpenAI)

**Quick Win:**
Update homepage to: **"Self-optimizing OCR for structured extraction"**
Add one paragraph about the optimizer to every page.

**Big Opportunity:**
Make the optimizer the hero. It's your moat. AWS can't build this. OpenAI wrappers don't have it. It saves weeks of manual work and is genuinely innovative.

---

**Bottom Line:** You built something more valuable than you're claiming. The GTM docs sell "infrastructure" when you should be selling "infrastructure + AI that optimizes it." Fix the positioning, emphasize the optimizer, and you'll differentiate from every competitor.

---

**Next Steps:**
1. Review this doc
2. Decide which improvements to prioritize
3. Update messaging.md with optimizer-first positioning
4. Rewrite homepage hero
5. Add optimizer to accuracy report email

**Timeline:** 1-2 weeks to update all GTM materials.

---

**Last Updated:** 2025-12-25
