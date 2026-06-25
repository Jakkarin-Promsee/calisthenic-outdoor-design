# Load & Requirement Analysis — Outdoor Calisthenics Gym
## Document 3/4 · Load Analysis (Draft 1)

| Item | Details |
|---|---|
| Document Status | Draft 1 — Preliminary assessment for engineer's review |
| Last Updated | 17 June 2026 |
| Prepared By | Functional Design Researcher (not a licensed engineer) |
| Reference Standards | EN 16630:2015 (design loads) · EN 1993 (structural steel/welds) · Hilti HSA ETA-11/0374 (anchor bolts) |
| Related Documents | [Master Index (TOC)](toc.md) · [Gallery 1/4](design/design.gallery.md) · [Design Specification 2/4](spec.full.md) · [Verification Summary 4/4](spec.summary.md) · [Scope & Liability](policy.liability.md) · [Reference Research](research.md) |

> **Disclaimer** — This document identifies how users load each piece of equipment, how forces flow through each member, and provides a **preliminary** assessment of whether members carry the load — for the engineer to review and verify. **It is not a certified structural calculation.** All results and material capacity figures are in document 4/4.

---

## 1. Design Load Basis (EN 16630:2015 Table 1)

EN 16630 specifies design forces for permanent outdoor fitness equipment with the dynamic factor (C_dyn) already included.

| Number of simultaneous users (n) | Total mass G_n (kg) | C_dyn | Total vertical design force F_tot,v (N) |
|:---:|:---:|:---:|:---:|
| 1 | 99 | 2.00 | **1,942** |
| 2 | 185 | 1.50 | **2,722** |

- **Primary design load = 1,942 N per user station** (includes dynamics from swinging/impact per the standard)
- Members shared by 2 simultaneous users (adult + child) use 2,722 N
- Lateral force (from body swing) estimated at approximately 0.5 × vertical force

### Material Assumptions
- Steel fy = 235 MPa (standard galvanised hollow section, conservative) · Allowable stress for dynamic loading ≈ 0.6 fy ≈ 141 MPa
- Grip tubes and rungs welded at both ends = "fixed-end" condition (mid-span moment ≈ PL/8)
- Utilisation criterion (stress / fy): **≤ 0.6 = pass (good margin)** · **0.6–1.0 = watch (does not yield but limited margin)** · **> 1.0 = fail**

---

## 2. PIECE 1 — Pull-up Bar

### 2.1 Structure

| Sub-item | Member | Section | Size |
|---|---|---|---|
| Posts | Post_Left / Right | SHS 76×76×3.2 | Height 2.30m · 1.0m apart |
| Post | Post_Child | SHS 76×76×3.2 | Height 1.60m |
| Bar | Bar_PullUp_High | OD 34×3.2 | Length 1.50m · z = 2.20m |
| Bar | Bar_PullUp_Low | OD 34×3.2 | Length 1.00m · z = 1.50m |

### 2.2 Exercises → Forces → Load Path

Primary path: hands → bar (mid-span) → bar-to-post welds (2 ends) → posts → base plates → anchor bolts → concrete

| Exercise | Nature | Primary direction | Member(s) governing |
|---|---|---|---|
| Dead hang | Static | Down (−Z) | Bar bending at mid-span · posts in compression |
| Pull-up | Semi-dynamic | Down | Bar · welds |
| Kipping pull-up | Dynamic + swing | Down + lateral (±Y) | Bar + base moment at post → anchor bolts |
| Muscle-up | Highest dynamic | Down + forward thrust | Bar at peak bending · welds |
| Body swing | Dynamic lateral | Lateral (±Y) | Base moment at post → alternating anchor bolt tension |
| Child on low bar | Light | Down | Bar_Low → Post_Child, Post_Left |

### 2.3 Demand and Preliminary Assessment

