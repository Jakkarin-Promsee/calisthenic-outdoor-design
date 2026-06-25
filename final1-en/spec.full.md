# Design Specification — Outdoor Calisthenics Gym
## Document 2/4 · Design Specification (Draft 1)

| Item | Details |
|---|---|
| Document Status | Draft 1 — For engineer's review |
| Last Updated | 17 June 2026 |
| Prepared By | Functional Design Researcher (not a licensed engineer) |
| Reference Standards | EN 16630:2015 · EN 1176 · EN 1993 (structural steel) · Hilti HSA ETA-11/0374 |
| Related Documents | [Master Index (TOC)](toc.md) · [Gallery 1/4](design/design.gallery.md) · [Load Analysis 3/4](spec.requirement.md) · [Verification Summary 4/4](spec.summary.md) · [Scope & Liability](policy.liability.md) · [Reference Research](research.md) |

> **Disclaimer and scope** — This document is a functional design and preliminary assessment compiled from publicly available standards and manufacturer data by a person who is not a licensed engineer. **It is therefore not a certified engineering drawing.** The preparer strongly recommends that this be reviewed and certified by a licensed engineer (designer, site supervisor, design approver, and safety inspector) before construction.
>
> **Role division** — The preparer defines: form, dimensions, heights, and functional requirements. A licensed engineer/contractor defines: structural capacity calculations, steel grade selection, welding, and foundations — and bears the legal responsibility.

---

## 1. Project Scope and Conditions

- Total area approximately 6 × 5 m (30 m²) · Equipment-use area approximately 5 × 4 m
- Users: 1 adult + 1 child approximately 5 years old
- Outdoor installation — hot-dip galvanised steel throughout
- 4 structural equipment pieces + 1 impact-absorbing floor system

### Coordinate System
- X-axis = width (left −, right +) · Y-axis = depth (front/rear of frame) · Z-axis = height from standing level
- Z = 0 = top surface of rubber flooring (actual standing level) · all heights measured above rubber floor
- All posts and ground-bearing legs cut +25 mm longer than nominal height (the excess sits below the rubber; base plates rest on the concrete surface)

### Material Summary (whole project — hot-dip galvanised steel)

| Group | Section | Used For |
|---|---|---|
| Primary structural posts | SHS 76 × 76 mm, wall 3.2 mm | Pull-up, snake posts |
| Secondary structural posts | SHS 50 × 50 mm, wall 2.3 mm (short) / 2.8 mm (tall) | Monkey bar posts |
| Grip bars / rungs | Round tube OD 34 mm, wall 3.2 mm | Grip bars, rungs, entry rails, wave bar, side grips |
| Structural/grip tubes (large) | Round tube OD 42 mm, wall 3.2 mm | Dip bar, snake Bar_Straight |

> Note on grip tube sizes: OD 34 mm and OD 42 mm fall within EN 16630's grip diameter range (16–45 mm) · OD 42 is close to the 45 mm upper limit — do not increase OD further

---

## 2. PIECE 1 — Pull-up Bar

3-post frame + 2 bars · Adult bar at z = 2.20 m · Child bar at z = 1.50 m

### Components
| Member | Section | Size | Position |
|---|---|---|---|
| Post_Child | SHS 76×76×3.2 | Height 1.60 m | x = −1.75 m |
| Post_Left | SHS 76×76×3.2 | Height 2.30 m | x = −0.75 m (shared between both bars) |
| Post_Right | SHS 76×76×3.2 | Height 2.30 m | x = +0.75 m |
| Bar_PullUp_High | OD 34×3.2 | Length 1.50 m | z = 2.20 m (Left–Right span) |
| Bar_PullUp_Low | OD 34×3.2 | Length 1.00 m | z = 1.50 m (Child–Left span) |

- 3 posts in line along x-axis, 1.00 m centre-to-centre · bars welded to post face, 0.10 m below post top
- Footprint: 2.50 m wide × ~0.10 m deep

---

## 3. PIECE 2 — Snake Bar

2 posts + structural straight bar + wave grip bar + side U-grips on both sides

