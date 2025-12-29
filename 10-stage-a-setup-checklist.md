# Stage A Setup Checklist - 2-Day Sprint

**Timeline:** 2 days
**Goal:** Set up complete product-to-revenue automation stack for self-serve motion  
**Total Cost:** $25-265/mo (can start at $0)

**Prerequisites:**
- Basic coding knowledge (JavaScript/Python)
- Access to your application codebase
- 2 full days of focused work
- YouTube tutorials linked for each tool (watch as you go)

---

## Day 1: Core Foundation (8-10 hours)

### Morning (3-4 hours): PostHog + HubSpot

#### PostHog Setup (1.5-2 hours)

**📺 Tutorials:**
- [PostHog Official Channel](https://www.youtube.com/@PostHog) - Official tutorials and guides
- Search YouTube: "PostHog setup tutorial 2024" for most recent videos
- [PostHog Docs: Quick Start](https://posthog.com/docs/getting-started/install)

**Account Setup (15 min):**
- [ ] Create PostHog account: https://posthog.com/signup (free tier: 1M events/month)
- [ ] Create new project
- [ ] Copy Project API Key

**Install SDK (15 min):**
- [ ] Install PostHog SDK:
  - JavaScript/React: `npm install posthog-js`
  - Python: `pip install posthog`
  - Node.js: `npm install posthog-node`
- [ ] Initialize PostHog in your app:
  ```javascript
  import posthog from 'posthog-js'
  
  posthog.init('YOUR_PROJECT_API_KEY', {
    api_host: 'https://app.posthog.com'
  })
  ```

**Event Instrumentation (1 hour):**
- [ ] Implement `account_created` event (when user signs up):
  ```javascript
  posthog.capture('account_created', {
    user_id: user.id,
    email: user.email,
    source: 'docs' // or 'homepage', 'signup_page'
  });
  ```

- [ ] Implement `api_key_created` event (when API key is generated):
  ```javascript
  posthog.capture('api_key_created', {
    user_id: user.id,
    email: user.email
  });
  ```

- [ ] Implement `context_created` event (when optimizer completes):
  ```javascript
  posthog.capture('context_created', {
    user_id: user.id,
    context_id: context.id,
    baseline_accuracy: context.baseline_accuracy,
    final_accuracy: context.final_accuracy,
    improvement: context.improvement,
    cost: context.total_cost,
    iterations: context.iterations_run
  });
  ```

- [ ] Implement `accuracy_report_email_sent` event (if email provided):
  ```javascript
  posthog.capture('accuracy_report_email_sent', {
    user_id: user.id,
    context_id: context.id,
    email: user.email
  });
  ```

- [ ] Implement `first_process_call` event (first successful /process call):
  ```javascript
  posthog.capture('first_process_call', {
    user_id: user.id,
    context_id: context.id,
    pages_processed: 1
  });
  ```

- [ ] Implement `volume_milestone` event (for usage tracking):
  ```javascript
  posthog.capture('volume_milestone', {
    user_id: user.id,
    total_pages: 100 // or 500, 1000, etc.
  });
  ```

**Quick Test (15 min):**
- [ ] Trigger each event manually
- [ ] Verify events appear in PostHog dashboard
- [ ] Check event properties are captured

---

#### HubSpot CRM Setup (1.5-2 hours)

**📺 Tutorials:**
- [HubSpot Academy YouTube](https://www.youtube.com/@HubSpot) - Official HubSpot training
- Search YouTube: "HubSpot CRM free setup tutorial 2024" for most recent videos
- [HubSpot Academy: Free CRM Course](https://academy.hubspot.com/courses/free-crm)

**Account Setup (10 min):**
- [ ] Create HubSpot free account: https://www.hubspot.com/products/crm
- [ ] Complete account setup wizard
- [ ] Navigate to Settings → Properties

**Custom Properties Creation (30 min):**
- [ ] Go to Settings → Properties → Contact Properties
- [ ] Create these properties (click "Create property" for each):
  - [ ] `activation_status` (Type: Dropdown)
    - Options: account_created, api_key_created, context_created, first_process_call, recurring_user
  - [ ] `account_created_date` (Type: Date)
  - [ ] `api_key_created_date` (Type: Date)
  - [ ] `context_created_date` (Type: Date)
  - [ ] `context_id` (Type: Text)
  - [ ] `baseline_accuracy` (Type: Number)
  - [ ] `final_accuracy` (Type: Number)
  - [ ] `improvement` (Type: Number)
  - [ ] `optimizer_cost` (Type: Number)
  - [ ] `first_process_call_date` (Type: Date)
  - [ ] `total_pages_processed` (Type: Number)
  - [ ] `pql_score` (Type: Number)

**Deal Pipeline Setup (20 min):**
- [ ] Go to Sales → Deals → Pipelines
- [ ] Create new pipeline: "Self-Serve Pipeline"
- [ ] Add stages:
  1. Trial
  2. Active Free
  3. PQL
  4. Customer
  5. Expansion Opportunity

**Lists Setup (10 min):**
- [ ] Go to Contacts → Lists
- [ ] Create list: "High Priority Leads"
- [ ] Create list: "PQLs"
- [ ] Create list: "Inactive Users"

**Basic Workflow (20 min):**
- [ ] Go to Automation → Workflows
- [ ] Create workflow: "New Account Created"
  - Trigger: Contact created
  - Action: Set `activation_status` = "account_created"
  - Action: Tag "new_signup"

---

### Afternoon (4-5 hours): Brevo + Stripe

#### Brevo (Email) Setup (2-2.5 hours)

**📺 Tutorials:**
- Search YouTube: "Brevo email marketing setup tutorial 2024" or "Sendinblue automation 2024"
- Popular channels: Automation Step by Step, Marketing tutorials
- [Brevo Documentation](https://developers.brevo.com)

**Account Setup (30 min):**
- [ ] Create Brevo account: https://www.brevo.com (Free tier: 300 emails/day)
- [ ] Verify sender domain:
  - [ ] Go to Senders & IP → Senders
  - [ ] Add your domain
  - [ ] Add SPF record to your DNS
  - [ ] Add DKIM record to your DNS
  - [ ] Wait for verification (can take up to 24 hours, but continue setup)

**Email Sequences Creation (1.5-2 hours):**

**1. Onboarding Sequence (30 min):**
- [ ] Go to Campaigns → Email Campaigns → Create campaign → Automated
- [ ] Create sequence: "Onboarding"
- [ ] Add emails:
  - [ ] **Day 0:** Welcome email
    - Subject: "Welcome to DeepRead - Your API key is ready"
    - Content: API key, quick-start guide, dashboard link
    - CTA: "Create your first context"
  - [ ] **Day 1:** "Did you hit any issues?"
    - Subject: "Need help getting started?"
    - Content: Troubleshooting guide, support link
  - [ ] **Day 3:** Use case examples
    - Subject: "How [Company X] processes 10K docs/day"
  - [ ] **Day 7:** Power features
    - Subject: "Unlock advanced features"
  - [ ] **Day 14:** Social proof
    - Subject: "Join 100+ teams using DeepRead"

**2. Activation Nudge (20 min):**
- [ ] Create sequence: "Activation Nudge"
- [ ] Trigger: User has API key but no context created in 48hrs
- [ ] Email: "Your context is just one upload away"
  - Subject: "Stuck? Here's how to create your first context"
  - Content: Step-by-step eval set upload guide
  - CTA: "Upload your eval set now"

**3. Context Created Follow-up (20 min):**
- [ ] Create sequence: "Context Ready"
- [ ] Trigger: Context created
- [ ] Email: "Your context is ready!"
  - Subject: "Your context is ready! [baseline_accuracy]% → [final_accuracy]% accuracy"
  - Content: context_id, accuracy report, how to use in /process calls
  - CTA: "Make your first process call"

**4. Upsell Sequence (30 min):**
- [ ] Create sequence: "Approaching Limit"
- [ ] Trigger: Usage >80% of free tier
- [ ] Add emails:
  - [ ] **Email 1 (at 80 pages):** "You're crushing it!"
  - [ ] **Email 2 (+3 days):** "Upgrade to keep processing"
  - [ ] **Email 3 (+7 days):** "Last chance"

**5. Re-engagement (10 min):**
- [ ] Create sequence: "Re-engagement"
- [ ] Trigger: 14 days inactive
- [ ] Email: "We miss you! What's new?"

**Testing (10 min):**
- [ ] Send test emails to yourself
- [ ] Verify all links work
- [ ] Check email rendering

---

#### Stripe Setup (2-2.5 hours)

**📺 Tutorials:**
- [Traversy Media: Stripe Checkout](https://www.youtube.com/@TraversyMedia) - Search "Stripe checkout"
- [freeCodeCamp: Stripe Payment](https://www.youtube.com/@freecodecamp) - Full payment integration courses
- Search YouTube: "Stripe checkout integration React Node.js 2024" for most recent tutorials
- [Stripe Official Docs: Checkout](https://stripe.com/docs/payments/checkout)

**Account Setup (20 min):**
- [ ] Create Stripe account: https://stripe.com
- [ ] Complete business verification
- [ ] Set up bank account for payouts
- [ ] Get API keys (Publishable key + Secret key)

**Product & Pricing Setup (30 min):**
- [ ] Go to Products → Add product
- [ ] Create products:
  - [ ] Free tier: $0/mo (0 pages/month)
  - [ ] Starter: $99/mo (or pay-as-you-go)
  - [ ] Growth: $499/mo
  - [ ] Team: $999/mo
- [ ] Set up usage-based pricing (if applicable)

**Checkout Integration (1-1.5 hours):**
- [ ] Install Stripe SDK:
  ```bash
  npm install @stripe/stripe-js  # Frontend
  npm install stripe             # Backend
  ```

- [ ] Create checkout flow in your app:
  ```javascript
  // Frontend: Create checkout session
  const response = await fetch('/api/create-checkout-session', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ priceId: 'price_xxx' })
  });
  const session = await response.json();
  window.location.href = session.url;
  ```

  ```javascript
  // Backend: Create checkout session endpoint
  const stripe = require('stripe')(process.env.STRIPE_SECRET_KEY);
  
  app.post('/api/create-checkout-session', async (req, res) => {
    const session = await stripe.checkout.sessions.create({
      payment_method_types: ['card'],
      line_items: [{
        price: req.body.priceId,
        quantity: 1,
      }],
      mode: 'subscription',
      success_url: `${req.headers.origin}/success`,
      cancel_url: `${req.headers.origin}/cancel`,
    });
    res.json({ url: session.url });
  });
  ```

**Webhook Setup (30 min):**
- [ ] Go to Developers → Webhooks
- [ ] Add endpoint: `https://yourdomain.com/api/stripe-webhook`
- [ ] Select events to listen for:
  - [ ] `customer.subscription.created`
  - [ ] `customer.subscription.updated`
  - [ ] `customer.subscription.deleted`
  - [ ] `invoice.payment_succeeded`
  - [ ] `invoice.payment_failed`
- [ ] Copy webhook signing secret
- [ ] Implement webhook handler:
  ```javascript
  app.post('/api/stripe-webhook', express.raw({type: 'application/json'}), (req, res) => {
    const sig = req.headers['stripe-signature'];
    const event = stripe.webhooks.constructEvent(req.body, sig, process.env.STRIPE_WEBHOOK_SECRET);
    
    switch (event.type) {
      case 'customer.subscription.created':
        // Handle new subscription
        break;
      case 'invoice.payment_succeeded':
        // Handle successful payment
        break;
    }
    res.json({received: true});
  });
  ```

**Testing (20 min):**
- [ ] Test checkout with test card: `4242 4242 4242 4242`
- [ ] Verify webhook events are received
- [ ] Test subscription creation flow

---

## Day 2: Integration & Automation (8-10 hours)

### Morning (4-5 hours): PostHog → HubSpot Integration

**📺 Tutorials:**
- Search YouTube: "PostHog HubSpot integration webhook 2024"
- [PostHog Docs: HubSpot Integration](https://posthog.com/docs/integrate/third-party/hubspot)

**Webhook Setup (2-3 hours):**

**Option 1: Direct Webhook (Recommended - 2 hours)**
- [ ] Create webhook endpoint in your backend:
  ```javascript
  app.post('/api/posthog-webhook', async (req, res) => {
    const event = req.body;
    
    // Get HubSpot contact by email
    const hubspot = require('@hubspot/api-client');
    const hubspotClient = new hubspot.Client({ accessToken: process.env.HUBSPOT_API_KEY });
    
    try {
      // Find or create contact
      const contact = await hubspotClient.crm.contacts.basicApi.getByEmail(event.properties.email);
      
      // Update contact based on event type
      switch (event.event) {
        case 'account_created':
          await hubspotClient.crm.contacts.basicApi.update(contact.id, {
            properties: {
              activation_status: 'account_created',
              account_created_date: new Date().toISOString()
            }
          });
          break;
        case 'api_key_created':
          await hubspotClient.crm.contacts.basicApi.update(contact.id, {
            properties: {
              activation_status: 'api_key_created',
              api_key_created_date: new Date().toISOString()
            }
          });
          break;
        case 'context_created':
          await hubspotClient.crm.contacts.basicApi.update(contact.id, {
            properties: {
              activation_status: 'context_created',
              context_created_date: new Date().toISOString(),
              context_id: event.properties.context_id,
              baseline_accuracy: event.properties.baseline_accuracy,
              final_accuracy: event.properties.final_accuracy,
              improvement: event.properties.improvement,
              optimizer_cost: event.properties.cost
            }
          });
          break;
        case 'first_process_call':
          await hubspotClient.crm.contacts.basicApi.update(contact.id, {
            properties: {
              activation_status: 'first_process_call',
              first_process_call_date: new Date().toISOString()
            }
          });
          break;
      }
    } catch (error) {
      console.error('HubSpot update error:', error);
    }
    
    res.json({ received: true });
  });
  ```

- [ ] Install HubSpot API client:
  ```bash
  npm install @hubspot/api-client
  ```

- [ ] Get HubSpot API key:
  - [ ] Go to HubSpot Settings → Integrations → Private Apps
  - [ ] Create private app
  - [ ] Grant permissions: Read/Write contacts
  - [ ] Copy API key

- [ ] Configure PostHog webhook:
  - [ ] Go to PostHog → Project Settings → Webhooks
  - [ ] Add webhook: `https://yourdomain.com/api/posthog-webhook`
  - [ ] Select events: account_created, api_key_created, context_created, first_process_call

**Option 2: Zapier (No-code - 1 hour)**
- [ ] Create Zapier account
- [ ] Create Zap: PostHog → HubSpot
- [ ] Connect PostHog (add API key)
- [ ] Connect HubSpot (OAuth)
- [ ] Map event properties to HubSpot fields
- [ ] Test and activate

**HubSpot Workflows (1-2 hours):**

**📺 Tutorials:**
- [HubSpot Academy: Workflows Course](https://academy.hubspot.com/courses/workflows) - Official free course
- [HubSpot Academy YouTube](https://www.youtube.com/@HubSpot) - Search "workflows"
- Search YouTube: "HubSpot workflows automation tutorial 2024"

- [ ] Create workflow: "API Key Created"
  - Trigger: Property `api_key_created_date` is set
  - Action: Set `activation_status` = "api_key_created"
  - Action: Enroll in Brevo: "Quick-start guide" email
  - Action: Create task: "Check if context created in 48hrs"

- [ ] Create workflow: "Context Created"
  - Trigger: Property `context_created_date` is set
  - Action: Set `activation_status` = "context_created"
  - Action: IF email provided: Enroll in Brevo: "Accuracy report" email
  - Action: Create task: "Check if first process call in 24hrs"

- [ ] Create workflow: "First Process Call"
  - Trigger: Property `first_process_call_date` is set
  - Action: Set `activation_status` = "first_process_call"
  - Action: Enroll in Brevo: "Congrats" email
  - Action: Calculate initial PQL score

- [ ] Create workflow: "PQL Detection"
  - Trigger: Property `pql_score` >50
  - Action: Tag "pql"
  - Action: Add to "PQLs" list
  - Action: Create deal in "PQL" stage

**PQL Scoring (30 min):**
- [ ] Create workflow: "Calculate PQL Score" (runs daily)
  - Trigger: Scheduled (daily at 9am)
  - Action: Calculate score:
    ```
    PQL Score = 
      (pages_processed × 0.1) +
      (days_active × 5) +
      (final_accuracy × 0.3) +
      (context_recreated ? 10 : 0)
    ```
  - Action: Update `pql_score` property
  - Action: If score >50: Tag "pql"

**Testing (30 min):**
- [ ] Trigger each event manually
- [ ] Verify HubSpot contact updates
- [ ] Check workflows execute
- [ ] Verify emails are sent

---

### Afternoon (4-5 hours): Brevo Integration + Slack Alerts + Testing

#### Brevo → HubSpot Integration (1 hour)

**📺 Tutorials:**
- Search YouTube: "Brevo HubSpot integration 2024" or "Sendinblue HubSpot sync"
- [Brevo Integration Docs](https://help.brevo.com/hc/en-us/articles/209467485)

- [ ] Go to Brevo → Integrations → HubSpot
- [ ] Connect HubSpot account (OAuth)
- [ ] Configure sync:
  - [ ] Sync contacts: Brevo → HubSpot
  - [ ] Sync email activity to HubSpot timeline
- [ ] Test: Send test email, verify it appears in HubSpot

---

#### Slack Alerts Setup (1 hour)

**📺 Tutorials:**
- [HubSpot Academy: Slack Integration](https://academy.hubspot.com/courses/slack-integration)
- Search YouTube: "HubSpot Slack notifications setup 2024"

**Slack Integration:**
- [ ] Go to HubSpot Settings → Integrations → Slack
- [ ] Connect Slack workspace
- [ ] Configure notifications:
  - [ ] New contact created (enterprise domains only)
  - [ ] Deal stage changed
  - [ ] Task created

**Custom Alerts (via Webhook):**
- [ ] Create Slack app: https://api.slack.com/apps
- [ ] Create incoming webhook
- [ ] Add webhook to HubSpot workflow:
  ```javascript
  // In HubSpot workflow action
  fetch('YOUR_SLACK_WEBHOOK_URL', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
      text: `🎯 New PQL: ${contact.email} - Score: ${contact.pql_score}`
    })
  });
  ```

- [ ] Create alerts:
  - [ ] "New High-Priority Lead" (enterprise domain)
  - [ ] "New PQL" (pql_score >50)
  - [ ] "New Customer" (subscription created)
  - [ ] "Approaching Limit" (usage >80%)

---

#### Dashboard Creation (1 hour)

**PostHog Dashboards:**
- [ ] Go to PostHog → Dashboards → New Dashboard
- [ ] Create "Activation Funnel" dashboard:
  - [ ] Add funnel: Account created → API key → Context created → First process call
  - [ ] Add conversion rate metrics
- [ ] Create "Usage" dashboard:
  - [ ] Total pages processed
  - [ ] Average pages per user
  - [ ] Volume milestones

**HubSpot Dashboards:**
- [ ] Go to Reports → Dashboards → Create dashboard
- [ ] Create "Revenue" dashboard:
  - [ ] MRR growth
  - [ ] New customers this month
  - [ ] PQL → Paid conversion rate

---

#### End-to-End Testing (1-2 hours)

**User Journey Test:**
- [ ] Create test account
- [ ] Verify `account_created` event → HubSpot contact created
- [ ] Create API key → Verify `api_key_created` event → HubSpot updated → Email sent
- [ ] Upload eval set → Verify `context_created` event → HubSpot updated → Email sent
- [ ] Make first process call → Verify `first_process_call` event → HubSpot updated → Email sent
- [ ] Check all workflows execute correctly
- [ ] Verify Slack alerts fire

**Integration Testing:**
- [ ] Test PostHog → HubSpot webhook
- [ ] Test HubSpot → Brevo integration
- [ ] Test Stripe webhook events
- [ ] Verify all data syncs correctly

**Email Testing:**
- [ ] Test all email sequences with real account
- [ ] Verify personalization works (context_id, accuracy stats)
- [ ] Check email deliverability
- [ ] Test unsubscribe flow

---

## Quick Reference: Tool Links & Tutorials

### PostHog
- **Sign up:** https://posthog.com/signup
- **Docs:** https://posthog.com/docs
- **📺 Official Channel:** [PostHog YouTube](https://www.youtube.com/@PostHog)
- **📺 Search:** "PostHog setup tutorial 2024" on YouTube for most recent videos
- **Quick Start:** https://posthog.com/docs/getting-started/install

### HubSpot
- **Sign up:** https://www.hubspot.com/products/crm
- **Docs:** https://developers.hubspot.com/docs/api/overview
- **📺 Official Channel:** [HubSpot Academy YouTube](https://www.youtube.com/@HubSpot)
- **📺 Free Courses:** [HubSpot Academy](https://academy.hubspot.com) - Free CRM and Workflows courses
- **📺 Search:** "HubSpot CRM free setup 2024" on YouTube

### Brevo (Sendinblue)
- **Sign up:** https://www.brevo.com
- **Docs:** https://developers.brevo.com
- **📺 Search:** "Brevo email marketing setup 2024" or "Sendinblue automation tutorial 2024" on YouTube
- **Popular Channels:** Automation Step by Step, Marketing tutorials

### Stripe
- **Sign up:** https://stripe.com
- **Docs:** https://stripe.com/docs
- **📺 Recommended Channels:**
  - [Traversy Media](https://www.youtube.com/@TraversyMedia) - Search "Stripe checkout"
  - [freeCodeCamp](https://www.youtube.com/@freecodecamp) - Full payment integration courses
- **📺 Search:** "Stripe checkout integration React Node.js 2024" on YouTube
- **Official:** https://stripe.com/docs/payments/checkout

---

## Troubleshooting Quick Fixes

**Events not firing:**
- Check PostHog SDK initialization
- Verify API key is correct
- Check browser console for errors
- Use PostHog debug mode

**HubSpot not updating:**
- Verify webhook is receiving events
- Check HubSpot API credentials
- Review workflow logs
- Check for rate limits

**Emails not sending:**
- Verify sender domain is verified (SPF/DKIM)
- Check Brevo account status
- Review email logs
- Check spam folder

**Stripe webhook not working:**
- Verify webhook endpoint is accessible
- Check webhook signing secret
- Test with Stripe CLI: `stripe listen --forward-to localhost:3000/api/stripe-webhook`

---

## Success Checklist

**By end of Day 2, you should have:**
- ✅ All 6 core events tracking in PostHog
- ✅ HubSpot contacts auto-creating from events
- ✅ 3+ email sequences active in Brevo
- ✅ Stripe checkout working
- ✅ PostHog → HubSpot integration working
- ✅ Basic workflows in HubSpot
- ✅ PQL scoring logic implemented
- ✅ Slack alerts configured
- ✅ Basic dashboards created
- ✅ End-to-end test passed

---

## Next Steps (After 2 Days)

**Week 1:**
- Monitor activation funnel daily
- Check email open/click rates
- Verify PQL scoring is working
- Fix any integration issues

**Month 1:**
- Add Apollo for enrichment (optional, $49/mo)
- Optimize email sequences based on performance
- Refine PQL scoring model
- Add more advanced workflows

**Resources:**
- [Revenue Flows](./05-revenue-flows.md) - Detailed automation logic
- [Metrics & KPIs](./06-metrics-kpis.md) - What to track
- [Stage A Playbook](./02-stage-a-self-serve.md) - GTM strategy

---

**Last Updated:** 2025-01-21
