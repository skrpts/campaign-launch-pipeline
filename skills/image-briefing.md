---
type: skill
id: image-briefing
title: Image Briefing
description: "Generates detailed image briefs for designers or AI image generators from campaign or content context"
tags: [Production, Creative, Marketing]
connections:
  - target: llm-service
    type: runs_on
---

## Capability

Takes campaign context, content themes, or brand guidelines and produces structured image briefs that can be handed to a designer or fed to an AI image generator. Each brief specifies composition, mood, colour palette, subject matter, and format constraints.

## When to Use

- When a marketing campaign needs visual assets but the content team writes the briefs
- When social media posts need accompanying images defined at planning time
- When product launches require visual specifications before the design team is engaged

## What It Produces

For each requested image:

1. **Subject** — what the image should depict
2. **Composition** — layout, focal point, framing (e.g. "centred product shot", "lifestyle scene")
3. **Mood and tone** — emotional quality (e.g. "professional but approachable", "bold and urgent")
4. **Colour palette** — specific colours or palette constraints (e.g. "brand colours only", "warm earth tones")
5. **Format** — dimensions, aspect ratio, file format (e.g. "1080x1080 for Instagram", "16:9 hero banner")
6. **Text overlay** — any text that should appear on the image, with placement guidance
7. **Negative constraints** — what the image should NOT include

## Inputs

- Campaign brief, content plan, or post description
- Brand guidelines (optional — used to constrain colour and style)
- Target platform (optional — determines format constraints)

## Outputs

One or more structured image briefs, each with all fields above populated.
