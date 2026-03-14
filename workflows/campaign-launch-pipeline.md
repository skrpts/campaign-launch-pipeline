---
type: workflow
id: campaign-launch-pipeline
title: Campaign Launch Pipeline
description: "End-to-end campaign creation: brief, audience segmentation, copy, and launch plan"
tags: [Production]
connections:
  - target: audience-segmentation
    type: uses
  - target: campaign-planning
    type: uses
  - target: campaign-brief-generator
    type: uses
  - target: copywriting
    type: uses
  - target: llm-service
    type: runs_on
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

Invoke the **copywriting** skill to produce channel-specific copy for all touchpoints defined in the campaign plan. Copy is written against the **brand-voice-guidelines** and **content-style-guide** to ensure consistency across channels.

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
| Segment profiles ready for campaign targeting | Segment profiles ready for campaign targeting |
| Draft campaign plan | Draft campaign plan with channel mix, timeline, and budget breakdown |
| Complete campaign brief document | Complete campaign brief document |
| Polished copy for each channel: headlines, body text, and call-to-action variants | Polished copy for each channel: headlines, body text, and call-to-action variants |

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

To test this workflow immediately after import:

```
Customer Data: "Paste the latest metrics, exported data, or summary notes relevant to the workflow."
Market Research: "Paste the relevant brief, notes, source material, or dataset here."
Behavioural Analytics: "Paste the latest metrics, exported data, or summary notes relevant to the workflow."
Business Objectives: "Paste the relevant brief, notes, source material, or dataset here."
```

