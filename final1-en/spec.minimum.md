# Material Floor — Outdoor Calisthenics Gym

## Material Minimum Worksheet · Working Tool — Internal calculation aid, NOT a construction specification

| Item | Details |
|---|---|
| Document Status | **Internal working tool** — not a specification, and not for certification |
| Last Updated | 17 June 2026 |
| Calculated from | [Design Specification (2/4)](spec.full.md) + [Load Analysis (3/4)](spec.requirement.md) revised 14 June 2026 |
| Prepared By | Functional Design Researcher (not a licensed engineer) |
| Design load standard | EN 16630:2015 Table 1 (1,942 N/station incl. dynamics) — same basis as documents 3/4 and 4/4 |
| Related Documents | [Master Index (TOC)](toc.md) · [Gallery (1/4)](design/design.gallery.md) · [Design (2/4)](spec.full.md) · [Load Analysis (3/4)](spec.requirement.md) · [Verification + Foundation (4/4)](spec.summary.md) · [Scope & Liability](policy.liability.md) |

---

> # IMPORTANT WARNING — Read Before Every Use
>
> **This document does not certify fitness for real use under any circumstances.** Every "minimum" value in this file is the point at which the material **just yields under the design load** — it is the **"guaranteed failure below this line"** threshold, NOT the **"this is enough to use safely"** threshold.
>
> - Primary minimum value = util 1.0 (σ = fy = 235 MPa) → **safety margin remaining = 0 (zero)**
> - **Not included:** fatigue from repeated loading, weld quality, lateral buckling, wind loads, corrosion allowance, site tolerances — these factors mean real equipment can fail even when the material passes this minimum threshold
> - **Single purpose:** use as a _screening filter_ when selecting material at the steel supplier — if the shop's stock is **smaller** than the minimum → reject immediately (no need to evaluate further) · if **equal to or larger than** the minimum → it is merely a _candidate that has not been eliminated_; send to the certifying party (Party C) for review and confirmation
> - **The construction specification is [spec.full.md](spec.full.md) only** (wall 3.2mm, which maintains safety margin above yield) — this file is not a substitute, and **must NOT be used to build, order materials independently, or cite as a requirement**
> - **Recalculate the entire file every time actual materials change** (steel grade fy, OD/section, span length, or design load changed) — every value is tied to the assumptions in §2. If assumptions change, all values are void.

---

## 1. What This File Is / Is Not

| This file **IS** | This file **IS NOT** |
|---|---|
| A tool to check whether "shop stock is too small to reject immediately" | A construction specification |
| A theoretical floor: how far can material be reduced before yield | A certification that "above this line is safe / 100% usable" |
| A tool to show "how much safety margin the full spec (3.2mm) has over the minimum" | A signed engineer's structural calculation |
| Numbers tied to a fixed set of assumptions (§2) | Values that are permanently valid without recalculating |

**Decision rule:**

> For each member, compare the **section modulus (Z) of the shop's stock** with the **Z_min** value in the table:
>
> - `Z(shop stock) < Z_min` → **Reject immediately** (real piece will yield under the design load)
> - `Z(shop stock) ≥ Z_min` → **Not eliminated** — keep as a candidate; send to Party C for review and certification. **Do NOT treat as automatically passing.**
> - Also compare against the **"maintain margin (0.6 fy)" minimum** column: if the shop's stock reaches this line = it has safety margin close to the original design spec (much more reassuring) · if it falls between the two lines = structurally adequate in strength but margin is reduced; the certifying party must decide

---

## 2. Calculation Method and Assumptions (The Basis of All Numbers — Recalculate Everything if Changed)

### 2.1 Fixed Assumptions

- **Design load P = 1,942 N** per user station (EN 16630 Table 1 including C_dyn = 2.0) — same as documents 3/4 and 4/4
- **Steel fy = 235 MPa** (standard galvanised hollow section, conservative value)
- Grip tubes/rungs welded at both ends = **fixed-end** condition (mid-span moment = P×L/8) · cantilever members = **cantilever** condition (root moment = P×a)
- Grip tube **OD held constant** (34mm / 42mm) per EN 16630 grip principle (16–45mm) — only **wall thickness** may be reduced, never OD
- Self-weight ignored (1,942 N live load dominates at short spans) — slightly conservative simplification

### 2.2 Moment Demand (M) — Independent of Material: Fixed Values

Moment depends only on _load × geometry_. Changing wall/grade changes the strength, not the demand — this is why the minimum can be found directly.

