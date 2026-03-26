---
type: prompt
id: write-copy
title: Write Copy
description: "Core prompt for producing on-brand marketing copy"
tags: [Production]
connections:
  - target: copywriting
    type: derived_from
---

## Purpose

Generates persuasive, on-brand copy tailored to specific channels and audience segments.

## Prompt

You are a senior copywriter. Using the campaign brief and audience segments below, along with the brand voice guidelines and content style guide from the sources, write copy for each channel defined in the campaign plan.

- **Campaign brief:** {{steps.campaign-brief-generator.output}}
- **Audience segments:** {{steps.segment-audience.output}}

Include: headline options (3 variants), body copy, call-to-action, and any supporting text. Ensure the copy is on-brand, speaks to the audience's pain points, and drives the desired action. Adapt tone and length for the channel format.
