# Handover Summary — For Party B (Coordinator)

## TL;DR Handover Summary · From Party A (Researcher) → Party B

| Item | Details |
|---|---|
| What this document is | A "whole project at a glance" narrative — what Party A has produced, where the numbers come from, where each document is and how to read it, so Party B can pick up and coordinate immediately |
| How this differs from TOC | [toc.md](toc.md) is the formal index (what exists, where) · this document is the "background explanation" — why decisions were made, how calculations were done, and what to watch for |
| For whom | Internal use between Party A ↔ Party B only (not the document to give Party C — that is [tldr.c.md](tldr.c.md) + [policy.handoff.md](policy.handoff.md)) |
| Last Updated | 17 June 2026 |

---

## 1. How to Read Efficiently

If time is short, read only this section, §2 (Roles), and §5 (Watch Points) — that is enough to continue the work.

**Recommended order when time permits:**

1. This document in full (overview + background)
2. [policy.liability.md](policy.liability.md) — roles and liability (most important document about people)
3. [spec.full.md](spec.full.md) → [spec.requirement.md](spec.requirement.md) → [spec.summary.md](spec.summary.md) — design → load → verification
4. [research.md](research.md) + [research.connection-assembly.md](research.connection-assembly.md) — sources of all figures

---

## 2. What Is This Project

An outdoor calisthenics gym in the backyard of Party C (Phi Khao)

| Item | Value |
|---|---|
| Site area | ~6 × 5 m (30 m²) · Usable equipment area ~5 × 4 m |
| Users | 1 adult + 1 child ~5 years old |
| Budget | ~150,000 THB · Current estimate ~89,000 · Contingency ~61,000 |
| Conditions | Outdoor → hot-dip galvanised steel throughout |
| Equipment | 4 structural pieces + 1 impact-absorbing rubber floor system |

---

## 3. Four Parties — and Your Role (Party B)

> Full detail in [policy.liability.md](policy.liability.md) · Summary here for quick orientation

| Party | Who | Role |
|---|---|---|
| **A** | Researcher (person delivering this to you) | Research/standards ~90% · 3D models · draft requirements · rough budget estimate · **no authority to finalise specifications** |
| **B** | **Coordinator (you)** | Receive and coordinate · **select/propose functional design to Party C for approval** · not a contractor, not a certifying engineer |
| **C** | Phi Khao = property owner + PE-licensed engineer + site inspector (one person, three roles) | **Reviews, verifies, certifies, and approves the design** · decides to proceed · hires the contractor |
| **D** | External contractor | Party C hires to build per the approved design · no authority to change the design |

**What you (Party B) need to understand clearly:**

- All of Party A's work is **"preliminary draft inputs"** with no effect until you receive it, use it, adapt it, or pass it on
- Once you propose the design to Phi Khao, **the authority to decide and the responsibility to certify belong to Party C** (the PE-licensed engineer)
- Written role separation only protects you **when actual conduct matches what the document says** (see §4)

---

## 4. Working Rules for Handover (Read before every step)

These rules are what make this document set genuinely effective — failing any one of them immediately weakens the protection.

1. **Use "recommend/suggest", not "must"** in documents that go to Phi Khao or the contractor — if written as "a licensed engineer must inspect before construction" and Phi Khao does not actually inspect, the condition fails immediately. (The entire document set has been written with "recommend/suggest" throughout — maintain this tone.)
2. **Technical data attached = "compiled from public sources · as-is · no warranty"** for Phi Khao to verify independently — never say or write "I certify it is structurally sound."
3. **Do not state in any formal document or contract that the data/design was produced by automation tools** — Thai law on this area is not yet settled and interpretation is difficult. Always describe the source as "compiled from publicly available sources (as-is)."
4. **You must genuinely be the "coordinator"** — do not direct the welder, supervise the welding, or personally carry out installation as a contractor would. In practice, a court may find you to be the actual contractor regardless of what the document says.
5. **The construction contract with the contractor (Party D) must be in Party C's name**, not yours or Party A's.
6. **Have Phi Khao sign [policy.handoff.md](policy.handoff.md)** (the handover letter + acknowledgement of the certifying role) and retain the signed copy as evidence · the internal A↔B agreement ([policy.liability.md](policy.liability.md)) is signed between the two of you separately.

