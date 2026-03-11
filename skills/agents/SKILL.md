---
name: agents
description: AI agent design and automation skill for solopreneurs. Use when user needs to audit workflows for automation, design AI agents, or build automation recipes using n8n + Claude API. Triggers on "ai agent", "automation", "workflow automation", "n8n", "agent design", "automate my business", or /agent commands.
---

# AI Agent Skill

Your AI-powered business operating system. Design, build, and deploy AI agents that handle the work you shouldn't be doing manually.

## Commands

| Command | Description |
|---------|-------------|
| `/agent:audit` | Audit your workflow, rank automation opportunities by ROI |
| `/agent:design` | Design an AI agent spec (trigger, workflow, tools, output) |
| `/agent:build` | Step-by-step build guide (n8n + Claude API) |
| `/agent:leads` | Lead qualifier agent recipe |
| `/agent:support` | Customer support agent recipe |
| `/agent:content` | Content repurposing agent recipe |
| `/agent:inbox` | Email triage + draft agent recipe |
| `/agent:social` | Social media scheduling agent recipe |
| `/agent:onboard` | Client onboarding agent recipe |
| `/agent:invoice` | Invoice + payment follow-up agent recipe |
| `/agent:research` | Market/competitor research agent recipe |
| `/agent:help` | Command reference |

---

## Principles

1. **Automate the repeatable, humanize the valuable.** If it takes judgment, taste, or relationship — keep it human.
2. **Every agent needs a human checkpoint.** No fully autonomous agent should touch clients or money without a review gate.
3. **Start with the highest-ROI automation, not the coolest one.** Boring automations that save 5 hours/week beat flashy ones that save 20 minutes.
4. **An agent that fails silently is worse than no agent.** Every agent must alert on failure.
5. **Cost per automation < cost of your time.** If the API bill exceeds the hourly rate you'd pay someone, rethink the approach.

---

## Stage 1: Automation Audit (`/agent:audit`)

Before building anything, figure out what's worth automating. Most solopreneurs automate the wrong things first.

### Step 1: Task Inventory

List everything you do in a typical week. Be honest — include the 10-minute tasks you think don't matter. They add up.

```
WEEKLY TASK INVENTORY
======================
| # | Task                        | Category      | Frequency   | Time/Occurrence | Total hrs/wk |
|---|-----------------------------|---------------|-------------|-----------------|--------------|
| 1 | [e.g., Reply to inquiries]  | [Sales]       | [Daily]     | [15 min]        | [1.25]       |
| 2 | [e.g., Post on LinkedIn]    | [Marketing]   | [3x/week]   | [30 min]        | [1.5]        |
| 3 | [e.g., Send invoices]       | [Finance]     | [Weekly]    | [45 min]        | [0.75]       |
| 4 | [e.g., Onboard new client]  | [Operations]  | [2x/month]  | [2 hours]       | [1.0]        |
| 5 |                             |               |             |                 |              |
|...|                             |               |             |                 |              |
```

Categories: Sales, Marketing, Finance, Operations, Support, Admin, Research

### Step 2: Automation Scorecard

Score each task on four dimensions. Be ruthless.

```
AUTOMATION SCORECARD
=====================
| # | Task                  | Repetitive | Rule-Based | Error-Prone | Time (hrs/wk) | ROI Score |
|---|-----------------------|------------|------------|-------------|----------------|-----------|
|   |                       | (1-5)      | (1-5)      | (1-5)       |                |           |
| 1 | Reply to inquiries    | 4          | 3          | 2           | 1.25           | 11.25     |
| 2 | Post on LinkedIn      | 5          | 4          | 1           | 1.5            | 15.0      |
| 3 | Send invoices         | 5          | 5          | 3           | 0.75           | 9.75      |
| 4 | Onboard new client    | 4          | 4          | 4           | 1.0            | 12.0      |
```

**ROI Score formula:**

```
ROI Score = (Repetitive + Rule-Based + Error-Prone) x Time (hrs/wk)
```

**Scoring guide:**

```
Repetitive (1-5)
  1 = Unique every time, no two instances alike
  2 = Some patterns but mostly custom
  3 = Half repeatable, half custom
  4 = Mostly the same steps, minor variations
  5 = Identical every single time

Rule-Based (1-5)
  1 = Requires deep judgment, creativity, or intuition
  2 = Mostly judgment with some clear rules
  3 = Mix of rules and judgment calls
  4 = Clear rules with occasional edge cases
  5 = Fully deterministic — if X then Y, always

Error-Prone (1-5)
  1 = Almost never make mistakes here
  2 = Rare errors, low impact
  3 = Occasional errors, moderate impact
  4 = Frequent small errors or occasional big ones
  5 = Regularly make mistakes, high impact when wrong
```

### Step 3: Priority Matrix

Plot your tasks into four quadrants:

```
                        HIGH ROI
                           |
              STRATEGIC    |    QUICK WINS
             (plan these)  |   (do these first)
                           |
    HARD TO ---------------+--------------- EASY TO
    AUTOMATE               |                AUTOMATE
                           |
              SKIP         |    NICE-TO-HAVE
           (don't bother)  |   (do when bored)
                           |
                        LOW ROI
```

**Quick Wins** (High ROI + Easy to automate):
- Tasks scoring ROI > 10 that use standard tools (email, spreadsheets, forms)
- Usually: invoice reminders, social posting, email sorting, data entry

**Strategic** (High ROI + Hard to automate):
- Tasks scoring ROI > 10 that need custom logic or multiple integrations
- Usually: lead qualification, client onboarding, content repurposing

**Nice-to-Have** (Low ROI + Easy to automate):
- Tasks scoring ROI < 10 that are simple to set up
- Usually: file organization, notification routing, calendar management

**Skip** (Low ROI + Hard to automate):
- Not worth the effort. Revisit in 6 months.

### Step 4: Human-Required Flags

Some tasks should never be fully automated, no matter the ROI score. Flag these:

```
HUMAN-REQUIRED FLAGS
=====================
[!] Creative work — brand voice, design, strategy
[!] Relationship moments — first client call, conflict resolution, celebrations
[!] High-stakes decisions — pricing, hiring, partnerships, legal
[!] Emotional intelligence — reading tone, detecting frustration, showing empathy
[!] Novel situations — first-time problems, unusual requests
```

For flagged tasks: automate the preparation, keep the execution human. Example: AI drafts the proposal, you review and send it.

### Audit Output

Deliver a ranked list:

```
AUTOMATION PRIORITIES
======================
Priority 1 (This week):  [Quick win with highest ROI score]
Priority 2 (This week):  [Second quick win]
Priority 3 (Next week):  [Third quick win or first strategic]
Priority 4 (This month): [Strategic automation]
Priority 5 (This month): [Strategic automation]

Estimated time saved: [X] hours/week
Estimated build time: [Y] hours total
Payback period: [Y / X] weeks
```

---

## Stage 2: Agent Design (`/agent:design`)

Every agent starts with a spec. No spec, no build. This prevents the most common failure mode: building something that solves the wrong problem.

### Agent Spec Template

