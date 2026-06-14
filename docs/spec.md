# Calisthenic Equipment — Blender Model Spec

> **Blender unit = 1 metre.** All dimensions in metres unless noted.
> World origin: ground level at (0, 0, 0). +Z = up, +Y = forward/depth, +X = right.
> All pieces use `save_as_mainfile` — open each `.blend` directly to see objects in viewport.

---

## File Structure

| File                                  | Collection        | Description                                   |
| ------------------------------------- | ----------------- | --------------------------------------------- |
| `pullup_bar_v1.blend` (…`_v2`)        | `PullUpBar`       | 2 SHS posts + 1 round bar (v2 adds child low bar) |
| `snake_bar_v1.blend` (…`_v5`)         | `SnakeBar`        | 2 SHS posts + straight + NURBS wave bar (v2–v5 add side bars) |
| `dip_bar_v1.blend`                    | `DipBar`          | 3 portal-frame pieces (NURBS, round profile)  |
| `monkey_flying_bar_v1.blend` (…`_v3`) | `MonkeyFlyingBar` | 4-zone monkey bar + flying bar + ladder       |
| `floor_v1.blend`                      | `Floor`           | 6×5m rubber platform + concrete edge          |
| `main_scene.blend`                    | —                 | Links the 5 collections as instances          |

All `.blend` files use `bpy.data.libraries.load(fp, link=True)` in main_scene.
To update a piece: edit its own `.blend` → save → open `main_scene.blend` → `File > External Data > Reload Linked`.

### Design variants (versions)

**Every piece file uses the `_v{n}` naming** — there are no unsuffixed "origin" files (they were deleted;
`v1` *is* the baseline). `main_scene.blend` links the **`_v1`** of each piece. To preview another version,
re-point that library (`library.filepath = "//<piece>_v{n}.blend"` then `library.reload()`) — the instance
empty keeps its position, so the layout is preserved.

| Piece               | Versions                              |
| ------------------- | ------------------------------------- |
| `monkey_flying_bar` | `_v1` / `_v2` / `_v3`                 |
| `snake_bar`         | `_v1` / `_v2` / `_v3` / `_v4` / `_v5` |
| `pullup_bar`        | `_v1` / `_v2`                         |
| `dip_bar`           | `_v1` only _(3 variants pending)_     |
| `floor`             | `_v1` only                            |

See the per-piece **Versions** subsections below for what each differs.

---

## Global Conventions

### Materials / Bevel

**Colour scheme — blue / white (minimal · modern · matte powder-coat look).**
Each piece file defines its own copies of these materials (same names/values) so they
read identically once linked into `main_scene`. All Principled BSDF, `metallic=0`,
base colours given as sRGB 0–255 (convert to linear when setting `default_value`).

| Material          | Used on                                                       | sRGB          | Roughness | Notes                              |
| ----------------- | ------------------------------------------------------------- | ------------- | --------- | ---------------------------------- |
| `Steel_Blue`      | all structure: posts, rails, braces, ladder rails, dip frame  | (40,125,195)  | 0.50      | matte azure powder-coat            |
| `Grip_White`      | all grip: pull-up/snake bars, monkey + ladder rungs           | (238,241,244) | 0.82      | matte; subtle Noise→Bump (≈0.15) for non-slip grip |
| `Floor_Concrete`  | `Floor_Main`                                                  | (205,207,210) | 0.90      | light concrete slab                |
| `Zone_EPDM_Blue`  | `Equipment_Zone_4x3`                                          | (150,196,226) | 0.85      | soft-blue EPDM rubber safety zone  |
| `Marker_White`    | `Frame_N/S/E/W`                                              | (244,247,249) | 0.70      | zone boundary strips               |

> Render note: use **Standard** view transform (AgX over-desaturates the blues/whites).
> The dip frame is a single bent tube → one colour (`Steel_Blue`); can switch to white or
> two-tone if a split look is wanted.

- SHS posts use **Bevel modifier**: `bev.width = BEVEL_W`, `bev.segments = 3` for rounded edges.
- `BEVEL_W = 0.004` (4mm) for monkey bar elements; `0.008` (8mm) for 100mm pullup/snake bar posts.

### Joint Extension (monkey bar only)

All SHS bars in `monkey_flying_bar.blend` use `ext1` / `ext2` parameters:

```python
p1_extended = p1 - direction * ext1
p2_extended = p2 + direction * ext2
```

`EXT = POST_SHS = 0.025m` — bars extend 25mm past nominal endpoints so they overlap at joints, eliminating visible gaps. **Do not remove this extension** or gaps will reappear at perpendicular junctions.

> **Exception — angled rails use `ext=0`.** Because `EXT = half-width`, the extension makes *perpendicular* joints sit flush. But on the **angled** rails (`Rail_Z2_L/R`, `Rail_Z4_L/R`) it pushes the end past the corner and a stub pokes out (most visible at the Zone 4 flying-bar tip). These four rails are built with `ext1=ext2=0` so they end exactly on the corner; the overlapping horizontal rails (Z1/Z3/Tri_Horiz) keep their EXT and hide the joint.

### Post cap convention

All grip bars sit **10 cm below post tops**. Post height = bar height + 0.10.

### SHS scale formula

`primitive_cube_add(size=1)` creates vertices at ±0.5. To get dimension D: `obj.scale = D` (not D/2).

