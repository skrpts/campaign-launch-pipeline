---
type: workflow
id: campaign-launch-pipeline
title: Campaign Launch Pipeline
description: "End-to-end campaign creation: brief, audience segmentation, copy, and launch plan"
tags: [Production, analysis:audience, planning:campaign, design:launch]
connections:
  - target: audience-segmentation
    type: uses
  - target: campaign-planning
    type: uses
  - target: campaign-brief-generator
    type: uses
  - target: copywriting
    type: uses
  - target: content-briefing
    type: uses
  - target: llm-service
    type: runs_on
  - target: brand-voice-guide
    type: references
metadata:
  estimated_duration: "15-30 minutes"
  trigger: manual
---

## Overview

This workflow guides a complete campaign launch from initial audience analysis through to polished, ready-to-publish copy. It ensures campaigns are grounded in audience insight, structured with clear objectives, and expressed in compelling, on-brand language.

## Pipeline Stages

### Stage 1: Audience Segmentation

**Input:** Customer data, market research, behavioural analytics

Invoke the **audience-segmentation** skill to analyse the target market and identify distinct audience segments. Each segment is profiled with demographics, psychographics, pain points, preferred channels, and a recommended messaging angle.

**Output:** Segment profiles ready for campaign targeting

### Stage 2: Campaign Planning

**Input:** Segment profiles, business objectives, budget, timeline

Invoke the **campaign-planning** skill to design a multi-channel campaign strategy. This stage maps audience segments to channels, allocates budget, sets KPIs, and builds a content calendar with milestones.

**Output:** Draft campaign plan with channel mix, timeline, and budget breakdown

### Stage 3: Campaign Brief Generation

**Input:** Campaign plan, segment profiles, business context

Invoke the **campaign-brief-generator** prompt to produce a structured campaign brief from the plan. The brief includes SMART objectives, key messages, channel rationale, measurement plan, and risk assessment. It uses the **campaign-brief-template** as its structural foundation.

**Output:** Complete campaign brief document

### Stage 4: Copywriting

**Input:** Campaign brief, brand voice guidelines, content style guide

Invoke the **copywriting** skill to produce channel-specific copy for all touchpoints defined in the campaign plan. Copy is written against the **brand-voice-guide** and **content-style-guide** to ensure consistency across channels.

**Output:** Polished copy for each channel: headlines, body text, and call-to-action variants

## Inputs

| Name | Required | Description | Example |
|------|----------|-------------|---------|
| `{{input.customer_data}}` | Yes | Customer data | `Paste the latest metrics, exported data, or summary notes relevant to the workflow.` |
| `{{input.market_research}}` | Yes | market research | `Paste the relevant brief, notes, source material, or dataset here.` |
| `{{input.behavioural_analytics}}` | Yes | behavioural analytics | `Paste the latest metrics, exported data, or summary notes relevant to the workflow.` |
| `{{input.business_objectives}}` | No | business objectives | `Paste the relevant brief, notes, source material, or dataset here.` |

## Outputs

| Name | Description |
|------|-------------|
| Segment profiles | Audience segments with demographics, psychographics, pain points, and channel preferences |
| Campaign plan | Multi-channel strategy with channel mix, timeline, and budget breakdown |
| Campaign brief | Structured brief with SMART objectives, key messages, measurement plan, and risk assessment |
| Channel copy | Polished copy for each channel: headlines, body text, and call-to-action variants |

## Setup

Before running this workflow:

1. No external services required — paste your content directly and provide any supporting context as inputs or source nodes.
2. Review the included documents, assets, or source nodes and customise them to match your team, brand, or domain conventions where needed.
3. No specific AI provider or API key is required beyond your configured skrptiq LLM provider.

## Provider Notes

- Most stages work with any capable model; stronger models usually improve synthesis, judgement, and writing quality.
- Extraction, classification, and formatting steps generally run well on smaller or faster models.
- Because there are no vendor-specific integrations here, provider choice is mostly a trade-off between speed, quality, and cost.

## Example Input

To test this workflow immediately after import, paste the following sample data into each input field:

**Customer Data:**
```
FocusFlow is a B2B SaaS productivity app for teams of 10–200. Current customer base: 3,400 paying accounts, mostly in tech, professional services, and education. Monthly churn: 4.2%. Average contract value: £380/year. Top acquisition channels: organic search (38%), referrals (27%), paid search (19%). Support tickets show the most-loved features are shared task boards and the daily focus planner. Most-requested missing feature: calendar integration. NPS score: 42 (up from 36 last quarter). 68% of active users log in at least 4 days per week.
```

**Market Research:**
```
UK productivity software market growing at 12% CAGR. Key competitors: Todoist (consumer-focused, strong brand), Asana (enterprise, complex onboarding), and Motion (AI-native, small but growing fast). FocusFlow's differentiator is simplicity — teams adopt it without training. Analyst reports highlight a gap in the market for "mid-complexity" tools that sit between simple to-do apps and full project management suites. Buyer personas from recent interviews: Team Leads who want visibility without micromanaging, and Operations Managers who need reporting without the overhead of enterprise tools. Seasonal trend: new tool adoption spikes in January and September (new year / post-summer planning).
```

**Behavioural Analytics:**
```
Highest-engagement feature: shared task boards (used by 84% of active teams). Onboarding completion rate: 61% — biggest drop-off at the "invite teammates" step (only 43% complete it). Users who invite at least 2 teammates in the first week have 3x higher 90-day retention. Email open rates: 28% average, 41% for product update emails. Blog traffic has grown 22% quarter-on-quarter; top-performing posts are "how-to" guides and comparison articles. Free trial to paid conversion: 11%. Users who engage with the daily focus planner during trial convert at 19%.
```

**Business Objectives:**
```
Q2 2025 growth campaign. Primary goal: increase free trial sign-ups by 30% over Q1 baseline (Q1 baseline: 1,200 trials/month). Secondary goal: improve trial-to-paid conversion from 11% to 15% by driving activation of key features during trial. Budget: £45,000 for the quarter. Channels to consider: paid search, LinkedIn advertising, content marketing, email nurture sequences, and partner co-marketing. Brand constraint: no aggressive comparison marketing — position on own strengths rather than competitor weaknesses. Campaign must be live by 7 April 2025.
```