### Components
| Member | Section | Size | Position |
|---|---|---|---|
| Post_Snake_L / R | SHS 76×76×3.2 | Height 2.10 m | x = ±1.038 m |
| Bar_Straight (main structural bar) | OD 42×3.2 | Length 2.00 m | z = 1.962 m |
| Bar_Wave (grip) | OD 34×3.2 | Path ~5.73 m | z = 2.00 m |
| Side_Grip_L / R (grip) | OD 34×3.2 | Path 0.664 m/piece · 4 pieces/side | x = ±1.038 m · z = 0.10–1.85 m |

### Bar_Wave geometry
- Single tube spanning between posts (x = −1.038 → +1.038 m) at z = 2.00 m, inserted 38 mm into each post face
- Forms 4 wave loops alternating in the y-axis (±0.50 m from post centreline) · all bends R = 100 mm · 8 × 90° bends total
- Cut/bend lengths (along tube): straight sections 400-338-800-300-800-300-800-338-400 mm (total 4,476 mm) + 8 bends × 157 mm (1,257 mm) = **5,733 mm** (verified against 3D model)

### Bar_Straight and Side Grips
- Bar_Straight (OD 42) sits below Bar_Wave (OD 34), touching at z = 1.983 m, welded continuously — main structural bar; wave bar provides grip
- Side grips: each piece is a U-shape projecting −Y 250 mm, rising 250 mm, R = 100 mm at each corner, 2 weld points per piece at post face · 4 levels per side (lower/upper weld points): 0.10/0.35, 0.60/0.85, 1.10/1.35, 1.60/1.85 m · same on both sides, 8 pieces total, 16 weld points
- Footprint: 2.00 m wide (working distance between posts) × ~1.00 m deep

---

## 4. PIECE 3 — Dip Bar

3 × ⊓-frame creating 2 grip channels (60 cm and 50 cm) + 3 × C-handle nub accessories

### Components
| Member | Section | Size | Position (x centred) |
|---|---|---|---|
| DipBar_01 | OD 42×3.2 | Path ~3.14 m | 0.000 m |
| DipBar_02 | OD 42×3.2 | Path ~3.14 m | 0.642 m |
| DipBar_03 | OD 42×3.2 | Path ~3.14 m | 1.184 m |
| Nub_01–03 | OD 42×3.2 | Path ~0.63 m/piece | 1 per frame |

- Each frame is a tube bent into an inverted ⊓ shape, height 1.20 m · 2 ground legs (y = 0 and y = 0.75 m)
- Top corners: nub side (y = 0) uses R = 10 mm (weld joint) · far side (y = 0.75 m) uses R = 120 mm
- Working channels: DipBar_01→02 = 60 cm (chest dip) · DipBar_02→03 = 50 cm (tricep dip)
- Nub: C-handle opening toward frame, projecting −Y · width (depth) 250 mm, height 200 mm (z = 1.00–1.20 m), R = 80 mm at each corner, welded at 2 points on frame face
- Footprint: 1.226 m wide × 1.00 m deep

---

## 5. PIECE 4 — Monkey + Flying Bar

Continuous frame 5.0 m long × 1.0 m wide · 5 zones + 2 ladder access points

### Zone Profile (side elevation)
| Zone | Y range | Height Z |
|---|---|---|
| Zone 0 (entry) | −1.0 → 0.0 m | 1.00 m |
| Zone 1 (low flat) | 0.0 → 1.0 m | 1.00 m |
| Zone 2 (incline 45°) | 1.0 → 2.0 m | 1.00 → 2.00 m |
| Zone 3 (high flat) | 2.0 → 3.0 m | 2.00 m |
| Zone 4 (flying incline 35°) | 3.0 → 4.0 m | 2.00 → 2.70 m |