| Member | Formula | M demand (kN·m) |
|---|---|---:|
| Pull-up Bar_High (L=1.5m) | P×L/8 | 0.364 |
| Pull-up Bar_Low (L=1.0m) | P×L/8 | 0.243 |
| Monkey rungs / Rail_Z0 (L=1.0m) | P×L/8 | 0.243 |
| Snake Bar_Straight (L=2.0m) | P×L/8 | 0.486 |
| Snake Side_Grip (cantilever 0.25m) | P×a | 0.486 |
| Dip top beam (L=0.62m) | P×L/8 | 0.150 |
| Dip nub (cantilever 0.25m) | P×a | 0.486 |
| Pull-up / snake posts (lateral 0.5P at h=2.2m) | 0.5P×h | 2.13 |
| Monkey tall post — with brace | (document 3/4 §5.3) | 0.65 |
| Monkey tall post — without brace | (document 3/4 §5.3) | 1.62 |

### 2.3 Formulas for "Minimum"

1. **Minimum section modulus:**
   - Yield line (primary): `Z_min = M / fy = M / 235`
   - Maintain margin line (reference): `Z_min(0.6fy) = M / (0.6×fy) = M / 141`
     _(M in N·mm, Z_min in mm³)_
2. **Section modulus of candidate section:**
   - Round tube: `Z = (π/32) × (D⁴ − (D−2t)⁴) / D`
   - SHS box: `Z = (B⁴ − (B−2t)⁴) / (6B)`
3. **Find minimum wall t (when OD/B is fixed):**
   `t ≥ (D − ⁴√(D⁴ − 10.186×Z_min×D)) / 2` (10.186 = 32/π)
   Then **round up** to find the nearest standard stock size (common wall stock: 1.5 / 2.0 / 2.3 / 2.5 / 2.8 / 3.0 / 3.2 / 3.5 / 4.0mm)

### 2.4 Utilisation Scale (= σ/fy)

