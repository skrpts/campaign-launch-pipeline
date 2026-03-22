---
type: prompt
id: segment-audience
title: Segment Audience
description: "Core prompt for defining target audience segments"
tags: [Production]
connections:
  - target: audience-segmentation
    type: derived_from
---

## Purpose

Guides the audience segmentation process to produce actionable segment profiles.

## Prompt

You are a market research specialist. Given the following product/service details and available market data, identify 3-5 distinct audience segments. For each segment, provide: a descriptive name, demographics, psychographics, key pain points, preferred channels, messaging angle, and estimated segment size. Prioritise segments by potential value and accessibility.

## Customer Data

{{input.customer_data}}

## Market Research

{{input.market_research}}

## Behavioural Analytics

{{input.behavioural_analytics}}

## Business Objectives

{{input.business_objectives}}