### Components
| Group | Member | Section | Size | Qty |
|---|---|---|---|---|
| Short posts | Post y=−1, 0, 1 (L/R) | SHS 50×50×2.3 | Height 1.00 m | 6 |
| Tall posts | Post_y2 (L/R) | SHS 50×50×2.8 | Height 2.00 m | 2 |
| Tall posts (apex) | Post_y3 (L/R) | SHS 50×50×2.8 | Height 2.70 m | 2 |
| Rungs + entry rails | 35 rungs + Rail_Z0 ×3 | OD 34×3.2 | Length 1.00 m | 38 |
| Structural rails (Zone 1–2) | Rail_Z1, Rail_Z2, Tri_Horiz | SHS 50×50×2.3 | Z1/Tri_Horiz = 1.00 m · **Rail_Z2 = 1.414 m (45° incline)** | 6 |
| Structural rails (Zone 3–4) | Rail_Z3, Rail_Z4 | SHS 50×50×2.8 | Z3 = 1.00 m · **Rail_Z4 = 1.22 m (35° incline)** | 4 |

- Triangle brace at Zone 4 apex: Post_y3 (vertical) + Tri_Horiz (horizontal, z = 2.70 m) + Rail_Z4 (35° incline) — **reduces effective height and overturning moment at tall post base · critical structural member — do not remove**
- Rail wall thickness = matching post in same zone (Zone 1–2 = 2.3 mm · Zone 3–4 = 2.8 mm) · **Tri_Horiz uses 2.3 mm despite being at triangle apex** because it carries axial force (compression/tension) not direct bending; Rail_Z4 (hypotenuse) uses 2.8 mm matching tall posts
- **Inclined rail lengths (for ordering/cutting):** Rail_Z2 = **1.414 m** (Δy 1.0 × Δz 1.0 → 45°) · Rail_Z4 = **1.22 m** (Δy 1.0 × Δz 0.7 → 35°) — centre-to-centre per drawing · **Cut length** with insertion extension at both ends +50 mm: Z2 cut ~1.46 m · Z4 cut ~1.27 m
- Rung spacing 20 cm (Zone 1–3) and 25 cm (Zone 4) · Zone 0 rails (Rail_Z0) are round tube because users must grip them
- Front ladder at y = 0; side ladder at x = +0.50 m rising to Zone 3
- Footprint: 1.00 m wide × 5.00 m long

---

## 6. PIECE 5 — Impact-Absorbing Rubber Flooring

| Item | Value |
|---|---|
| Thickness | 25 mm (minimum) — see increased-thickness condition below |
| Material | EPDM top surface on SBR base (or solid EPDM) UV-resistant |
| Form | 50×50 cm interlocking rubber tiles or wet-pour |
| Coverage area | ~20 m² (full equipment zone) |
| Substrate | Flat concrete, ~1% drainage slope; anchors drilled through rubber into concrete |

- Rubber flooring defines the datum z = 0 (actual standing level)
- Fall safety condition (Critical Fall Height): 25 mm rubber is rated for falls of approximately 1.0–1.4 m · Monkey apex (2.70 m) and Pull-up (2.30 m) exceed this range → **under Monkey and Pull-up, increase rubber thickness to 40–50 mm** (Monkey fall height ~1.70 m typically requires ≥ 50 mm — verify Critical Fall Height of actual material with supplier · posts in those areas cut proportionally longer to account for increased rubber thickness)

---

## 7. Assembly Method (What-if) — Shop-welded Sub-assemblies, Field-bolted

> **Status of this section:** This is a *supplementary option* and does not replace or remove the primary design in §2–6 · Prepared to address hot-dip galvanising constraints · Background and principles in [Connection Research — Shop-welded Field-bolted](research.connection-assembly.md) · Structural load verification of this option is in [Document 3/4 §7](spec.requirement.md)

### 7.1 Rationale

- Site welding burns off the zinc in the heat-affected zone (~30–50 mm around the weld), causing rust within weeks
- Galvanising the full assembled frame means pieces are too large for the bath (Thai baths typically 3–4 m deep)
- **Approach:** weld sub-assemblies in the shop → HDG-galvanise each sub-assembly individually → bolt together on site through end plate pairs (end plate at bar end ↔ face plate on post face) → achieves both strong welds (shop-welded before galvanising) and complete coating (entire piece galvanised after welding)