```
AGENT SPEC
===========
Name:             [Descriptive name — e.g., "Lead Qualifier Bot"]
Owner:            [Who maintains this agent]
Version:          [Start at 1.0]

TRIGGER
-------
Type:             [Schedule / Webhook / Email / Form / Event / Manual]
Source:           [Where the trigger comes from]
Frequency:        [How often it fires]
Conditions:       [Any filters before the agent runs]

INPUT
-----
Data:             [What data the agent receives]
Format:           [JSON, email body, form fields, etc.]
Required fields:  [What must be present or agent should abort]
Optional fields:  [Nice-to-have data that improves output]

WORKFLOW
--------
Step 1:           [Action — be specific]
Step 2:           [Action]
Step 3:           [Action]
  ...
Step N:           [Final action]

TOOLS & INTEGRATIONS
---------------------
- [Service/API]: [What it does in this workflow]
- [Service/API]: [What it does in this workflow]
- [Database]:    [What it reads/writes]

AI MODEL
--------
Model:            [Claude Sonnet for speed, Claude Opus for reasoning, GPT-4o for cost]
Why:              [Justify the choice — complexity, cost, latency requirements]
Token budget:     [Max input + output tokens per run]
Temperature:      [0.0-1.0 — lower for classification, higher for creative]

OUTPUT
------
Produces:         [Email, Slack message, database entry, file, API call, etc.]
Destination:      [Where output goes]
Format:           [Structure of the output]

HUMAN CHECKPOINT
-----------------
Review point:     [Where a human reviews before the agent continues]
Reviewer:         [Who reviews — you, VA, team member]
SLA:              [How quickly must the human respond]
Auto-proceed:     [If no review in X hours, what happens — wait, proceed, alert]

FALLBACK
--------
On error:         [Retry X times, then alert via [channel]]
On uncertainty:   [If AI confidence < threshold, route to human]
On missing data:  [Request missing info / skip / use defaults]

SUCCESS METRICS
----------------
- [Metric 1]:     [Target — e.g., "Process 95% of leads within 5 minutes"]
- [Metric 2]:     [Target — e.g., "Reduce manual lead sorting from 5hrs to 30min/week"]
- [Metric 3]:     [Target — e.g., "Zero missed high-priority leads"]

COST ESTIMATE
--------------
API calls/month:  [Volume estimate]
Cost/call:        [Based on model + token usage]
Monthly total:    [$X]
Break-even:       [Hours saved × hourly rate > monthly cost]
```

### Trigger Types

Choose the right trigger for the job:

```
TRIGGER TYPE GUIDE
===================
| Type           | Use When                                    | n8n Node          | Example                    |
|----------------|---------------------------------------------|-------------------|----------------------------|
| Schedule       | Task runs at fixed intervals                | Cron / Schedule   | Daily social posts         |
| Webhook        | External event sends data to your agent     | Webhook           | Form submission            |
| Email          | Incoming email triggers workflow             | Email Trigger     | Support request            |
| Polling        | Check a source periodically for changes     | HTTP Request+Cron | New RSS item               |
| Event          | Database or app event fires                 | App Trigger       | New Stripe payment         |
| Manual         | You explicitly kick it off                  | Manual Trigger    | Research request           |
| Threshold      | Metric crosses a boundary                   | IF + Schedule     | Lead score > 80            |
| Chain          | Another agent's output triggers this one    | Execute Workflow   | Lead qualified → onboard   |
```

### Tool Selection Guide

Common n8n nodes for solopreneur agents:

```
TOOL SELECTION
===============
| Need                    | n8n Node(s)                        | Notes                          |
|-------------------------|------------------------------------|--------------------------------|
| AI reasoning            | HTTP Request (Claude API)          | System prompt + user message   |
| Email send              | Gmail / SMTP                       | Use OAuth for Gmail            |
| Email receive           | Email Trigger (IMAP)               | Poll interval matters          |
| Spreadsheet             | Google Sheets                      | Read, append, update           |
| CRM                     | HTTP Request to CRM API            | Or native node if available    |
| Slack/Discord           | Slack / Discord node               | Webhooks for incoming          |
| Database                | Postgres / Supabase                | Structured data storage        |
| Web scraping            | HTTP Request + HTML Extract        | Respect robots.txt             |
| File generation         | Code node (JS)                     | PDF, CSV, etc.                 |
| Payment                 | Stripe node                        | Invoices, subscriptions        |
| Calendar                | Google Calendar                    | Create, read, update events    |
| Form data               | Webhook + Typeform/Tally           | Webhook is most flexible       |
| Social media            | HTTP Request to platform APIs      | LinkedIn, Twitter, etc.        |
| Project management      | ClickUp / Notion / Trello node     | Task creation and updates      |
```

### Prompt Engineering for Agents

Agent prompts are different from chat prompts. They must be deterministic, structured, and failure-aware.

```
AGENT PROMPT TEMPLATE
======================
You are [agent name], an AI assistant that [one-sentence purpose].

CONTEXT:
- You work for [business name], a [business type]
- Your role is to [specific function]
- You operate as part of an automated workflow

INSTRUCTIONS:
1. [First thing to do with the input]
2. [Second thing to do]
3. [Third thing to do]

OUTPUT FORMAT:
Return your response as JSON with this exact structure:
{
  "classification": "[category]",
  "confidence": [0.0-1.0],
  "summary": "[brief summary]",
  "action": "[recommended action]",
  "details": "[additional context]"
}

RULES:
- If confidence < 0.7, set action to "HUMAN_REVIEW"
- Never fabricate information — if data is missing, say so
- Keep summaries under 100 words
- [Domain-specific rules]

EXAMPLES:
Input: [example input]
Output: [example output]
```

### Testing Checklist

Before deploying any agent:

```
TESTING CHECKLIST
==================
[ ] Happy path — standard input produces correct output
[ ] Empty input — agent handles gracefully (doesn't crash or hallucinate)
[ ] Malformed input — agent rejects or flags for review
[ ] Edge case: very long input — stays within token limits
[ ] Edge case: ambiguous input — routes to human review
[ ] Edge case: duplicate input — doesn't process twice
[ ] Failure mode: API timeout — retries then alerts
[ ] Failure mode: API error — logs error, alerts owner
[ ] Failure mode: downstream service down — queues for retry
[ ] Cost check: run 100 test inputs, verify cost matches estimate
[ ] Speed check: end-to-end latency acceptable for use case
[ ] Human checkpoint: review gate works, notifications arrive
```

### Cost Estimation

```
COST CALCULATOR
================
Model: Claude Sonnet 4
  Input:  $3.00 / 1M tokens
  Output: $15.00 / 1M tokens

Model: Claude Opus 4
  Input:  $15.00 / 1M tokens
  Output: $75.00 / 1M tokens

Model: GPT-4o
  Input:  $2.50 / 1M tokens
  Output: $10.00 / 1M tokens

Model: GPT-4o-mini
  Input:  $0.15 / 1M tokens
  Output: $0.60 / 1M tokens

Formula:
  Monthly cost = (avg_input_tokens × input_price + avg_output_tokens × output_price) × runs_per_month

Example — Lead Qualifier (Claude Sonnet):
  ~800 input tokens + ~400 output tokens per lead
  100 leads/month
  = (800 × $0.000003 + 400 × $0.000015) × 100
  = ($0.0024 + $0.006) × 100
  = $0.84/month

Rule of thumb: Most solopreneur agents cost $1-20/month in API fees.
If your estimate exceeds $50/month, consider:
  - Using a smaller model for simple classification
  - Caching repeated queries
  - Batching requests
  - Adding a rule-based pre-filter before the AI step
```

---

## Stage 3: Build Guide (`/agent:build`)

Practical guide to building agents with n8n and the Claude API.

### n8n Setup

**Self-hosted (recommended for solopreneurs):**

