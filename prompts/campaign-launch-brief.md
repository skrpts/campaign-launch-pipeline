---
type: prompt
id: campaign-launch-brief
title: "Campaign Launch Brief"
description: "Collects campaign details and objectives for launch planning"
tags: [Production]
inputs:
  campaign_name:
    label: "Campaign Name"
    description: "Name or title of the campaign"
    example: "Q3 Product Launch — Analytics Dashboard"
    required: true
    type: text
  business_objectives:
    label: "Business Objectives"
    description: "What this campaign should achieve"
    example: "Generate 500 qualified leads, 10% conversion to trial"
    required: true
    type: text
  target_market:
    label: "Target Market"
    description: "Who you want to reach"
    example: "Marketing managers and CMOs at mid-market B2B SaaS"
    required: true
    type: text
connections:
  - target: audience-segmentation
    type: derived_from
metadata:
  output_format: markdown
  prompt_type: task
---

You are a campaign strategist. Segment the target market for this campaign launch.

**Campaign:** {{input.campaign_name}}
**Objectives:** {{input.business_objectives}}
**Target market:** {{input.target_market}}

Divide into 3-5 actionable segments with demographics, pain points, decision criteria, messaging angle, and channel strategy.
