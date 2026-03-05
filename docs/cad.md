---
layout: default
title: CAD exports: STEP vs GLB
permalink: /cad/
---

[Home]({{ '/' | relative_url }}) · [Why]({{ '/why/' | relative_url }}) · [MVD checklist]({{ '/mvd/' | relative_url }}) · [Open formats]({{ '/open-formats/' | relative_url }}) · [CAD files]({{ '/cad/' | relative_url }}) · [LLMs]({{ '/llms/' | relative_url }}) · [Templates]({{ '/templates/' | relative_url }}) · [Balance]({{ '/balance/' | relative_url }})

---

# CAD exports for open collaboration (Inventor/Vault → everyone)

If your native CAD lives in **Inventor + Vault**, that can still coexist with open collaboration.

The trick is to treat **open exports** as part of the deliverable, alongside the native source.

## STEP vs GLB at a glance

| Format | What it is | Best for | Not great for |
|---|---|---|---|
| **STEP (.step/.stp)** | CAD interchange format (precise B‑rep solids/surfaces + assembly structure, depending on export options) | engineering exchange, manufacturing handoff, long-term archival, importing into open CAD (e.g., FreeCAD) | preserving Inventor features/constraints; lightweight visualization |
| **GLB (.glb)** | Binary glTF (mesh + materials for real-time rendering) | fast viewing, web previews, AR/VR, Blender rendering | manufacturing accuracy, parametric edits, CAD constraints |

**Recommendation:** export **both** whenever practical:
- STEP = **engineering truth**
- GLB = **communication + review**

## A “release package” policy that works with Vault

Keep native Inventor + Vault as the internal source of truth.  
But for every *released revision* (or milestone), publish an **export bundle**:

```
/exports/<project>/<rev_or_date>/
  model.step          # assembly (and/or parts)
  model.glb           # same assembly for viewing
  drawings.pdf        # 2D drawings as PDF
  bom.csv             # BOM/table
  README.md           # what changed + how to use
  preview.png         # optional quick screenshot/render
```

In the README, include:
- units
- coordinate system / datums
- how to verify fit (test points)
- Vault item/revision IDs (so people can trace back)

## Notes for Inventor users

- Pick one STEP protocol (AP214 or AP242) and keep it consistent across exports.
- Export assemblies *and* critical single parts if downstream users need them separately.
- If you care about colors, make sure your chosen STEP options preserve them.

## When GLB is the right choice

GLB shines when you want:
- a browser-based viewer,
- quick design reviews,
- easy Blender import for renderings,
- or lightweight “what does it look like?” sharing.

You can keep GLB files small by exporting **simplified** geometry (no tiny fillets, suppressed fasteners, etc.) if the goal is review rather than manufacturing.

---

➡️ Back to: [Open file formats]({{ '/open-formats/' | relative_url }})
