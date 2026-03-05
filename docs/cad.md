---
title: "CAD exports (STEP vs GLB)"
permalink: /cad/
---

# CAD exports for open collaboration

If your native CAD lives in **Inventor + Vault**, you can still collaborate with people who don’t have a license:

## STEP — engineering truth
- Precise geometry for measurement, manufacture, interchange
- Best for: sharing with other CAD/analysis tools (including open-source)

## GLB — fast preview
- Mesh + materials for viewing, web, Blender
- Best for: design reviews, rendering, “what does it look like?”

**Recommendation:** export both when practical.

## Minimal “export bundle” (per revision)

- `model.step` (assembly)
- `drawings.pdf`
- `bom.csv`
- `README.md` (what changed + how to verify)
- optional: `model.glb` + `preview.png`

Full details and a suggested folder structure are in the repository README.