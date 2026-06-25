# Reference Research — Shop-welded Field-bolted Connection System
## (Welded in shop · Galvanised as separate pieces · Bolted on site)

| Item | Details |
|---|---|
| Status | Reference research document — not yet a construction drawing |
| Date Compiled | 16 June 2026 |
| Related Documents | [TOC](toc.md) · [Design Specification](spec.full.md) · [Load Analysis](spec.requirement.md) |
| Problem Statement | On-site welding burns/blisters the zinc coating in the weld zone · galvanising the fully assembled structure means pieces may exceed the galvanising bath size → Solution: weld each piece to its plate in the shop → HDG galvanise each piece separately → bolt the plates together on site |
| Primary Sources | Steel Tube Institute (AISC) · EN 1993-1-8 (Eurocode 3) · Galvanizers Association of Australia (GAA) · AGA (American Galvanizers Association) · Structure Magazine |

> **Warning:** Figures in this document are preliminary estimates from research and have not been verified by a licensed engineer. They are not yet a construction-ready drawing.

---

## Table of Contents

1. [TL;DR — Summary Answers](#1-tldr)
2. [Principles and Industry Examples](#2-principles)
3. [Connection Types for This Project](#3-connection-types)
4. [End Plate Design — Dimensions and Bolt Layout](#4-end-plate)
5. [Bolt Selection — Grade, Size, Quantity, Capacity](#5-bolts)
6. [HDG Galvanising Requirements — Vent Holes and Work Sequence](#6-galvanising)
7. [Torque Specifications](#7-torque)
8. [Recommendations by Piece (PIECE 1–4)](#8-by-piece)
9. [Structural Changes Required](#9-structural-changes)
10. [Items to Confirm with the Engineer](#10-open-issues)
11. [References](#11-references)

---

## 1. TL;DR

| Issue | Answer |
|---|---|
| Is this method viable? | Yes — this is the standard industry practice of "shop-welded, field-bolted" used in bridges, steel building frames, and playground equipment |
| Do steel sizes need to change? | No — existing SHS/tube sizes are more than adequate; only face plates need to be added to the post faces |
| Plate sizes | SHS 76: **100×100×10 mm** · SHS 50: **80×80×8 mm** · OD 34/42: **80×80×8 mm** |
| Bolt sizes | **M12 Grade 8.8 HDG** at all main connection points · M10 Grade 8.8 for monkey bar rungs |
| Number of bolts | **4 bolts/connection** for main pieces · **2 bolts/end** for rungs |
| Bolt hole size | Ø15 mm for M12 · Ø13 mm for M10 (drilled before galvanising — no re-tapping needed) |
| Vent holes | Required on all sealed sections: SHS76 → **Ø32 mm** · SHS50 → **Ø25 mm** · OD34 → **Ø14 mm** · OD42 → **Ø18 mm** |
| Torque for M12 HDG | **100–115 N·m** (25% increase over bare steel due to higher zinc thread friction) |
| Monkey bar 35 rungs | **No plate needed per rung** — weld rungs into a rail section first → galvanise the whole section → bolt sections to posts |
| Minor field welds needing touch-up | Cold zinc spray (ASTM A780, zinc ≥93%) applied over cut/weld areas as needed |

---

## 2. Principles

### 2.1 Why Welding Damages HDG Galvanising

HDG (Hot-Dip Galvanising) creates a zinc-iron alloy layer bonded at 450–460°C. The heat from welding (800–1,400°C) causes:

1. Zinc to burn away in the Heat-Affected Zone (HAZ) — a band approximately 30–50 mm wide around the weld line
2. The zinc-free area to rust within weeks in outdoor conditions

Standard industry remedies:
- **Method A (small):** Weld → apply cold zinc spray to repair the zinc-free zone — partial protection only, approximately 5–10× thinner than HDG
- **Method B (medium):** Weld everything → HDG galvanise the complete assembly — best coating quality but the piece must fit the galvanising bath (typical Thai baths are 3–4 m deep)
- **Method C (this project):** Weld sub-assemblies → HDG galvanise each sub-assembly separately → bolt the plated pieces together on site — achieves high-quality coating and easy site assembly

### 2.2 Industry Examples

| Industry | Method Used | Reason |
|---|---|---|
| Small steel bridge | Bolted end plate (pieces 3–6 m each) | Galvanise separately → easy transport |
| Pre-engineered Building (PEB) | Shop-welded frame → field bolts + end plate | MB/AISC standard |
| Prefabricated playground (Easyfit, Berliner) | Galvanised fittings + bolt assembly | No on-site welding |
| Tower crane mast | Bolted flanged sections | Add sections upward one at a time |
| EN 16630 outdoor fitness equipment (BarManiaPro) | Post separate piece bolted to anchor → bar bolted into bracket | Detachable for maintenance |

### 2.3 T-stub Principle (EN 1993-1-8)

End plate connection design per European standard uses the "T-stub equivalent" model with 3 failure modes:

```
Mode 1: Plate hinge (plate is too thin)
  → plate yields at the weld line + bolt elongates
  → requires a thicker plate

Mode 2: Bolt fracture + prying (plate is medium thickness)
  → bolt carries tension + prying force from plate bending
  → requires larger bolt or thicker plate

Mode 3: Bolt fracture only (plate is thick enough)
  → plate is rigid, no bending · bolt carries load directly
  → the best condition → requires plate ≥ 9–12 mm thick
```

For EN 16630 loads of 1,942 N (≈ 0.2 tonnes) per connection, **the load is very low** — 8–10 mm plates will sit in Mode 3 in every case. The plate thickness chosen is driven by geometric requirements (space to fit a wrench), not structural capacity.

---

## 3. Connection Types

This project has three appropriate connection types:

### Type A — End Plate on Bar + Face Plate on Post Face

```
   [Post SHS 76]
   |           |
   |  [face    |  ← 100×100×10 mm plate welded to post face (shop)
   |   plate]  |     4× Ø15 holes matching the bar end plate
   |           |
        ↕ 4× M12 bolts
   [bar OD34/42]
   [   end     ]  ← 100×100×10 mm plate welded to bar end (shop)
   [   plate   ]     4× Ø15 holes + Ø14 vent hole
```

Used for: **Pull-up Bar_High / Bar_Low · Snake Bar_Straight · Side_Grip**

### Type B — Through-bolt Through Rail Section (monkey bar)

```
   [Rail SHS 50]
   |           |
   ●           ●  ← drill through both walls Ø13
   |           |
   [M10 bolt + nut inside/outside]
   |
   [rung OD34]
   [end plate] ← Ø80×8 mm welded to rung end (if required)
```

Used for: **Monkey bar rungs** (however, the Rail Section approach is recommended instead — see §8)

### Type C — Base Plate (already in the design)

```
   [Post SHS]
   |       |
   [base plate] SHS76: 210×210×9 mm · SHS50: 180×180×9 mm
   ||||||||||||  ← 4× M12 anchor bolt into concrete floor
```

Used for: **All posts** (specified in spec.summary.md — not changed)

---

## 4. End Plate — Dimensions and Bolt Layout

### 4.1 Edge Distance Requirements (EN 1993-1-8 Table 3.3)

| Parameter | Minimum formula | Value used (M12) | Value used (M10) |
|---|---|---|---|
| Edge distance e₁ (plate end, along force direction) | ≥ 1.2 × d₀ | ≥15.6 mm → **use 25 mm** | ≥13.2 mm → **use 20 mm** |
| Edge distance e₂ (plate side, perpendicular to force) | ≥ 1.2 × d₀ | ≥15.6 mm → **use 25 mm** | ≥13.2 mm → **use 20 mm** |
| Bolt pitch p₁ (between bolts, along force direction) | ≥ 2.2 × d₀ | ≥28.6 mm → **use 50 mm** | ≥24.2 mm → **use 40 mm** |
| Bolt pitch p₂ (perpendicular to force direction) | ≥ 2.4 × d₀ | ≥31.2 mm → **use 50 mm** | ≥26.4 mm → **use 40 mm** |

> d₀ = hole diameter: M12 → d₀ = 13 mm (standard) or 15 mm (after HDG) · M10 → d₀ = 11 mm or 13 mm

### 4.2 Recommended Plate Sizes

| Section being connected | Plate type | Size (W×H×T) | Bolt pattern | Clearance from bolt edge to plate edge |
|---|---|---|---|---|
| SHS 76×76 — Bar end plate | End plate | **100 × 100 × 10 mm** | 4× M12 in 50×50 mm grid | 25 mm all sides |
| SHS 76×76 — Post face plate | Face plate | **100 × 100 × 10 mm** | Holes match end plate | 25 mm |
| SHS 50×50 — Rail section end | End plate | **80 × 80 × 8 mm** | 4× M10 in 40×40 mm grid | 20 mm all sides |
| OD 34 — Bar/rung end | End cap plate | **80 × 80 × 8 mm** | 2× M10 · pitch 40 mm | 20 mm |
| OD 42 — Dip/snake bar end | End cap plate | **90 × 90 × 10 mm** | 2× M12 · pitch 50 mm | 20 mm |

> **Note:** the 100×100 mm plate on SHS 76 projects (100−76)/2 = 12 mm beyond the post face on each side — acceptable, no effect on capacity

### 4.3 Bearing Check on SHS Wall (through-bolt case)

For M10 through-bolt passing through SHS 50×50×2.3 mm wall:

```
Fb,Rd = 2.5 × αb × fu × d × t / γM2
      = 2.5 × 0.61 × 360 MPa × 10 mm × 2.3 mm / 1.25
      = 10,062 N / 1.25
      = 8,050 N (8.1 kN) per bolt per wall layer

2 wall layers × 2 bolts = 4 × 8.1 = 32.4 kN >> 1.942 kN → Pass (margin 16×)
```

---

## 5. Bolts — Grade, Size, Quantity, and Capacity

### 5.1 Grade 8.8 HDG Selected

| Grade | f_ub (MPa) | Relative cost | Suitability |
|---|---|---|---|
| 4.6 | 400 | Low | Not recommended — low strength, requires more bolts |
| **8.8** | **800** | **Medium** | **Recommended** — standard structural grade · widely available in Thailand |
| 10.9 | 1,000 | Higher | More than needed |
| A2-70 (SS) | 700 | High | Excellent corrosion resistance but ~3–5× more expensive than HDG 8.8 |

> Use **Grade 8.8 Hot-Dip Galvanised (HDG)** throughout — consistent with the anchor bolt grade already specified

### 5.2 Bolt Capacity per Bolt (EN 1993-1-8, γM2 = 1.25)

| Size | As (mm²) | F_v,Rd (shear/bolt) | F_t,Rd (tension/bolt) |
|---|---|---|---|
| M10 G8.8 | 58.0 | **22.3 kN** | **33.4 kN** |
| M12 G8.8 | 84.3 | **32.4 kN** | **48.6 kN** |

### 5.3 Safety Margin vs. Design Load

| Connection point | Design load | Capacity (lowest mode) | Safety margin |
|---|---|---|---|
| 4× M12 — pull-up bar to post | 1,942 N | 4×32.4 kN = 129.6 kN | **67×** |
| 2× M10 — monkey rung to rail | 1,942 N | 2×22.3 kN = 44.6 kN | **23×** |
| 4× M10 — rail section to post | 1,942 N | 4×22.3 kN = 89.2 kN | **46×** |

> Loads are very small relative to bolt capacity — plate and bolt sizing is driven by geometric requirements (wrench access), not structural capacity

### 5.4 Washers

Use **flat HDG washers** at every connection (thickness ≥3 mm) to distribute load over the plate face and prevent bolt heads from pulling through thin plate.

---

## 6. HDG Galvanising — Vent Holes and Work Sequence

### 6.1 Why Vent Holes Are Critical

When HDG galvanising, the piece is immersed in a zinc bath at ~450°C. Air and flux trapped inside sealed hollow sections expands and converts to vapour. Without an escape path:
- The vapour pressure builds up → the piece **explodes / is ejected from the bath (life-threatening hazard)**
- In some cases: uneven coating inside → rust starts from the inside

### 6.2 Minimum Vent Hole Size

Hole area ≥25% of the internal cross-sectional area (GAA / ASTM A385):

| Section | Internal area | 25% | Hole Ø (round) | Recommendation |
|---|---|---|---|---|
| SHS 76×76×3.2 | 69.6² = 4,844 mm² | 1,211 mm² | Ø39.3 → **Ø40 mm** | Drill 1 hole in base plate near the wall |
| SHS 50×50×2.3 | 45.4² = 2,061 mm² | 515 mm² | Ø25.6 → **Ø26 mm** (use **Ø28 mm**) | Drill 1 hole in base plate or end cap |
| OD 34×3.2 | π×13.8² = 598 mm² | 150 mm² | Ø13.8 → **Ø14 mm** | Drill 1 hole in end plate |
| OD 42×3.2 | π×17.8² = 995 mm² | 249 mm² | Ø17.8 → **Ø18 mm** | Drill 1 hole in end plate |

> **Hole position:** do not drill at the centre of the plate — drill offset toward the tube inner wall, at least 10 mm from the weld line in every case (allows flux to escape and prevents it from pooling between the wall and the hole)

### 6.3 Work Sequence

```
[Cutting/bending shop]
  1. Cut SHS/tube to length
  2. Drill bolt holes Ø15 mm (M12) or Ø13 mm (M10)
  3. Drill vent holes per table §6.2

[Welding — shop]
  4. Weld end plate to bar/rung ends (small sub-assembly)
  5. Weld face plate to post face (at bar connection point)
  6. Weld base plate to post bottom
  7. Inspect all welds (must be continuous and full perimeter — no gaps)
  8. Clean, chip flux and spatter

[HDG galvanising plant]
  9. Galvanise HDG each sub-assembly separately (do not assemble before galvanising)
 10. Inspect coating after galvanising (minimum 85 µm per EN ISO 1461)

[Site]
 11. Fix anchor bolts + post base plates into concrete
 12. Assemble: align post face plate ↔ bar end plate so holes match
 13. Insert bolts + washers at all holes, hand-tight (snug-tight) first
 14. Torque with calibrated torque wrench per §7
 15. Apply cold zinc spray over any cut or welded areas done on site (if any)
```

### 6.4 Bolt Holes After Galvanising

HDG adds approximately 50–85 µm coating per surface → holes drilled at Ø15 mm (for M12) and Ø13 mm (for M10) before galvanising will still accept the bolts without re-tapping:

| Bolt | Drilled before galvanising | After galvanising (loses ~0.2 mm radius) | Bolt shank diameter (with coating) | Remaining clearance |
|---|---|---|---|---|
| M12 | Ø15 mm | ≈ Ø14.6 mm | 12.7 mm | ~0.95 mm/side |
| M10 | Ø13 mm | ≈ Ø12.6 mm | 10.6 mm | ~1.0 mm/side |

> If a bolt does not pass through: use a Ø15.5 mm drill bit to ream lightly, or clean with a wire brush (no need to re-tap — the holes are clearance holes, not threaded)

---

## 7. Torque

### 7.1 Recommended Torque Values

HDG increases the K-factor (thread friction coefficient) from 0.20 (bare steel) to ~0.25 (HDG) → the required torque increases by ~25%:

| Bolt | Grade | Condition | Target torque |
|---|---|---|---|
| M10 | 8.8 | HDG (no lubricant) | **52–65 N·m** |
| M12 | 8.8 | HDG (no lubricant) | **100–115 N·m** |
| M12 | 8.8 | HDG + anti-seize compound | ~85–91 N·m |

> To reduce torque and simplify future disassembly: apply **anti-seize compound** to the nut thread before torquing → K-factor returns close to 0.20 → torque requirement ≈ bare steel value

### 7.2 Tightening Procedure

1. Insert all bolts at the connection, hand-tight until snug
2. Tighten in a crisscross (star) pattern in two passes: 50% torque → 100% torque
3. Verify: use a tension-indicator bolt head or draw a straight line across the bolt and nut to check for rotation

---

## 8. Recommendations by Piece

### 8.1 PIECE 1 — Pull-up Bar

Sub-assemblies:
- **Post_Left / Right / Child** (each post separately): post + base plate + **2 face plates** (at z=2.20 m and z=1.50 m)
- **Bar_High** (adult bar): OD34×1.50 m tube + **2 end plates** at both ends
- **Bar_Low** (child bar): OD34×1.00 m tube + **2 end plates** at both ends

Face plates on post (at z=2.20 m and z=1.50 m):
- Size **100×100×10 mm**, welded flush with the SHS 76 post face on the side the bar connects to
- 4× Ø15 mm holes in a 50×50 mm centred grid
- Fillet weld around the plate perimeter to the SHS face (throat ≥5 mm)

End plates on bar:
- Size **100×100×10 mm**, welded perpendicular to OD34 tube axis at each bar end
- 4× Ø15 mm holes in a 50×50 mm grid (matching the post face plate)
- Vent hole **Ø14 mm** off-centre, close to the tube wall

Bolts: **4× M12 × 40 mm G8.8 HDG** per end (total 8 bolts/bar)

### 8.2 PIECE 2 — Snake Bar

Sub-assemblies:
- **Post_L / R**: post + base plate + face plate for Bar_Straight (at z=1.962 m)
- **Bar_Straight** (OD42×2.00 m): + **2 end plates 90×90×10 mm**
- **Bar_Wave** (OD34): welded along the full length of Bar_Straight → galvanised as a single unit with Bar_Straight (no separate plate needed)
- **Side_Grip** (8 pieces, OD34): each piece + **2 end plates 80×80×8 mm** welded at both ends

> Side_Grip has 2 weld points per piece (top and bottom) on the Post_L or R face — each post needs 4 face plates/post (= 8 face plates for both posts), each 80×80×8 mm with 2×M10

### 8.3 PIECE 3 — Dip Bar

DipBar frame (⊓ shape): OD42 tube bent into a U → 2 ground-anchored legs

Sub-assemblies: **Each DipBar_01/02/03 frame is one sub-assembly**, galvanised HDG as a complete frame (piece is not large — ~120×75 cm)

The legs already have base plates per the original design (120×120×6 mm base plate · 2× M10/leg) → **no change**

Nub C-grip handle: welded into the DipBar frame before galvanising — part of the same sub-assembly → **no separate plate required**

### 8.4 PIECE 4 — Monkey + Flying Bar (Special Case)

**Problem:** 35 rungs OD34 each 1.0 m long — making a plate per rung = 70 end plates + 140 bolts → complex and expensive

**Recommended approach: Rail Section method**

Divide the rail into sections by post spacing (1 m/section) → weld rungs into a rail section in the shop → HDG galvanise the whole section → bolt sections to posts on site:

```
Example section (Zone 1):
  [Rail_Z1_L] SHS 50×50 × 1.0 m long
  ├── rung ①  OD34 × 1.0 m  welded at y=0.00
  ├── rung ②  OD34 × 1.0 m  welded at y=0.20
  ├── rung ③  OD34 × 1.0 m  welded at y=0.40
  ├── rung ④  OD34 × 1.0 m  welded at y=0.60
  └── rung ⑤  OD34 × 1.0 m  welded at y=0.80
  → HDG galvanise the whole section → bolt end plate to post
```

End plate at rail section ends: **80×80×8 mm** · 4× M10 G8.8 · 40×40 mm grid

Post face plate (on SHS 50 post face receiving the rail): **80×80×8 mm** · matching holes

Vent hole for rail section SHS 50: drill **Ø28 mm** at both end plates (off-centre, near the wall)

**Total rail sections for the complete monkey bar:**

| Zone | Rail L | Rail R | Rungs per section |
|---|---|---|---|
| Zone 0 (y=−1→0) | 1 | 1 | — (round tube) |
| Zone 1 (y=0→1) | 1 | 1 | 5 rungs/section |
| Zone 2 (y=1→2, 45° incline) | 1 | 1 | ~25 cm spacing along slope |
| Zone 3 (y=2→3) | 1 | 1 | 5 rungs/section |
| Zone 4 (y=3→4, 35° incline) | 1 | 1 | ~25 cm spacing along slope |

Total ~10 rail sections + triangle brace → galvanise 10 pieces instead of 35 individual pieces

---

## 9. Structural Changes Required

| Item | Change? | Details |
|---|---|---|
| SHS 76×76×3.2 size | No change | More than adequate — margin ≥20× |
| SHS 50×50×2.3/2.8 size | No change | — |
| OD34/OD42 tube size | No change | — |
| Base plate + anchor bolt | No change | Use as per original design (210×210×9, M12) |
| **Face plates added to post face** | **Add** | 100×100×10 mm welded at post face at each bar connection point |
| **End plates added to bar ends** | **Add** | Sizes per §4.2 |
| **Vent holes in all base plates** | **Add** | SHS76: Ø40 mm · SHS50: Ø28 mm (bolt holes exist but are insufficient) |
| **Vent holes in bar end plates** | **Add** | OD34: Ø14 mm · OD42: Ø18 mm |
| Post/bar cut lengths | Check | Each end plate adds +10 mm total per connection — typically no practical effect, but should be noted on the drawing |
| Triangle brace (Monkey Zone 4) | No change | Must remain per original design |

---

## 10. Items to Confirm with the Engineer

1. **Weld throat at face plate → post:** Is a 5 mm fillet weld all around the 100×100 plate sufficient, or is full penetration required?
2. **Plate thickness in detailed prying check:** Is 10 mm sufficient or is 12 mm required? (Preliminary estimate is adequate but the T-stub has not yet been formally calculated)
3. **Bearing on SHS wall (through-bolt monkey):** Wall at 2.3 mm passes per estimate in §4.3 — should be confirmed by the engineer
4. **SHS50 rail section end plate:** 4× M10 in a 40×40 mm grid may be tighter than standard (e₂ ≈ 20 mm, close to minimum) — consider using a 90×90 mm plate instead
5. **On-site assembly sequence:** Should posts be erected before or after bars? End plates may block access to some connection points depending on assembly order
6. **Vent hole in SHS76 base plate:** Ø40 mm is a large hole — verify that it does not reduce plate capacity (for a 210×210×9 mm plate it should not, but confirmation is recommended)

---

## 11. References

- Steel Tube Institute (AISC): [HSS Bolted End-Plate Connections Under Bending Moment](https://steeltubeinstitute.org/resources/rectangular-hss-bolted-end-plate-connections-under-bending-moment/)
- Steel Tube Institute: [Round HSS Bolted End-Plate Connections Under Axial Tension](https://steeltubeinstitute.org/resources/round-hss-bolted-end-plate-connections-under-axial-tension-loading/)
- University of Sydney Research: [Design Model for Bolted Moment End Plate Connections using SHS](https://ses.library.usyd.edu.au/bitstream/handle/2123/23914/r827.pdf)
- Structure Magazine: [Structural Connections for Hot-Dip Galvanizing](https://www.structuremag.org/article/structural-connections-for-hot-dip-galvanizing/)
- American Galvanizers Association: [Sizing Clearance Holes for HDG Fasteners](https://galvanizeit.org/knowledgebase/article/sizing-clearance-holes-for-hdg-fasteners)
- AGA: [Venting & Drainage — Hollow Structural Sections](https://galvanizeit.org/design-and-fabrication/fabrication-considerations/venting-and-drainage1)
- GAA (Australia): [Venting & Draining Guide](https://gaa.com.au/venting-draining-guide/)
- GAA/GANZ: [Best Practice Guide for HDG Bolts & Bolted Joints (2025)](https://www.galvanizing.org.nz/docs/GAA_GANZ_Guide_for_HDG_Bolts&Bolted_Joints.pdf)
- AIMS Industrial: [Metric Bolt Torque Chart G4.6–12.9](https://aimsindustrial.com.au/blogs/product-guides/metric-bolt-torque-chart)
- EN 1993-1-8:2005 (Eurocode 3, Part 1-8): Design of joints — §6.2.4 T-stub equivalent
- EN ISO 1461:2009: Hot dip galvanized coatings on fabricated iron and steel articles
- ASTM A780: Standard Practice for Repair of Damaged and Uncoated Areas of Hot-Dip Galvanized Coatings