---

## 5. Design and Numbers (Full Narrative)

### 5.1 Five Equipment Pieces

| Piece | Summary | Main materials |
|---|---|---|
| **Pull-up Bar** | 3 posts (adult 2.30m + child 1.60m) · high bar z=2.20m, 1.5m long · child bar z=1.50m, 1.0m long | Posts SHS 76 · Bars OD 34 |
| **Snake Bar** | 2 posts 2.10m · structural straight bar (Bar_Straight OD 42) + wave grip bar (Bar_Wave OD 34, 4 loops, path 5.73m) + U-grip rails 4 pieces/side | Posts SHS 76 · OD 42 + OD 34 |
| **Dip Bar** | 3 × ⊓ frame, height 1.20m · grip channels 60cm (chest dip) + 50cm (tricep dip) · C-handle nub accessories × 3 | OD 42 |
| **Monkey + Flying Bar** | 5m long × 1m wide · 5 zones (entry 1.0m → incline up → flying incline 35° finishing at 2.70m) · 35 rungs + triangle brace at apex | Posts SHS 50 · Rungs OD 34 |
| **Rubber Floor** | EPDM 25mm (increase to 40–50mm under monkey/pull-up) · ~20 m² · defines floor datum z=0 | EPDM/SBR UV-resistant |

### 5.2 Why These Pipe Sizes

- **Grip bars OD 34mm (1″ BSP)** and **OD 42mm (1¼″ BSP)** — both within EN 16630's grip diameter range (16–45mm), consistent with international brands (grip bars 33–34mm, dip 38–43mm) · OD 42 is near the 45mm ceiling → **never increase OD further; if additional strength is needed, increase wall thickness instead**
- **Posts SHS 76 / SHS 50** — comparable to the home/rig segment (GetRXD, Rogue, TOLYMP) which uses 76mm or 80×60mm at ~3mm wall → aligned with the same tier. (Brand comparison detail in [research.md §3–4](research.md))

### 5.3 Calculation Basis

- Uses **EN 16630:2015 Table 1** as design load: **1,942 N per user station** (includes dynamic factor C_dyn = 2.0) · 2 users = 2,722 N
- **The old 5 kN baseline is no longer used** — 1,942 N is the correct standard value
- Utilisation criterion (stress/fy): **≤ 0.6 = pass (good margin)** · **0.6–1.0 = watch (does not yield but limited margin)** · **> 1.0 = fail**

### 5.4 Assessment Results — All Pass, With 6 Watch Points

Under EN 16630 load and specified materials (wall 3.2mm), **no member yields.** Points requiring particular attention (in order of importance):

| # | Watch point | Issue | Proposed remedy |
|---|---|---|---|
| 1 | **Triangle brace Zone 4 (monkey)** | Tall post 2.70m passes **because this brace exists** (without it: util 0.87) | Do not remove · never use/erect frame without brace · if removed, upgrade to SHS 76 |
| 2 | **Pull-up high bar OD 34, 1.5m span** | Util 0.71 (moderate margin) · **2 users simultaneously → util ≈ 1.0** | Full-perimeter weld at both ends · increase wall to 4–5mm · or reduce span to 1.2m · confirm 1-user-at-a-time use |
| 3 | **Snake side grip + dip nub (cantilever members)** | Bending moment at weld root · side grip util 0.95 (near yield) | Full-perimeter weld at both points/piece · reduce cantilever 250→150mm · or increase wall for cantilever members only |
| 4 | **Dip frame lateral stability** | 3 independent frames, 2 bolts/leg | Add cross-brace welding 3 frames together · or increase to 3–4 bolts/leg |
| 5 | **Weld quality + anti-corrosion coating** | Dynamic load points + heat damages galvanising | Full-perimeter fillet weld ≥ 5mm · repair all coating damaged by heat |
| 6 | **Fall-safety rubber floor** | Monkey falls 1.70m — exceeds 25mm rubber rating | Increase to ≥ 50mm under monkey/pull-up · verify Critical Fall Height with supplier |

