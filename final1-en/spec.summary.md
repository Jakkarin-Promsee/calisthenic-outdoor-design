# Verification Summary & Foundation
## Document 4/4 · Verification Summary (Draft 1)

| Item | Details |
|---|---|
| Document Status | Draft 1 — Preliminary verification for engineer's review |
| Last Updated | 17 June 2026 |
| Prepared By | Functional Design Researcher (not a licensed engineer) |
| Reference Standards | EN 16630:2015 · EN 1993 · Hilti HSA ETA-11/0374 (C20/25 uncracked) |
| Related Documents | [Master Index (TOC)](toc.md) · [Gallery 1/4](design/design.gallery.md) · [Design Specification 2/4](spec.full.md) · [Load Analysis 3/4](spec.requirement.md) · [Scope & Liability](policy.liability.md) · [Reference Research](research.md) |

> **Disclaimer** The verification results in this document are preliminary (first-order) calculations intended to confirm order-of-magnitude sizing and identify points for re-checking. **They are not a certified structural engineering calculation.** The preparer strongly recommends that a licensed civil/structural engineer review, compute, and certify the design before construction — in particular the 2.70 m monkey bar structure.

---

## 1. Summary of Verification Results

Under EN 16630:2015 design load (1,942 N per user station, including dynamics) and specified materials (wall 3.2 mm), **all members pass preliminary verification — none yield.**

| Member | Utilisation | Assessment |
|---|---|---|
| SHS 76 posts (pull-up, snake) | 0.42 | Pass (high margin) |
| Monkey tall post SHS 50×2.8 — with triangle brace | 0.35 | Pass (conditional on brace) |
| Monkey rung OD 34, 1.0 m span | 0.47 | Pass |
| Snake bar (composite section — Bar_Straight + Bar_Wave) | < 0.60 | Pass |
| Dip bar top beam / legs / nub | 0.18–0.59 | Pass |
| All anchor bolts (M12×120) | ≤ 7.6 / 12.3 kN | Pass (margin ~1.6–2×) |
| Pull-up Bar_High OD 34, 1.5 m span | 0.71 | **Watch** (moderate margin) |
| Snake side grip (250 mm cantilever) | 0.95 | **Watch** (near yield) |
| Weld quality at dynamic load points | Skill-dependent | **Watch** |

> Criteria: utilisation ≤ 0.6 = pass with good margin · 0.6–1.0 = watch (does not yield but margin is limited) · > 1.0 = fail

---

## 2. Calculation Detail

### 2.1 Assumptions

- Steel fy = 235 MPa · Allowable stress for dynamic loading ≈ 0.6 fy = 141 MPa
- Design load 1,942 N/station (EN 16630 Table 1, includes C_dyn = 2.0)
- Grip bars welded at both ends = fixed-end condition (mid-span moment ≈ PL/8)

### 2.2 Section Properties (calculated)

| Section | Section modulus Z (mm³) | Yield moment My (kN·m) | Allowable at 0.6 fy (kN·m) |
|---|---:|---:|---:|
| OD 34 × 3.2 | 2,183 | 0.51 | 0.31 |
| OD 42 × 3.2 | 3,519 | 0.83 | 0.50 |
| SHS 76 × 76 × 3.2 | 21,702 | 5.10 | 3.06 |
| SHS 50 × 50 × 2.8 | 7,879 | 1.85 | 1.11 |
| SHS 50 × 50 × 2.3 | 6,672 | 1.57 | 0.94 |

### 2.3 Bending Demand vs Capacity (at 1,942 N design load)

