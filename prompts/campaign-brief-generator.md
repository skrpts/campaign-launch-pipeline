---
type: prompt
id: campaign-brief-generator
title: Campaign Brief Generator
description: "Creates a structured campaign brief from initial requirements"
tags: [Production]
connections:
  - target: campaign-brief-template
    type: references
---

Create a structured campaign brief from the following inputs. Include:

- Campaign name and tagline options
- Background and business context
- SMART objectives
- Target audience (primary and secondary)
- Key messages (3 max)
- Channel recommendations with rationale
- Budget breakdown
- Timeline with milestones
- Success metrics and measurement plan
- Risks and contingencies

## Inputs

Use the campaign plan, audience segment profiles, and business context provided by the previous pipeline stages to generate the brief.
