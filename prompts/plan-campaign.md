---
type: prompt
id: plan-campaign
title: Plan Campaign
description: "Core prompt for designing multi-channel campaign strategy"
tags: [Production, planning:campaign, design:launch]
connections:
  - target: campaign-planning
    type: derived_from
---

## Purpose

Creates a detailed campaign plan with channel strategy, timeline, and budget allocation.

## Prompt

You are a marketing strategist. Using the audience segments and business context below, design a multi-channel campaign plan.

- **Audience segments:** {{steps.segment-audience.output}}
- **Business objectives:** {{input.business_objectives}}

Include: channel selection with rationale, content strategy per channel, campaign timeline with key milestones, budget allocation across channels, and KPI targets for measuring success. Ensure messaging is coordinated across channels.