| Member | Design moment (kN·m) | Stress (MPa) | Utilisation | Result |
|---|---:|---:|---:|---|
| Pull-up Bar_High OD 34, 1.5 m span | 0.36 | 167 | 0.71 | **Watch** |
| Monkey rung OD 34, 1.0 m span | 0.24 | 111 | 0.47 | Pass |
| Snake side grip (250 mm cantilever) | 0.49 | 222 | 0.95 | **Watch** |
| Snake Bar_Straight OD 42 (single tube, L=2.0 m) | 0.49 | 138 | 0.59 | Pass |
| Dip top beam OD 42, 0.62 m span | 0.15 | 43 | 0.18 | Pass |
| Dip nub OD 42 (250 mm cantilever) | 0.49 | 138 | 0.59 | Pass |
| Pull-up / snake posts SHS 76 | 2.13 | 98 | 0.42 | Pass |
| Monkey tall post SHS 50×2.8 — **with brace** | 0.65 | 82 | 0.35 | Pass |
| Monkey tall post SHS 50×2.8 — **without brace** | 1.62 | 206 | 0.87 | **Watch** |

> **Grip bar capacity at maximum (fixed ends, 0.6 fy / yield):** OD 34, 1.0 m span = 2.46 / 4.10 kN · 1.5 m span = 1.64 / 2.74 kN · vs EN design load 1.94 kN → 1.0 m span passes with high margin; 1.5 m span has moderate margin

### 2.4 Deflection (Pull-up Bar_High OD 34, 1.5 m, at 1,942 N)

Fixed ends: ~4.6 mm (L/326) · Simply supported: ~18 mm (L/82) — within serviceable range when welded fixed at both ends

### 2.5 Anchor Bolt Tension from Overturning

| Post | Base moment (kN·m) | Tension/bolt (2 bolts on tension side) | M12×120 capacity | Result |
|---|---:|---:|---:|---|
| Pull-up SHS 76 (2.30 m) | 2.13 | 7.6 kN | 12.3 kN | Pass |
| Snake SHS 76 (2.10 m) | 1.94 | 6.9 kN | 12.3 kN | Pass |
| Monkey tall post (2.70 m) — using no-brace moment (conservative) | 1.62 | 5.8 kN | 12.3 kN | Pass |

> M12×120 with h_ef 65 mm in C20/25 concrete: recommended tension 12.3 kN/bolt (Hilti HSA, including factor 1.4) · steel capacity of bolt ~42 kN — concrete/embedment governs

---

## 3. Watch Points — Recommended Remedies

Listed in order of importance — remedies are suggestions for consideration (for grip bars: keep the OD for grip and increase the wall instead · for posts/welds/foundation: fully adjustable)

| # | Watch point | Status | Proposed remedies (A / B / C) |
|---|---|---|---|
| 1 | **Triangle brace Zone 4 (Monkey)** — conditional pass for tall post | Watch | A. Confirm weld continuity of Tri_Horiz + Rail_Z4 + rail · B. Never use or erect frame without brace in place · C. If brace removed in future, upgrade post to SHS 76 |
| 2 | **Pull-up Bar_High OD 34, 1.5 m span** — moderate margin (0.71) | Watch | A. Full-perimeter weld at both ends (mandatory) · B. Increase wall to 4.0–5.0 mm (keep OD 34) for more margin · C. Reduce span to 1.2 m · Note: assessed at 1 user — if 2 users simultaneously on high bar (EN n=2), util ≈ 1.0 |
| 3 | **Snake side grip + dip nub (cantilever members)** — weld bending moment | Watch | A. Full-perimeter weld at both attachment points · B. Reduce cantilever from 250 to 150 mm · C. Increase wall thickness specifically for cantilever members |
| 4 | **Lateral stability of dip frame** — 3 independent frames, 2 bolts/leg | Watch | A. Weld a crossbrace connecting all 3 frames · B. Increase to 3–4 bolts/leg · C. Extend base plate in x-axis |
| 5 | **Weld quality at dynamic load points** (bar-to-post, rung-to-rail) | Watch | A. Full-perimeter fillet weld ≥ 5 mm (not tack welds) · B. Gusset plate at critical points · C. Apply cold zinc galvanising spray to restore all coating damaged by heat |
| 6 | **Fall safety — rubber flooring** | Recommend check | Under Monkey (2.70 m) and Pull-up (2.30 m), 25 mm rubber is insufficient → increase to 40–50 mm (Monkey fall height 1.70 m typically requires ≥ 50 mm · verify Critical Fall Height of actual product with supplier) |
| 7 | **Corrosion protection** | Decision needed | Full hot-dip galvanising (weld first, then dip as complete piece) is far more durable · if using cold zinc spray at weld points, those joints will be the first rust sites in 3–5 years |
| 8 | **Protruding anchor bolt threads** | Recommend check | Cover with dome cap nut or trim excess threads and apply rust protection per EN 16630 §4.3.3 · Chamfer base plate corners to prevent trip/impact hazard |

