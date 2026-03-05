---
layout: default
title: LLMs and documentation
permalink: /llms/
---

[Home]({{ '/' | relative_url }}) · [Why]({{ '/why/' | relative_url }}) · [MVD checklist]({{ '/mvd/' | relative_url }}) · [Open formats]({{ '/open-formats/' | relative_url }}) · [CAD files]({{ '/cad/' | relative_url }}) · [LLMs]({{ '/llms/' | relative_url }}) · [Templates]({{ '/templates/' | relative_url }}) · [Balance]({{ '/balance/' | relative_url }})

---


# LLMs and documentation

LLMs changed *how* we create and consume documentation — but they **did not** remove the need for it.

## What LLMs are great at

- turning rough notes into clean READMEs
- producing checklists and troubleshooting trees
- summarizing long documents
- generating consistent formatting and tone

**LLMs reduce the cost of “packaging” information.**

## What LLMs cannot do (without real inputs)

- infer wiring you never captured
- recreate calibration steps you never wrote down
- guess which revision was “the one that worked”
- replace photos you didn’t take before closing the enclosure

**If the ground truth is missing, the model will fill gaps — often confidently.**

## So: should documentation be “for LLMs” too?

Write for humans first — and make it machine-friendly by default.

Machine-friendly usually means:
- plain text formats (Markdown/CSV/etc.)
- short sections with clear headings
- numbered procedures
- explicit values and expected results
- captions/alt text for images (so content is searchable)

## A useful mental model

- Docs are your **source of truth**
- LLMs are an **accelerator** that makes your truth easier to access

➡️ Next: [Templates]({ '/templates/' | relative_url })
