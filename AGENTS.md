# AGENTS.md — Calisthenic Equipment Design

Tool-agnostic guide for **any** AI coding agent working in this repo (Cursor, Codex, Aider, Gemini CLI, Claude Code, …).
Claude Code users: this file + [CLAUDE.md](CLAUDE.md) (the latter adds the full Blender code-pattern library and harness notes).

---

## What this project is

A design + engineering-**research** package for a permanent **outdoor calisthenics gym** in a private back garden.

| | |
|---|---|
| **Users** | 1 adult + 1 child (~5 years) |
| **Site** | ~6 × 5 m plot (30 m²) · usable equipment area ~5 × 4 m |
| **Budget** | ~150,000 THB (current estimate ~89,000) |
| **Build** | 4 welded hot-dip-galvanised steel structures + EPDM rubber safety floor |
| **Modelling** | 3D models in Blender (via BlenderMCP) |
| **Standards** | EN 16630:2015 (outdoor fitness) · EN 1176 (playground safety) · Eurocode 3 |
| **Status** | **Release 1 complete (2026-06-26)** · public repo · docs are **draft, pending licensed-engineer review** |

---

## ⚠️ Read first — safety & scope (non-negotiable)

- This repo is **functional design + research, NOT certified engineering.** The author is **not a licensed engineer**. A licensed professional engineer (**Party C**) must independently review, calculate, certify, and physically inspect (structure, welds, foundations, anchors) **before any construction — and especially before a child uses the equipment.**
- All load numbers are **preliminary, first-order**. Never present anything here as a final structural calculation, as "safe", or as authorising construction.
- The **MIT + functional-design disclaimer** in [LICENSE](LICENSE) and the READMEs must stay intact — do not remove or soften the disclaimer.

### Document-writing rules (from [final1-th/ai/my-situation.md](final1-th/ai/my-situation.md) — read it before touching any policy / quotation / handoff doc)

- ⛔ **Never write the word "AI"** in any contract, quotation, or handover document.
- ✅ Use **"แนะนำ" (recommend)**, never **"ต้อง" (must)**, in handoff docs — so a clause can't "break" if the engineer doesn't actually inspect.
- Four roles: **ก/A** = researcher · **ข/B** = coordinator · **ค/C** = owner + licensed engineer + inspector (one person) · **ง/D** = external contractor.

---

## Source of truth

| Path | Role |
|---|---|
| **`final1-th/`** | ★ **Source of truth** — formal Thai deliverable. Start at [final1-th/toc.md](final1-th/toc.md). |
| `final1-en/` | Parallel **English** set (British spelling), mirror of `final1-th/`. **Edit both together to keep them in sync.** |
| `archive/` | Superseded drafts — **reference only, never build from these.** |

**Quick reads:** owner/engineer → `tldr.c.md` · coordinator → `tldr.b.md` · everyone → `toc.md`.

---

## Engineering basis — don't change without recomputing

- **Design load** = EN 16630:2015 Table 1 = **1,942 N per user station** (dynamic factor C_dyn = 2.0 already included). The old **5 kN figure is retired** — do not reintroduce it.
- **Walls** per the design draft (not a shop quote): grips OD 34 / OD 42; posts SHS 76×76 wall **3.2 mm**.
- **Rule for strengthening a bar: add wall thickness only — never increase OD** (OD is fixed by available pipe sizes: 1″ = 34 mm, 1¼″ = 42 mm).
- ⚠️ `archive/specs/*.explore.13062026.*` capture real-shop materials (thinner walls) but are **not yet recomputed** for load — **do not treat as final.**

---

## 3D models (Blender)

- **Current files: `models/final1-blender/`** — use the highest `_vN` of each piece. **Do not edit `models/archive/`** (old versions kept for comparison; don't rename or collapse them — the owner compares them).
- Models are built/edited via **BlenderMCP**. Even without a live Blender link you can run headless QA:
  `blender --background --factory-startup --python scripts/inspect_pieces.py`
- **Saving a piece:** `bpy.ops.wm.save_mainfile()` — **NOT** `save_as_mainfile` (renames the file) and **NOT** `bpy.data.libraries.write()` (creates a library-only file that opens empty).
- Each piece file must contain **exactly ONE correctly-named collection** (e.g. `MonkeyFlyingBar`). A duplicate `…​.001` collection makes the main scene link the empty one.
- **Full Blender code patterns** (SHS prism, named/round cylinders, Bézier 90° bends, zone reference, common mistakes): **[CLAUDE.md](CLAUDE.md).**

| Piece | Current file | Note |
|---|---|---|
| Pull-up bar | `pullup_bar_v2.blend` | adult bar z=2.20 m + child bar z=1.50 m · posts SHS 76 · bar OD 34 |
| Snake bar | `snake_bar_v5.blend` | straight OD 42 + 4-loop wave grip OD 34 + side U-grips |
| Dip bar | `dip_bar_v3.blend` | 3 × ⊓-frames · OD 42 · nub C-handle R=80 mm |
| Monkey + flying bar | `monkey_flying_bar_v4.blend` | 5 m, 5 zones, 35 rungs OD 34 · triangle brace at apex |
| Floor slab | `floor_v1.blend` | 6×5 m concrete |
| Main scene | `final_main_scene.blend` | all pieces linked + positioned |

---

## Repo map

```
final1-th/             source of truth (Thai, formal)      ← start at toc.md
final1-en/             English mirror (British spelling)
archive/               superseded drafts (reference only — never build from)
models/final1-blender/ current .blend pieces + main scene
models/archive/        old .blend versions (reference only)
renders/               stills + walkthrough animation (git-ignored)
scripts/               inspect_*.py (QA) · render_*.py · make_gif.py
assets/                HDRI environment lighting (git-ignored)
LICENSE                MIT + functional-design disclaimer
README.md / README-th.md   public overview (EN primary / TH)
CLAUDE.md              Claude Code working notes + Blender pattern library
AGENTS.md              this file
```

---

## Conventions

- **Tracked in git:** `.md` docs, design images/PDF under `final1-*/design/`, `.blend` files under `models/`. Renders, HDRI, and `.blend1` backups are git-ignored.
- **Editing deliverables:** change Thai (`final1-th/`) and English (`final1-en/`) **together** so the two stay in sync.
- **Commits:** short conventional prefixes (`docs:`, `feat:`, `refactor:`, `chore:`). Branch off `main` before committing if asked; **don't push unless asked.**
- **Versioned `.blend`:** highest `_vN` in `final1-blender/` is current — don't renumber or delete versions without asking.
