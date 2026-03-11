# solo-agents

Your AI-powered business operating system. Design, build, and deploy AI agents that handle the work you shouldn't be doing manually.

A Claude Code skill for solopreneurs who want to automate their business with n8n and the Claude API -- without over-engineering it.

## Install

```bash
npx skills add ORBWEVA/solo-agents
```

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

## Architecture

```
  /agent:audit                /agent:design              /agent:build
  List all tasks         -->  Spec the agent        -->  Build in n8n
  Score by ROI                Define trigger,             Wire up Claude API
  Prioritize                  workflow, tools,            Error handling
                              output, fallback            Deploy + monitor
       |                           |                           |
       v                           v                           v
  +----------+              +------------+             +-------------+
  | DISCOVER |    ------>   |   DESIGN   |   ------>   |    BUILD    |
  | what to  |              |   how it   |             |   make it   |
  | automate |              |   works    |             |   real      |
  +----------+              +------------+             +-------------+
                                                              |
                                                              v
                                                       +-------------+
                                                       |   DEPLOY    |
                                                       |   monitor   |
                                                       |   iterate   |
                                                       +-------------+
```

## Agent Recipes

| Recipe | Command | Difficulty | Build Time | Monthly Cost |
|--------|---------|------------|------------|--------------|
| Lead Qualifier | `/agent:leads` | Medium | 3-4 hours | $1-5 |
| Customer Support | `/agent:support` | Medium | 4-5 hours | $2-10 |
| Content Repurposer | `/agent:content` | Easy | 2-3 hours | $1-3 |
| Email Triage | `/agent:inbox` | Medium | 3-4 hours | $3-15 |
| Social Scheduler | `/agent:social` | Easy | 2-3 hours | $1-5 |
| Client Onboarding | `/agent:onboard` | Medium | 4-6 hours | $0.50-2 |
| Invoice & Payment | `/agent:invoice` | Easy | 2-3 hours | $0.50-2 |
| Market Research | `/agent:research` | Hard | 5-6 hours | $5-20 |

**Total estimated cost for all agents: $14-62/month. Estimated time saved: 20-40 hours/week.**

## How It Works

This is a pure markdown skill -- no executable code, no dependencies. It provides structured frameworks, templates, and step-by-step recipes that Claude Code uses to guide you through designing and building AI agents.

Each recipe includes:
- Trigger and input specification
- Complete n8n workflow architecture
- Claude API system prompts (copy-paste ready)
- Human checkpoint definitions
- Cost estimates and success metrics
- Common pitfalls and how to avoid them

## Principles

1. **Automate the repeatable, humanize the valuable.**
2. **Every agent needs a human checkpoint.**
3. **Start with the highest-ROI automation, not the coolest one.**
4. **An agent that fails silently is worse than no agent.**
5. **Cost per automation < cost of your time.**

## Part of the ORBWEVA Founder Toolkit

Built by [ORBWEVA](https://github.com/ORBWEVA) for solopreneurs and small teams running lean.

See also:
- [@orbweva/gtm-skills](https://github.com/ORBWEVA/gtm-skills) -- GTM, GEO, and SEO skills
- [@orbweva/dt-skill](https://github.com/ORBWEVA/dt-skill) -- Design Thinking skill

## License

MIT