> Main structure (SHS 76 posts, foundations, anchors) has high margin (util 0.2–0.5) — not critical points

### 5.5 Wall Thickness — Actual vs Minimum (Piece by Piece)

> **Read carefully (important):** "Minimum wall" column = wall thickness at which the material **just yields** under the design load = **zero margin remaining**. This is the "guaranteed failure below this line" threshold — used only to **screen out undersized shop stock** (if shop material is below this minimum → reject immediately). **This is NOT a recommendation to reduce the wall in practice.** The actual specification for construction uses **wall 3.2mm and SHS 50 at 2.3/2.8mm** per [spec.full.md](spec.full.md), which already includes safety margin. Any wall reduction requires Party C to recalculate and certify. Full derivation in [spec.minimum.md](spec.minimum.md).

| Member | Section · actual wall | Utilisation | Minimum wall (yield · zero margin) | How far can it be reduced / notes |
|---|---|---:|---|---|
| **Pull-up** posts ×3 | SHS 76×76 · **3.2mm** | 0.42 | **1.5mm** (keep SHS 76)¹ᵃ | Keep SHS 76: bending margin is large but **never reduce alone without checking lateral buckling**¹ |
| **Pull-up** Bar_High (1.5m span) | OD 34 · **3.2mm** | 0.71 | 2.3mm | Already thin — should **increase** to 4–5mm, not reduce |
| **Pull-up** Bar_Low (1.0m span) | OD 34 · **3.2mm** | ~0.47 | 1.5mm | Theoretically ~53% margin remaining |
| **Snake** posts ×2 | SHS 76×76 · **3.2mm** | 0.42 | **1.5mm** (keep SHS 76)¹ᵃ | Keep SHS 76: bending margin large, **never reduce without buckling check**¹ |
| **Snake** Bar_Straight (2.0m span) | OD 42 · **3.2mm** | 0.59 | 2.0mm | Theoretically ~41% margin remaining |
| **Snake** Bar_Wave (grip) | OD 34 · **3.2mm** | Low | ~1.5mm | Relies on Bar_Straight for structural load |
| **Snake** Side_Grip (250mm cantilever) | OD 34 · **3.2mm** | 0.95 | 3.0mm | **Almost no room to reduce** (near specification limit) |
| **Dip** top beam (0.62m span) | OD 42 · **3.2mm** | 0.18 | ~0.5mm² | **Never reduce below 1.5–2.0mm**² |
| **Dip** nub C-handle (250mm cantilever) | OD 42 · **3.2mm** | 0.59 | 2.0mm | Theoretically ~41% margin remaining |
| **Dip** vertical legs | OD 42 · **3.2mm** | Low | Governed by buckling³ | Maintain specification³ |
| **Monkey** rungs ×35 + Rail_Z0 (1.0m span) | OD 34 · **3.2mm** | 0.47 | 1.5mm | Theoretically ~53% margin remaining |
| **Monkey** short posts ×6 (1.0m tall) | SHS 50×50 · **2.3mm** | ~0.62⁴ | **1.5mm** (keep SHS 50)¹ᵇ | Minimum available in Thai market — passes bending; Party C should confirm⁴ |
| **Monkey** tall posts y2/y3 ×4 — **with brace** | SHS 50×50 · **2.8mm** | 0.35 | **1.5mm** (keep SHS 50)¹ᵇ⁵ | Conditional on brace⁵ — without brace, minimum wall jumps to 2.5mm immediately |
| **Monkey** tall posts y2/y3 — **without brace** | SHS 50×50 · **2.8mm** | 0.87 | **2.5mm** (keep SHS 50) | Very little margin · **brace must always be present**⁵ |

