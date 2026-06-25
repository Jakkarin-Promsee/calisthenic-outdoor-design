# Project Document Index — Outdoor Calisthenics Gym

## Master Index & Document Map (Draft 1)

| Item           | Details                                                           |
| -------------- | ----------------------------------------------------------------- |
| Document Status | Draft 1 — Navigation index for all project documents             |
| Last Updated   | 17 June 2026                                                      |
| Prepared By    | Functional Design Researcher (not a licensed engineer)            |
| Document Scope | Folder `final1-en/` — Official project document set              |
| How to Use     | Click any document title to open it · every document links back to this index |

> **Disclaimer** This document is a navigation index only and contains no technical content or binding obligations. Each document defines its own status, completeness, and liability scope. The entire set is a **draft**; the preparer strongly recommends that a licensed engineer review and certify the design before any construction.

---

## 1. Recommended Reading Order

> **Quick start:** Party B (Coordinator) begin at [tldr.b.md](tldr.b.md) (full project summary for handover) · Party C (Owner/Engineer) begin at [tldr.c.md](tldr.c.md) (quick 2–3-minute read)

1. Understand **roles and liability scope** — [Internal Agreement A/B](policy.liability.md) · [Handover Letter for Party C](policy.handoff.md)
2. **Review the visual overview before the detailed figures** — [Design Gallery (1/4)](design/design.gallery.md) · [Design PDF](design/design.pdf) — to grasp form, proportions, and overall layout
3. Study **specifications, dimensions, and materials** — [Design Specification (2/4)](spec.full.md)
4. Review **load analysis and verification results** — [Load & Requirement Analysis (3/4)](spec.requirement.md) → [Verification Summary & Foundation (4/4)](spec.summary.md)
5. Review **data sources and reference figures** — [Reference Research (main set)](research.md) · [Shop-welded Field-bolted Connection Research](research.connection-assembly.md)

---

## 2. Official Document Set — `final1-en/`

> Project source of truth · Formal English version · Updated 17 June 2026

| Document                                                                           | Status    | Summary                                                                                                                                                                 |
| ---------------------------------------------------------------------------------- | --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Design Gallery (1/4)](design/design.gallery.md)                                   | Draft 1   | 3D renders and equipment views — images are not to scale; all values governed by 2/4                                                                                     |
| [Design Specification (2/4)](spec.full.md)                                         | Draft 1   | Form, dimensions, heights, materials, and foundation system for all 5 pieces (PIECE 1–5) · **§7 (what-if): sub-assembly shop-weld + field-bolt system — plate/bolt/vent-hole sizes** |
| [Load & Requirement Analysis (3/4)](spec.requirement.md)                           | Draft 1   | How users load each piece, load paths, and member demand values (based on EN 16630) · **§7 (what-if): bolted-connection capacity check + semi-rigid joint effect**       |
| [Verification Summary & Foundation (4/4)](spec.summary.md)                         | Draft 1   | Utilisation results for all members · foundation/anchor system · remedial options A/B/C · BOM                                                                            |
| [Scope, Liability & Working Agreement (Internal A/B)](policy.liability.md)          | Finalised | Internal agreement between Researcher (A) ↔ Coordinator (B) · four-party roles · liability limitation · relevant Thai laws · effective upon signing                      |
| [Design Handover & Acknowledgement Letter](policy.handoff.md)                      | Finalised | Handover letter for Owner/Engineer (Party C) to sign, acknowledging the certifying role — separate from the internal agreement                                            |
| [Reference Research (main set)](research.md)                                       | Reference | Survey of 9 manufacturers · EN 16630 + Hilti HSA · base plate / anchor sizing · Thai market prices — source of all figures                                               |
| [Connection Research — Shop-welded Field-bolted](research.connection-assembly.md)  | Reference | End plate connection principles · plate/bolt sizing · HDG vent holes · torque · per-piece recommendations                                                                |

### 2.1 Working Tools — Not Official Specifications

> These are intentionally separate from the official documents above — for internal working use only. **Do not use for construction or cite as a specification.** The construction specification is always [spec.full.md](spec.full.md).

| Tool                                           | Status                              | Summary                                                                                                                                                                         |
| ---------------------------------------------- | ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Material Minimum Worksheet (spec.minimum.md)](spec.minimum.md) | Working tool · **not a spec** | Calculates the theoretical "material floor" (yield util = 1.0 + 0.6fy margin line) for every load point from spec.full + spec.requirement · Use to **eliminate undersized stock at the shop** (below the floor = cut immediately) · margin = 0; does not certify fitness for actual use · must be recalculated whenever actual materials change |

### 2.2 Handover Summaries (TL;DR)

> Handover overviews that supplement (not replace) the index and specification set. For actual figures and requirements, always refer to documents 2/4–4/4.

| Document                                  | For                      | Summary                                                                                        |
| ----------------------------------------- | ------------------------ | ---------------------------------------------------------------------------------------------- |
| [Handover Summary (internal A/B)](tldr.b.md) | Party B (Coordinator)  | Full project overview + decision rationale + document map + pending tasks — designed for handover |
| [Quick Summary for Owner/Engineer](tldr.c.md) | Party C (Owner/Engineer) | 2–3-minute read + engineering input requests + pointer to handover letter                    |

---

## Appendix — Folder Structure

```
final1-en/
├── toc.md                           ← this index
├── tldr.b.md                        ← handover summary (internal A/B)
├── tldr.c.md                        ← quick summary for Owner/Engineer (Party C)
├── spec.full.md                     ← design specification (2/4)
├── spec.requirement.md              ← load & requirement analysis (3/4)
├── spec.summary.md                  ← verification summary & foundation (4/4)
├── spec.minimum.md                  ← material minimum worksheet (not a spec)
├── policy.liability.md              ← scope & liability (internal A/B agreement)
├── policy.handoff.md                ← design handover letter (Party C signs)
├── research.md                      ← reference research (main set)
├── research.connection-assembly.md  ← connection research — shop-welded field-bolted
└── design/                          ← drawings and images
    ├── design.gallery.md            ← design gallery (1/4)
    ├── design.pdf
    └── images/
```