```python
obj.scale = (half_sz * 2, half_sz * 2, length)  # correct
obj.scale = (half_sz, half_sz, length/2)          # ❌ gives half size — bug already fixed
```

---

## Pull Up Bar

**File:** `pullup_bar_v1.blend` (also `_v2`) | **Collection:** `PullUpBar`

> **Raised +10cm** (was posts 2.2m / bar 2.10m) — the original bar sat too low once the 10cm post-cap gap
> pulled it down, so the whole piece was extended up 10cm (cap kept).

### Objects

| Object            | Type       | Location (x, y, z) | Dimensions             |
| ----------------- | ---------- | ------------------ | ---------------------- |
| `Post_Left`       | Cube (SHS) | (−0.75, 0, 1.15)   | 100×100mm, height 2.3m |
| `Post_Right`      | Cube (SHS) | (+0.75, 0, 1.15)   | 100×100mm, height 2.3m |
| `Bar_PullUp_High` | Cylinder   | (0, 0, 2.20)       | OD 34mm, length 1.5m   |

### Dimensions

- Post cross-section: **100×100mm SHS** (scale kept on object, **not** applied: `scale=(0.1, 0.1, 2.3)`)
- Post height: **2.30m** (z=0 to z=2.30)
- Post spacing: **1.50m** centre-to-centre (X axis)
- Bar OD: **34mm** → radius = 0.017m
- Bar height: **z = 2.20m** (10cm below post top at 2.30m)
- Bar length: **1.50m** along world X axis
- Bevel on posts: `width=0.008`, `segments=3`

### Bar rotation

`Bar_PullUp_High` has `rotation_euler = (0, π/2, 0)` stored as **object property — NOT applied to mesh**.

### ⚠️ Known gotcha

**Do NOT call `transform_apply(rotation=True)` on `Bar_PullUp_High`.**
The 90° Y-rotation is object-level. Applying it bakes it into local vertex coords, doubling the Z offset (bar ends up at z≈4.20 instead of 2.10).

### How to modify

| Task                | What to change                                                             |
| ------------------- | -------------------------------------------------------------------------- |
| Change bar height   | `Bar_PullUp_High.location.z = new_post_height − 0.10`                      |
| Change post height  | Scale Post cubes on Z, `location.z = new_h/2`, update bar z                |
| Change post spacing | Move Posts to ±spacing/2, recreate bar with `depth = spacing`              |
| Change bar OD       | Delete bar, `primitive_cylinder_add(radius=new_r)` — do NOT apply rotation |

### Real-world spec

- Post: SHS 100×100×4.5mm, grade SS400
- Bar: Round pipe OD 33–34mm, seamless, wall 3.2mm
- Coating: Sandblast + Epoxy Primer + Powder Coat (UV grade)

### Versions

The section above describes **`pullup_bar_v1.blend`** (the raised adult bar — 2 posts + 1 high bar).

| Version | Posts                         | Bars                                                              |
| ------- | ----------------------------- | ---------------------------------------------------------------- |
| **v1**  | 2 × 2.3m @ x=±0.75            | high bar @ z=2.20, 1.5m wide                                      |
| **v2**  | v1 + 1 child post 1.6m @ x=−1.75 | v1 high bar **+** child low bar @ z=1.50, 1.0m wide (x=−1.75→−0.75) |

**v2 = v1 + a child pull-up bar on the −X side** — a third (shorter) post lets a low bar hang beside the
adult one. Layout along X: `[Post_Child 1.6m] —(low bar 1.5m, 1.0m wide)— [Post_Left 2.3m] —(high bar 2.20m, 1.5m wide)— [Post_Right 2.3m]`.

New objects (added to the `PullUpBar` collection, same materials/bevel as v1):

| Object           | Type       | Location (x, y, z) | Dimensions             |
| ---------------- | ---------- | ------------------ | ---------------------- |
| `Post_Child`     | Cube (SHS) | (−1.75, 0, 0.80)   | 100×100mm, height 1.6m |
| `Bar_PullUp_Low` | Cylinder   | (−1.25, 0, 1.50)   | OD 34mm, length 1.0m   |

- Child bar keeps the 10cm post-cap (post 1.6m → bar 1.50m). Bar is round OD 34mm like the high bar
  (`rotation_euler=(0,π/2,0)`, **not applied**).
- Child post 1m to the **left** of `Post_Left`; mirror to +X (x=+1.75, bar x=+1.25→ between Post_Right) if the right side is preferred.

> ⚠️ Footprint grows leftward to x≈−1.80, so if v2 is linked into `main_scene` the `PullUpBar`
> `instance_offset` (bottom-left corner) shifts from (−0.800, −0.050, 0) — re-derive it when swapping.

---

## Snake Bar

**File:** `snake_bar_v1.blend` | **Collection:** `SnakeBar`

> **Raised +10cm** (was posts 2.0m / bars 1.90m) so the grip bars sit at a round 2.00m — same reason as the
> pull-up bar (the 10cm cap had pulled the bar too low). **All snake versions `v1`–`v5` share this raise.**

### Objects