| Point | Design moment / force | Utilisation | Assessment |
|---|---|---|---|
| Bar_High mid-span, 1.5m span | M ≈ 0.36 kN·m (fixed ends) | 0.71 | **Watch** — passes, moderate margin |
| Post base | M ≈ 2.1 kN·m | 0.42 | Pass |
| Bar-to-post weld | Shear ≈ 1.0 kN/end + moment | Skill-dependent | Watch — full-perimeter weld required |
| Anchor bolts (tension) | ≈ 7.6 kN/bolt (2 bolts on tension side) | < capacity 12.3 kN | Pass |

> **User count assumption:** Bar_High assessment above is for 1 user (1,942 N) · If designed for 2 simultaneous adults, or adult + child, on the high bar (EN 16630 n = 2 = 2,722 N), mid-span moment increases to approximately 0.51 kN·m → utilisation ≈ 1.0 (no margin remaining). Confirm that the high bar is intended for single-user use, or, if 2-user loading is required, increase the tube wall / reduce the span.

> **PIECE 1 summary:** All pass · Watch points: Bar_High OD 34, 1.5m span (moderate margin) and bar-to-post weld quality.

---

## 3. PIECE 2 — Snake Bar

### 3.1 Structure

| Sub-item | Member | Section | Size |
|---|---|---|---|
| Posts | Post_Snake_L / R | SHS 76×76×3.2 | Height 2.10m |
| Structural bar | Bar_Straight | OD 42×3.2 | Length 2.00m · z = 1.962m |
| Grip bar | Bar_Wave | OD 34×3.2 | Path 5.73m · z = 2.00m |
| Side grips | Side_Grip_L / R | OD 34×3.2 | 250mm cantilever · 4 pieces/side |

### 3.2 Exercises → Forces → Load Path

- Wave bar path: hands → Bar_Wave → (welded continuously to Bar_Straight) → structural bar → posts → foundation
- Side grip path: hands → Side_Grip (cantilever) → 2 weld points on post face → post → foundation

| Exercise | Nature | Primary direction | Member(s) governing |
|---|---|---|---|
| Hang on wave bar | Static–semi-dynamic | Down | Bar_Wave → Bar_Straight → posts |
| Wave bar traverse | Dynamic | Down + lateral | Bar_Straight at peak bending when user at mid-span |
| Side grip hang/pull | Dynamic | Down at cantilever tip | Bending moment at weld root + tube wall at grip |
| Child side rail climb | Light–moderate | Down + out (−Y) | Side grip → post |

### 3.3 Demand and Preliminary Assessment

| Point | Design moment / force | Utilisation | Assessment |
|---|---|---|---|
| Bar_Straight + Wave (composite), mid-span 2.0m | M ≈ 0.49 kN·m | < 0.6 | Pass (composite section much stronger than single tube) |
| Side grip (250mm cantilever) | M ≈ 0.49 kN·m at weld root | 0.95 | **Watch** — near yield |
| Side grip welds (2 points/piece) | ≈ 2 kN/point | Skill-dependent | Watch — full-perimeter weld required |
| Posts + anchor bolts | M_base ≈ 1.94 kN·m → 6.9 kN/bolt | Pass | Pass |

> **PIECE 2 summary:** Passes · Watch point: side grip (250mm cantilever) — bending moment at weld root and tube wall. Recommend reducing cantilever or increasing wall thickness for side grip members only.

---

## 4. PIECE 3 — Dip Bar

### 4.1 Structure

| Sub-item | Member | Section | Size |
|---|---|---|---|
| ⊓ frames | DipBar_01–03 | OD 42×3.2 | Height 1.20m · legs at y = 0 and 0.75m |
| C-handle nub | Nub_01–03 | OD 42×3.2 | 250mm cantilever · 200mm tall |

### 4.2 Exercises → Forces → Load Path

Primary path: hands → top beam of frame → 2 legs (compression) → base plates → anchor bolts · Note: unlike pull-up, this is a **downward push** force, not a pull.

| Exercise | Nature | Primary direction | Member(s) governing |
|---|---|---|---|
| Dip (push up and down) | Semi-dynamic | Down (push) | Top beam → legs (compression) → base |
| L-sit (hold, legs horizontal) | Static | Down + small moment | Top beam · front leg carries more |
| Asymmetric push | Semi-dynamic | Down + lateral tilt (±X) | Overturning moment → base |
| Nub grip | Semi-dynamic | Down at cantilever tip | Bending moment at nub weld |