¹ SHS posts cannot be reduced on bending alone — bending at base is only one load mode; real posts carry axial compression + bending + lateral buckling + base moment simultaneously.
¹ᵃ SHS 76, keep OD: minimum wall for bending = 1.5mm (Z ≈ 10,887 mm³ > Z_min 9,064) — SHS 76 has very large bending reserve, but 2.2m tall posts face buckling risk; never reduce actual wall without Party C checking the buckling mode.
¹ᵇ SHS 50, keep OD: minimum wall for bending = 1.5mm (lowest practically available in Thai market) — use only as a screening threshold, not as a recommendation to reduce.
² Dip top beam needs almost no wall for bending, but minimum actual wall is governed by "outdoor corrosion + localised denting + welding" — never reduce below ~1.5–2.0mm.
³ Dip legs in axial compression governed by lateral buckling (not yielding) → maintain section per specification.
⁴ Short post utilisation calculated conservatively (lateral force 0.5P at post top) · in practice, monkey load descends vertically through rungs → rails share load → posts carry mostly axial → actual util is lower.
⁵ Triangle brace (Post_y3 + Tri_Horiz + Rail_Z4) changes everything: **with brace** → tall post minimum wall = 1.5mm · **without brace** → minimum jumps to 2.5mm. Do not remove the brace.

### 5.6 Foundations

- All posts and legs **cut +25mm longer** (allowance for rubber thickness) · weld base plate **9mm** + anchor **M12×120 HDG** + top cap 3mm
- Total: **21 base plates** (200×200 = 9 [pull-up 3 + snake 2 + monkey tall posts 4] · 150×150 = 6 [monkey short posts] · 120×120 = 6 [dip legs]) · **72 anchors** · 15 top caps
- M12 anchors, embedment h_ef 65mm, tension capacity 12.3 kN/bolt (Hilti HSA, C20/25) · requires concrete slab ≥ 140mm thick

### 5.7 Assembly Option (Important for Contractor Discussion)

Problem: welding on site burns off the galvanising and leads to rust; but welding the full frame before galvanising can make pieces too large for the bath.

**Solution (documented):** weld into small sub-assemblies in the shop → hot-dip galvanise each piece individually → **field-bolt together using end plates on site.**

- All plates **9mm** + bolts **M12/M10 Grade 8.8 HDG** · Assessment result: plates/bolts pass comfortably (util < 0.15)
- **One critical watch point:** the pull-up bar high joint is sensitive to "joint stiffness" — if bolts are loose enough to allow free rotation, the mid-span moment doubles (util 1.42 → fail). Bolts must be fully tightened, or the pull-up frame should be welded as a complete sub-assembly (no joint at the bar)
- **Vent holes in all closed hollow sections before galvanising — mandatory** — without them, sections explode in the galvanising bath (lethal hazard)
- Full detail in [research.connection-assembly.md](research.connection-assembly.md) and [spec.full.md §7](spec.full.md)

---

## 6. Where to Find Each Document

All files are in the `final1-en/` folder

