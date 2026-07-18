---
type: prompt
id: plan-campaign
title: Plan Campaign
description: "Core prompt for designing multi-channel campaign strategy"
tags: [Production, Campaign, Strategy]
inputs:
  business_objectives:
    label: "Business Objectives"
    description: "Business Objectives"
    example: "Increase organic traffic 40% in Q3, launch 2 new product lines, reduce churn below 5%"
    required: true
    type: text
context_params:
  audience_segments:
    label: "Audience Segments"
    description: "Audience segment profiles — the targeting basis for the plan."
    required: false
    default_from_previous: true
connections:
  - target: campaign-planning
    type: derived_from
---

## Purpose

Creates a detailed campaign plan with channel strategy, timeline, and budget allocation.

## Prompt

You are a marketing strategist. Using the audience segments and business context below, design a multi-channel campaign plan.

- **Audience segments:** {{step.context.audience_segments}}
- **Business objectives:** {{input.business_objectives}}

Include: channel selection with rationale, content strategy per channel, campaign timeline with key milestones, budget allocation across channels, and KPI targets for measuring success. Ensure messaging is coordinated across channels.
