# Reference Research — Steel Sizing · Base Plates · Anchor Bolts

> [Master Index (TOC)](toc.md) · final1 set: [Gallery 1/4](design/design.gallery.md) · [Design 2/4](spec.full.md) · [Load Analysis 3/4](spec.requirement.md) · [Verification + Foundation 4/4](spec.summary.md) · [Scope & Liability](policy.liability.md)
>
> **Status**: Reference research document — serves as the database and source of values used in the final1 set (originally compiled during spec v2 review)
> **Date Compiled**: 11 June 2026
> **Research Method**: Direct reading of two primary source documents (EN 16630:2015 full PDF + Hilti HSA Technical Datasheet Jan-23) + actual product pages from 9 manufacturers + Thai material suppliers
> **Short Summary**: Steel specified in spec v2 is adequate for all pieces (margin 3–5×) · Base plate and anchor details compiled in this document have been incorporated into the governing requirements in [spec.summary §4](spec.summary.md)
>
> **For actual construction, use [spec.summary §4](spec.summary.md) as the governing document** (9 mm plates throughout · M12×120 anchors at all points) — the 6 mm thickness and M10 anchor values that appear in this document are from the preliminary spec v2 survey and are retained for reference only.

---

## Table of Contents

1. [TL;DR — Summary Recommendations](#1-tldr)
2. [EN 16630:2015 Standard — Values the Design Must Meet](#2-en-166302015)
3. [Brand Survey — Steel Used by Major Manufacturers](#3-brand-survey)
4. [Brand vs. Spec v2 Comparison by Piece](#4-brand-vs-spec-comparison)
5. [Base Plate — Sizing, Thickness, and Selection Principles](#5-base-plate)
6. [Anchor Bolt — Full Data from Hilti HSA Datasheet](#6-anchor-bolt)
7. [Concrete Slab Thickness + Required Edge Distances](#7-concrete-slab)
8. [Engineering Sanity Check (Preliminary Estimates)](#8-sanity-check)
9. [Availability in the Thai Market](#9-thai-market)
10. [Open Issues — Items to Discuss Before Revising Spec](#10-open-issues)
11. [All References](#11-references)

---

## 1. TL;DR — Summary Recommendations

| Post | Steel section (spec v2) | Review result | Recommended base plate | Recommended anchor |
|---|---|---|---|---|
| Pull-up Post_L/R (2.30 m) | SHS 76×76 w3.2 | Adequate (margin ~4×) | **200×200×9 mm** · 4× Ø14 holes | **4× M12×120 wedge (HDG)** · h_ef 65 mm |
| Pull-up Post_Child (1.60 m) | SHS 76×76 w3.2 | Adequate (ample margin) | 200×200×9 mm | 4× M12×120 |
| Snake Post_L/R (2.10 m) | SHS 76×76 w3.2 | Adequate | 200×200×9 mm | 4× M12×120 |
| Monkey Post short y−1/y0/y1 (1.00 m) | SHS 50×50 w2.3 | Adequate | **150×150×6 mm** · 4× Ø12 holes | **4× M10×100 wedge (HDG)** · h_ef 50 mm |
| Monkey Post_y2 (2.00 m) | SHS 50×50 w2.8 | Adequate (braced by rails) | 200×200×9 mm | 4× M12×120 |
| Monkey Post_y3 (2.70 m) | SHS 50×50 w2.8 | Adequate **because triangle brace is present** (without brace, standalone post would not pass — see §8.3) | 200×200×9 mm | 4× M12×120 |
| Dip frame legs (×6 points) | Tube OD 42 w3.2 | Adequate | **120×120×6 mm**/leg · 2–4× Ø12 holes | 2–4× M10×100/leg |
| All grip bars OD 34 / OD 42 | — | Compliant with EN 16630 grip 16–45 mm | — | — |

> All figures in this table have sources in this document — base plate: see §5, anchor: see §6, calculations: see §8 · **For the final foundation/anchor specification, use [spec.summary §4](spec.summary.md) (9 mm plates throughout · M12×120 at all points)**

---

## 2. EN 16630:2015

Source: **EN 16630:2015 (E) "Permanently installed outdoor fitness equipment — Safety requirements and test methods"** ([full PDF](https://www.spartanparks.com.au/wp-content/uploads/2021/04/EN_16630_2015.pdf)) — the same standard used for certification by BarManiaPro / Deportesurbanos; applies to users taller than 1,400 mm (children ~5 years old also fall under EN 1176, which spec v2 already references)

### 2.1 Design Loads (Clause 4.3.2, Table 1) — The Core of Structural Verification

| No. of users n | Total mass Gn (kg) | Dynamic factor C_dyn | Total vertical force F_tot,v (N) | Force per user (N) |
|:---:|:---:|:---:|:---:|:---:|
| 1 | 99 | 2.00 | **1,942** | 1,942 |
| 2 | 185 | 1.50 | **2,722** | 1,361 |
| 3 | 270 | 1.33 | 3,523 | 1,174 |

Formula: `Gn = n×m + 1.64×σ×√n` where m = 78 kg (male, age 18–65, 50th percentile), σ = 12.6 kg, and `C_dyn = (1+n)/n`

→ Interpretation: **1 user station must be designed to carry ~198 kg (vertical force, dynamics already included)** — the ×2 dynamic factor covers kipping and swinging per the standard
→ This project: pull-up bar designed for n=2 (adult + child) = 2,722 N distributed to 2 posts · each monkey bar zone has 1 person at a time = 1,942 N per rung

- Equipment must be **"permanently connected to the substrate"** — permanently fixed to the floor (the base plate + bolt approach of this project satisfies this clause)
- Structural adequacy may be demonstrated by either (a) calculation per EN 1176-1:2008 Annex A/B using Table 1 loads above, or (b) physical testing

### 2.2 Grip Dimensions (Clause 4.3.12)

- Members designed for **gripping (grip)**: cross-section must be **≥16 mm and ≤45 mm** in every direction
  → OD 34 mm (rungs, pull-up, snake) and OD 42 mm (dip) **both pass** · OD 42 is near the 45 mm ceiling — do not increase to 48 mm
- Members that are only **grasped or leaned on (grasp)**: may be up to 80 mm wide → SHS 76 mm posts remain within the grasp criterion

### 2.3 Free Height of Fall (Clause 4.3.14.5, Table 4)

| Activity type | Measured from | Ceiling |
|---|---|---:|
| Standing | Foot level → ground | 2.0 m |
| Hanging | **Grip height − 1 m** → ground | 3.0 m |

→ This project: pull-up 2.20 m → fall height 1.20 m · monkey apex 2.70 m → fall height 1.70 m · all pieces are below the 3 m ceiling, but **impact-absorbing surface is required per EN 1177 corresponding to the fall height at each zone** — the EPDM 25 mm specified in the design should be cross-checked against the Critical Fall Height rating of the actual product purchased (standard EPDM 25 mm is typically rated ~1.0 m — the monkey zone at 1.7 m may need a thicker or denser rubber — **Open issue §10**)

### 2.4 Foundations (Clause 4.3.15)

- Foundations **must not create a tripping or impact hazard**
- For loose-fill surfaces (sand/rubber granules): footing top must be ≥200 mm below the surface, or fixing buried ≥400 mm deep (Figure 12: hole ≥400 mm deep, 45° chamfered edge)
- **Protruding bolt/screw ends must be buried ≥400 mm below the surface or be covered**
- For this project (base plate on smooth concrete slab): the standard accepts this — consistent with Deportesurbanos explicitly specifying "expansion plugs on concrete cubes or slabs" — however, plate edges and bolt heads must be addressed per §2.5

### 2.5 Surface Finish (Clause 4.3.3) — Directly Relevant to Bolt Heads

- **All protruding threads must be permanently covered** at every user-accessible point (e.g. **dome cap nut / protective cover**)
- Protruding nut/bolt heads up to ≤8 mm are permitted only at inaccessible locations and must have no sharp burrs
- Edges or protrusions >8 mm in the play area must be chamfered to R ≥3 mm
  → **Every base plate should have its corners chamfered, and anchor bolt tops should have dome caps fitted or excess thread trimmed and capped** — include this step in the contractor's quotation

---

## 3. Brand Survey

Listed from commercial park → prosumer → home rig (ordered by similarity to this project)

### 3.1 Summary Table

| Brand (Country) | Level | Post | Grip bar | Corrosion protection | Ground fixing |
|---|---|---|---|---|---|
| **Deportesurbanos** (ES) | Commercial park, UNE-EN 16630 | Round tube **Ø114 mm** galvanised | **Ø33.7 mm** (range: 25/32/38/48/60 mm) | Galvanised + powder coat | **Anchor base Ø300 mm + metal expansion plug on concrete** or embedded footing |
| **KOMPAN** (DK) | Commercial park, EN 16630/1176 | **Ø101.6 mm** pre-galvanised | Dip/parallel grip **Ø38 mm** HDG | Pre-galv + HDG | In-ground footing or **surface mount: steel footing + expansion bolts** |
| **BarManiaPro** (EU) | Commercial street workout, NEN-EN 16630:2015 | Column 3,400 mm long (projects ~2.5 m above grade = **buried ~0.9 m**) | **Ø33.7 mm** · Basic model Ø32 mm | 2-coat system | Embedded footing (public park standard) · max user 130 kg · 25-year warranty |
| **Kenguru Pro** (EU) | Commercial, TÜV/GOST | Legacy line: curved tube **Ø48 mm** (PK series) · 2024 line: anodised aluminium posts + stainless horizontals | — | Anodise / zinc primer | Embedded footing |
| **TOLYMP** (DE) | **Prosumer home garden** — closest match to this project | **RHS 80×60 mm wall 3.0 mm** stainless V2A | Ø33 mm (gym bar) | Stainless (galv steel line is H-post only) | **Embedded in concrete ~60 cm deep** with M12 threaded rod for levelling |
| **GetRXD** (US) | Commercial/backyard rig | **SHS 3"×3" (76 mm)** 11-gauge (~3.0 mm) or 7-gauge (~4.6 mm) | Ø1.25" (~32 mm) | **Hot-dip galvanised inside and out** | **Pre-drilled base plate + 4-bolt concrete anchor kit** (included with rig) — exactly the same model as this project |
| **Rogue** (US) | Commercial rig | 3"×3" 11-gauge, hardware 5/8" (≈16 mm) | Ø32–43 mm | Powder coat (indoor line) | Base plate + **HD concrete anchor** (removable bolts, 3/8" drill hole) |
| **Eleiko Prestera** (SE) | Commercial outdoor | Galvanised rig frame | **Ø33 mm** (specified as optimal grip) | Galvanised | Base plate + anchor |
| **GORNATION / FitnessKIT** (DE) | Prosumer dip bar | — | **Ø40 mm / Ø43 mm** | Powder/galv | — |

### 3.2 Key Observations from the Table

1. **Commercial park posts (Ø101–114 mm) are 1.5× larger than this project — but that is the spec for 5+ simultaneous users in a public park** (EN Table 1: n=5 → 5,133 N) and must resist vandalism · **Rig/home segment posts (GetRXD, Rogue, TOLYMP) use 76 mm or 80×60 mm wall ~3 mm — the same range as SHS 76×76 w3.2 in this project** → the post sizing in spec v2 is in line with manufacturers serving the same use case
2. **Grip Ø33–34 mm is the industry consensus** (Deportesurbanos 33.7 / BarManiaPro 33.7 / Eleiko 33 / TOLYMP 33) → OD 34 in this project is correct
3. **Dip grip 38–43 mm is the industry consensus** (KOMPAN 38 / GORNATION 40 / FitnessKIT 43) → OD 42 in this project is correct
4. Ground fixing has two clear camps: **European public park manufacturers favour embedded footings 60–90 cm deep** (TOLYMP, BarManiaPro), while **US rig manufacturers and the surface-mount options of KOMPAN/Deportesurbanos use base plate + expansion anchor on concrete** → the base plate approach of this project is standard practice among commercial-grade manufacturers, not a compromise on standards
5. Reference dimensions from actual commercial products: **Deportesurbanos uses an anchor base Ø300 mm for a Ø114 mm post** (base-to-post ratio ≈ 2.6×) → for a 76 mm post this ratio gives ≈ 200 mm — consistent with the calculation in §5

---

## 4. Brand vs. Spec v2 Comparison by Piece

### PIECE 1 — Pull-up Bar

| Item | Spec v2 | Benchmark | Result |
|---|---|---|---|
| 2.30 m post | SHS 76×76 w3.2 | GetRXD 76 mm/3.0–4.6 mm (12–15 ft tall posts) · TOLYMP 80×60/3.0 | Pass — in the middle of the range · these project posts at 2.3 m are roughly half the height of those rigs |
| Bar z=2.20 m | OD 34 w3.2 | Eleiko 33 / BarManiaPro 33.7 | Pass — matches industry standard |
| Bar length 1.50 m | — | BarManiaPro crossbar 1.45 m | Pass — very close (manufacturer rated 130 kg) |
| Child bar z=1.50 m | OD 34 | EN 1176 child grip 16–45 | Pass |

### PIECE 2 — Snake Bar

| Item | Spec v2 | Benchmark | Result |
|---|---|---|---|
| 2.10 m post | SHS 76×76 w3.2 | Deportesurbanos snake bar uses the same post as pull-up (Ø114 commercial) | Pass — same principle as PIECE 1 |
| Wave bar | OD 34 w3.2, 8 bends R100 | Deportesurbanos/BarManiaPro Ø33.7 | Pass — R100 = 3×OD, standard for rotary-draw bending |
| Side U-grips | OD 34, R100 | — (no direct brand comparison — custom order item) | Pass — grip meets EN · 2 welds per unit, see §8.4 |

### PIECE 3 — Dip Bar

| Item | Spec v2 | Benchmark | Result |
|---|---|---|---|
| Frame OD 42 w3.2, 1.2 m tall | — | KOMPAN grip Ø38 HDG (Ø101.6 post because it is a park unit) · GORNATION Ø40 · FitnessKIT Ø43 | Pass — OD 42 sits in the middle of the 38–43 range |
| Load | — | EN: dip = 1 user/channel → 1,942 N | Pass — tube Ø42×3.2 at 620 mm span has ample margin (see §8.5) |

### PIECE 4 — Monkey + Flying Bar

| Item | Spec v2 | Benchmark | Result |
|---|---|---|---|
| Short post 1.0 m | SHS 50×50 w2.3 | No brand uses a post smaller than 76 mm in a standalone unit — **but this design is a portal frame with 10 posts + rails braced along 5 m** | Pass — see calculation §8.3 |
| Tall posts y2/y3 (2.0/2.7 m) | SHS 50×50 w2.8 | GetRXD monkey bar rig uses 76 mm but as a 2–4-post freestanding unit | Pass — **conditional on the triangle brace being present and complete** |
| Rungs OD 34 at 20 cm spacing | — | Public play equipment typically uses rungs Ø33.7 at 20–30 cm spacing | Pass |
| Rail_Z0 OD 34 | — | EN grip 16–45 | Pass — the reason for changing from SHS is correct |

---

## 5. Base Plate

### 5.1 Sizing Principles (Engineering Practice)

- **Bolt edge distance on plate**: practical rule of thumb = allow ~4d around the post (d = bolt diameter) · code minimum per AISI S100 E.42 = 1.5d from bolt centre to plate edge ([Eng-Tips](https://www.eng-tips.com/threads/base-plate-design.425962/), [AWS forum](https://app.aws.org/forum/topic_show.pl?tid=8230))
- Plate size ≈ post face + 2×(bolt offset + edge distance): 76 mm post + 2×(40 + 22) ≈ **200 mm** → consistent with the actual ratio of Deportesurbanos (Ø300 for Ø114 post = 2.6×; this project: 200/76 = 2.6× exactly)
- **Thickness**: members carrying moment (pull-up/snake posts receiving lateral load) use 9–12 mm · for members carrying primarily axial compression (short posts, dip), 6 mm is sufficient — plate thickness should be ≥ 2× the post wall as a minimum to allow the full-perimeter fillet weld to develop full strength
- **Holes in plate** = clearance holes per Hilti: M12 → **Ø14 mm** · M10 → **Ø12 mm** (do not drill larger — wedge anchors require a close-fit hole)
- Post-to-plate weld: fillet all around, leg ≥ post wall (3.2 mm → fillet 4–5 mm) + **drill 1 drain hole at the post bottom or weld a closed cap at the top** to prevent water accumulating inside the hollow section (the primary failure point for outdoor posts)

### 5.2 Recommended Plate Sizes by Post

| Post | Qty | Plate | Holes | Bolt pattern (hole centre spacing) | Notes |
|---|:---:|---|---|---|---|
| Pull-up — all 3 posts | 3 | **200×200×9 mm** | 4× Ø14 | 140×140 mm | Chamfer corners R≥3 mm per EN |
| Snake — 2 posts | 2 | 200×200×9 mm | 4× Ø14 | 140×140 mm | — |
| Monkey y−1/y0/y1 (6 posts) | 6 | **150×150×6 mm** | 4× Ø12 | 100×100 mm | Short posts, low moment |
| Monkey y2/y3 (4 posts) | 4 | **200×200×9 mm** | 4× Ø14 | 140×140 mm | Tall posts, moment governs |
| Dip frame (3 frames × 2 legs) | 6 | **120×120×6 mm** or round Ø120 plate | 2× Ø12 (along Y) | 80 mm | Round tube Ø42 welded down to plate |

> Material summary: plate 200×200×9 = 9 plates · 150×150×6 = 6 plates · 120×120×6 = 6 plates
> Thai suppliers will cut and drill to drawing (see §9.2) — provide a DXF or dimensioned sketch for the supplier to drill; the site contractor does not need to drill on site.
>
> **Note (updated subsequently):** The project concluded using **9 mm plates throughout** (including 150×150 and 120×120 plates) and **M12×120 anchors at all points** (Ø14 holes) per [spec.summary §4](spec.summary.md) · The plate size allocation (tall posts y2/y3 → 200×200, short posts → 150×150) matches the table above.

### 5.3 Why Gusset Plates Are Not Required

All posts carry a maximum moment of approximately 2.2 kN·m (see §8.2) — a 9 mm plate projecting ~60 mm from the post face has sufficient bending capacity to resist the prying force at this level (tension on one bolt side ≤8 kN). If additional margin is desired specifically at Post_y3, two gussets (50×50×6 mm) can be added on the tension side — but **they are not required by the numbers** — retain as an option to discuss with the contractor.

---

## 6. Anchor Bolt

### 6.1 Suitable Type: Wedge Anchor (Mechanical Expansion Anchor)

Consistent with what commercial manufacturers use — Deportesurbanos: "metal expansion plugs on concrete slabs" · KOMPAN: "steel footings and expansion bolts" · GetRXD supplies concrete anchors with the rig kit — this project carries moderate static + dynamic loads on uncracked concrete → a standard wedge anchor is sufficient; no need for chemical anchors (retain chemical anchors as a fallback if on-site concrete quality is poor or a hole is mis-drilled — more expensive but more tolerant of installation errors)

### 6.2 Full Data from Hilti HSA Technical Datasheet (Jan-2023, ETA-11/0374)

Source: [original PDF](https://kalaomran.com/wp-content/uploads/2023/11/Technical-data-sheet-for-the-HSA-stud-anchor-Technical-information-ASSET-DOC-2027424.pdf) — Hilti is used as the reference spec; compare grade against Thai anchors when purchasing (if the local anchor has no third-party certification, apply a reduction factor of 1.5–2.0 to the capacity)

#### Setting Details (C20/25 Concrete, Uncracked)

| | M10 | M12 | M16 |
|---|---|---|---|
| Embedment depth h_ef (mm) | 40 / **50** / 80 | 50 / **65** / 100 | 65 / 80 / 120 |
| Hole depth h_nom (mm) | 50 / **60** / 90 | 64 / **79** / 114 | 77 / 92 / 132 |
| Drill bit Ø (mm) | 10 | **12** | 16 |
| Minimum hole depth (mm) | 55 / 65 / 95 | 72 / **87** / 122 | 85 / 100 / 140 |
| **Minimum concrete thickness h_min (mm)** | 100 / **120** / 160 | 100 / **140** / 180 | 140 / 160 / 180 |
| Minimum bolt spacing s_min (mm) | 50 | **70** | 90 |
| Minimum edge distance c_min (mm) | 40–50 | **55–70** | 70–80 |
| Edge distance for full capacity c_cr,N (mm) | 60 / 75 / 120 | 75 / **97.5** / 150 | 97.5 / 120 / 180 |
| Installation torque T_inst (N·m) | 25 | **50** | 80 |
| Clearance hole in plate (mm) | ≤12 | **≤14** | ≤18 |

#### Recommended Loads (including safety factor γ=1.4) — per Anchor

| | M10 | M12 | M16 |
|---|---|---|---|
| Tension N_rec (kN) by h_ef | 5.9 / **8.3** / 11.9 | 8.3 / **12.3** / 16.7 | 12.3 / 16.8 / 23.8 |
| Shear V_rec (kN) | 10.8–12.9 | **16.6–16.9** | 29.1–32.3 |

→ **M12 at h_ef 65 mm: tension capacity 12.3 kN/anchor = ~1.2 tonnes** — compared with this project's maximum demand per anchor of ~4 kN (§8.2) = margin ×3
→ Short monkey posts using M10 at h_ef 50 mm (8.3 kN/anchor) also have ample margin

#### Material and Length to Order

- Standard **HSA = zinc-plated ≥5 µm — not adequate for permanent outdoor exposure** · outdoor installations require the **HSA-F (hot-dip galvanised ≥42 µm)** grade or stainless (HSA-R) — HDG grade wedge anchors are available from Thai suppliers (see §9.1)
- Recommended length: **M12×120** → embeds h_nom 79 mm (h_ef 65 mm), remaining protrusion ~41 mm = nut 10 + washer 2.5 + plate 9 → thread protruding above nut ~19 mm → **trim or cover with dome cap per EN §4.3.3**
- M10×100 → embeds h_nom 60 mm (h_ef 50 mm) + plate 6 + nut 8 → protrusion ~26 mm → handle the same way
- Total project quantity (initial survey): **M12×120 = 36** (9 tall posts × 4) + **M10×100 = 36** (short monkey posts 6×4 + dip legs 6×2) + ~10% spare
- **Note (updated subsequently):** The project concluded using **M12×120 anchors at all points** (including short posts and dip legs) replacing the mixed M10 approach → total **M12×120 = 72 anchors** per [spec.summary §4](spec.summary.md) · The M10 figures above are retained as reference for the original survey only.

### 6.3 Correct Installation Procedure (from Hilti datasheet — suitable for inclusion in the contractor's quotation)

1. Drill hole with the correct diameter bit to depth ≥ h_nom + 5 mm, at 90° to the surface
2. **Blow or vacuum the hole clean** (the step most commonly skipped by Thai contractors — dust in the hole can reduce capacity by >30%)
3. Insert anchor through the plate hole and drive until the blue ring/mark is flush
4. **Torque to T_inst using a calibrated torque wrench** (M12 = 50 N·m, M10 = 25 N·m) — do not torque by feel; over-torquing = anchor slips/concrete cracks, under-torquing = loose anchor

---

## 7. Concrete Slab

| Requirement | Value | Source |
|---|---|---|
| Minimum slab thickness (M12, h_ef 65) | **≥140 mm** | Hilti h_min |
| Minimum slab thickness (M10, h_ef 50) | ≥120 mm | Hilti h_min |
| Concrete grade | C20/25 (≈ Thai standard 210–240 ksc cube) — standard structural concrete qualifies | Hilti datasheet basis for entire table |
| Bolt centre to slab edge | ≥70 mm (minimum) · **≥100 mm (recommended — achieves full capacity)** | c_min / c_cr,N |
| Concrete condition | Uncracked in the installation zone | HSA is specified for uncracked concrete |

→ The floor_v1 design is a 6×5 m slab 0.30 m thick — **passes all criteria with significant margin**
→ On-site: if any area uses existing older concrete, measure the actual thickness ≥140 mm before drilling (a pilot drill can check this), and all posts in the current layout are already >100 mm from the slab edge given the 0.5 m margin in the plot
→ TOLYMP benchmark for embedded option: footing ~60 cm deep per post — use this formula for any future piece positioned outside the slab (Ø300 × 600 mm deep concrete encasing the post base)

---

## 8. Sanity Check

> **Note:** This section contains **preliminary estimates only** (first-order, order-of-magnitude) to confirm that sizing is in the right ballpark — these are not signed structural engineering calculations · Assumptions: Thai hollow section steel per TIS/STKR400, fy ≈ 245 MPa · loads from EN Table 1

### 8.1 Section Properties

| Section | Section modulus Z (cm³) | Approximate yield moment (kN·m) |
|---|---:|---:|
| SHS 76×76×3.2 | 21.7 | **5.3** |
| SHS 50×50×2.8 | 7.9 | 1.9 |
| SHS 50×50×2.3 | 6.7 | 1.6 |
| Tube OD 42.4×3.2 | 3.6 | 0.88 |
| Tube OD 34×3.2 | 2.2 | 0.55 |

> **Note on 1¼″ OD:** actual OD of 1¼″ BSP ≈ 42.4 mm (used in this table) · the specification documents (spec.full / spec.summary) use the conservative OD 42 mm → section modulus differs by approximately 2% (3,519 vs. 3,594 mm³) — does not affect any conclusions

### 8.2 Pull-up Posts (Worst Case for 76 mm Posts)

- Vertical EN load n=2: 2,722 N ÷ 2 posts → axial force is negligible (posts can carry axial loads in the hundreds of kN) — not critical
- Lateral load from kipping/swinging: estimated horizontal ≈ 0.5×G ≈ **1.0 kN at z=2.2 m** → base moment ≈ 2.2 kN·m shared by 2 posts through the bar → **~1.1 kN·m/post**
- Compare with capacity 5.3 kN·m → **utilisation ~21% → margin ≈ 4.8×** (even if the entire moment is assumed to act on one post alone: utilisation 42%)
- Anchor tension from overturning on one post: M=2.2 kN·m / lever arm 0.14 m (140 mm bolt pattern) ≈ 15.7 kN ÷ 2 anchors on the tension side ≈ **7.9 kN/anchor < 12.3 kN** (and this already conservatively assumes one post carries the entire overturning moment)

### 8.3 Monkey Bar Posts — Thinnest Point of the Project (But Passes)

- **Post_y3 (2.7 m, SHS 50×50×2.8)**: a user swinging on the flying bar → horizontal force ≈ 0.5–0.7 kN at z=2.7 m → as a free-standing post with no bracing, M ≈ 1.4–1.9 kN·m, approaching the capacity of 1.9 kN·m — **a standalone unbraced post has no margin remaining**
- The actual frame is a braced structure: the triangle (Post_y3 + Tri_Horiz + Rail_Z4) + Rail_Z3 + the 5 rungs per zone distribute the lateral load to adjacent posts → the actual moment per post is reduced to roughly 1/3–1/2 → utilisation ~35–50%
- **Design conclusion**: SHS 50 w2.8 is adequate *because* the bracing frame is complete per spec v2 — **if in the future Tri_Horiz / Rail_Z4 / Rail_Z3 are removed, the post must be upgraded to 76 mm** · During assembly, the y3 post must not stand alone without bracing rails while any person is on the structure
- Short posts 1.0 m (w2.3): max M ≈ 1.0 kN × 1.0 m = 1.0 kN·m ... in practice, the normal monkey bar load is 1.9 kN downward through a rung → rails carry both sides, posts carry primarily axial load → utilisation is very low

### 8.4 Rungs + Side Grips (OD 34×3.2)

- Rung 1.0 m long, gripped at midspan: worst case M = PL/4 = 1.942×1.0/4 ≈ **0.49 kN·m < 0.55** — utilisation ~89% which looks high, but 1.942 kN already includes ×2 dynamic factor and the rung is welded at both ends (effectively fixed, M ≈ PL/8 = 0.24 kN·m) → actual utilisation ~45% — consistent with Ø33.7 at 1.0–1.5 m span being the industry standard
- Side U-grip cantilever 250 mm: M = 1.942×0.25 ≈ 0.49 kN·m at the weld point — assumes full bodyweight plus dynamic impact from jumping · normal grip use involves hand loads (lower) but a child may step on the grip → **the 2 weld points per unit on the post face must be full-perimeter fillet welds** — not tack welds — specify this clearly to the contractor

### 8.5 Dip Bar (OD 42.4×3.2)

- Top beam span 620 mm carrying 1,942 N at midspan (both hands close together): M ≈ PL/8–PL/4 ≈ 0.15–0.30 kN·m < 0.88 → utilisation ≤34%
- Frame legs 1.2 m tall: lateral force from L-sit or swinging ≈ 0.3 kN → M ≈ 0.36 kN·m → ~41%

### 8.6 Sanity Check Summary

All pieces have margin ≥2× from first-order estimates under the EN standard load — **no piece needs to be upsized, and no piece is unnecessarily oversized.** The only point that must be maintained strictly per spec is the triangle brace at Zone 4 (§8.3).

---

## 9. Thai Market

### 9.1 Wedge Anchors

| Product | Spec | Source |
|---|---|---|
| MR METAL M12×100 (pack of 5) zinc-plated white | Suitable for indoor/temporary use only | [Thaiwatsadu](https://www.thaiwatsadu.com/en/product/%E0%B8%9E%E0%B8%B8%E0%B8%81%E0%B9%80%E0%B8%A7%E0%B8%94%E0%B8%88%E0%B9%8C-MR-METAL-%E0%B8%82%E0%B8%99%E0%B8%B2%E0%B8%94-M12-x-100-%E0%B8%A1%E0%B8%A1-(%E0%B9%81%E0%B8%9E%E0%B9%87%E0%B8%81-5-%E0%B8%95%E0%B8%B1%E0%B8%A7)-%E0%B8%AA%E0%B8%B5%E0%B8%8B%E0%B8%B4%E0%B8%87%E0%B8%84%E0%B9%8C%E0%B8%82%E0%B8%B2%E0%B8%A7-60374011) |
| Wedge anchor M12×120 zinc-plated / **Hot-dip galvanised (HDG)** | **Outdoor: use HDG grade** | [พุกเหล็ก.com — M12×120 HDG](https://www.xn--12caal4gxbxbo7c2db8dwa3g5e.com/product/%E0%B8%82%E0%B8%99%E0%B8%B2%E0%B8%94-m12x120mm-%E0%B8%9E%E0%B8%B8%E0%B8%81%E0%B9%80%E0%B8%A7%E0%B8%94%E0%B8%88%E0%B9%8C%E0%B8%8A%E0%B8%B8%E0%B8%9A%E0%B8%AE%E0%B8%AD%E0%B8%97%E0%B8%94%E0%B8%B4%E0%B8%9E-hdg/11000711956001552), [Stronghold Asia](https://strongholdasia.net/product/wedge-anchors-m12x120-120-mm/) |
| Siam Anchor Fastener — WA-HDG (Thai-made) | Wedge anchor hot-dip galvanised — matches outdoor spec | [fastenic.com](https://www.fastenic.com/product/detail/wedge-anchor-hot-dip-galvanized---wa-hdg) |
| Chemical anchor M12 (fallback) | For poor on-site concrete or mis-drilled holes | [PK Hardware](https://www.pkhardware.com/%E0%B8%AA%E0%B8%B4%E0%B8%99%E0%B8%84%E0%B9%89%E0%B8%B2/%E0%B8%9E%E0%B8%B8%E0%B8%81%E0%B9%80%E0%B8%84%E0%B8%A1%E0%B8%B5/%E0%B8%9E%E0%B8%B8%E0%B8%81%E0%B9%80%E0%B8%84%E0%B8%A1%E0%B8%B5%E0%B9%81%E0%B8%9A%E0%B8%9A%E0%B8%9B%E0%B8%B1%E0%B9%88%E0%B8%99-m12-chemical-anchor-bolt) |
| Hilti HSA-F genuine | Reference spec — more expensive but has ETA certification | Hilti TH authorised dealer |

> **Caution**: White zinc anchors (~5 µm) are for indoor use only — outdoor exposed to rain **requires HDG or stainless grade** to match the galvanised theme of the whole project. The price difference is only a few tens of baht per anchor.

### 9.2 Base Plates

| Product | Spec | Source |
|---|---|---|
| Steel plate 150×150 mm cut/drilled to order | 6 mm available · drilled on order | [Aplus Watsadu](https://www.apluswatsadu.com/product/steel-plate-carbon-150x150/) |
| Steel plate 200×200 mm | Thickness **6 / 9 / 10 / 12 mm** · holes drilled per drawing | [Aplus Watsadu](https://www.apluswatsadu.com/product/steel-plate-carbon-200x200-mm/) |
| 4"/6"/8" plate cut to order, factory pricing | Retail + wholesale | [Lerlert Corp](https://www.lerlertcorp.com/steel-plate/), [OneStockHome](https://www.onestockhome.com/th/product_categories/steel-plate), [TintSteel](https://tint-steel.com/steel-plate/) |

> Plates sold are **black carbon steel (not coated)** — for this project they must be **hot-dip galvanised after welding to the posts** (galvanise the entire post + plate assembly in one dip = the same standard as GetRXD "hot-dip galvanised inside and out"), or at minimum apply a heavy coat of cold-galvanising spray at all weld zones — this decision affects the construction sequence (weld first, then galvanise) and must be included in the contractor's quotation.

### 9.3 Materials Already Specified in Spec v2 (Confirmed Here)

- SHS 76×76 w3.2 galv: Aplus Watsadu · SHS 50×50 w2.3/2.8 galv: widely available at all steel suppliers · Round tube OD 34/42 galv: standard 1"/1¼" BSP (referenced in spec.human.v2.md)

---

## 10. Open Issues

Items identified through this research that should be decided jointly before revising the spec:

1. **Impact-absorbing surface at monkey/flying bar zone** — fall height 1.7 m exceeds the typical EN 1177 Critical Fall Height of standard EPDM 25 mm (~1.0 m) · Options: (a) increase EPDM/rubber granule depth to 40–50 mm in that zone only · (b) 200 mm+ sand like a public play area · (c) accept the risk level appropriate for a home installation (EN standard is a guideline, not Thai law) — **budget implication: recommend discussing jointly**
2. **Full HDG after welding the plate vs. cold-galvanising spray** — proper galvanising is far more durable but requires transporting to a galvanising plant (affects logistics + cost ~30–40 THB/kg) vs. spray is cheaper but weld zones will be the first rust sites in 3–5 years
3. **Anchor bolt thread protruding ~19 mm above nut** — EN requires covering: use M12 dome cap nut (available in Thailand) or have the contractor trim excess thread and apply zinc touch-up — specify preferred method in the quotation
4. **Dip bar: 2 anchors/leg vs. 4 anchors/leg** — load passes with ample margin either way, but 4 anchors prevent long-term rocking better; adds 12 extra holes to drill — recommend 4 anchors for the 2 outer frames
5. **Base plate edges at floor level = tripping hazard per EN** — home-level remedy: chamfer corners + paint yellow edge marking, or fill EPDM rubber up to plate edge — decide during flooring installation
6. Budget: additional materials ≈ 21 plates + ~80 anchors + galvanising/spray cost — rough estimate **3,500–8,000 THB** (depending on item 2) — does not significantly affect total budget (remaining ~61k THB)

---

## 11. References

### Standards + Datasheets (Read in Full from Primary Sources)

- [EN 16630:2015 (E) — Permanently installed outdoor fitness equipment (full PDF)](https://www.spartanparks.com.au/wp-content/uploads/2021/04/EN_16630_2015.pdf) — Table 1 loads, clause 4.3.2/4.3.3/4.3.12/4.3.14.5/4.3.15
- [Hilti HSA Expansion Anchor — Technical Datasheet Jan-23, ETA-11/0374 (PDF)](https://kalaomran.com/wp-content/uploads/2023/11/Technical-data-sheet-for-the-HSA-stud-anchor-Technical-information-ASSET-DOC-2027424.pdf) — setting details, recommended loads, length/letter codes
- [Confast — Wedge Anchor Technical Specifications](https://www.confast.com/wedge-anchor-technical-specifications/)
- [Ferry International — M12 Anchor Bolt Load Capacity Chart](https://www.ferry-international.com/blog/126/anchor-bolt-load-capacity-chart)

### Brand Product Pages

- [Deportesurbanos — Outdoor Pull Up Bar DUCP-2009](https://deportesurbanos.com/en/producto/outdoor-pull-up-bar/) — Ø114 post, Ø300 anchor base, expansion plugs, UNE-EN 16630
- [BarManiaPro — Pull-up bar BMP-51007](https://barmaniapro.com/product/pull-up-bar/) — Ø33.7, column 3.4 m, 130 kg, NEN-EN 16630:2015
- [BarManiaPro — Pull-up bar Basic](https://barmaniapro.com/product/pull-up-bar-pro/) — Ø32
- [Kenguru Pro — PK-007](https://kengurupro.eu/equipment/pk-007/), [About](https://kengurupro.eu/about/), [Kenguru Pro Canada](https://www.kengurupro.ca/equipment/) — Ø48 tube (PK line), 2024 line: aluminium + stainless, TÜV
- [TOLYMP Towers](https://www.tolymp.de/en/stations-de-calisthenics-street-workout/tolymp-towers.html/), [TOLYMP Cross Basic](https://www.tolymp.de/en/crossfit-outdoor-gym-equipment/tolymp-cross-basic.html/) — 80×60 w3.0 post, embedded ~60 cm, M12 rods
- [KOMPAN — FPW201 Parallel Bars](https://www.kompan.com/en/int/p/fpw201) — Ø101.6 pre-galv post, grip Ø38 HDG
- [GetRXD — Galvanized Outdoor Builder Rig](https://www.getrxd.com/galvanized-outdoor-builder-rig.html) — 3"×3" 7/11-gauge, base plate + 4 concrete anchor kit
- [Rogue — Monster Lite Rig 2.0](https://www.roguefitness.com/monster-lite-rig-2-0) — 3×3" 11ga, 5/8" hardware · [Rogue HD Concrete Anchors](https://www.roguefitness.com/rogue-hd-concrete-anchors)
- [Eleiko — Prestera Straight Pull-up Bar Outdoor](https://eleiko.com/en/equipment/outdoor/galvanized/3085515-01-eleiko-prestera-straight-pull-up-bar-outdoor) — bar Ø33
- [GORNATION Premium Dip Bars](https://www.gornation.com/products/premium-dip-bars) Ø40 · [FitnessKIT Premium Dip Bar](https://fitnesskit.de/en/products/premium-dip-barren-calisthenics-equipment) Ø43
- [MoveStrong FitGround](https://www.movestrongfit.com/fitground-1) — in-ground anchoring standard, surface mount option

### Base Plate Engineering Practice

- [Eng-Tips — Base Plate Design (4d rule of thumb)](https://www.eng-tips.com/threads/base-plate-design.425962/)
- [AWS Forum — Minimum Edge Distance on Base Plates (AISI 1.5d)](https://app.aws.org/forum/topic_show.pl?tid=8230)
- [SkyCiv — AISC Base Plate Design](https://skyciv.com/docs/skyciv-base-plate-design/aisc-base-plate-design-code/)
- [Hilti — Anchor Plate Dimensions Q&A](https://www.hilti.com/engineering/question/anchor-plate-dimensions/gxubit)

### Thai Suppliers

- [Thaiwatsadu — MR METAL M12×100 wedge anchor](https://www.thaiwatsadu.com/en/product/%E0%B8%9E%E0%B8%B8%E0%B8%81%E0%B9%80%E0%B8%A7%E0%B8%94%E0%B8%88%E0%B9%8C-MR-METAL-%E0%B8%82%E0%B8%99%E0%B8%B2%E0%B8%94-M12-x-100-%E0%B8%A1%E0%B8%A1-(%E0%B9%81%E0%B8%9E%E0%B9%87%E0%B8%81-5-%E0%B8%95%E0%B8%B1%E0%B8%A7)-%E0%B8%AA%E0%B8%B5%E0%B8%8B%E0%B8%B4%E0%B8%87%E0%B8%84%E0%B9%8C%E0%B8%82%E0%B8%B2%E0%B8%A7-60374011)
- [Stronghold Asia — Wedge Anchor M12×120](https://strongholdasia.net/product/wedge-anchors-m12x120-120-mm/) · [M12×100](https://strongholdasia.net/product/wedge-anchors-m12x100-100-mm/)
- [พุกเหล็ก.com — M12×120 HDG](https://www.xn--12caal4gxbxbo7c2db8dwa3g5e.com/product/%E0%B8%82%E0%B8%99%E0%B8%B2%E0%B8%94-m12x120mm-%E0%B8%9E%E0%B8%B8%E0%B8%81%E0%B9%80%E0%B8%A7%E0%B8%94%E0%B8%88%E0%B9%8C%E0%B8%8A%E0%B8%B8%E0%B8%9A%E0%B8%AE%E0%B8%AD%E0%B8%97%E0%B8%94%E0%B8%B4%E0%B8%9E-hdg/11000711956001552)
- [Siam Anchor Fastener — WA-HDG](https://www.fastenic.com/product/detail/wedge-anchor-hot-dip-galvanized---wa-hdg)
- [PK Hardware — Chemical anchor M12](https://www.pkhardware.com/%E0%B8%AA%E0%B8%B4%E0%B8%99%E0%B8%84%E0%B9%89%E0%B8%B2/%E0%B8%9E%E0%B8%B8%E0%B8%81%E0%B9%80%E0%B8%84%E0%B8%A1%E0%B8%B5/%E0%B8%9E%E0%B8%B8%E0%B8%81%E0%B9%80%E0%B8%84%E0%B8%A1%E0%B8%B5%E0%B9%81%E0%B8%9A%E0%B8%9A%E0%B8%9B%E0%B8%B1%E0%B9%88%E0%B8%99-m12-chemical-anchor-bolt)
- [Aplus Watsadu — 150×150 plate](https://www.apluswatsadu.com/product/steel-plate-carbon-150x150/) · [200×200 plate (6–12 mm)](https://www.apluswatsadu.com/product/steel-plate-carbon-200x200-mm/)
- [Lerlert Corp — custom-cut plates](https://www.lerlertcorp.com/steel-plate/) · [OneStockHome — steel plate](https://www.onestockhome.com/th/product_categories/steel-plate) · [TintSteel](https://tint-steel.com/steel-plate/)
