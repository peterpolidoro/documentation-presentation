---
layout: default
title: Open file formats
permalink: /open-formats/
---

[Home]({{ '/' | relative_url }}) · [Why]({{ '/why/' | relative_url }}) · [MVD checklist]({{ '/mvd/' | relative_url }}) · [Open formats]({{ '/open-formats/' | relative_url }}) · [CAD files]({{ '/cad/' | relative_url }}) · [LLMs]({{ '/llms/' | relative_url }}) · [Templates]({{ '/templates/' | relative_url }}) · [Balance]({{ '/balance/' | relative_url }})

---


# Open file formats (avoid lock-in)

**Rule of thumb:**
> If someone needs to buy a license just to *open* your documentation, it isn’t documentation — it’s a hostage note.

Open formats reduce risk from:
- expired licenses,
- vendor changes,
- missing legacy software,
- and “we can’t open that file anymore.”

## Two-layer strategy (practical, not ideological)

You can still use proprietary tools.  
Just don’t let them be the **only** place the knowledge lives.

### Layer 1 — Source (what you edit)
- Markdown / plain text for notes and READMEs
- CSV for BOMs and tables
- SVG for diagrams when possible
- STEP for CAD interchange (when possible)

### Layer 2 — Exports (what everyone can open)
- PDF (prefer PDF/A when archiving)
- PNG/JPG for photos
- PDF drawings + STEP models for CAD deliverables

## Recommended “open” formats by artifact type

| Artifact | Preferred open format(s) | Why it helps |
|---|---|---|
| Text docs / procedures | `.md`, `.txt` | readable anywhere, diffable, searchable |
| Tables / BOMs | `.csv` | opens in Excel, LibreOffice, Python, etc. |
| Config / parameters | `.json`, `.yaml`, `.toml` | parseable + human-readable |
| Vector diagrams | `.svg` | scalable, editable, web-native |
| Photos | `.jpg`, `.png` | universal viewing + easy sharing |
| Presentations | **web pages** (HTML/Markdown) + `.odp` + PDF export | no license to view; editable via open tools |
| CAD exchange | `.step` / `.stp` (and 2D PDF drawings) | durable interchange across CAD tools |
| CAD visualization / review | `.glb` (glTF) | lightweight viewing, Blender/web, fast sharing |
| Experimental data | `.csv` or domain standard (HDF5/NetCDF/etc.) | long-term reuse |

## CAD exports (Inventor/Vault friendly)

If your team uses a proprietary CAD + PDM stack, you can still keep downstream collaboration open:
- export **STEP** for engineering interchange
- export **GLB (glTF)** for viewing/review

See: [CAD exports: STEP vs GLB]({{ '/cad/' | relative_url }})

## Presentations without PowerPoint

If your “slides” are:
- a GitHub Pages site (like this one), or
- a Markdown → HTML slide deck tool (Reveal.js/Marp/etc.), or
- an `.odp` file (OpenDocument Presentation),

…then anyone can view the content without purchasing a proprietary office suite.

## A small but powerful habit

Whenever you make something in a proprietary tool:
1. Save the native file (if needed)
2. Export an open version **in the same folder**
3. Write 2 sentences: what changed + why

➡️ Next: [LLMs and documentation]({ '/llms/' | relative_url })