---
layout: default
title: Copy/paste templates
permalink: /templates/
---

[Home]({{ '/' | relative_url }}) · [Why]({{ '/why/' | relative_url }}) · [MVD checklist]({{ '/mvd/' | relative_url }}) · [Open formats]({{ '/open-formats/' | relative_url }}) · [CAD files]({{ '/cad/' | relative_url }}) · [LLMs]({{ '/llms/' | relative_url }}) · [Templates]({{ '/templates/' | relative_url }}) · [Balance]({{ '/balance/' | relative_url }})

---


# Copy/paste templates

These are intentionally **boring**. Boring is good: it scales.

## README template (hardware + software)

```text
Project: <name>
Owner / contact:
Last updated: YYYY-MM-DD
Status: Explore | Prototype | Deliver

1) Summary (what is it?)
- Purpose:
- Current state:
- What “working” means:

2) Where things are
- CAD:
- Exports (PDF/STEP/DXF):
- BOM:
- Schematics:
- Firmware/software:
- Test data:

3) Photos
- 00_photos/<filenames>

4) Build / setup
- Tools required:
- Safety notes:
- Steps:
- Gotchas:

5) Connections (wiring / optics / plumbing)
- Power:
- Signals:
- Grounding/shielding:
- Alignment references:

6) Operation (how to use it)
- Startup:
- Normal use:
- Shutdown:
- Troubleshooting:

7) Verification (how to know it works)
- Test procedure:
- Expected results:
- Calibration constants & where stored:

8) Known issues / TODO
- …

9) Changelog (what changed, when, why)
- YYYY-MM-DD: <change> (reason)
```

## Photo checklist (minimum set)

- [ ] Full system on bench (with a ruler for scale)
- [ ] Inside the enclosure *before closing it*
- [ ] Connectors and cable routing closeups
- [ ] Labels / part numbers / key components
- [ ] One photo that shows the “reference orientation” (for reassembly)

## “Definition of Done” checklist

A task is done when:
- [ ] someone else can reproduce the result from your doc
- [ ] files are in open formats (or have open exports)
- [ ] the test procedure is written and it passes (or failure is documented)
- [ ] the next step is obvious

---

If you want this template as a single printable page, export this site page to PDF.