```yaml
# docker-compose.yml
version: '3.8'
services:
  n8n:
    image: n8nio/n8n:latest
    restart: unless-stopped
    ports:
      - "5678:5678"
    environment:
      - N8N_HOST=n8n.yourdomain.com
      - N8N_PORT=5678
      - N8N_PROTOCOL=https
      - WEBHOOK_URL=https://n8n.yourdomain.com/
      - N8N_ENCRYPTION_KEY=your-random-encryption-key
      - N8N_BASIC_AUTH_ACTIVE=true
      - N8N_BASIC_AUTH_USER=admin
      - N8N_BASIC_AUTH_PASSWORD=your-secure-password
    volumes:
      - n8n_data:/home/node/.n8n

volumes:
  n8n_data:
```

**Cloud (n8n.io):**
- Starter plan: $24/month, 5 active workflows
- Pro plan: $60/month, 50 active workflows
- Good for getting started, migrate to self-hosted when you hit limits

### Claude API Integration in n8n

Use an HTTP Request node to call the Claude Messages API:

```
METHOD: POST
URL: https://api.anthropic.com/v1/messages

HEADERS:
  x-api-key: {{ $credentials.anthropicApiKey }}
  anthropic-version: 2023-06-01
  content-type: application/json

BODY (JSON):
{
  "model": "claude-sonnet-4-20250514",
  "max_tokens": 1024,
  "system": "Your system prompt here",
  "messages": [
    {
      "role": "user",
      "content": "{{ $json.inputData }}"
    }
  ]
}
```

**Credential setup:**
1. In n8n, go to Credentials > Add Credential > Header Auth
2. Name: `Anthropic API`
3. Header Name: `x-api-key`
4. Header Value: your Claude API key

### Common n8n Patterns

**Pattern 1: Webhook > Process > Respond**
Best for: form submissions, external events, API integrations

```
[Webhook] → [Set/Transform] → [HTTP Request (Claude)] → [Parse JSON] → [IF branch] → [Action]
                                                                            |
                                                                            → [Human Review]
```

**Pattern 2: Schedule > Fetch > Transform > Send**
Best for: recurring reports, social posting, monitoring

```
[Cron] → [HTTP Request (fetch data)] → [HTTP Request (Claude)] → [Parse JSON] → [Gmail/Slack/Sheets]
```

**Pattern 3: Email Trigger > AI Classify > Route > Act**
Best for: inbox triage, support tickets, lead capture

```
[Email Trigger] → [HTTP Request (Claude classify)] → [Switch node]
                                                         |→ "urgent" → [Slack alert + Draft reply]
                                                         |→ "client" → [Add to CRM + Draft reply]
                                                         |→ "spam"   → [Archive]
                                                         |→ "other"  → [Label + Skip]
```

### Error Handling

Every production agent needs error handling:

```
ERROR HANDLING PATTERN
=======================
1. Wrap AI calls in a try/catch (n8n Error Trigger node)
2. On API error (429, 500, 503):
   - Wait 30 seconds
   - Retry up to 3 times
   - If still failing, send alert to Slack/email
3. On malformed AI response:
   - Log the raw response
   - Route to human review
   - Don't retry (probably a prompt issue)
4. On downstream service failure:
   - Queue the action for retry
   - Alert if queue grows beyond threshold
5. Dead letter queue:
   - After all retries exhausted, store failed items in a "failed" sheet/table
   - Review weekly
```

n8n settings for retry:
- On the HTTP Request node: Settings > Retry on Fail > Max Retries: 3, Wait Between: 30000ms
- Add an Error Trigger workflow for unhandled failures

### Monitoring and Logging

```
MONITORING SETUP
=================
1. Execution log:
   - n8n stores execution history (Settings > Executions)
   - Set retention to 30 days minimum
   - Enable "Save failed executions" always

2. Success/failure tracking:
   - Add a Google Sheets "Agent Log" with columns:
     | Timestamp | Agent | Status | Input Summary | Output Summary | Cost |
   - Append a row at the end of every workflow run

3. Alerting:
   - Error Trigger workflow → Slack/email notification
   - Include: agent name, error message, input data, timestamp

4. Weekly review:
   - Check execution counts vs expected
   - Review failed executions
   - Check API costs in provider dashboard
   - Verify human checkpoints are being actioned
```

### Cost Management

```
COST MANAGEMENT STRATEGIES
============================
1. Model routing:
   - Use GPT-4o-mini or Claude Haiku for simple classification ($0.15-0.80/1M input)
   - Use Claude Sonnet for medium complexity ($3/1M input)
   - Reserve Claude Opus for complex reasoning ($15/1M input)

2. Caching:
   - If the same input produces the same output, cache it
   - Use a Google Sheet or database as a simple cache
   - Check cache before calling AI

3. Pre-filtering:
   - Use rule-based logic (IF nodes) before AI nodes
   - Only send to AI what actually needs AI
   - Example: filter spam by sender domain before classifying content

4. Batching:
   - Collect items over an hour, process in batch
   - One API call with 10 items < 10 separate API calls
   - Use n8n's "Wait" node or item batching

5. Token optimization:
   - Keep system prompts concise (every token costs money)
   - Limit max_tokens to what you actually need
   - Use structured output (JSON) to reduce response length

Monthly cost monitoring:
  - Set a budget alert in your API provider dashboard
  - Track cost per agent per month in your Agent Log sheet
  - If any agent exceeds $20/month, review and optimize
```

---

## Stage 4: Lead Qualifier Agent (`/agent:leads`)

```
AGENT: Lead Qualifier
======================
USE CASE:      Automatically score and route incoming leads so you respond
               to hot prospects in minutes, not hours.
DIFFICULTY:    Medium
BUILD TIME:    3-4 hours
MONTHLY COST:  $1-5 (based on 50-200 leads/month)

TRIGGER:       New form submission (webhook) or email inquiry
SOURCE:        Website contact form, Typeform, Tally, or email

INPUT:
  - Name
  - Email address
  - Company (if provided)
  - Message / inquiry text
  - Source (which form or channel)

WORKFLOW:
  Step 1: Receive form data via webhook
  Step 2: Extract and normalize fields
  Step 3: Enrich — look up company website/LinkedIn (optional HTTP request)
  Step 4: Send to Claude for ICP scoring and classification
  Step 5: Route based on score:
          - Hot (80-100): Immediate Slack alert + personalized auto-reply
          - Warm (50-79): Add to CRM + template reply within 24hrs
          - Cold (20-49): Add to nurture sequence
          - Spam (0-19): Archive, no reply
  Step 6: Log to tracking spreadsheet

n8n NODES NEEDED:
  - Webhook:          Receives form submission
  - Set:              Normalize and clean input fields
  - HTTP Request:     (Optional) Enrich from LinkedIn/Clearbit
  - HTTP Request:     Claude API call for scoring
  - Code:             Parse Claude response JSON
  - Switch:           Route by score tier (hot/warm/cold/spam)
  - Gmail:            Send auto-reply (hot leads)
  - Google Sheets:    Log lead + score + classification
  - Slack:            Alert for hot leads

CLAUDE PROMPT:
  You are a lead qualification assistant for [YOUR BUSINESS].

  MY IDEAL CUSTOMER PROFILE (ICP):
  - [Industry/niche]
  - [Company size or revenue range]
  - [Role/title of decision maker]
  - [Pain points we solve]
  - [Budget range]

  SCORING CRITERIA:
  - ICP match (0-30 points): How well does this lead match my ideal customer?
  - Intent signal (0-30 points): How strong is their buying intent based on their message?
  - Budget signal (0-20 points): Any indication they can afford our services?
  - Urgency (0-20 points): How time-sensitive is their need?

  Analyze this lead and return JSON:
  {
    "score": [0-100],
    "tier": "hot|warm|cold|spam",
    "confidence": [0.0-1.0],
    "icp_match": { "score": [0-30], "reasoning": "..." },
    "intent": { "score": [0-30], "reasoning": "..." },
    "budget": { "score": [0-20], "reasoning": "..." },
    "urgency": { "score": [0-20], "reasoning": "..." },
    "summary": "[1-2 sentence summary of this lead]",
    "suggested_reply_tone": "enthusiastic|professional|exploratory|decline",
    "talking_points": ["point 1", "point 2", "point 3"]
  }

OUTPUT:
  - Slack notification (hot leads only)
  - Auto-reply email (hot leads, personalized)
  - CRM entry or spreadsheet row (all leads)
  - Weekly lead summary report

HUMAN CHECKPOINT:
  - Hot leads: Slack alert with score + summary. You decide whether to call immediately.
  - Warm leads: Review batch of draft replies before sending (daily, 5-minute task).
  - Auto-replies for hot leads can be sent automatically if confidence > 0.9.

SUCCESS METRICS:
  - Response time to hot leads < 10 minutes (vs hours before)
  - Lead-to-meeting conversion rate improvement
  - Zero missed hot leads
  - Time spent on lead sorting: < 30 min/week (vs 3-5 hours before)

COMMON PITFALLS:
  - ICP too vague — be specific. "Small businesses" is useless. "SaaS companies,
    10-50 employees, Series A, looking for design services" is actionable.
  - Auto-reply sounds robotic — write the template in your voice, use merge fields
    for personalization, keep it short.
  - Not updating ICP — review and adjust scoring criteria monthly based on which
    leads actually converted.
  - Scoring drift — periodically compare AI scores to your gut feeling. Recalibrate
    the prompt if they diverge.
```

