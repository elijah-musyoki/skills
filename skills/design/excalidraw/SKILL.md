---
name: excalidraw
description: "Create hand-drawn diagrams using excalidraw-cli (JSON-to-.excalidraw, export URLs, checkpoints). Use when asked to draw architecture flows, decision charts, or visual notes."
license: MIT
compatibility:
  - opencode >=1.0.0
---

# Excalidraw CLI Skill

Create `.excalidraw` files from JSON. Default roughness=2, rounded corners, handwritten font.

## Quick start
```bash
excalidraw create --json '[...]' -o out.excalidraw
excalidraw export out.excalidraw
```

## Key patterns
- Dark mode: `darkbg` rectangle first.
- Arrow bindings: `startBinding` / `endBinding` with `fixedPoint`.
- Label shorthand on shapes/arrows.

## References
- `references/defaults.md` — color palette, sizing, font rules
- `references/patterns.md` — shapes, arrows, camera
- `references/examples.md` — happy-path, architecture, decision flow