| Object               | Type        | Location (x, y, z) | Notes                            |
| -------------------- | ----------- | ------------------ | -------------------------------- |
| `Post_Snake_Left`    | Cube (SHS)  | (−1.0, 3.0, 1.05)  | 100×100mm, height 2.1m           |
| `Post_Snake_Right`   | Cube (SHS)  | (+1.0, 3.0, 1.05)  | 100×100mm, height 2.1m           |
| `Bar_Snake_Straight` | Cylinder    | (0, 3.0, 2.00)     | OD 34mm, length 2.0m, structural |
| `Bar_Snake_Wave`     | NURBS Curve | (varies)           | OD 34mm, 17 control pts, z=2.00m |

> **Scene Y offset = +3.0m** from pull-up bar to avoid scene overlap.

### Dimensions

- Post: **100×100mm SHS**, height **2.1m**, spacing **2.0m** (X), bevel `width=0.008`
- Structural bar: **OD 34mm**, length **2.0m**, z=**2.00m** (10cm below post top)
- Wave bar: NURBS, `bevel_depth=0.017`, `bevel_resolution=6`, `order_u=3`, `use_fill_caps=True`

### Wave bar control points

17 points. All at z=2.00 (after the +10cm raise). `Y_OFF=3.0` (scene offset). `DEPTH=0.50m`.
Pattern: 4 U-shapes alternating +Y / −Y, each **0.50m wide × 0.50m deep**.

| #   | x     | y         | Role                  |
| --- | ----- | --------- | --------------------- |
| 0   | −1.00 | Y_OFF     | start (left post)     |
| 1   | −1.00 | Y_OFF+0.5 | U1 back-left corner   |
| 2   | −0.75 | Y_OFF+0.5 | U1 flat mid           |
| 3   | −0.50 | Y_OFF+0.5 | U1 back-right corner  |
| 4   | −0.50 | Y_OFF     | junction 1            |
| 5   | −0.50 | Y_OFF−0.5 | U2 front-left corner  |
| 6   | −0.25 | Y_OFF−0.5 | U2 flat mid           |
| 7   | 0.00  | Y_OFF−0.5 | U2 front-right corner |
| 8   | 0.00  | Y_OFF     | junction 2            |
| 9   | 0.00  | Y_OFF+0.5 | U3 back-left corner   |
| 10  | +0.25 | Y_OFF+0.5 | U3 flat mid           |
| 11  | +0.50 | Y_OFF+0.5 | U3 back-right corner  |
| 12  | +0.50 | Y_OFF     | junction 3            |
| 13  | +0.50 | Y_OFF−0.5 | U4 front-left corner  |
| 14  | +0.75 | Y_OFF−0.5 | U4 flat mid           |
| 15  | +1.00 | Y_OFF−0.5 | U4 front-right corner |
| 16  | +1.00 | Y_OFF     | end (right post)      |

Edit via: `spline.points[i].co = (x, y, z, 1.0)`.

### ⚠️ Known gotcha

Same as pull-up bar: do NOT apply rotation on `Bar_Snake_Straight`.

### Real-world spec

- Post: SHS 100×100×4.5mm, SS400
- Wave bar: Round pipe OD 34mm, seamless — bent at each U corner, bend radius ≈80–100mm
- Junctions (pt 4, 8, 12) weld to structural bar at x=−0.5, 0, +0.5

### Versions

The section above describes the original (`snake_bar.blend` / `snake_bar_v1.blend` — identical). **v2**,
**v3**, **v4** and **v5** keep the original horizontal wave bar but add **vertical "side snake bars" on each post**.

**The +10cm raise is now the baseline** for *all* versions `v1`–`v5` (posts 2.1m, straight + wave bars 2.0m —
see the base section above). `v1` is just that raised wave bar; `v2`–`v5` add side climbing bars on top of it.

**Side snake bars** (`Bar_Snake_Side_L` / `_R`) — NURBS like the wave bar (`bevel_depth=0.017`,
`bevel_resolution=6`, `order_u=3`, `use_endpoint_u`, `Grip_White`). Normally climb each post from floor `z=0`
to the wave-bar endpoint `(±1.0, 3.0, 2.00)` (v2: 8 castellated U-units of 25cm; v3/v4: 4 outward grips).
**v5 is the exception** — its grips are pulled down 15cm so they sit `z=0.10…1.85` (10cm above floor, 15cm
below the wave bar) and do **not** connect to the floor or wave bar.