**Auto-Reply Templates by Tier:**

```
HOT LEAD AUTO-REPLY
====================
Subject: Re: {{ lead.subject || "Your inquiry" }}

Hi {{ lead.firstName }},

Thanks for reaching out. {{ talking_points[0] }}

I'd love to learn more about what you're working on.
Are you free for a quick 15-minute call this week?

Here's my calendar: [CALENDAR_LINK]

{{ your_name }}


WARM LEAD REPLY (draft for review)
====================================
Subject: Re: {{ lead.subject || "Your inquiry" }}

Hi {{ lead.firstName }},

Thanks for getting in touch. I read through your message and
{{ talking_points[0] }}.

I've put together some thoughts on how we might help — would
you be open to a brief conversation?

{{ your_name }}
```

---

## Stage 5: Customer Support Agent (`/agent:support`)

```
AGENT: Customer Support Triage
================================
USE CASE:      Classify support requests, draft responses for common issues,
               and escalate complex ones — so you're not starting from blank
               every time.
DIFFICULTY:    Medium
BUILD TIME:    4-5 hours
MONTHLY COST:  $2-10 (based on 100-500 tickets/month)

TRIGGER:       New support email received (IMAP trigger) or form submission
SOURCE:        Support email inbox or help desk form

INPUT:
  - Sender email
  - Subject line
  - Email body
  - Attachments (flagged, not processed)
  - Previous conversation history (if available)

WORKFLOW:
  Step 1: Receive email via IMAP trigger or webhook
  Step 2: Check if sender is existing client (lookup in CRM/spreadsheet)
  Step 3: Send to Claude for classification and draft response
  Step 4: Route based on classification:
          - FAQ / Known issue: Auto-draft response → human approval queue
          - Bug report: Create ticket in project management tool → acknowledge
          - Feature request: Log in feature request tracker → acknowledge
          - Billing: Route to billing workflow → flag as priority
          - Complaint: IMMEDIATE Slack alert → do not auto-respond
          - Unclear: Route to human with AI summary
  Step 5: Log interaction in support tracker

n8n NODES NEEDED:
  - Email Trigger (IMAP):  Receives support emails
  - Google Sheets:         Client lookup
  - HTTP Request:          Claude API call
  - Code:                  Parse response, extract classification
  - Switch:                Route by category
  - Gmail:                 Send drafted reply (after approval)
  - Slack:                 Alert for complaints and urgent issues
  - ClickUp/Notion:        Create tickets for bugs/features
  - Google Sheets:         Log all interactions

CLAUDE PROMPT:
  You are a customer support assistant for [YOUR BUSINESS].

  KNOWLEDGE BASE:
  - [Common FAQ 1: question and answer]
  - [Common FAQ 2: question and answer]
  - [Common FAQ 3: question and answer]
  - [Known issue 1: description and workaround]
  - [Known issue 2: description and workaround]

  CLIENT STATUS: {{ clientStatus || "unknown" }}

  CLASSIFY this support request into ONE of:
  - faq (matches a known question/answer)
  - bug (something is broken)
  - feature_request (wants something new)
  - billing (payment, invoice, refund related)
  - complaint (unhappy, frustrated, threatening)
  - unclear (can't determine intent)

  RESPOND with JSON:
  {
    "category": "faq|bug|feature_request|billing|complaint|unclear",
    "confidence": [0.0-1.0],
    "sentiment": "positive|neutral|negative|angry",
    "priority": "low|medium|high|urgent",
    "summary": "[1-sentence summary of the issue]",
    "draft_response": "[Empathetic, helpful draft reply]",
    "internal_notes": "[Notes for the team about this ticket]",
    "needs_human": true|false,
    "reason_for_human": "[Why this needs human attention, if applicable]"
  }

  RULES:
  - Always be empathetic in draft responses
  - Never promise timelines you can't keep
  - If sentiment is "angry", ALWAYS set needs_human to true
  - If confidence < 0.7, set needs_human to true
  - Reference knowledge base answers when applicable
  - Keep draft responses under 150 words

OUTPUT:
  - Draft reply in approval queue (Google Sheet or Slack)
  - Ticket in project management tool (bugs, features)
  - Slack alert (complaints, urgent issues)
  - Logged interaction in support tracker

HUMAN CHECKPOINT:
  - ALL draft replies go through approval queue before sending
  - Complaints: immediate Slack alert, never auto-respond
  - Exception: After 2 weeks of reviewing, you can enable auto-send
    for FAQ responses with confidence > 0.95

ESCALATION RULES:
  Priority Urgent → Slack alert within 1 minute
  Priority High   → Slack alert within 15 minutes
  Priority Medium → Batch review twice daily
  Priority Low    → Batch review daily

SUCCESS METRICS:
  - First response time < 30 minutes (business hours)
  - Correct classification rate > 90%
  - Draft response acceptance rate > 80% (you send without major edits)
  - Customer satisfaction maintained or improved
  - Time spent on support: reduced by 60%

COMMON PITFALLS:
  - Knowledge base too small — start with top 20 questions, expand weekly
  - Auto-responding to complaints — never. Always human.
  - Ignoring sentiment — a simple FAQ answer delivered to an angry customer
    needs a different tone than the same answer to a curious one
  - Not updating the knowledge base — add new FAQs as you discover them
```

---

## Stage 6: Content Repurposing Agent (`/agent:content`)