### 4.3 Demand and Preliminary Assessment

| Point | Design moment / force | Utilisation | Assessment |
|---|---|---|---|
| Top beam (short span 0.62m) | M ≈ 0.15 kN·m | 0.18 | Pass |
| Vertical legs (axial compression, 1.2m span) | ≈ 2 kN | Very low | Pass |
| Nub C-handle (250mm cantilever) | M ≈ 0.49 kN·m | 0.59 | Pass |
| Lateral stability / anchor bolts at base | Overturning moment about X-axis | — | **Watch** — see §4.4 |

### 4.4 Lateral Stability

The 3 ⊓ frames are structurally independent with no cross-bracing. Anchor bolts are 2 per leg, arranged in the y-direction → lateral (x-axis) overturning resistance is limited. Although lateral forces from dipping are small, the system relies entirely on anchor bolts for lateral stability. Recommend welding short horizontal cross-braces between the 3 frames at a consistent height, so the 3-frame group acts as one unit.

> **PIECE 3 summary:** Passes in primary direction (compression) with high margin · Watch point: lateral stability of independent frames.

---

## 5. PIECE 4 — Monkey + Flying Bar

### 5.1 Structure

| Sub-item | Member | Section | Size |
|---|---|---|---|
| Short posts (Zone 0–2) | Post y=−1, 0, 1 | SHS 50×50×2.3 | Height 1.00m |
| Tall post (Zone 3) | Post_y2 | SHS 50×50×2.8 | Height 2.00m |
| Tall post (Zone 4 apex) | Post_y3 | SHS 50×50×2.8 | Height 2.70m |
| Rungs + entry rails | 35 rungs + Rail_Z0 ×3 | OD 34×3.2 | Length 1.00m |
| Structural rails (Zone 1–2) | Rail_Z1, Rail_Z2, Tri_Horiz | SHS 50×50×2.3 | — |
| Structural rails (Zone 3–4) | Rail_Z3, Rail_Z4 | SHS 50×50×2.8 | — |

### 5.2 Exercises → Forces → Load Path

- Primary path: hands → rung (1.0m span) → side rails (Rail) → posts → foundation
- Swinging: lateral moment → tall post (particularly Post_y3 at 2.70m) → foundation → alternating anchor bolt tension

| Exercise | Nature | Primary direction | Member(s) governing |
|---|---|---|---|
| Bar-to-bar brachiation | Dynamic (impact each rung) | Down + lateral | Rung bending → rail → post |
| Flying bar (Zone 4, 35° incline) | High dynamic | Down + high lateral | Post_y3 — highest base overturning moment |
| Hang / swing on single rung | Dynamic | Down + lateral | Rung + rail + post |
| Ladder climb / child play (low rungs) | Light | Down | Rungs/ladder → short posts |

### 5.3 Demand and Preliminary Assessment

| Point | Design moment / force | Utilisation | Assessment |
|---|---|---|---|
| Rungs OD 34, 1.00m span (fixed ends) | M ≈ 0.24 kN·m | 0.47 | Pass |
| Tall post Post_y3 — **with triangle brace** | M ≈ 0.65 kN·m | 0.35 | Pass (conditional on brace) |
| Tall post Post_y3 — **without brace** | M ≈ 1.6 kN·m | 0.87 | **Watch** → **triangle brace is essential** |
| Anchor bolts — tall post (tension) | ≈ 5.8 kN/bolt | < 12.3 kN | Pass |
| Rung-to-rail welds (many points) | ≈ 1 kN/end + dynamic | Skill-dependent | Watch — fatigue + full-perimeter weld required |

> **PIECE 4 summary:** Passes — **with the critical condition that the triangle brace (Post_y3 + Tri_Horiz + Rail_Z4) is complete and fully welded.** Never use the frame without the brace. Also note fall safety from 2.70m apex (see document 4/4).