| Version | Weave plane | U pattern                                                                                |
| ------- | ----------- | ---------------------------------------------------------------------------------------- |
| **v2**  | Y (Y–Z)     | Full in/out U's, depth ±0.25m. L & R **mirrored in Y** so each top U sits opposite the top wave bar's U at its post (else the right one's top U collides with the wave bar). |
| **v3**  | X (X–Z)     | **Outward grips only** — 4 U-hooks per post bulging away from centre (depth 0.25m, 25cm tall, 50cm pitch), straight runs between; inner-facing U's removed (climbing-hold look). |
| **v4**  | Y (Y–Z)     | Same outward-grips-only pattern as v3 but bulging in **Y** (forward/back) instead of X, so the X footprint stays narrow (just the ±1.0 post span) and doesn't collide sideways with neighbouring equipment in the layout. L & R **mirrored** (left grips →−Y, right →+Y) to dodge the wave bar's U at each post. |
| **v5**  | Y (Y–Z)     | Outward grips only like v4, but **all the same Y direction** (both posts →−Y, no mirror) and the whole bar **pulled down 15cm** → grips span `z=0.10…1.85` (bottom 10cm above floor; top 15cm below the wave bar). The drop clears the wave bar so same-direction grips no longer collide with it; the side bar no longer reaches the floor or the top. |

> Earlier note: the user first said the v2 side bars should weave on the "X axis" but meant Y (forward/back).
> v3 is the X-axis variant (left/right), trimmed to outer grips only; **v4** is v3 rotated back to Y because
> the sideways (X) grips ate into neighbouring equipment's space in the layout; **v5** turns v4's grips all
> the same way and drops the whole side bar 15cm to clear the top wave bar.

---

## Dip Bar

**File:** `dip_bar_v1.blend` | **Collection:** `DipBar`

### Objects

| Object      | Type        | x position | Notes                                  |
| ----------- | ----------- | ---------- | -------------------------------------- |
| `DipBar_01` | NURBS Curve | 0.00       | piece 1                                |
| `DipBar_02` | NURBS Curve | 0.60       | 60cm from piece 1                      |
| `DipBar_03` | NURBS Curve | 1.10       | 50cm from piece 2                      |

### Shape (per piece)

Portal frame (∩): one continuous bent **round** pipe (single piece, no welds).

```
Side view (YZ plane, single piece):
    ←75cm→
    ──────   z = 1.20m
   ╱      ╲  curved NURBS bends
  │        │  120cm legs
  ○        ○  z = 0 (ground)
 y=0     y=0.75
```

### Bevel profile (round)

Each `DipBar_0x` curve uses a **round** cross-section — the dip frame is one continuous bent pipe, so it is round all the way (no welded joints to need a square section):

- `curve.bevel_mode='ROUND'`, `curve.bevel_depth=0.021` (OD 42mm), `bevel_resolution=6`, `use_fill_caps=True`, `bevel_object=None`
- No `SqProfile` helper (removed — it was a square/squircle profile from an earlier revision).

### Control points (per piece, x=x_pos fixed)

11 NURBS points. `use_endpoint_u=True`, `order_u=3`.

| #   | y     | z     | Role                  |
| --- | ----- | ----- | --------------------- |
| 0   | 0.000 | 0.000 | front leg bottom      |
| 1   | 0.000 | 0.550 | mid front leg         |
| 2   | 0.000 | 1.050 | upper front leg       |
| 3   | 0.000 | 1.200 | front top corner      |
| 4   | 0.120 | 1.200 | just past front bend  |
| 5   | 0.375 | 1.200 | mid grip              |
| 6   | 0.630 | 1.200 | just before back bend |
| 7   | 0.750 | 1.200 | back top corner       |
| 8   | 0.750 | 1.050 | upper back leg        |
| 9   | 0.750 | 0.550 | mid back leg          |
| 10  | 0.750 | 0.000 | back leg bottom       |

### Spacing

- Piece 1–2: **60cm** → two grip widths available (60cm + 50cm)
- Piece 2–3: **50cm**

### ⚠️ Known gotcha

NURBS curve object — do NOT apply transforms. Edit control points via Python only.
Cross-section is set per-curve via `bevel_mode='ROUND'` + `bevel_depth` (no external profile object).

### Real-world spec

- Material: Round pipe OD 42–45mm, one piece bent into the ∩ frame (no welds)
- Fabricated by bending single pipe, bend radius ≈80–120mm at corners
- 60cm = wider grip (chest focus), 50cm = narrower (tricep focus)

---

## Monkey Flying Bar

**File:** `monkey_flying_bar_v1.blend` (also `_v2` / `_v3`) | **Collection:** `MonkeyFlyingBar`

### Overview

4-zone inclined monkey bar, total **4m long × 1.00m wide**.

- Zones run along **Y axis** (Y=0 → Y=4)
- Width along **X axis** (X=−0.500 → X=+0.500, `HW=0.500`)
- All structural members are **SHS 50×50mm** except round rungs and ladder rungs

### Key constants

```python
HW        = 0.500   # half-width (total 1.00m)
BAR_R     = 0.017   # OD 34mm → r=17mm  (round rungs + ladder rungs)
POST_SHS  = 0.025   # SHS 50×50mm half  (rails, posts, braces)
LAD_SHS   = 0.020   # SHS 40×40mm half  (ladder rails)
BEVEL_W   = 0.004   # 4mm edge bevel
EXT       = 0.025   # 25mm extension per joint end (fills gaps)
GAP       = 0.100   # 10cm post cap above rung height

Z1_POST   = 0.50    # Zone 1 post top
Z1_RNG    = 0.40    # Zone 1 rung height (= Z1_POST − GAP)
Z3_POST   = 2.00    # Zone 3 post top
Z3_RNG    = 1.90    # Zone 3 rung height (= Z3_POST − GAP)
ANG4      = 35°     # Zone 4 flying bar angle
Z4_RNG_END = 1.90 + tan(35°) ≈ 2.600  # flying bar end height = triangle right-angle vertex
```

### Rung height function

```python
def rung_z(y):
    if   y <= 1.0:  return 0.40                              # Zone 1 flat
    elif y <= 2.0:  return 0.40 + (y-1.0) * 1.50            # Zone 2 diagonal
    elif y <= 3.0:  return 1.90                              # Zone 3 flat
    else:           return 1.90 + (y-3.0) * tan(35°)        # Zone 4 flying
```

---

### Zone 1 — Flat, low section

**Y = 0 → 1m | Rung height = 0.40m | Post height = 0.50m**

| Object                    | Type                   | Positions                        |
| ------------------------- | ---------------------- | -------------------------------- |
| `Rail_Z1_L` / `Rail_Z1_R` | SHS 50×50mm            | (±HW, 0→1, z=0.40), horizontal   |
| `Z1_00` … `Z1_05`         | Round cylinder OD 34mm | y = 0.0, 0.2, 0.4, 0.6, 0.8, 1.0 |
| `Post_y0_L` / `Post_y0_R` | SHS 50×50mm            | (±HW, 0, 0→0.50), vertical       |
| `Post_y1_L` / `Post_y1_R` | SHS 50×50mm            | (±HW, 1, 0→0.50), vertical       |

- **6 rungs**, 20cm gaps, all horizontal at z=0.40m
- Rungs span full width: x=−HW to x=+HW
- Rails and rungs extended by `EXT=25mm` at each end

---

### Zone 2 — Diagonal transition

**Y = 1 → 2m | Height rises from 0.40m to 1.90m**

| Object                    | Type                   | Positions                         |
| ------------------------- | ---------------------- | --------------------------------- |
| `Rail_Z2_L` / `Rail_Z2_R` | SHS 50×50mm            | (±HW, 1→2, z=0.40→1.90), diagonal |
| `Z2_01` … `Z2_08`         | Round cylinder OD 34mm | 8 intermediate rungs (see below)  |

#### Zone 2 rung spacing — 20cm measured along slope

```
Slope vector: ΔY=1.0, ΔZ=1.50 → slope length = √(1² + 1.5²) ≈ 1.803m
step_y = 0.20 × (1.0 / 1.803) ≈ 0.111m per rung (in Y)
n = floor(1.803 / 0.20) = 9 gaps → 8 intermediate rungs
```

Rung Y positions: `y = 1.0 + i × 0.111` for i = 1..8 (≈1.111, 1.222, …, 1.889)
Z at each rung: `z = rung_z(y)` — all rungs are **horizontal** (not perpendicular to slope).

- Zone 2 rungs do NOT include y=1.0 (Zone 1 end) or y=2.0 (Zone 3 start) — those are added by neighbouring zones.

---

### Zone 3 — Flat, high section

**Y = 2 → 3m | Rung height = 1.90m | Post height = 2.00m**

| Object                              | Type                   | Positions                      |
| ----------------------------------- | ---------------------- | ------------------------------ |
| `Rail_Z3_L` / `Rail_Z3_R`           | SHS 50×50mm            | (±HW, 2→3, z=1.90), horizontal |
| `Z3_00` … `Z3_04`                   | Round cylinder OD 34mm | y = 2.0, 2.2, 2.4, 2.6, 2.8    |
| `Post_y2_L` / `Post_y2_R`           | SHS 50×50mm            | (±HW, 2, 0→2.00), vertical     |
| `Lad_Rail_F`                        | SHS 40×40mm            | (HW, 2, 0→1.90), vertical      |
| `Lad_Rail_B`                        | SHS 40×40mm            | (HW, 3, 0→1.90), vertical      |
| `Lad_0.20` … `Lad_1.80`, `Lad_1.90` | Round cylinder OD 34mm | (HW, 2→3, z=0.2,0.4,…,1.9)     |

- **5 rungs** (y=2.0–2.8), 20cm gaps. Note: y=3.0 rung belongs to Zone 4.
- **Side ladder on right side (x=+HW)**: 10 round rungs from z=0.20 to z=1.90 (top rung = rung height).
  Ladder rails (SHS 40×40mm) do NOT use joint extension — they run along Y at fixed x=HW.
- Post_y3 is listed under Zone 4 (it extends to the triangle apex).

---

### Zone 4 — Flying bar (35°)

**Y = 3 → 4m | Starts at z=1.90m, rises at 35°, ends at z=2.60m**

| Object                        | Type                   | Positions                             | Notes                         |
| ----------------------------- | ---------------------- | ------------------------------------- | ----------------------------- |
| `Rail_Z4_L` / `Rail_Z4_R`     | SHS 50×50mm            | (±HW, 3→4, z=1.90→2.60), diagonal 35° |                               |
| `Z4_00` … `Z4_04`             | Round cylinder OD 34mm | y=3.0, 3.25, 3.50, 3.75, 4.00         | 25cm gaps                     |
| `Post_y3_L` / `Post_y3_R`     | SHS 50×50mm            | (±HW, 3, 0→**2.60**), vertical        | extends to triangle apex      |
| `Tri_Horiz_L` / `Tri_Horiz_R` | SHS 50×50mm            | (±HW, 3→4, z=2.60), horizontal        | 90° arm                       |
| `Tri_Cap_B`                   | SHS 50×50mm            | (−HW→+HW, 4, z=2.60)                  | cross brace at flying bar end |

> **No `Tri_Cap_C`.** The cross brace at the 90° corner (y=3) was intentionally removed — the side ladder already ties the left/right frames together there, so it was redundant and visually cluttered.

#### Right-angle triangle brace geometry

```
C = (y=3, z=2.60) ─── Tri_Horiz (horizontal) ──→ B = (y=4, z=2.60)
│                                                   │
│  Post_y3 upper section (vertical leg)             = flying bar end (Z4_rung_04)
│
A = (y=3, z=1.90)  ──── Rail_Z4 / flying bar (hypotenuse 35°) ────→ B
```

- **Right angle at C** (between Post_y3 vertical and Tri_Horiz horizontal) ✓
- **Hypotenuse = the flying bar itself** (Rail_Z4 + Z4 rungs)
- Post_y3 ends at **z = Z4_RNG_END = 2.60m** (NOT 2.70 — no extra GAP above triangle)
- Tri_Horiz is fully horizontal (not angled) → all weld joints are 90°

#### Zone 4 rung positions

5 rungs, 25cm gaps: `y = 3.0, 3.25, 3.50, 3.75, 4.00`. Heights from `rung_z(y)`.

- Z4_00 (y=3.0): z = 1.90m (= Zone 3 rung height, shared boundary)
- Z4_04 (y=4.0): z = 2.60m (= Z4_RNG_END, at triangle corner B)

---

### Full object list summary

| Category       | Objects                                                    | Material | Dims    |
| -------------- | ---------------------------------------------------------- | -------- | ------- |
| Rails          | `Rail_Z1_L/R`, `Rail_Z2_L/R`, `Rail_Z3_L/R`, `Rail_Z4_L/R` | SHS      | 50×50mm |
| Zone 1 rungs   | `Z1_00`–`Z1_05`                                            | Round    | OD 34mm |
| Zone 2 rungs   | `Z2_01`–`Z2_08`                                            | Round    | OD 34mm |
| Zone 3 rungs   | `Z3_00`–`Z3_04`                                            | Round    | OD 34mm |
| Zone 4 rungs   | `Z4_00`–`Z4_04`                                            | Round    | OD 34mm |
| Vertical posts | `Post_y0_L/R`, `Post_y1_L/R`, `Post_y2_L/R`, `Post_y3_L/R` | SHS      | 50×50mm |
| Triangle brace | `Tri_Horiz_L/R`, `Tri_Cap_B`                               | SHS      | 50×50mm |
| Ladder rails   | `Lad_Rail_F`, `Lad_Rail_B`                                 | SHS      | 40×40mm |
| Ladder rungs   | `Lad_0.20`–`Lad_1.90` (10 rungs)                           | Round    | OD 34mm |

### How to modify

| Task                            | What to change                                                                                             |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Change zone 1/3 height          | Update `Z1_POST`, `Z1_RNG`, `Z3_POST`, `Z3_RNG`. Rebuild rails + rungs + posts                             |
| Change flying bar angle         | Update `ANG4`. Recalculate `Z4_RNG_END = Z3_RNG + tan(ANG4)`. Rebuild Rail_Z4, Post_y3, Z4 rungs, triangle |
| Change zone 2 rung density      | Recompute `slope` and `step_y`. Rebuild Z2 rungs                                                           |
| Add/remove zone 4 rungs         | Adjust rung y positions list. Keep Post_y3 height = `rung_z(4.0)`                                          |
| Change total width              | Update `HW`. All rails, rungs, ladder span from −HW to +HW                                                 |
| Move ladder to left side        | Change all `HW` to `−HW` in ladder objects                                                                 |
| Make rails round instead of SHS | Replace `mk_shs` calls for Rail_Zx with `mk_rail` (NURBS smooth curve)                                     |

### ⚠️ Known gotchas

**1. Zone 3 has 5 rungs (y=2.0–2.8), NOT 6** — the y=3.0 rung belongs to Zone 4 (Z4_00). If you add a Z3 rung at y=3.0, it creates a visible double-rung at the boundary.

**2. Zone 2 rung spacing is along the slope**, not horizontal Y distance. Using horizontal 20cm gaps gives incorrect (too-wide) visual spacing. Always compute `step_y = 0.20 × (dY/slope)`.

**3. EXT=25mm extension on PERPENDICULAR SHS bars only** — horizontal rails/braces (Z1, Z3, Tri_Horiz) and posts use `ext1=EXT, ext2=EXT` so they sit flush at right-angle joints. The **angled rails** (`Rail_Z2_L/R`, `Rail_Z4_L/R`) use `ext1=ext2=0` — with EXT they poke a stub past the corner (the old Zone 4 flying-bar overhang). Build angled members exactly corner-to-corner; let the perpendicular members overlap to fill the joint.

**4. SHS scale formula** — `obj.scale = (half_sz*2, half_sz*2, length)`. Using `(half_sz, half_sz, length/2)` gives half-size posts (this bug was already fixed).

**5. Post_y3 height = Z4_RNG_END (2.60m), NOT Z4_POST_END (2.70m)** — the triangle right-angle is at z=2.60 (the flying bar end height). The old 2.70 height added a useless 10cm cap.

---

### Versions

The section above describes the **original** (`monkey_flying_bar.blend`). Three variants are saved as
`monkey_flying_bar_v1/v2/v3.blend`. **Common change in all three: no 10cm post cap** — every post top sits
**flush at rung height** (not 10cm above), in all zones, EXCEPT the structural `Post_y3` (the flying-bar
triangle leg, which must reach the apex). Posts still use `ext2=0.025` so they end flush with the rail's
top surface. Rung heights are raised to the original *post* heights.

| Version | Zone 0 (y=−1→0)         | Zone 1 | Zone 2 ramp          | Zone 3 | Zone 4 flying bar              | Front ladder (y=0)                         |
| ------- | ----------------------- | ------ | -------------------- | ------ | ------------------------------ | ------------------------------------------ |
| **v1**  | —                       | 0.50m  | 0.50→2.00 (8 rungs)  | 2.00m  | 2.00→2.70 @35°                 | — (Zone 1 low enough to step up)           |
| **v2**  | —                       | 1.00m  | 1.00→2.00 (6 rungs)  | 2.00m  | 2.00→2.70 @35°                 | rungs 0.20→0.80 @20cm                     |
| **v3**  | —                       | 1.50m  | 1.50→2.50 (6 rungs)  | 2.50m  | 2.00→2.70 @35° (step −50cm)   | rungs 0.20→1.40 @20cm                     |
| **v4**  | 2 posts + 3 bars @1.00m | 1.00m  | 1.00→2.00 (6 rungs)  | 2.00m  | 2.00→2.70 @35°                 | rungs 0.20→0.80 @20cm                     |
| **v5**  | 2 posts + 3 bars @1.50m | 1.50m  | 1.50→2.50 (6 rungs)  | 2.50m  | 2.00→2.70 @35° (step −50cm)   | rungs 0.20→1.40 @20cm                     |

- **Zone 2 rung count** follows the 20cm-along-slope rule: `n = floor(√(ΔY²+ΔZ²)/0.20) − 1` (v1 ΔZ=1.5 → 8; v2/v3/v4/v5 ΔZ=1.0 → 6).
- **Side ladder** (Zone 3, x=+HW) climbs to the deck height each version (v1/v2/v4 → 2.00, v3/v5 → 2.50).
- **v3/v5 — Zone 4 intentional step**: flying bar starts at 2.00m while Zone 3 = 2.50m → 50cm step down at Zone 3↔4 junction (keeps apex at 2.70m).
- **Front ladder** = round OD34 rungs (`FrontLad_*`), full width (−HW→+HW) at y=0 face, 20cm apart.
- **Zone 0 (v4/v5 only)**: entry frame at y=−1→0. Objects: `Post_pre_y0_L/R` (SHS 50×50mm, height = Z1_RNG), `Rail_Z0_Cross` (top cross bar y=−1), `Rail_Z0_L/R` (side rails y=−1→0). All SHS steel. `instance_offset = (−0.525, −1.025, 0)`.

---

## #Floor

**File:** `floor_v1.blend` | **Collection:** `Floor`

### Objects

| Object                       | Type | Location      | Dimensions       | Material            |
| ---------------------------- | ---- | ------------- | ---------------- | ------------------- |
| `Floor_Main`                 | Cube | (0, 0, 0.05)  | 6m × 5m × 0.10m  | `Floor_Rubber`      |
| `Concrete_N/S/E/W` (4 strips)| Cube | perimeter     | 5cm border, 0.10 tall | `Concrete_Edge_Mat` |

**Rubber pad + concrete edge.** The rubber slab is **10cm** thick (was 30cm). A **5cm-wide
concrete border** (`Concrete_N/S/E/W`, four strips just outside the 6×5 rubber) frames it —
like a real EPDM pad with a concrete edge restraint. Both sit flush, top at local `z=0.10`.
No zone marker / frame strips. `Floor_Rubber` = deeper EPDM blue with granule speckle + micro-bump;
`Concrete_Edge_Mat` = grey concrete with bump.

### Dimensions

- **Platform**: 6m × 5m rubber, **0.10m** tall, + 5cm concrete border (outer ≈6.1m × 5.1m).
- In `main_scene`, `Instance_Floor` is at `z=-0.10` so the rubber top is the ground plane `z=0`.
- Keep equipment ≥1m from each edge as a fall-zone margin (EN 1176) — judged during layout.

### Real-world spec

- 10cm concrete base/curb + EPDM rubber surfacing inside the concrete edge.

---

## #Main Scene

**File:** `main_scene.blend`

### Linked instances

| Instance object            | → Collection      | Source file (links the `_v1` of each) |
| -------------------------- | ----------------- | ------------------------------------- |
| `Instance_PullUpBar`       | `PullUpBar`       | `pullup_bar_v1.blend`                 |
| `Instance_SnakeBar`        | `SnakeBar`        | `snake_bar_v1.blend`                  |
| `Instance_DipBar`          | `DipBar`          | `dip_bar_v1.blend`                    |
| `Instance_MonkeyFlyingBar` | `MonkeyFlyingBar` | `monkey_flying_bar_v1.blend`          |
| `Instance_Floor`           | `Floor`           | `floor_v1.blend`                      |

Positioning of equipment on the floor is done by moving instance objects in main_scene.
To show a different version of a piece, re-point its library (`library.filepath = "//<piece>_v{n}.blend"`,
then `library.reload()`) — the instance empty keeps its position so the layout is preserved.

### Origin convention — bottom-left corner (for easy layout)

Each piece collection has its `instance_offset` set to the **bottom-left corner** of its
footprint `(minX, minY, 0)`, so an instance's `location` is exactly where that corner lands.
Place by corner: `instance.location = (X, Y, 0)` puts the piece's bottom-left corner at `(X, Y)`.

| Collection        | `instance_offset` (bottom-left) |
| ----------------- | ------------------------------- |
| `Floor`           | (−3.000, −2.500, 0)             |
| `PullUpBar`       | (−0.800, −0.050, 0)             |
| `SnakeBar`        | (−1.050, +2.483, 0)             |
| `DipBar`          | (−0.021, −0.021, 0)             |
| `MonkeyFlyingBar` | (−0.525, −0.025, 0)             |

> With `Floor` placed at `(0,0,0)` the slab spans world `(0,0)→(6,5)`, so equipment corners
> are placed in positive X/Y on the slab. `instance_offset` does **not** move geometry — the
> per-object coordinates in the tables above are unchanged. **Layout is committed** (`Instance_Floor`
> at `z=-0.10` so the 10cm slab's top is the ground plane `z=0`; equipment placed with fall-zone margins).

### Lighting & environment (outdoor, photoreal pass)

Built in `main_scene.blend` only (not in piece files). **Blender 5.1**, render engine **Cycles** (OptiX GPU).

- **World:** Sky Texture `sky_type='HOSEK_WILKIE'` (this build's procedural sky; no Nishita), `turbidity≈1.8`.
- **Key:** `Sun` lamp, energy `4.6`, warm `(1.0,0.93,0.82)`, low elevation (rot ≈63°) for longer shadows.
- **Fill:** `FillArea` area light, energy `120`.
- **Ground:** `Ground` = a 120m bmesh grid (~280×280, base `z=-0.30`) with **three Displace modifiers**
  (Hills/Bumps/Pits — CLOUDS + VORONOI textures) so the terrain physically undulates (real dimension, not a flat plane).
  Peaks kept below platform top (`z=0`). Replaces the old flat `Lawn` plane + `GrassPatch` hair (removed — read flat).
- **Terrain material** `Terrain_Blend`: **green grass base** (procedural multi-noise greens, dominant) with
  **faint dirt** (`brown_mud_03`) showing through on **slopes + sparse patches** (slope mask = `MapRange(Normal.Z, 0.80→0.95, To 1→0)`;
  ⚠️ set `To Min/Max` or the mask inverts and the whole field turns dirt). `brown_mud_03` normal map for relief.
- **Grass blades:** `Ground` has a **hair particle system** (~340k strands, length `0.33`, tapered `root_radius≈0.011`,
  `Grass_Blade` green root→tip). Confined to a **tight** `grass` vertex-group (radius ≤16m of platform) so the
  fixed strand budget packs ~600/m² → reads as tall, dense turf (not sparse sticks). Beyond it, the green terrain texture.
  ⚠️ Blender 5.1: `pset.cycles` width is gone — strands are near-invisible until `root_radius`≈0.011–0.015.
  ⚠️ Particle **object-instancing** (`render_type='OBJECT'`, for blade-tuft meshes) did **not** render in this 5.1 build —
  stick with `render_type='PATH'` strands, or use Geometry Nodes scatter if real blade cards are needed.
- **Trees:** procedural — `Tree_trunk` (cone, `Bark`) + displaced icospheres `Tree_foliage` (`Leaves`), behind the platform.
- **Camera:** parented to `CamRig` (orbit); recentre with **lens shift** `shift_y≈0.10` (keeps the chosen angle); DOF ~f/12 keeps terrain sharp.
- **Render:** Cycles (OptiX), **AgX – High Contrast**, exposure `+0.2`, ~90 samples + denoise.

> Poly Haven note: a flat plane + texture always reads flat — give ground **real geometry** (subdivided mesh +
> Displace) for dimension. Poly Haven has no clean green-lawn texture; `aerial_grass_rock` is rocky/tan, so it's
> **multiplied with green** + Hue/Sat. Dirt = `brown_mud_03`, sand = `aerial_sand`.

> People: needs **Sketchfab** (chosen) or Hyper3D enabled in the BlenderMCP panel — Poly Haven has no human models.

### Presentation: people + camera pan animation

- **People (scale figures):** `Adult_*` (1.75m) + `Child_*` (1.10m), built from primitives (head/torso/
  arms/legs) with `Skin` / `Shirt_*` / `Pants_*` materials. Stand on the rubber for scale.
- **Orbit rig:** empty `CamRig` at scene centre `(3,2.5,1.15)`; `Camera` parented to it
  (`matrix_parent_inverse = Identity`, local offset `(0,-11,2.8)`, aimed at rig origin). Rotating `CamRig.z`
  `0→2π` over frames `1–96` (24 fps) orbits the camera 360°, always framed on the equipment.
  > Gotcha: set the rig's `location` **then `view_layer.update()`** before reading `matrix_world`,
  > or the parent-inverse is stale and the camera ends up off-centre.
- **Video output:** this build has **no FFMPEG** image format and no `imageio`. Render a **PNG sequence**
  (`pan_frames/frame_####.png`, in ≤32-frame chunks to avoid MCP timeouts), then combine with
  `make_gif.py` (Pillow) → `design_pan.gif`. For an mp4, install ffmpeg or `imageio-ffmpeg`.

### Reload workflow

```python
# After editing any piece .blend file:
bpy.ops.wm.open_mainfile(filepath="main_scene.blend")
bpy.ops.wm.revert_mainfile()  # reloads all linked libraries
```

### ⚠️ Library linking gotcha

If a collection name is duplicated inside a .blend file (e.g. `MonkeyBar` and `MonkeyBar.001`), Blender links the FIRST one found — which may be empty. Always ensure **exactly one collection** with the target name exists in each piece file. To fix: rebuild the piece file clean with `wm.read_homefile(use_empty=True)` and `save_as_mainfile`.