```
AGENT: Content Repurposer
===========================
USE CASE:      Turn one piece of content into platform-specific posts for
               LinkedIn, Twitter/X, email newsletter, and Instagram — so one
               blog post becomes a week of content.
DIFFICULTY:    Easy
BUILD TIME:    2-3 hours
MONTHLY COST:  $1-3 (based on 4-8 posts/month)

TRIGGER:       New blog post published (RSS feed or webhook) or manual trigger
SOURCE:        Blog RSS feed, CMS webhook, or manual URL input

INPUT:
  - Blog post title
  - Blog post full text
  - Blog post URL
  - Author name
  - Key takeaways (optional, AI will extract if not provided)

WORKFLOW:
  Step 1: Fetch new blog post content (RSS or webhook payload)
  Step 2: Send full text to Claude for analysis and repurposing
  Step 3: Generate platform-specific content:
          - LinkedIn post (professional, insight-led)
          - Twitter/X thread (punchy, hook-driven)
          - Email newsletter snippet (personal, value-first)
          - Instagram caption (visual-friendly, hashtag-ready)
  Step 4: Add all drafts to review spreadsheet
  Step 5: Notify via Slack that new content is ready for review
  Step 6: (Optional) After approval, queue in social scheduler

n8n NODES NEEDED:
  - RSS Feed Read / Webhook:   Content trigger
  - HTTP Request:              Fetch full post content (if RSS only gives summary)
  - HTTP Request:              Claude API call
  - Code:                      Parse and split platform-specific outputs
  - Google Sheets:             Store drafts for review
  - Slack:                     Notify that content is ready
  - (Optional) HTTP Request:   Post to Buffer/Hootsuite/LinkedIn API

CLAUDE PROMPT:
  You are a content repurposing specialist for [YOUR BUSINESS].

  BRAND VOICE: [Describe your tone — e.g., "Professional but approachable.
  Uses concrete examples. Avoids jargon. First-person perspective."]

  Given this blog post, create platform-specific content:

  BLOG POST:
  Title: {{ title }}
  URL: {{ url }}
  Content: {{ content }}

  Return JSON with:
  {
    "key_takeaways": ["takeaway 1", "takeaway 2", "takeaway 3"],
    "linkedin": {
      "post": "[LinkedIn post, 150-300 words. Start with a hook.
                Use line breaks for readability. End with a question
                or CTA. Include the blog URL.]",
      "hashtags": ["#tag1", "#tag2", "#tag3"]
    },
    "twitter": {
      "thread": [
        "1/ [Hook tweet — the most interesting insight, max 280 chars]",
        "2/ [Supporting point or example]",
        "3/ [Another insight]",
        "4/ [Practical takeaway]",
        "5/ [CTA + link to full post]"
      ]
    },
    "email": {
      "subject_line": "[Compelling email subject, max 60 chars]",
      "preview_text": "[Preview text, max 90 chars]",
      "body": "[2-3 paragraph email snippet. Personal tone.
               Tease the key insight, link to full post.]"
    },
    "instagram": {
      "caption": "[Instagram caption. Conversational.
                   Include CTA. Max 200 words.]",
      "hashtags": ["#tag1", "#tag2", "...up to 15 relevant hashtags"]
    }
  }

  RULES:
  - Each platform version should feel native, not copy-pasted
  - LinkedIn: professional, thought-leadership tone
  - Twitter: punchy, quotable, thread-friendly
  - Email: personal, like writing to a friend who's interested in this topic
  - Instagram: visual-first language, emoji-light, community-focused
  - Never start LinkedIn posts with "I'm excited to announce" or "Thrilled to share"
  - Never use "In today's fast-paced world" or similar cliches

OUTPUT:
  - Google Sheet row per blog post with columns for each platform
  - Slack notification: "New content batch ready for review: [post title]"

HUMAN CHECKPOINT:
  - Review all drafts before posting (spreadsheet or Slack approval)
  - Typical review time: 10-15 minutes per blog post batch
  - After refining the prompt for your voice, approval becomes mostly rubber-stamping

SUCCESS METRICS:
  - One blog post → 4 platform-specific pieces within 10 minutes (vs 2-3 hours manually)
  - Draft acceptance rate > 75% (posted with minor or no edits)
  - Consistent posting frequency (no more "I forgot to post this week")
  - Engagement rate maintained or improved vs manually written posts

COMMON PITFALLS:
  - Generic brand voice description — be specific. Share 3-5 example posts you've
    written that nail your voice. Put them in the prompt as examples.
  - Too many hashtags on LinkedIn — 3-5 max. More looks spammy.
  - Identical content across platforms — the whole point is adaptation, not copy-paste.
  - Not including the blog link — every piece should drive traffic back to the source.
```

---

## Stage 7: Email Triage Agent (`/agent:inbox`)

```
AGENT: Email Triage
=====================
USE CASE:      Classify, prioritize, and draft responses for incoming email
               so you spend 15 minutes on email instead of 2 hours.
DIFFICULTY:    Medium
BUILD TIME:    3-4 hours
MONTHLY COST:  $3-15 (based on 200-1000 emails/month)

TRIGGER:       New email received (IMAP polling, every 5 minutes)
SOURCE:        Primary business inbox

INPUT:
  - Sender name and email
  - Subject line
  - Email body (plain text, stripped of signatures)
  - Thread history (if reply)
  - Attachments (flagged, not content-analyzed)

WORKFLOW:
  Step 1: Receive email via IMAP trigger
  Step 2: Skip if sender is in ignore list (newsletters, notifications)
  Step 3: Check if sender is known (client, prospect, vendor lookup)
  Step 4: Send to Claude for classification and priority scoring
  Step 5: Route based on classification:
          - Client (urgent): Slack alert + draft reply → top of queue
          - Client (normal): Draft reply → daily review queue
          - Prospect: Route to lead qualifier agent
          - Vendor/partner: Categorize → weekly review batch
          - Administrative: Auto-label → handle in batch
          - Spam/irrelevant: Archive
  Step 6: Apply Gmail labels based on classification
  Step 7: Log in email tracker spreadsheet

n8n NODES NEEDED:
  - Email Trigger (IMAP):   Poll inbox
  - IF:                      Filter ignore list
  - Google Sheets:           Contact lookup (client/prospect/vendor)
  - HTTP Request:            Claude API call
  - Code:                    Parse classification
  - Switch:                  Route by category
  - Gmail:                   Apply labels, create drafts
  - Slack:                   Alert for urgent items
  - Google Sheets:           Log all classified emails

CLAUDE PROMPT:
  You are an email triage assistant for [YOUR NAME] at [YOUR BUSINESS].

  KNOWN CONTACTS:
  {{ contactContext }}

  BUSINESS CONTEXT:
  - I run [business description]
  - My current priorities are: [list 2-3 current priorities]
  - Active projects: [list active client projects]

  CLASSIFY this email:

  From: {{ senderName }} <{{ senderEmail }}>
  Subject: {{ subject }}
  Body: {{ body }}
  Thread: {{ threadHistory || "New conversation" }}

  Return JSON:
  {
    "category": "client|prospect|vendor|admin|personal|spam",
    "priority": "urgent|high|medium|low",
    "confidence": [0.0-1.0],
    "summary": "[1-sentence summary — what do they want?]",
    "requires_response": true|false,
    "response_deadline": "[today|this week|no rush|never]",
    "suggested_label": "[Gmail label to apply]",
    "draft_response": "[Draft reply if response needed, null otherwise]",
    "action_items": ["item 1", "item 2"],
    "sentiment": "positive|neutral|negative|urgent"
  }

  RULES:
  - Emails from known clients are ALWAYS at least "high" priority
  - Emails mentioning "invoice", "payment", or "overdue" are ALWAYS "urgent"
  - Emails from unknown senders with buying signals → category: "prospect"
  - Newsletter, marketing, notification emails → category: "spam", priority: "low"
  - If uncertain about category, default to "admin" with needs_human: true
  - Draft responses should match my communication style: [brief, professional, friendly]
  - Keep draft responses under 100 words unless the topic requires detail

OUTPUT:
  - Gmail labels applied automatically
  - Draft replies created in Gmail
  - Slack alerts for urgent items
  - Daily summary: "You have X emails to review — Y urgent, Z drafts ready"

HUMAN CHECKPOINT:
  - All draft replies sit in Gmail Drafts until you review and send
  - Urgent client emails: Slack notification so you can respond personally
  - Never auto-send on behalf of the user
  - Daily 15-minute email review: check drafts, send/edit, handle urgent

SUCCESS METRICS:
  - Email processing time: < 15 min/day (vs 1-2 hours)
  - Zero missed urgent emails
  - Draft acceptance rate > 70%
  - All client emails responded to within 4 business hours
  - Inbox stays under 20 unprocessed emails at end of day

COMMON PITFALLS:
  - Overly aggressive spam filtering — legitimate cold outreach may be valuable
  - Not updating the ignore list — new newsletter subscriptions slip through
  - Context gap — the agent doesn't know about a recent phone call or meeting.
    Add a "recent context" field you update weekly.
  - Reply-all disasters — never auto-send. Drafts only.
```

