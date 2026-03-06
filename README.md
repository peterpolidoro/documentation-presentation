# Documentation as a Deliverable (GitHub Pages talk)

**Live site (slides):** https://peterpolidoro.github.io/documentation-presentation/

This repository contains a short, projector-friendly talk published as **GitHub Pages** from the `docs/` directory.
The **web pages are the slides**.

This README is the **handout**: the fuller argument, practical details, format recommendations, and copy/paste templates.

---

## The story in one paragraph

We are all makers, and we love building quality tools for others.
I used to think the job ended when a high-quality rig or instrument was delivered to a scientist.
Over time I realized a working instrument is only the meal.
The lab also needs the recipe: the parts, steps, settings, tests, and rationale that let other people rebuild it, trust it, and improve it.
That is what documentation is for.

A short version of the message is:

- a working rig or instrument is **one good meal**
- documentation is **the recipe**
- quality in a lab means delivering **the recipe and at least one verified meal**

---

## Slide sequence

The current GitHub Pages presentation is organized as:

1. **Makers** - shared identity and pride in craft
2. **The job I thought I had** - build it, hand it off, move on
3. **Meals and recipes** - the core metaphor
4. **Recipe card** - what must be captured
5. **Open formats** - a recipe only helps if people can open it
6. **Balance** - do not write the whole cookbook before tasting the dish
7. **Done** - someone else can open it, understand it, rebuild it, and modify it

---

## Quality means repeatability

A beautiful, clever, high-performing artifact is valuable.
But in a scientific and engineering environment, the deeper value is that other people can:

- understand what was built
- trust how it works
- repeat the result
- change it without starting from zero

That is why the deliverable is not only the physical artifact or the software artifact.
The deliverable is also the documentation that makes the design legible and reproducible.

> The hardware and software are artifacts. The documentation is the recipe that makes them transferable.

---

## Minimum Viable Documentation (the recipe card)

If you do nothing else, capture these.

### 1) What it is
- What is it?
- Who is it for?
- What does "working" mean?

### 2) Photos (fastest win)
- Full system overview on the bench
- Inside enclosure **before closing it**
- Closeups of connectors, labels, cable routing, optics alignment references
- Include a ruler or known object for scale when it helps

### 3) Bill of Materials (BOM)
- A simple **CSV** is fine
- Mark critical parts, alternates, and long-lead items

### 4) Interfaces and connections
- Power requirements and connector types
- Wiring/pinout, grounding/shielding notes, warnings
- Optics/mechanics: reference datums, alignment features, coordinate conventions

### 5) Build and setup steps
- The order that matters
- Tools required
- Non-obvious gotchas

### 6) Test and calibration
- Procedure to verify it works
- Expected results (numbers or pass/fail conditions)
- Where calibration constants live and how they are updated

### 7) Versions and known issues
- CAD revision / export date
- PCB and schematic revision
- Firmware/software version
- Config/settings files
- What does not work yet and the next step

### Definition of Done

A task is not done until:
- someone else can follow the doc and get the same result, or
- you documented why it is not repeatable yet.

---

## Open file formats (avoid lock-in)

**Rule of thumb:** if someone needs to buy a license just to **open** your documentation, it is not really shared documentation.

### Two-layer strategy (practical, not ideological)

You can still use proprietary tools.
Just do not let them be the **only** place the knowledge lives.

- **Layer 1 - Source (what you edit):** native CAD, native schematics, native docs, and other tool-specific files
- **Layer 2 - Exports (what everyone can open):** open, durable formats stored beside the source

### Recommended formats by artifact type

| Artifact | Preferred open format(s) | Notes |
|---|---|---|
| Text docs / procedures | `.md`, `.txt` | readable anywhere, searchable, diffable |
| Tables / BOMs | `.csv` | opens in Excel, LibreOffice, Python, and many other tools |
| Config / parameters | `.json`, `.yaml`, `.toml` | parseable and human-readable |
| Diagrams | `.svg` | scalable, editable, web-native |
| Photos | `.jpg`, `.png` | universal viewing |
| Drawings | `.pdf` | good frozen deliverable |
| Presentations | **web pages (HTML/Markdown)** + `.odp` + PDF export | avoid proprietary slide lock-in |
| CAD exchange | `.step` / `.stp` (+ 2D PDF drawings) | durable interchange across CAD tools |
| CAD visualization / review | `.glb` (glTF) | lightweight viewing, Blender, web |

---

## Inventor + Vault collaboration: what to export

If your mechanical team uses **Inventor with Vault**, keep that as the internal source of truth for editing.
But publish a predictable export bundle so that everyone else can view and reuse the design.

### STEP vs GLB

**STEP (`.step/.stp`) - engineering truth**
- precise CAD geometry for measurement, manufacturing, and interchange
- best when downstream users need accurate solids or surfaces
- reality: you usually lose parametric history when moving between CAD systems

**GLB (`.glb`) - fast preview**
- mesh plus materials for quick viewing and review
- best when the goal is "see it and discuss it" or render it in Blender or on the web
- not a substitute for manufacturing-accurate geometry

**Recommendation:** export **both** when practical.

### A release package that works with Vault

For every released revision or milestone, publish an export bundle like:

```text
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

## Right-sized documentation

There are two easy failure modes.

### Too little
- nobody can reproduce or maintain it
- the critical decision or hidden setup detail lives only in someone's memory

### Too much, too early
- you over-specify before users have touched a prototype
- you spend effort documenting the wrong design

A better pattern for exploratory work is:
1. prototype early
2. document what you learned
3. add formality as uncertainty drops

A useful line for the talk is:

> Do not write the whole cookbook before tasting the dish.

---

## LLMs and documentation

LLMs reduce the cost of **packaging** information.
They do not replace **ground truth**.

LLMs are useful for:
- turning rough notes into cleaner READMEs
- generating checklists and troubleshooting guides
- summarizing long documents

LLMs cannot recover:
- photos you never took
- revision IDs you never wrote down
- wiring, settings, or calibration steps you never captured

A practical rule is:
- write for humans first
- make it machine-friendly by default with open text formats, clear headings, short sections, numbered procedures, and explicit expected results

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
- What "working" means:

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
- ...

9) Changelog (what changed, when, why)
- YYYY-MM-DD: <change> (reason)
```

### Photo checklist (minimum set)

- [ ] Full system on bench (include a ruler if helpful)
- [ ] Inside enclosure before closing it
- [ ] Connectors and cable routing closeups
- [ ] Labels / part numbers / key components
- [ ] One photo that shows the reference orientation for reassembly
