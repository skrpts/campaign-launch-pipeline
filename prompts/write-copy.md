---
type: prompt
id: write-copy
title: Write Copy
description: "Core prompt for producing on-brand marketing copy"
tags: [Production, Campaign, Strategy]
context_params:
  campaign_brief:
    label: "Campaign Brief"
    description: "The structured campaign brief — the source of truth for messaging and channels."
    required: false
    default_from_previous: true
  audience_segments:
    label: "Audience Segments"
    description: "Audience segment profiles — the targeting evidence for the copy."
    required: false
connections:
  - target: copywriting
    type: derived_from
---

## Purpose

Generates persuasive, on-brand copy tailored to specific channels and audience segments.

## Prompt

You are a senior copywriter. Using the campaign brief and audience segments below, along with the brand voice guidelines and content style guide from the sources, write copy for each channel defined in the campaign plan.

- **Campaign brief:** {{step.context.campaign_brief}}
- **Audience segments:** {{step.context.audience_segments}}

Include: headline options (3 variants), body copy, call-to-action, and any supporting text. Ensure the copy is on-brand, speaks to the audience's pain points, and drives the desired action. Adapt tone and length for the channel format.