---

## Stage 8: Social Media Agent (`/agent:social`)

```
AGENT: Social Media Scheduler
================================
USE CASE:      Generate and schedule social media posts from your content
               calendar so you never miss a posting day.
DIFFICULTY:    Easy
BUILD TIME:    2-3 hours
MONTHLY COST:  $1-5 (based on 20-60 posts/month)

TRIGGER:       Scheduled — runs daily at 7 AM or weekly on Monday
SOURCE:        Content calendar (Google Sheet) or content repurposer output

INPUT:
  - Content calendar entries for the current period
  - Past post performance data (optional, for optimization)
  - Brand voice guidelines
  - Platform-specific requirements

WORKFLOW:
  Step 1: Cron trigger fires at scheduled time
  Step 2: Read content calendar from Google Sheet
  Step 3: Filter for posts due today/this week
  Step 4: For each scheduled slot without pre-written content:
          - Send topic/theme to Claude for post generation
  Step 5: Format for each platform (character limits, hashtag rules)
  Step 6: Add to posting queue (Buffer, Hootsuite, or direct API)
  Step 7: Log generated posts in content tracker
  Step 8: Weekly: Pull engagement metrics → update performance log

n8n NODES NEEDED:
  - Schedule Trigger:    Daily or weekly cron
  - Google Sheets:       Read content calendar + write generated posts
  - HTTP Request:        Claude API call for post generation
  - Code:                Format for platform requirements
  - HTTP Request:        Post to Buffer/Hootsuite API or LinkedIn/Twitter API
  - Google Sheets:       Log performance metrics
  - Slack:               Weekly engagement summary

CLAUDE PROMPT:
  You are a social media content creator for [YOUR BUSINESS].

  BRAND VOICE: [your voice description]
  AUDIENCE: [who follows you and why]
  GOAL: [thought leadership / lead gen / community / brand awareness]

  CONTENT CALENDAR ENTRY:
  Date: {{ date }}
  Platform: {{ platform }}
  Topic/Theme: {{ topic }}
  Content type: {{ type — e.g., "tip", "story", "question", "case study" }}
  Reference material: {{ reference || "none" }}

  Generate a {{ platform }} post about {{ topic }}.

  PLATFORM RULES:
  - LinkedIn: 150-300 words. Hook in first line. Line breaks for readability.
    Professional but human. End with question or CTA. 3-5 hashtags.
  - Twitter/X: Max 280 chars per tweet. Punchy. Can suggest a thread (max 5 tweets).
  - Instagram: Caption max 200 words. Conversational. 10-15 hashtags (separate block).
    Suggest image concept.

  Return JSON:
  {
    "post_text": "[The post content]",
    "hashtags": ["#tag1", "#tag2"],
    "image_suggestion": "[Description of ideal accompanying image]",
    "best_time_to_post": "[Suggested posting time based on platform best practices]",
    "engagement_hook": "[The element designed to drive engagement — question, poll, CTA]"
  }

  RULES:
  - Never start with "I'm excited to share" or "In today's world"
  - Every post must provide value (teach, inspire, or entertain)
  - Include a mix of formats across the week (don't post 5 tips in a row)
  - Reference real experiences, case studies, or data when possible

OUTPUT:
  - Posts queued in scheduling tool or posted directly
  - Content tracker updated with generated posts
  - Weekly engagement report via Slack

HUMAN CHECKPOINT:
  - Review generated posts before they go live (approval column in sheet)
  - After 2 weeks of consistent quality, consider auto-posting for low-risk platforms
  - Always review before auto-posting on LinkedIn (highest professional stakes)

SUCCESS METRICS:
  - Consistent posting schedule (zero missed days)
  - Post generation time: < 5 min review (vs 30-60 min writing)
  - Engagement rate maintained or improved
  - Follower growth trend positive
  - Content variety score (no more than 2 same-format posts in a row)

COMMON PITFALLS:
  - All posts sound the same — vary the content type (tip, story, question, data)
  - Ignoring platform differences — what works on LinkedIn flops on Twitter
  - Not using a content calendar — random AI-generated posts lack strategy
  - Over-automating — some posts should be spontaneous, reactive, authentic
  - Hashtag spam — quality over quantity, especially on LinkedIn
```

---

## Stage 9: Client Onboarding Agent (`/agent:onboard`)