---

## 6. Preliminary Assessment Summary (For Engineer's Review)

Under EN 16630 load and specified materials (wall 3.2mm), **all members pass the preliminary assessment** — no member yields. Points requiring particular attention and verification (in priority order):

1. **Triangle brace Zone 4 of Monkey** — the condition that makes the tall post pass; confirm weld continuity and rail connections
2. **Pull-up high bar OD 34, 1.5m span** — moderate margin (utilisation 0.71); recommend fixed-end weld and consider increasing wall for more margin
3. **Snake side grips and dip nub (cantilever members)** — bending moment at weld root; weld full-perimeter
4. **Dip frame lateral stability** — consider cross-bracing between the 3 frames
5. **Weld quality at all dynamic load points** and restoration of galvanising coating damaged by heat
6. **Fall safety (rubber floor)** under Monkey and Pull-up

> Primary structural members (SHS 76 posts, foundations, base plates, anchor bolts) have high margin (utilisation 0.2–0.5) — not critical points · Detailed member capacity and foundation details are in document 4/4.

---

## 7. What-if: Bolted Connection Analysis (Sub-assembly Shop-weld + Field-bolt Option)

> **Status of this section:** This is a verification of the *supplementary option* described in [document 2/4 §7](spec.full.md). It does not replace or alter the results of §1–6 above. It adds a "bolted field-joint layer" in place of site welding, then verifies whether 9mm plates and Grade 8.8 bolts are adequate and what effect this has on the structural members.

### 7.1 Additional Assumptions

- Design load unchanged (EN 16630): 1,942 N/station · lateral force ≈ 0.5 × vertical
- Plates: steel fy = 235 MPa · **9mm thick (practically available)**
- Bolts: Grade 8.8 (fub = 800 MPa) · safety factor γM2 = 1.25
- Structural bar joints assumed "fixed-end" (end moment = PL/8) — check whether the joint can develop this moment and what happens if it cannot (see §7.4)

### 7.2 Connection Component Capacities (Reference)

**Grade 8.8 bolt per bolt (Fv = shear, Ft = tension)**

| Size | As (mm²) | Fv,Rd | Ft,Rd |
|---|---:|---:|---:|
| M10 | 58.0 | 22.3 kN | 33.4 kN |
| M12 | 84.3 | 32.4 kN | 48.6 kN |

**9mm plate capacity — T-stub model (EN 1993-1-8)** — example at Pull-up connection (M12):
- Plastic moment of plate strip: M_pl = l_eff × t² × fy / 4 = 60 × 9² × 235 / 4 ≈ 285,500 N·mm (l_eff ≈ 60mm)
- Mode 1 row capacity: F_Rd = 4 × M_pl / m = 4 × 285,500 / 13 ≈ **87.8 kN/row** (m = bolt-to-tube-wall distance ≈ 13mm)
- Since bolts are close to the tube, plate capacity is **very high** — the 9mm plate is not the governing limit at any connection

### 7.3 Per-Connection Assessment (Demand → Utilisation)

Bolt tension per bolt = (end moment ÷ lever arm between bolt rows) ÷ 2 bolts/row

| Connection | V/end | M/end (PL/8) | Lever arm | Tension/bolt | Bolt util (tension) | Plate util (T-stub) | Result |
|---|---|---|---|---|---|---|---|
| Pull-up Bar_High (L=1.5m, 4×M12) | 0.97 kN | 0.364 kN·m | 60mm | 3.03 kN | 0.06 | 0.07 | Pass |
| Pull-up Bar_Low (L=1.0m, 4×M12) | 0.97 kN | 0.243 kN·m | 60mm | 2.03 kN | 0.04 | 0.05 | Pass |
| Snake composite (L=2.0m, 4×M12) | 0.97 kN | 0.486 kN·m | 70mm | 3.47 kN | 0.07 | 0.07 | Pass |
| Snake Side_Grip (cantilever, 2×M10/point) | 0.97 kN | cantilever → tension 1.94 kN/point | — | 0.97 kN | 0.03 | < 0.05 | Pass |
| Monkey rail section (L=1.0m, 4×M10) | 0.97 kN | 0.243 kN·m | 60mm | 2.03 kN | 0.06 | 0.04 | Pass |

