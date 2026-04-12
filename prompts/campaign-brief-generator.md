---
type: prompt
id: campaign-brief-generator
title: Campaign Brief Generator
description: "Creates a structured campaign brief from initial requirements"
tags: [Production, Campaign, Strategy]
inputs:
  business_objectives:
    label: "Business Objectives"
    description: "Business Objectives"
    example: "Increase organic traffic 40% in Q3, launch 2 new product lines, reduce churn below 5%"
    required: true
    type: text
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

- **Campaign plan:** {{steps.Campaign Planning.output}}
- **Audience segment profiles:** {{steps.Audience Segmentation.output}}
- **Business objectives:** {{input.business_objectives}}