```
AGENT: Client Onboarding
==========================
USE CASE:      Automate the sequence of emails, tasks, and setup steps when
               a new client signs on — so nothing falls through the cracks.
DIFFICULTY:    Medium
BUILD TIME:    4-6 hours
MONTHLY COST:  $0.50-2 (based on 2-10 new clients/month)

TRIGGER:       New Stripe payment received or contract signed (webhook)
SOURCE:        Stripe webhook, DocuSign webhook, or manual trigger

INPUT:
  - Client name and email
  - Service/package purchased
  - Payment amount and plan
  - Company name (if B2B)
  - Any intake form responses

WORKFLOW:
  Step 1: Receive payment/contract webhook
  Step 2: Send personalized welcome email (immediate)
  Step 3: Create project workspace (ClickUp/Notion/Google Drive folder)
  Step 4: Send intake questionnaire (Typeform/Google Form link)
  Step 5: Schedule kickoff call (Calendly link in follow-up email)
  Step 6: Set up recurring invoice if subscription (Stripe)
  Step 7: Add client to CRM / client tracker spreadsheet
  Step 8: Day 3: Check if intake form completed → reminder if not
  Step 9: Day 7: Check if kickoff scheduled → reminder if not
  Step 10: Create internal brief from intake responses (AI-generated)

n8n NODES NEEDED:
  - Webhook:            Stripe/DocuSign event
  - Code:               Extract and normalize client data
  - Gmail:              Send welcome email sequence
  - HTTP Request:       Create ClickUp/Notion workspace
  - Google Sheets:      Add to client tracker
  - Stripe:             Set up subscription if needed
  - Wait:               Delay nodes for Day 3, Day 7 follow-ups
  - IF:                 Check if intake/kickoff completed
  - HTTP Request:       Claude API for generating client brief
  - Slack:              Internal notification of new client

CLAUDE PROMPT (for client brief generation):
  You are an account manager preparing a client brief for [YOUR BUSINESS].

  CLIENT INFORMATION:
  Name: {{ clientName }}
  Company: {{ companyName }}
  Package: {{ packageName }}
  Intake responses: {{ intakeData }}

  Generate a client brief:
  {
    "executive_summary": "[2-3 sentences about this client and their needs]",
    "goals": ["goal 1", "goal 2", "goal 3"],
    "challenges": ["challenge 1", "challenge 2"],
    "success_criteria": ["metric 1", "metric 2"],
    "communication_preferences": "[how they prefer to communicate]",
    "timeline_expectations": "[their expected timeline]",
    "red_flags": ["any concerns noted from intake"],
    "recommended_approach": "[your suggested strategy]",
    "first_deliverable": "[what to prepare for kickoff]"
  }

WELCOME EMAIL TEMPLATE:
  Subject: Welcome to [YOUR BUSINESS] — Let's get started

  Hi {{ clientName }},

  I'm thrilled to have you on board. Here's what happens next:

  1. Fill out your intake questionnaire (5 min): [FORM_LINK]
  2. Book your kickoff call: [CALENDLY_LINK]
  3. I'll set up your project workspace and share access

  Your project space will be ready within 24 hours. In the meantime,
  the intake form helps me prepare so we hit the ground running on
  our kickoff call.

  Questions before we start? Just reply to this email.

  Looking forward to working together,
  {{ yourName }}

OUTPUT:
  - Welcome email sent (immediate)
  - Project workspace created
  - Client added to tracker
  - Intake form sent
  - Kickoff scheduling email sent
  - Follow-up reminders (Day 3, Day 7) if needed
  - AI-generated client brief (after intake completed)
  - Slack notification to team

HUMAN CHECKPOINT:
  - Review AI-generated client brief before kickoff call
  - Personally respond if client replies to welcome email
  - Approve before escalating missed deadlines (Day 7+ without intake/kickoff)

SUCCESS METRICS:
  - 100% of clients receive welcome email within 5 minutes of payment
  - Intake form completion rate > 85% within 7 days
  - Kickoff call scheduled within 10 business days
  - Zero onboarding steps forgotten or missed
  - Client satisfaction with onboarding process

COMMON PITFALLS:
  - Welcome email feels automated — personalize it. Use their name, reference
    what they bought, acknowledge their specific situation if known.
  - Too many emails too fast — space out the sequence. Welcome immediately,
    intake form in welcome, kickoff scheduling Day 1, first reminder Day 3.
  - Not handling the edge case where someone pays but intake data is missing —
    have a fallback with minimal required info.
  - Workspace creation fails silently — verify workspace exists before sending
    the "your workspace is ready" email.
```

---

## Stage 10: Invoice & Payment Agent (`/agent:invoice`)

```
AGENT: Invoice & Payment Follow-Up
=====================================
USE CASE:      Generate invoices on schedule, send them, track payment status,
               and handle the awkward follow-up emails so you don't have to.
DIFFICULTY:    Easy
BUILD TIME:    2-3 hours
MONTHLY COST:  $0.50-2 (based on 5-30 invoices/month)

TRIGGER:       Project milestone reached, monthly schedule, or manual trigger
SOURCE:        Cron schedule, ClickUp task status change, or manual

INPUT:
  - Client name and email
  - Invoice amount
  - Description of services
  - Due date
  - Payment terms
  - Invoice number (auto-generated)

WORKFLOW:
  Step 1: Generate invoice (Stripe Invoice or custom template)
  Step 2: Send invoice email with PDF attached
  Step 3: Log in payment tracker spreadsheet (status: "sent")
  Step 4: Day 1 after due date: Check if paid
          - If paid: Update tracker, send thank you
          - If unpaid: Continue to Step 5
  Step 5: Day 3 overdue: Send gentle reminder
  Step 6: Day 7 overdue: Send firm reminder
  Step 7: Day 14 overdue: Send final notice
  Step 8: Day 21 overdue: Slack alert to you for personal follow-up
  Step 9: Update tracker at each stage

n8n NODES NEEDED:
  - Schedule Trigger:   Monthly invoice generation
  - Stripe:             Create and send invoice
  - Gmail:              Send invoice + reminders
  - Wait:               Delay between reminder stages
  - Stripe:             Check payment status
  - IF:                 Branch on paid/unpaid
  - Google Sheets:      Payment tracker
  - Slack:              Alert for overdue escalation

STRIPE INVOICE FLOW:
  1. Create Invoice: POST /v1/invoices (customer, auto_advance: false)
  2. Add Line Items: POST /v1/invoices/{id}/items
  3. Finalize: POST /v1/invoices/{id}/finalize
  4. Send: POST /v1/invoices/{id}/send
  5. Check status: GET /v1/invoices/{id} → status field

REMINDER SEQUENCE:

  DAY 3 — Gentle Reminder
  Subject: Quick reminder — Invoice #{{ invoiceNumber }}

  Hi {{ clientName }},

  Just a friendly reminder that invoice #{{ invoiceNumber }} for
  ${{ amount }} was due on {{ dueDate }}.

  You can pay directly here: {{ paymentLink }}

  If you've already sent payment, please disregard this note.

  Best,
  {{ yourName }}


  DAY 7 — Firm Reminder
  Subject: Invoice #{{ invoiceNumber }} — payment overdue

  Hi {{ clientName }},

  I wanted to follow up on invoice #{{ invoiceNumber }} for
  ${{ amount }}, which was due {{ daysOverdue }} days ago.

  Could you let me know when I can expect payment?
  Payment link: {{ paymentLink }}

  Thanks,
  {{ yourName }}


  DAY 14 — Final Notice
  Subject: Final notice — Invoice #{{ invoiceNumber }}

  Hi {{ clientName }},

  This is a final reminder regarding invoice #{{ invoiceNumber }}
  for ${{ amount }}, now {{ daysOverdue }} days overdue.

  Please arrange payment at your earliest convenience: {{ paymentLink }}

  If there's an issue with the invoice or you'd like to discuss
  payment terms, I'm happy to talk.

  {{ yourName }}


  DAY 21+ — Personal Follow-Up (you, not the bot)
  [Slack alert: "Invoice #X for Client Y is 21+ days overdue.
   Amount: $Z. All automated reminders sent. Your turn."]

OUTPUT:
  - Invoices created and sent via Stripe
  - Payment tracker updated at each stage
  - Reminder emails sent on schedule
  - Slack alerts for escalated overdue invoices
  - Monthly summary: invoices sent, paid, outstanding, overdue

HUMAN CHECKPOINT:
  - Review invoice before first send (especially for custom amounts)
  - Day 21+ overdue: you handle personally (may need phone call)
  - Exception: for recurring fixed-amount invoices, auto-send after 2 months
    of correct invoicing

SUCCESS METRICS:
  - 100% of invoices sent on time
  - Average payment time reduced (measure baseline first)
  - Overdue rate < 10%
  - Zero forgotten invoices
  - Time spent on invoicing: < 15 min/month (vs 2-3 hours)

COMMON PITFALLS:
  - Wrong amount — always verify before sending. Double-check for
    recurring invoices that the amount hasn't changed.
  - Aggressive tone in reminders — keep it professional and assume goodwill.
    People forget, have cash flow issues, or miss emails.
  - Not accounting for payment terms — some clients have Net 30 or Net 45.
    The "overdue" clock starts after THEIR terms, not yours.
  - Sending reminders for already-paid invoices — always check Stripe
    status before sending a reminder.
```

---

## Stage 11: Market Research Agent (`/agent:research`)

