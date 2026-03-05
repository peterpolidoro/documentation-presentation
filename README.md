# Documentation as a Deliverable (GitHub Pages talk)

**Live site (slide-like pages):** https://peterpolidoro.github.io/documentation-presentation/

This repository contains a short, projector-friendly talk published as **GitHub Pages** from the `docs/` directory.
The **web pages are the “slides.”**

This README is the **handout**: detailed notes, rationale, and copy/paste templates.

---

## The 10-minute message

If I disappeared tomorrow, could you rebuild this safely and correctly?

To make work repeatable, you need two things:

1. **Evidence** of what exists (photos, measurements, revisions)
2. **Instructions** to reproduce and verify (what, why, how, expected results)

> The hardware and software are artifacts — the documentation is the product.

---

## Minimum Viable Documentation (MVD) — handout version

If you do nothing else, capture these.

1) **One-paragraph summary**
- What is it?
- Who is it for?
- What does “working” mean?

2) **Photos (fastest win)**
- Full system overview on the bench
- Inside enclosure *before closing it*
- Closeups of connectors, labels, cable routing, optics alignment references
- Include a ruler / known object for scale when it helps

3) **Bill of Materials (BOM)**
- A simple **CSV** is fine
- Mark critical parts, alternates, and “long lead” items

4) **Interfaces / connections**
- Power requirements and connector types
- Wiring/pinout, grounding/shielding notes, “do not plug X into Y” warnings
- Optics/mechanics: reference datums, alignment features, coordinate conventions

5) **Build/setup steps (short, but real)**
- The order that matters
- Tools required
- The non-obvious “gotchas”

6) **Test + calibration**
- Procedure to verify it works
- Expected results (numbers or pass/fail conditions)
- Where calibration constants live and how they are updated

7) **Versions + known issues**
- CAD revision / export date
- PCB/schematic revision
- Firmware/software version
- Config/settings files
- What doesn’t work yet and the next step

### Definition of Done (simple rule)

A task is not “done” until:
- someone else can follow the doc and get the same result, **or**
- you documented why it’s not repeatable yet.

---

## Open file formats (avoid lock-in)

**Rule of thumb:** if someone needs to buy a license just to *open* your documentation, it isn’t documentation.

### Two-layer strategy (practical, not ideological)

You can still use proprietary tools. Just don’t let them be the **only** place the knowledge lives.

- **Layer 1 — Source (what you edit):** native CAD, native schematics, native docs, etc.
- **Layer 2 — Exports (what everyone can open):** open, durable formats stored beside the source

### Recommended formats by artifact type

| Artifact | Preferred open format(s) | Notes |
|---|---|---|
| Text docs / procedures | `.md`, `.txt` | readable anywhere, diffable, searchable |
| Tables / BOMs | `.csv` | opens in Excel, LibreOffice, Python, etc. |
| Config / parameters | `.json`, `.yaml`, `.toml` | parseable + human-readable |
| Diagrams | `.svg` | scalable, editable, web-native |
| Photos | `.jpg`, `.png` | universal viewing |
| Drawings | `.pdf` | good “frozen” deliverable |
| Presentations | **web pages (HTML/Markdown)** + `.odp` + PDF export | avoid proprietary slide lock-in |
| CAD exchange | `.step` / `.stp` (+ 2D PDF drawings) | durable interchange across CAD tools |
| CAD visualization / review | `.glb` (glTF) | lightweight viewing, Blender/web |

---

## Inventor + Vault collaboration: what to export

If your mechanical team uses **Inventor with Vault**, keep that as the internal source-of-truth *for editing*.
But publish a predictable “export bundle” so that everyone can view and reuse the design.

### STEP vs GLB (what each is for)

**STEP (`.step/.stp`) — engineering truth**
- Precise CAD geometry (good for measurement/manufacturing interchange)
- Best when downstream users need *accurate* solids/surfaces
- Reality: you usually lose parametric history/features when crossing CAD systems

**GLB (`.glb`) — fast preview**
- Mesh + materials for quick viewing/review (great for web + Blender)
- Best when the goal is “see it and discuss it” rather than manufacture it
- Not a substitute for manufacturing accuracy

**Recommendation:** export **both** when practical.

### A “release package” policy that works with Vault

For every released revision/milestone, publish an export bundle like:

```
/exports/<project>/<rev_or_date>/
  model.step          # assembly (and/or key parts)
  model.glb           # optional: same assembly for fast viewing
  drawings.pdf        # 2D drawings export
  bom.csv             # BOM/table
  README.md           # what changed + how to verify
  preview.png         # optional quick screenshot/render
```

In the `README.md`, include:
- units
- coordinate system / datums
- verification notes (test points, measurements)
- Vault item/revision IDs (traceability)

---

## LLMs and documentation (handout notes)

LLMs reduce the cost of **packaging** information (clean READMEs, checklists, summaries).
They do not replace **ground truth**:

- photos you didn’t take
- wiring you didn’t capture
- calibration steps you never wrote down
- “which revision worked” if you never recorded it

Practical guidance:
- Write for humans first.
- Make it machine-friendly by default: open text formats, clear headings, short sections, numbered procedures, explicit values and expected results.

---

## Copy/paste templates

### README template (hardware + software)

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

### Photo checklist (minimum set)

- [ ] Full system on bench (include a ruler if helpful)
- [ ] Inside enclosure *before closing it*
- [ ] Connectors and cable routing closeups
- [ ] Labels / part numbers / key components
- [ ] One photo that shows the “reference orientation” for reassembly

### “Definition of Done” checklist

- [ ] someone else can reproduce the result from the doc **or** failure is documented
- [ ] open formats exist (or open exports exist) next to the source files
- [ ] test procedure is written and it passes (or failure is documented)
- [ ] next step is obvious

---

## How this site is built

- GitHub Pages serves the content in `docs/`.
- Pages are written in Markdown (`.md`).
- The site theme is Cayman, with presentation-focused CSS overrides in `docs/assets/css/style.scss`.

To enable GitHub Pages:
1) Repo Settings → Pages
2) Deploy from a branch
3) Branch: `main`  Folder: `/docs`

---

## License (optional)

If you want others to reuse the talk, consider adding a Creative Commons license, e.g. CC BY 4.0.
