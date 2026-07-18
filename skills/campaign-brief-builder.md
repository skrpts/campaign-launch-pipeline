---
type: skill
id: campaign-brief-builder
title: Campaign Brief Generator
description: "Assembling a structured campaign brief from the campaign plan and audience segment profiles"
tags: [Production, Campaign, Strategy]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "4 minutes"
  avg_tokens: 3000
  trigger: manual
---

## Campaign Brief Generator

This skill compiles a structured campaign brief from the upstream campaign plan and audience segment profiles, ready to drive copywriting and creative production.

### Core Capability

Given the campaign plan plus the audience segment profiles, this skill produces a complete brief: SMART objectives, key messages, channel rationale, budget and timeline, measurement plan, and a risk assessment. It grounds every recommendation in the plan and segment evidence rather than restating them.

### Output Structure

A markdown campaign brief that downstream copywriting consumes as its single source of truth for messaging, channels, and success metrics.