- Shear per bolt = V ÷ 4 ≈ 0.24 kN (vs Fv,Rd 22–32 kN → util < 0.02) · combined tension+shear interaction < 0.1 at all connections
- Allowing prying force to double bolt tension: 3–7 kN still well below capacity 33–49 kN → no impact
- **Connection strength summary: 9mm plate + Grade 8.8 bolts pass at all connections, utilisation < 0.15** (connections are driven by geometric/wrench-clearance constraints, not strength)

### 7.4 Member-Level Effect — Semi-rigid Joint Stiffness

This is the most important finding in this section — not plate/bolt strength (which passes with high margin) but **rotational stiffness of the joint**, which affects the moment in the bar itself:

- Welded joint = fixed (rigid) → bar carries mid-span moment of PL/8
- Bolted joint = semi-rigid → if it rotates enough to approach "free rotation" (pinned), mid-span moment becomes **PL/4 (doubles)**

**Critical case — Pull-up Bar_High** (from §2.3: fixed-end utilisation = 0.71)

| Joint assumption | Mid-span moment | Bar utilisation | Result |
|---|---|---|---|
| Fixed (welded / properly tightened) | PL/8 = 0.364 kN·m | 0.71 | Pass (moderate margin) |
| Pinned (loose bolts / thin/soft plate) | PL/4 = 0.728 kN·m | **1.42** | **Fail** |

→ **Bar_High is the member most sensitive to joint stiffness** because its utilisation is already elevated (0.71)

**Why the bolted option is still considered viable:** the 9mm plate has only ~7% utilisation → the connection has ample capacity to develop the fixed-end moment (behaviour approaching rigid) provided the full 9mm plate is welded continuously around the tube perimeter and bolts are tightened to specification.

**Recommendations (in order):**
1. **Tighten bolts to full specification (snug-tight minimum) + use full 9mm plate** so the joint behaves close to rigid
2. **Have the engineer confirm the semi-rigid moment distribution** for Bar_High specifically (may wish to increase tube wall for more margin)
3. **Alternative to avoid this issue altogether:** weld the "complete Pull-up frame" (posts + bar) as a single sub-assembly (~2.5m wide × 2.3m tall — still fits in a 3–4m galvanising bath) so **no bolted joint exists at the bar ends** → preserves fully rigid joint behaviour without reliance on bolt tightness

> Snake composite and Monkey rail sections have more reserve (original util < 0.6) → semi-rigid case does not reach the critical threshold for those members, but tightening all bolts to spec is still recommended throughout.

### 7.5 What-if Summary (For Engineer's Review)

The shop-weld sub-assembly + field-bolt system using 9mm plates **passes preliminary assessment for connection strength at all joints** (plate and bolt utilisation < 0.15). Points requiring particular attention:

1. **Rotational stiffness of Pull-up Bar_High joint (semi-rigid)** — the determining condition for whether the bar passes or fails (§7.4). Bolts must be genuinely tightened, or use the complete-frame welding alternative.
2. **Wrench clearance around small-diameter tubes (OD 34/42)** — verify that bolt head / torque wrench has adequate space. Plate may need slight enlargement.
3. **Vent holes before galvanising** — safety during galvanising (not a strength issue, but mandatory — see document 2/4 §7.5)
4. **Thin SHS 50 wall at monkey face plate weld points** — check punching/local bending of 2.3–2.8mm wall at the plate attachment weld
5. **End plate weld quality (in shop, before galvanising)** — full-perimeter fillet weld throughout

> All figures are preliminary assessments. **The preparer strongly recommends that a licensed engineer review and certify** — particularly the detailed T-stub calculation, semi-rigid moment redistribution for Bar_High, and local bearing on SHS walls. Sources and formulae are in [Connection Research — Shop-welded Field-bolted](research.connection-assembly.md).