util ≤ 0.6 = design spec with safety margin · 0.6–1.0 = not yet yield but margin decreasing · **= 1.0 = just at yield (this file's primary minimum line)** · > 1.0 = yields/fails

---

## 3. Minimums by Piece

> Reading the tables: **"Minimum (yield)"** = reject threshold — smaller than this guarantees failure · **"Minimum maintain margin (0.6 fy)"** = still has safety margin close to original design spec · **"Actual spec"** = the value to use for real construction (from spec.full.md)

### 3.1 PIECE 1 — Pull-up Bar (OD 34 round tube held constant · wall only)

| Member | M (kN·m) | Z_min yield (mm³) | Min wall (yield) | Z_min maintain margin (mm³) | Min wall maintain margin | **Actual spec** |
|---|---:|---:|---|---:|---|---|
| Bar_High (L=1.5m) | 0.364 | 1,549 | **~2.05mm → round up 2.3** | 2,582 | **~4.1mm** | OD34 × **3.2** |
| Bar_Low (L=1.0m) | 0.243 | 1,034 | **~1.27mm → round up 1.5** | 1,723 | ~2.4mm | OD34 × **3.2** |

- **Bar_High is the critical member in this piece:** actual spec 3.2mm (util 0.71) falls _between_ the yield line (2.05mm) and the maintain-margin line (4.1mm) — meaning if shop stock < 2.3mm, reject immediately; but for a comfortable margin the target wall should be ~4mm (consistent with spec.full.md recommendation to increase to 4.0–5.0mm)
- SHS 76 posts for pull-up: see §3.5 (shared with snake posts)

### 3.2 PIECE 2 — Snake Bar

| Member | Section | M (kN·m) | Z_min yield (mm³) | Min (yield) | Min maintain margin | **Actual spec** |
|---|---|---:|---:|---|---|---|
| Bar_Straight (structural, L=2.0m) | OD 42 | 0.486 | 2,068 | wall **~1.69 → round up 2.0** | ~3.1mm | OD42 × **3.2** |
| Bar_Wave (grip) | OD 34 | \* | \* | wall **~1.5** (see note) | — | OD34 × 3.2 |
| Side_Grip (250mm cantilever) | OD 34 | 0.486 | 2,068 | wall **~2.97 → round up 3.0** | not achievable (see below) | OD34 × **3.2** |

- **Bar_Straight + Bar_Wave** in the actual design are welded together as a composite section (much stronger than a single tube) — the minimum above treats Bar_Straight as a **single tube** (conservative) · `*`Bar_Wave carries grip loads at individual contact points with the structural bar; its own moment is low; minimum wall for strength ≈ the rung level (~1.5mm), but in practice it relies on Bar_Straight as the primary load carrier
- **Side_Grip has almost no room to reduce:** actual spec util = 0.95 (already near yield) → yield line = wall ~3.0mm, close to actual spec 3.2mm · The **maintain-margin line (0.6 fy) is physically impossible for OD 34** at 250mm cantilever (would require Z of 3,447 mm³ ≈ a solid rod) → the correct approach for this member is "keep the thickest available wall, or reduce the cantilever length" — not a place to find material savings

### 3.3 PIECE 3 — Dip Bar (OD 42 round tube held constant)

| Member | M (kN·m) | Z_min yield (mm³) | Min (yield) | **Actual spec** |
|---|---:|---:|---|---|
| Top beam (L=0.62m) | 0.150 | 638 | wall **~0.48mm** (almost no bending demand) | OD42 × **3.2** |
| Nub C-handle (250mm cantilever) | 0.486 | 2,068 | wall **~1.69 → round up 2.0** | OD42 × **3.2** |
| Vertical legs (axial ~2 kN, 1.2m tall) | — | — | governed by **buckling, not yield** (see note) | OD42 × **3.2** |

- **Top beam:** short 0.62m span means extremely low moment → theoretical yield wall < 0.5mm, which **has no practical meaning**: actual minimum wall is governed by _factors other than bending_ (outdoor corrosion allowance, localised denting, welding) → never reduce below ~1.5–2.0mm even though the bending calculation would allow it
- **Vertical legs:** carry axial compression ~2 kN; Euler buckling capacity of OD 42 at 1.2m tall is many times the load → structurally much could be reduced, but again governed by durability/welding, not this file's scope; maintain section per spec

### 3.4 PIECE 4 — Monkey + Flying Bar

**Rungs (OD 34 held constant):**

| Member | M (kN·m) | Z_min yield (mm³) | Min (yield) | **Actual spec** |
|---|---:|---:|---|---|
| Rungs Z1–Z4 / Rail_Z0 (L=1.0m) | 0.243 | 1,034 | wall **~1.27 → round up 1.5** | OD34 × **3.2** |

**Posts (SHS 50 — section and wall may potentially vary, subject to brace conditions):**

| Post | M (kN·m) | Z_min yield (mm³) | Minimum section (yield) | **Actual spec** |
|---|---:|---:|---|---|
| Short posts Zone 0–2 (h=1.0m) | 0.97 | 4,128 | ~ **SHS 40×40×2.3** (Z≈4,123, util≈1.0) | SHS 50×50×**2.3** |
| Tall posts — **with triangle brace** | 0.65 | 2,766 | ~ **SHS 40×40×2.0** (Z≈3,668, util 0.75) | SHS 50×50×**2.8** |
| Tall posts — **without brace** | 1.62 | 6,894 | ~ SHS 50×50×2.8 (Z 7,879) — **no room to reduce** | SHS 50×50×**2.8** |

- **The triangle brace changes everything:** with brace → tall post theoretically reducible to SHS 40×2.0 · without brace → tall post requires ~SHS 50×2.8 in full (actual spec, no room to reduce) — **confirms that the triangle brace (Post_y3 + Tri_Horiz + Rail_Z4) must not be removed**, consistent with spec.full §5 and document 3/4 §5.3
- Structural rails (Rail_Z1–Z4, Tri_Horiz) are SHS 50 — carry loads continuously into posts; maintain per specification; not a place for material reduction

### 3.5 SHS 76 Posts (pull-up ×3 + snake ×2)

| Member | Base M (kN·m) | Z_min yield (mm³) | Minimum section (yield) | **Actual spec** |
|---|---:|---:|---|---|
| Pull-up / snake posts | 2.13 | 9,064 | ~ **SHS 50×50×4.0** (Z 10,461, util 0.87) — SHS 50×3.2 fails (Z 8,788, util 1.03) | SHS 76×76×**3.2** |

- This figure is calculated **for base bending only**. Real posts carry _axial compression + bending + lateral buckling (slenderness) + base anchor moment_ simultaneously — reducing from SHS 76 to SHS 50 would change slenderness and base/anchor moment entirely. **Never use this yield line alone to decide to downsize the post.** Maintain SHS 76 per specification unless the certifying party calculates all load modes.

---

### 3.6 SHS Posts — Maximum Wall Reduction if OD/SHS Is Held Constant

> **Context:** thicker walls are harder to find from general stock — the thicker required, the harder to source. The goal is to know "if I keep the same SHS size (cannot shrink OD/B), what is the lowest wall before the yield line" — useful for deciding at the steel shop.
>
> **Same limitation as above:** these numbers cover only **base bending (bending demand)** alone. Real posts carry combined modes (compression + bending + buckling + base anchors). Values are a **theoretical ceiling** — do not reduce without certifying party approval.

#### Formula Used (SHS Box Section)

`Z = (B⁴ − (B−2t)⁴) / (6B)`

Find minimum t: `(B−2t)⁴ ≥ B⁴ − 6B×Z_min` → `t_min = (B − ⁴√(B⁴ − 6B×Z_min)) / 2`

Then round up to nearest stock size (common SHS wall stock: 1.5 / 2.0 / 2.3 / 2.5 / 2.8 / 3.0 / 3.2 / 3.5 / 4.0mm)

#### SHS 76 Posts (pull-up ×3 + snake ×2)

| Item | M (kN·m) | Z_min yield (mm³) | Z of SHS 76 × various walls | Min wall (yield) | **Actual spec** | Actual util |
|---|---:|---:|---|---|---|---:|
| Pull-up / snake posts | 2.13 | 9,064 | 76×1.5 → Z≈10,887 ✓ · 76×1.4 → Z≈10,205 ✓ · below 1.4 → Z < 9,064 ✗ | **1.5mm** (rounded up from ~1.4mm) | SHS 76×**3.2** | 0.42 |

- **SHS 76 keeping same section, bending only:** wall can theoretically be reduced to **1.5mm** (the lowest stock still above yield) — a very large reduction from 3.2mm because SHS 76's large section provides substantial bending reserve
- **But never reduce in practice:** SHS 76 posts carry axial load + buckling + base moment simultaneously; thin wall causes the plate walls to buckle locally and increases slenderness (L/r), significantly reducing the buckling load capacity. The 1.5mm value is a **reject-threshold only for the case where a supplier offers SHS 76 with wall < 1.5mm** (rare in practice)

#### SHS 50 Posts (Monkey bar)

| Case | M (kN·m) | Z_min yield (mm³) | Z of SHS 50 × various walls | Min wall (yield) | **Actual spec** | Actual util |
|---|---:|---:|---|---|---|---:|
| Short posts Zone 0–2 (h=1.0m) | 0.97 | 4,128 | 50×1.5 → Z≈4,568 ✓ · 50×1.2 → Z≈3,701 ✗ | **1.5mm** (rounded up from ~1.3mm) | SHS 50×**2.3** | ~0.62 |
| Tall posts — **with brace** | 0.65 | 2,766 | 50×1.0 → Z≈2,867 ✓ · 50×0.8 → Z≈2,540 ✗ | **1.0mm\*** (rounded up from ~0.85mm) | SHS 50×**2.8** | 0.35 |
| Tall posts — **without brace** | 1.62 | 6,894 | 50×2.5 → Z≈7,164 ✓ · 50×2.3 → Z≈6,653 ✗ | **2.5mm** (rounded up from ~2.4mm) | SHS 50×**2.8** | 0.87 |

_\* 1.0mm is a mathematical value only — in practice, SHS 50 wall < 1.5mm is almost unavailable in Thai stock and too thin for outdoor use (corrosion/denting). Treat 1.5mm as the practical minimum for this case._

#### Summary Table — Post Stock Availability

| Post | Actual spec (wall) | Min wall for bending | Stock "not yet eliminated" | Risk |
|---|---|---|---|---|
| SHS 76 (pull-up/snake) | 3.2mm | 1.5mm | 1.5 / 2.0 / 2.3 / 2.5 / 2.8 / 3.0 / 3.2mm | **Never reduce without buckling check** — bending calc shows large margin because SHS 76 is big, but 2.2m-tall post has real buckling risk with thin wall |
| SHS 50 short posts | 2.3mm | 1.5mm | 1.5 / 2.0 / 2.3mm | Minimum practically available = 1.5mm · passes bending; Party C should confirm |
| SHS 50 tall posts (with brace) | 2.8mm | 1.5mm\* | 1.5 / 2.0 / 2.3 / 2.5 / 2.8mm | **Depends on triangle brace being complete** — without brace, minimum jumps to 2.5mm immediately |
| SHS 50 tall posts (without brace) | 2.8mm | 2.5mm | 2.5 / 2.8 / 3.0 / 3.2mm | Very little margin · **brace must always be present** |

> **Short summary:** SHS 76 in bending-only analysis can theoretically be reduced a lot, but must not be reduced in practice due to buckling · SHS 50 short posts and tall posts (with brace) practical minimum is **1.5mm** · SHS 50 tall posts **without brace** must not go below **2.5mm**, and the brace must be present

---

## 4. Items "Must Not Be Reduced Using This File" — Governed by Other Factors

This file calculates **bending (yield)** only. The members below have other critical failure modes not covered by this file → **maintain per actual spec (spec.full / spec.summary); do not use yield minimum line to justify reducing these.**

| Item | Governed by (not bending) | Maintain per |
|---|---|---|
| M12×120 anchor bolts | Pull-out / concrete cone capacity C20/25 + ETA certificate | spec.summary §4 (12.3 kN/bolt) |
| 9mm base plates / end plates | Shop stock 9mm + T-stub model + wrench clearance | spec.full §7 / spec.summary §4 |
| All welds | Welder skill + fatigue | Full-perimeter fillet, throat ≥ 5mm |
| Triangle brace Zone 4 | Structural stability / slenderness of tall post | Must not be removed |
| Dip legs / compression posts | Lateral buckling (Euler) | Maintain section per spec |
| Rubber floor thickness under Monkey/Pull-up | Critical Fall Height | 40–50mm |

> Reason not to reduce bolts/plates/rubber: these items are a small fraction of project cost but are **safety-critical components — if they fail, the consequences are severe** — not worth "screening" for alternatives

---

## 5. Summary — "How Far Can It Be Reduced" (vs Actual Spec 3.2mm)

This table is the main purpose of the file: see at a glance how much margin the full spec has above the minimum at each point (the lower the actual spec util, the more room to reduce theoretically) — sorted from most reducible to least:

| Member | Actual spec | Min (yield) | Actual spec util | Reducible (bending strength)¹ |
|---|---|---|---:|---|
| Dip top beam OD42 | 3.2mm | ~0.5mm² | 0.18 | Most (almost no bending demand²) |
| Monkey rungs / Bar_Low OD34 | 3.2mm | 1.5mm | 0.47 | ~47% of section remaining |
| Posts SHS 76 | 76×3.2 | ~SHS50×4.0³ | 0.42 | ~42%³ |
| Snake Bar_Straight OD42 | 3.2mm | 2.0mm | 0.59 | ~59% remaining |
| Dip nub OD42 | 3.2mm | 2.0mm | 0.59 | ~59% remaining |
| Pull-up Bar_High OD34 | 3.2mm | 2.3mm | 0.71 | ~71% remaining (already thin) |
| Monkey tall posts (with brace) | SHS50×2.8 | ~SHS40×2.0³ | 0.35 | ~35%³ |
| Snake Side_Grip OD34 | 3.2mm | 3.0mm | 0.95 | **Almost no room to reduce** |
| Monkey tall posts (without brace) | SHS50×2.8 | ~SHS50×2.8 | 0.87 | **Cannot reduce** (must have brace) |

¹ "Reducible" = proportion of section modulus used at minimum ≈ actual spec util (because Z_min = util × Z_spec) — **theoretical ceiling where margin = 0 only, NOT a recommendation to actually reduce**
² Very low bending demand but **never reduce below ~1.5–2.0mm** because governed by corrosion/denting/welding (§3.3)
³ Posts are indicative for base bending only — **do not use to downsize posts unilaterally** — combined buckling/anchor modes apply (§3.5)

---

## 6. When Actual Materials Change — How to Recalculate

1. Update **§2.1 assumptions** that have changed (e.g. fy of new steel grade, new OD, new span, new load P)
2. If geometry/load changes → recalculate **new moment demand M** (table 2.2) · if only material changes → existing M values are still valid
3. Recalculate `Z_min = M/fy` and `Z_min(0.6fy) = M/141` (§2.3)
4. Insert shop stock section/wall into the Z formula and compare against Z_min per **decision rule (§1)**
5. Update the document date in the header and note what was changed
6. **Recommend sending results to Party C for review and certification before ordering or building** — this file is not a substitute for certification

---

> **Closing note:** All figures in this file are preliminary assessments (first-order, bending vs. yield only) prepared as a convenience for screening shop stock only. **They are not a certified structural calculation and do not certify fitness for real use.** For actual construction, [spec.full.md](spec.full.md) is the governing document. The preparer strongly recommends that all values be reviewed, verified, and signed off by a licensed engineer per [policy.liability.md](policy.liability.md).