| File | What it is | Open when |
|---|---|---|
| [toc.md](toc.md) | Formal index of all documents | Want the full map |
| [design/design.gallery.md](design/design.gallery.md) | **Design 1/4** — 3D renders showing form/layout of all pieces | Want to see the design before reading numbers |
| [spec.full.md](spec.full.md) | **Design 2/4** — form, dimensions, heights, materials PIECE 1–5 + §7 assembly option | Want to know what each piece looks like and its dimensions |
| [spec.requirement.md](spec.requirement.md) | **Design 3/4** — how each exercise loads the structure; load path; utilisation | Want to know why the design carries the load |
| [spec.summary.md](spec.summary.md) | **Design 4/4** — full assessment results + foundation + remedies A/B/C + purchase BOM | Want to see the summary + items to buy |
| [spec.minimum.md](spec.minimum.md) | **Material minimum worksheet — not a spec** · tells whether shop stock is "too small to reject immediately" | At the shop when selecting material (below minimum → reject) |
| [policy.liability.md](policy.liability.md) | Internal A↔B agreement · 4-party roles · liability limitation · Thai law references | Before starting any step + before signing |
| [policy.handoff.md](policy.handoff.md) | Handover letter for Phi Khao (Party C) to sign — acknowledging the certifying role | When handing over to Phi Khao |
| [research.md](research.md) | Source of all figures — EN 16630, Hilti, 9-brand comparison, base plates, Thai market prices | Want to know where a number comes from |
| [research.connection-assembly.md](research.connection-assembly.md) | Shop-weld + field-bolt system (end plates, vent holes, torque) | Before talking to the contractor about assembly method |
| [tldr.c.md](tldr.c.md) | Short summary for Phi Khao (Party C) — quick 2–3-minute read | When approaching Phi Khao |

> **Tip:** every file has a link back to [toc.md](toc.md) and cross-links to related documents — follow the links within documents.

---

## 7. Where Are the 3D Models

Located in `models/Final_v1_draft/` (built in Blender)

| File | Description |
|---|---|
| `pullup_bar_v2.blend` | Pull-up bar (current) |
| `snake_bar_v5.blend` | Snake bar (current) |
| `dip_bar_v3.blend` | Dip bar (current) |
| `monkey_flying_bar_v4.blend` | Monkey + flying bar (current) |
| `floor_v1.blend` | Floor slab |
| `final_main_scene.blend` | Combined scene (all pieces linked) — open this to see the whole gym |

> Highest `_vN` suffix = current version · older files are in the `models/` root — do not accidentally edit those

---

## 8. Current Status and Pending Tasks

**Completed:**

- Design documents (spec 2/4–4/4) — formal versions, cross-checked
- Policy documents (internal agreement + handover letter)
- Reference research (2 documents)
- 3D models (all pieces + main scene)
- Handover summaries (this document + tldr.c.md)

**Still pending / to continue:**

- **Quotation/pricing document for 4-party use** — not yet done (can base on `archive/specs/quotation.full.md`)
- Pricing files available: `quotation.predict-price.md` (our estimate) · `quotation.full.md` (contractor submission form) · `*.explore.13062026.md` files (delta from actual shop visit — **not yet recomputed for structural capacity, do not treat as final**)
- Joint decisions needed on 5–6 open points in [research.md §10](research.md) (rubber thickness under monkey zone, hot-dip HDG vs spray, anchor bolt thread covers, number of dip bolts, etc.)

---

## 9. Reality Check (Do Not Forget)

- Liability/waiver agreements can limit **civil liability between parties** to a degree, but **cannot exclude criminal liability or liability to outsiders (e.g., a child who is injured and their family suing)**
- Paper protection only works when **actual conduct matches the stated roles** (see §4)
- **What genuinely prevents harm is hands-on inspection** — before letting children use the equipment, someone should physically check **every weld and the tightness of all base plates and anchors**, regardless of whether the papers are signed

---

## 10. How to Approach Phi Khao (Party C)

- Phi Khao is a PE-licensed engineer with limited time → start with [tldr.c.md](tldr.c.md) (short, quick read), then go into detail in person later
- Frame of conversation: we are **proposing** a functional design + research data · Phi Khao is the **reviewer/certifier/decision-maker** as the owner's engineer
- Have Phi Khao sign [policy.handoff.md](policy.handoff.md) and record the PE licence number
- Draw Phi Khao's attention above all to the 6 watch points in §5.4 — especially the monkey triangle brace, the pull-up high bar, and fall safety of the rubber floor