---

## 4. Foundation, Base Plates, and Anchors

All posts and ground-bearing legs have a welded steel base plate at the bottom and are fixed with expansion anchor bolts into concrete · Top of hollow posts closed with welded cap to prevent water ingress · All posts cut length = design height + 25 mm (allowance for rubber thickness)

### 4.1 Specification per Anchor Point

| Group | Base plate (9 mm) | Anchors | Top cap (3 mm) |
|---|---|---|---|
| SHS 76 posts — pull-up (3) + snake (2), total 5 | 200 × 200 mm · 4 × Ø14 holes | 4 × M12×120 HDG | 80 × 80 mm |
| Monkey tall posts SHS 50 — y2/y3, total 4 | 200 × 200 mm · 4 × Ø14 holes | 4 × M12×120 HDG | 55 × 55 mm |
| Monkey short posts SHS 50 — 6 posts | 150 × 150 mm · 4 × Ø14 holes | 4 × M12×120 HDG | 55 × 55 mm |
| Dip frame legs — 3 frames × 2 legs = 6 | 120 × 120 mm · 2 × Ø14 holes | 2 × M12×120 HDG | — (bottom sealed by plate) |

- Edge distances: bolt centre to plate edge ≥ 25 mm · bolt-to-bolt ≥ 70 mm · bolt centre to concrete edge ≥ 100 mm · concrete slab thickness ≥ 140 mm (for M12 h_ef 65 mm)
- Anchor installation: drill hole perpendicular, blow/vacuum clean, insert anchor, torque with calibrated torque wrench to manufacturer specification (M12 ≈ 50 N·m)
- Post-to-base-plate weld: full-perimeter fillet, throat ≥ wall thickness of post (≥ 4–5 mm) · drill drain hole at bottom of post or weld closed top cap to prevent water ingress

### 4.2 Foundation BOM Summary

| Item | Quantity |
|---|---|
| Base plate 200×200×9 mm | 9 |
| Base plate 150×150×9 mm | 6 |
| Base plate 120×120×9 mm | 6 |
| **Total base plates** | **21 plates** |
| Top cap 80×80×3 mm | 5 |
| Top cap 55×55×3 mm | 10 |
| **Total top caps** | **15 plates** |
| Anchor M12×120 HDG (with nut + washer) | 72 bolts (order ~80 with 10% spare) |

> Total anchor points = 21 = pull-up 3 + snake 2 + monkey 10 + dip 6 · Total anchors 72 = (15 SHS posts × 4) + (6 dip legs × 2)
>
> Base plate allocation: 200×200 (9 plates) = pull-up 3 + snake 2 + monkey tall posts y2/y3 (4) — monkey tall posts use the larger plate size (same as SHS 76 posts) because overturning moment governs (consistent with research §5.2) · 150×150 (6 plates) = monkey short posts · 120×120 (6 plates) = dip legs · This allocation should be confirmed by the engineer.

---

## 5. Calculation Limitations

- Preliminary first-order calculations only; does not include: detailed fatigue life, lateral buckling of inclined rails, floor slope effects, wind loads
- Lateral forces from user swinging estimated at 0.5× vertical force — should be verified by engineer
- Anchor capacity cited from Hilti HSA-F (hot-dip galvanised) datasheet — if a different product is used, cross-check the ETA certificate and add additional safety factor for products without certification
- Concrete slab must be ≥ C20/25 and not cracked at installation points — verify on site
- **Conclusion: a licensed civil/structural engineer should review, verify the calculations, and sign off on the design before construction**