### 7.2 Material constraint — 9 mm plates throughout

- Actual available plate thickness = **9 mm only** → standardise to 9 mm at all connections
- Consistent with existing base plates (already 9 mm) → single-thickness stock for the entire project, easy to procure and cut
- **Verification result: 9 mm plate is sufficient at all connections** (plate and bolt utilisation < 0.15) — calculation detail in [Document 3/4 §7](spec.requirement.md)

### 7.3 End Plates and Bolts by Connection Point

| Connection point | End plate (bar/rail end) | Face plate (post face) | Bolts | No. of connections |
|---|---|---|---|---|
| Pull-up Bar_High ↔ post | 100×100×9 around OD 34 tube | 100×100×9 on SHS 76 face | 4× M12 (60×60 pattern) | 2 ends |
| Pull-up Bar_Low ↔ post | 100×100×9 around OD 34 tube | 100×100×9 on SHS 76 face | 4× M12 (60×60) | 2 ends |
| Snake composite ↔ post | 110×110×9 around OD 42 tube | 110×110×9 on SHS 76 face | 4× M12 (70×70) | 2 ends |
| Snake Side_Grip ↔ post | 80×80×9 at U-end (OD 34) | 80×80×9 on SHS 76 face | 2× M10 | 16 points (2/piece × 8) |
| Monkey rail section ↔ post | 110×110×9 at rail SHS 50 end | 110×110×9 on SHS 50 face | 4× M10 (70×70) | ~20 ends |

- All bolts = **Grade 8.8 HDG** + flat HDG washer (≥ 3 mm thick) both sides
- Bolt hole patterns (60×60 / 70×70) may be adjusted to fit actual wrench clearance, but edge distance (plate edge to hole centre) must be ≥ 20 mm and hole centre must clear tube wall/weld line by ≥ 10 mm
- Weld end plate and face plate fully around their perimeter (fillet weld throat ≥ 5 mm) **in the shop before galvanising**

### 7.4 Pieces Galvanised as a Single Sub-assembly (no internal bolt joints)

- **Each Dip frame (DipBar_01/02/03 including Nub)** = 1 piece (~1.23 × 0.75 m, fits galvanising bath) → field-bolt only to base plates on floor
- **Snake composite (Bar_Straight OD 42 + Bar_Wave OD 34 welded continuously)** = 1 piece → field-bolt only at both ends to posts
- **Monkey rail section** = SHS 50 rail ~1 m with 5 rungs OD 34 pre-welded → galvanise the whole section, then bolt to posts (replaces making 35 individual rung plates)

### 7.5 Vent Holes (mandatory — drill before galvanising all closed hollow sections)

| Section | Min. vent hole diameter | Location |
|---|---|---|
| SHS 76×76 | Ø 40 mm | In base plate, offset toward tube wall |
| SHS 50×50 | Ø 28 mm | In base plate or end cap, offset toward wall |
| OD 34 tube | Ø 14 mm | In each end plate, offset toward tube wall |
| OD 42 tube | Ø 18 mm | In each end plate, offset toward tube wall |

> **Safety warning:** Sealed hollow sections without vent holes will **explode in the galvanising bath (lethal hazard)** and will have incomplete internal coating · Do not drill centred on the plate — drill off-centre close to tube wall, ≥ 10 mm from weld line (per ASTM A385 / EN ISO 1461)

### 7.6 Field Assembly Notes

- Torque (HDG bolts have ~25% higher thread friction than bare steel): **M12 ≈ 100–115 N·m · M10 ≈ 52–65 N·m** (or apply anti-seize compound to reduce torque and allow future disassembly)
- Tighten in crisscross pattern: 50% torque → 100% torque
- Apply cold zinc spray (zinc ≥ 93% per ASTM A780) to any cut/ground areas created on site
- Full work sequence: see [Connection Research §6.3](research.connection-assembly.md)

---

> Foundation details, base plates, and anchor bolts are in Document 4/4 [Verification Summary & Foundation](spec.summary.md) · Member-by-member load analysis is in Document 3/4 [Load & Requirement Analysis](spec.requirement.md)
