---
layout: default
title: Minimum Viable Documentation checklist
permalink: /mvd/
---

[Home]({{ '/' | relative_url }}) · [Why]({{ '/why/' | relative_url }}) · [MVD checklist]({{ '/mvd/' | relative_url }}) · [Open formats]({{ '/open-formats/' | relative_url }}) · [CAD files]({{ '/cad/' | relative_url }}) · [LLMs]({{ '/llms/' | relative_url }}) · [Templates]({{ '/templates/' | relative_url }}) · [Balance]({{ '/balance/' | relative_url }})

---


# Minimum Viable Documentation (MVD)

If you do nothing else, do this.

This is designed to be **Windows/CAD friendly** and low friction.

## MVD checklist

### 1) One-paragraph summary
- What is it?
- Who is it for?
- What does “working” mean?

### 2) Photos (the fastest win)
- Overall view + closeups
- **Before closing panels**
- Include at least one photo that shows **cables / connectors / labels**

### 3) Bill of Materials (BOM)
- A simple **CSV** is fine
- Mark critical parts and substitutes

### 4) Connections / interfaces
- Wiring/pinout
- Power requirements
- Any grounding/shielding rules
- Any “do not plug X into Y” warnings

### 5) Build/setup steps (short)
- The order that matters
- Tools required
- The non-obvious “gotchas”

### 6) Test & calibration
- Procedure to verify it works
- Expected results (numbers or pass/fail)
- Where calibration constants live

### 7) Versions / revisions
- CAD revision / drawing export date
- PCB/schematic revision
- Firmware/software version
- Config files / settings

### 8) Known issues & next steps
- What doesn’t work yet
- What to try next
- What you suspect is fragile

## Definition of Done (simple rule)

A task is not “done” until:
- someone else can follow the doc and get the same result, **or**
- you documented why it’s not repeatable yet.

➡️ Next: [Open formats]({ '/open-formats/' | relative_url })