```
AGENT: Market & Competitor Research
=====================================
USE CASE:      Automate periodic research sweeps on competitors, market trends,
               and industry news — delivered as a concise briefing you can
               read in 5 minutes.
DIFFICULTY:    Hard
BUILD TIME:    5-6 hours
MONTHLY COST:  $5-20 (based on research depth and frequency)

TRIGGER:       Weekly schedule (Monday morning) or on-demand manual trigger
SOURCE:        Cron trigger or manual with research question input

INPUT:
  - Research topic or question
  - Competitor list (names, URLs)
  - Industry keywords
  - Previous research reports (for trend comparison)

WORKFLOW:
  Step 1: Trigger fires (scheduled or manual)
  Step 2: For each competitor:
          - Fetch website homepage and key pages (HTTP Request)
          - Check for new blog posts (RSS)
          - Check social media for recent posts (API)
  Step 3: Search for industry news using news API or web search
  Step 4: Send all gathered data to Claude for synthesis
  Step 5: Generate structured research report
  Step 6: Compare with previous report for trend detection
  Step 7: Deliver report (email + Google Doc + Slack summary)
  Step 8: Archive in research history

n8n NODES NEEDED:
  - Schedule Trigger:    Weekly cron
  - HTTP Request:        Fetch competitor pages
  - RSS Feed Read:       Monitor competitor blogs
  - HTTP Request:        News API or web search API
  - HTTP Request:        Claude API for synthesis
  - Code:                Structure and format report
  - Gmail:               Deliver report
  - Google Sheets:       Archive findings
  - Google Docs:         (Optional) Create formatted report
  - Slack:               Summary notification

CLAUDE PROMPT:
  You are a market research analyst for [YOUR BUSINESS] in the
  [YOUR INDUSTRY] space.

  MY BUSINESS: [brief description of what you do and your positioning]
  MY COMPETITORS: [list with brief descriptions]

  RESEARCH DATA:
  {{ compiledResearchData }}

  Analyze this data and produce a research briefing:

  {
    "executive_summary": "[3-5 sentences — the most important things to know]",
    "competitor_updates": [
      {
        "competitor": "[name]",
        "notable_changes": "[what's new — pricing, features, content, positioning]",
        "threat_level": "low|medium|high",
        "opportunity": "[any gap or weakness you could exploit]"
      }
    ],
    "market_trends": [
      {
        "trend": "[description]",
        "relevance": "low|medium|high",
        "action_suggested": "[what to do about it]",
        "source": "[where this was observed]"
      }
    ],
    "industry_news": [
      {
        "headline": "[news item]",
        "source": "[publication]",
        "impact": "[how this affects your business]",
        "url": "[link]"
      }
    ],
    "opportunities": ["opportunity 1", "opportunity 2"],
    "threats": ["threat 1", "threat 2"],
    "recommended_actions": [
      {
        "action": "[specific action to take]",
        "priority": "low|medium|high",
        "timeline": "[this week|this month|this quarter]"
      }
    ]
  }

  RULES:
  - Focus on actionable intelligence, not just information
  - Flag anything that requires immediate attention
  - Compare with previous findings when available
  - Cite sources for all claims
  - Keep executive summary under 100 words
  - Rank everything by relevance to MY business

SOURCE QUALITY SCORING:
  When evaluating sources, rate reliability:
  - Tier 1 (high): Official company announcements, SEC filings, verified news outlets
  - Tier 2 (medium): Industry blogs, analyst reports, social media from official accounts
  - Tier 3 (low): Forum posts, unverified claims, opinion pieces
  Always note the tier in your analysis.

REPORT TEMPLATE (delivered via email):

  ============================================
  WEEKLY MARKET INTELLIGENCE BRIEFING
  {{ date }}
  ============================================

  EXECUTIVE SUMMARY
  {{ executiveSummary }}

  COMPETITOR WATCH
  {{ competitorUpdates — formatted as bullet points }}

  MARKET TRENDS
  {{ marketTrends — formatted as bullet points }}

  INDUSTRY NEWS
  {{ industryNews — headlines with links }}

  ACTION ITEMS
  {{ recommendedActions — prioritized list }}

  ---
  Sources: {{ sourceCount }} analyzed
  Confidence: {{ overallConfidence }}
  Next report: {{ nextReportDate }}
  ============================================

OUTPUT:
  - Email with formatted research briefing
  - Google Sheet row with structured data for trend tracking
  - Slack summary (executive summary only, link to full report)
  - (Optional) Google Doc with full formatted report

HUMAN CHECKPOINT:
  - Review report before acting on recommendations
  - Flag any surprising findings for deeper manual research
  - Weekly: 5-minute read of the briefing, mark action items to pursue

SUCCESS METRICS:
  - Consistent weekly delivery (zero missed reports)
  - At least 1 actionable insight per report
  - Competitor changes detected within 1 week of occurrence
  - Time spent on research: < 10 min/week review (vs 2-4 hours manual)
  - Source quality: > 70% from Tier 1-2 sources

COMMON PITFALLS:
  - Information overload — the report should be 1-2 pages, not 10. Synthesis
    is more valuable than raw data.
  - Stale competitor list — review and update quarterly
  - Confirmation bias — tell the AI to flag things that challenge your assumptions,
    not just things that confirm them
  - Over-reliance on web scraping — some competitor sites block scraping.
    Have fallback data sources (social media, press releases, job postings).
  - Not acting on findings — the report is useless if you don't read it.
    Keep it short enough that you actually will.
```

---

## Integration Notes

### Feeds From
- `/solo:time` (ORBWEVA time/productivity skill) — identifies which tasks consume time and should be automated
- `/solo:stack` (ORBWEVA tech stack skill) — identifies tools already in your stack that agents can connect to
- Any ORBWEVA founder skill that produces a repeatable process

### Feeds Into
- Actual n8n workflows that execute the automation
- `/solo:metrics` — agent performance contributes to business metrics
- Other ORBWEVA skills that benefit from automated data collection or routing

### Agent Chaining
Agents work best when they feed into each other:

```
EXAMPLE AGENT CHAIN
=====================
[Lead Qualifier] → hot lead detected
       ↓
[Client Onboarding] → payment received
       ↓
[Invoice Agent] → recurring billing set up
       ↓
[Support Agent] → ongoing client support
       ↓
[Content Agent] → case study from project
       ↓
[Social Agent] → promote case study
       ↓
[Research Agent] → find more prospects like this client
       ↓
[Lead Qualifier] → cycle continues
```

### Cost Summary by Agent

```
MONTHLY COST ESTIMATES (typical solopreneur volume)
=====================================================
| Agent              | Volume/month | Est. Cost | Time Saved  |
|--------------------|-------------|-----------|-------------|
| Lead Qualifier     | 50-200      | $1-5      | 3-5 hrs/wk  |
| Support Triage     | 100-500     | $2-10     | 5-8 hrs/wk  |
| Content Repurposer | 4-8 posts   | $1-3      | 2-3 hrs/wk  |
| Email Triage       | 200-1000    | $3-15     | 5-10 hrs/wk |
| Social Scheduler   | 20-60 posts | $1-5      | 2-4 hrs/wk  |
| Client Onboarding  | 2-10        | $0.50-2   | 1-2 hrs/ea  |
| Invoice & Payment  | 5-30        | $0.50-2   | 2-3 hrs/mo  |
| Market Research     | 4 reports   | $5-20     | 8-16 hrs/mo |
|--------------------|-------------|-----------|-------------|
| TOTAL              |             | $14-62/mo | 20-40 hrs/wk|
```

For most solopreneurs, the full stack pays for itself within the first week of operation.
