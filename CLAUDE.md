# CLAUDE.md — Calisthenic Equipment Design Project

## Project Overview

This project designs an **outdoor calisthenic gym** for a homeowner (วิศวกร, ~150,000 THB budget).
All 3D models are built in Blender via **BlenderMCP** (port 9876) using Python scripts.
The goal is a realistic layout draft, not a production render — no materials needed yet.

> 👥 **บริบทเรื่องคน/ความรับผิด — อ่านก่อนถ้าเจองาน policy / quotation / เอกสารส่งมอบ:** [final1-th/ai/my-situation.md](final1-th/ai/my-situation.md) — สรุปสถานการณ์ 4 ฝ่าย + กติกาการเขียนเอกสาร (เช่น ⛔ ห้ามใส่คำว่า "AI" ในสัญญา · ใช้คำว่า "แนะนำ" ไม่ใช่ "ต้อง")

---

## Stack & Tools

| Tool | Usage |
|---|---|
| Blender 5.1 + BlenderMCP | 3D modelling via `mcp__blender__execute_blender_code` · headless QA: `blender --background --factory-startup --python scripts/inspect_pieces.py` |
| `final1-th/` · `final1-en/` | ★ **Source of truth = `final1-th/` (ไทย)** · ฉบับ **อังกฤษ formal (British spelling)** คู่ขนานที่ `final1-en/` (เดิม `final1/` · เปลี่ยนชื่อ 26/06/2026 · README.md หลัก = อังกฤษ ลิงก์ไป final1-en) · ชุดทำงานหลัก 14/06/2026 — ฉบับ **formal ไทยทางการ** 3 เอกสาร: `spec.full.md` (1/3 แบบ+ข้อกำหนด PIECE 1–5) · `spec.requirement.md` (2/3 รายท่า+demand รับแรง) · `spec.summary.md` (3/3 ผลตรวจ+ฐานราก+ทางแก้ ก/ข/ค+ของสั่งซื้อ) · `policy.liability.md` (เอกสารกำกับ ฉบับร่าง 2: **ข้อตกลงภายใน Night↔เพื่อน [ฝ่าย ก/ข]** · แบ่งบทบาท **4 ฝ่าย** [ก=ผู้ค้นคว้า · ข=ผู้ประสานงาน · ค=เจ้าของ+วิศวกร กว.+ผู้ตรวจ คนเดียว · ง=ช่างภายนอก] · waiver/กฎหมาย) + `policy.handoff.md` (ฉบับร่าง 1: **หนังสือส่งมอบให้ฝ่าย ค เซ็น** — แยกไฟล์กันพี่เขางง · ใช้ถ้อยคำ **"แนะนำ" ไม่ใช่ "ต้อง"** กันเงื่อนไขพังถ้าวิศวกรไม่ตรวจจริง) — ทั้งคู่เป็นฉบับสมบูรณ์ (เจ้าของตัดสินใจไม่ผ่านทนาย รับความเสี่ยงเอง · มีผลเมื่อลงนาม) · **ฐานโหลด = EN 16630 Table 1 (1,942N/จุด รวม dynamic — เลิกใช้ 5kN)** · วัสดุ wall 3.2 ตาม draft (ไม่อิงร้าน) · verdict: **ผ่านหมด** เหลือ 3 จุดเฝ้าระวัง (monkey ต้องมีค้ำยันสามเหลี่ยม · pull-up bar 1.5m margin ปานกลาง · ชิ้นยื่น side-grip/nub) · ⚠️ ทุกไฟล์มี disclaimer + กรอบ consultant-handoff · **กฎแก้บาร์: เพิ่ม wall เท่านั้น ไม่เพิ่ม OD** |
| `archive/specs/spec.human.v3.md` | **base spec** (ที่มาของ `final1-th/spec.full.md`) — ใช้ `final1-th/` เป็นหลัก · ✅ Bar_Straight=42mm sync · wave path verified |
| `archive/specs/research.md` | Research อ้างอิง brand/มาตรฐาน/anchor (ฐานของ v3) |
| `archive/specs/spec.human.v2.md` | v2 — reference only (เนื้อหาเดียวกับ v3 · ใช้ v3 เป็นหลัก) |
| `archive/specs/spec.human.md` | v1 spec — reference only |
| `archive/docs/spec.md` | Original spec — **superseded**, ignore |
| `save_as_mainfile` | How each piece file is saved (NOT `libraries.write`) |
| Library Linking | `bpy.data.libraries.load(fp, link=True)` in main scene |

**Always check if Blender MCP is connected** before running code:
```python
ToolSearch(query="select:mcp__blender__execute_blender_code")
```

---

## File Structure

```
Desktop/calisthenic-design/
├── final1-th/                            ← ★★ SOURCE OF TRUTH (ชุดเอกสารส่งมอบ formal ไทย) — เริ่มที่ toc.md
│   ├── toc.md                          ← ดัชนีรวมทุกเอกสาร + ลำดับการอ่าน
│   ├── tldr.b.md · tldr.c.md           ← สรุปส่งต่อ (ข=ผู้ประสานงาน / ค=เจ้าของงาน-วิศวกร)
│   ├── spec.full.md                    ← ดีไซน์ละเอียด PIECE 1–5 (2/4)
│   ├── spec.requirement.md             ← รายท่า + วิเคราะห์รับแรง demand (3/4)
│   ├── spec.summary.md                 ← ฐานราก + verdict recheck + ทางแก้ ก/ข/ค + ของสั่งซื้อ (4/4)
│   ├── spec.minimum.md                 ← เครื่องมือกะวัสดุขั้นต่ำ (มิใช่สเปก)
│   ├── policy.liability.md             ← ข้อตกลงภายใน ก/ข + บทบาท 4 ฝ่าย
│   ├── policy.handoff.md               ← หนังสือส่งมอบให้ฝ่าย ค เซ็น
│   ├── research.md                     ← งานค้นคว้า: brands / EN 16630 / Hilti anchors
│   ├── research.connection-assembly.md ← ระบบต่อ shop-welded field-bolted
│   ├── ai/my-situation.md              ← บริบทคน 4 ฝ่าย + กติกาการเขียนเอกสาร
│   └── design/                         ← แกลเลอรี + PDF + รูป (tracked ใน git)
│       ├── design.gallery.md            ← แกลเลอรีภาพออกแบบ (1/4)
│       ├── design.pdf
│       └── images/ (1–16.png)
├── final1-en/                         ← ★ ชุดเดียวกัน ฉบับ **อังกฤษ formal** (British spelling) · mirror final1-th (รวมรูป/PDF) · README.md หลักลิงก์มาที่นี่
├── archive/                           ← เอกสารรุ่นเก่า เก็บอ้างอิง (ดู archive/README.md) — ห้ามใช้สร้างจริง
│   ├── README.md
│   ├── specs/                          ← สเปก/ใบราคา ก่อนรวมเป็น final1-th/ (spec.human v1–v3 · quotation* · research · severe · *.explore.13062026)
│   └── docs/                           ← เอกสารชุดแรกสุด (spec.md · measurements.md · quotation.md · quotation.predict.md)
├── models/
│   ├── final1-blender/                ← ★ WORKING FOLDER — ใช้ไฟล์ในนี้เป็นหลัก
│   │   ├── pullup_bar_v2.blend        ← Pull-up bar (current)
│   │   ├── snake_bar_v5.blend         ← Snake bar (current) — side bars = 4 U-grips/ข้าง
│   │   ├── dip_bar_v3.blend           ← Dip bar (current) — OD 42mm, nub R=80mm
│   │   ├── monkey_flying_bar_v4.blend ← Monkey+Flying bar (current) — Rail_Z0 = OD 34mm
│   │   ├── floor_v1.blend             ← Ground platform
│   │   └── final_main_scene.blend     ← Main scene (linked geometry)
│   ├── pullup_bar_v1–v2.blend         ← เก่า (v2 คือ current แต่อยู่ใน final1-blender/)
│   ├── snake_bar_v1–v5.blend          ← เก่า
│   ├── dip_bar_v1–v3.blend            ← เก่า
│   ├── monkey_flying_bar_v1–v5.blend  ← เก่า (v5 ในนี้ไม่มี Rail_Z0 update)
│   ├── floor_v1.blend                 ← duplicate
│   ├── main_scene.blend               ← เก่า (stale links)
│   ├── main_scene2.blend              ← เก่า
│   ├── main_scene3.blend              ← เก่า
│   └── _backups/                      ← .blend1 auto-backups (ignore)
├── renders/
│   ├── final/                         ← keeper stills (set1/2/3, photoreal)
│   ├── drafts/                        ← WIP / diagnostic / sketch previews
│   └── animation/                     ← walkthrough.mp4, pan_360.mp4, design_pan.gif
│       └── _frames/                   ← raw render frames (~2.6 GB, safe to delete)
├── assets/                            ← hdri_alps_field_4k.hdr (env lighting)
├── scripts/                           ← make_gif.py, render_pan.py, render_walkthrough.py
├── README.md                          ← project overview (English, primary)
├── README-th.md                       ← project overview (Thai)
└── CLAUDE.md                          ← this file
```

> **Versioning:** piece files keep `_vN` suffixes — highest N in `final1-blender/` is current.
> Do NOT collapse/rename versions without asking (owner compares them).
>
> **Quotation files (current, 11/06/2026 — สร้างจาก spec v3):**
> - `archive/specs/quotation.predict-price.md` — ราคาประเมิน + แผนตัด/ดัดที่ตรวจ bin-packing แล้ว (2 scenario: ชุบ HDG vs galv+spray)
> - `archive/specs/quotation.full.md` — ใบยื่นช่าง เว้นราคาให้จดจริง มีคำถาม 3 ข้อ + เงื่อนไข + ลายเซ็น
> - ⚠️ ไฟล์เก่า `archive/specs/quotation.md` และ `archive/docs/quotation.predict.md` = stale (อิง v2) — เก็บไว้อ้างอิงราคาเท่านั้น ห้ามยื่น
> - **ล่าสุด 13/06/2026**: `archive/specs/spec.explore.13062026.md` + `archive/specs/quotation.explore.13062026.md` = delta จากสำรวจร้านจริง (ท่อ OD34→wall 2.0, OD42→wall 2.5, bolt 1/2"×4", เพลท 9mm ทุกแผ่น) — ⚠️ ยังไม่ recompute การรับน้ำหนัก ห้ามถือเป็น final จนกว่าจะผ่านรอบคำนวณ
>
> **Known issue:** `models/main_scene.blend` (old) has stale link to `dip_bar.blend` (now `dip_bar_v3.blend`).
> Use `final1-blender/final_main_scene.blend` instead — has correct links.

---

## How to Work

### Editing a piece (in final1-blender)
1. Open the piece `.blend` via `bpy.ops.wm.open_mainfile(filepath=...)`
   — path: `C:/Users/BTCOM/Desktop/calisthenic-design/models/final1-blender/<file>.blend`
2. Make changes
3. Save with `bpy.ops.wm.save_mainfile()` (NOT `save_as_mainfile` — that renames the file)
4. Preview: open `final_main_scene.blend` → `bpy.ops.wm.revert_mainfile()` to reload links

### Rebuilding a piece from scratch
Use `bpy.ops.wm.read_homefile(use_empty=True)` to clear, then rebuild all objects,
then `bpy.ops.wm.save_as_mainfile(filepath=...)` to save into `final1-blender/`.

**Critical:** Each piece file must have exactly ONE collection with the correct name
(e.g. `MonkeyFlyingBar`). Duplicate collection names (e.g. `MonkeyFlyingBar.001`)
cause the main scene to link the empty one instead of the real one.

### Rendering for review
```python
sc.render.engine = 'BLENDER_EEVEE'  # fast, good enough for draft
# If scene has no World (sc.world is None), add a sun light:
bpy.ops.object.light_add(type='SUN', location=(0,0,5))
bpy.context.view_layer.objects.active.data.energy = 3
bpy.ops.render.render(write_still=True)
```
Save to `renders/` (`final/`, `drafts/`, or `animation/`) with descriptive names.

---

## Key Blender Patterns

### SHS square prism (structural posts, rails, braces)
```python
def mk_shs(p1, p2, half_sz, name=None, ext1=0, ext2=0):
    p1, p2 = Vector(p1), Vector(p2)
    d = (p2-p1).normalized()
    p1e = p1 - d*ext1          # extend past start
    p2e = p2 + d*ext2          # extend past end
    Le = (p2e-p1e).length

    bpy.ops.mesh.primitive_cube_add(size=1, location=(p1e+p2e)/2)
    obj = bpy.context.view_layer.objects.active
    obj.scale = (half_sz*2, half_sz*2, Le)   # ← scale = FULL dimension, not half
    obj.rotation_euler = d.to_track_quat('Z','Y').to_euler()
    bpy.ops.object.transform_apply(scale=True, rotation=True)
    bev = obj.modifiers.new('Bevel','BEVEL')
    bev.width = 0.004; bev.segments = 3
```
> **ext1/ext2 = 0.025m** at ALL joints in monkey_flying_bar — bars overlap 25mm inside
> each connection, eliminating visible gaps at angled junctions.

### Round cylinder — named, replaces existing (grip bars, rungs, Rail_Z0)
```python
def mk_cyl_named(name, p1, p2, r=0.017, verts=16):
    """Create/replace a named OD cylinder p1→p2, preserving collection membership."""
    p1v, p2v = Vector(p1), Vector(p2)
    L = (p2v - p1v).length
    mid = (p1v + p2v) / 2
    old = bpy.data.objects.get(name)
    colls = list(old.users_collection) if old else [col]
    if old: bpy.data.objects.remove(old, do_unlink=True)
    bpy.ops.mesh.primitive_cylinder_add(radius=r, depth=L, vertices=verts, location=mid)
    obj = bpy.context.view_layer.objects.active
    obj.rotation_euler = (p2v - p1v).normalized().to_track_quat('Z', 'Y').to_euler()
    obj.name = name
    for c in list(obj.users_collection): c.objects.unlink(obj)
    for c in colls: c.objects.link(obj)
    return obj
# OD 34mm: r=0.017 · OD 42mm: r=0.021
```

### Round cylinder — simple (no name tracking needed)
```python
def mk_cyl(p1, p2, r, name=None):
    p1, p2 = Vector(p1), Vector(p2)
    L = (p2-p1).length
    bpy.ops.mesh.primitive_cylinder_add(radius=r, depth=L, vertices=16, location=(p1+p2)/2)
    obj = bpy.context.view_layer.objects.active
    obj.rotation_euler = (p2-p1).normalized().to_track_quat('Z','Y').to_euler()
```

### Horizontal bar (pull-up bar, snake structural bar)
```python
bpy.ops.mesh.primitive_cylinder_add(
    radius=0.017, depth=1.5, vertices=24,
    location=(0, 0, 2.10),
    rotation=(0, math.pi/2, 0)   # ← lay flat along X axis
)
# ⚠️ Do NOT call transform_apply(rotation=True) — it doubles the Z offset
```

### Bezier curve with smooth 90° bends (snake wave bar, dip bar, side grips)
```python
# κ = 0.5523 — Bezier handle ratio for a circular 90° arc
def corner_pair(cx, cy, cz, ind, outd, R):
    """Returns (anchor_pt_dict, depart_pt_dict) for one 90° bend.
    ind = unit vector of incoming direction
    outd = unit vector of outgoing direction
    R = bend radius (CLR)
    """
    kR = R * 0.5523
    ax = cx - R*ind[0];  ay = cy - R*ind[1];  az = cz - R*ind[2]   # arc entry
    dx = cx + R*outd[0]; dy = cy + R*outd[1]; dz = cz + R*outd[2]  # arc exit
    ap = dict(co=(ax,ay,az), lt='VECTOR', rt='FREE',
              lh=None, rh=(ax+kR*ind[0], ay+kR*ind[1], az+kR*ind[2]))
    dp = dict(co=(dx,dy,dz), lt='FREE', rt='VECTOR',
              lh=(dx-kR*outd[0], dy-kR*outd[1], dz-kR*outd[2]), rh=None)
    return ap, dp

# Usage — snake side U-grip (z_lo=0.100, x=-1.038, local object offset=(1.050,-2.483,0)):
# p1 = V(-1.038, 3.000, z_lo)          ← bottom weld on post face (y=3.000 local)
# arc1 = corner_pair(-1.038, 2.750, z_lo,    (0,-1,0), (0,0,1), 0.100)
# arc2 = corner_pair(-1.038, 2.750, z_lo+0.250, (0,0,1), (0,1,0), 0.100)
# p6 = V(-1.038, 3.000, z_lo+0.250)    ← top weld on post face

# Apply points to Bezier spline:
cd = bpy.data.curves.new('name', 'CURVE')
cd.dimensions = '3D'; cd.bevel_depth = 0.017; cd.bevel_resolution = 6; cd.use_fill_caps = True
sp = cd.splines.new('BEZIER')
sp.bezier_points.add(n_pts - 1)
for i, pt in enumerate(points):
    bp = sp.bezier_points[i]
    bp.co = pt['co']
    bp.handle_left_type  = pt['lt']
    bp.handle_right_type = pt['rt']
    if pt['lh']: bp.handle_left  = pt['lh']
    if pt['rh']: bp.handle_right = pt['rh']
```

### NURBS curve (alternative for smooth paths)
```python
cd = bpy.data.curves.new('name', 'CURVE')
cd.dimensions = '3D'
cd.bevel_depth = 0.017        # round cross-section radius
cd.bevel_resolution = 6
cd.use_fill_caps = True
sp = cd.splines.new('NURBS')
sp.points.add(n - 1)
for i, (x,y,z) in enumerate(pts):
    sp.points[i].co = (x, y, z, 1.0)   # w=1.0 always
sp.use_endpoint_u = True
sp.order_u = 3                # quadratic: smooth but not too loose
```

### Move object to collection
```python
def to_col(obj, col):
    for c in list(obj.users_collection): c.objects.unlink(obj)
    col.objects.link(obj)
```

---

## Common Mistakes to Avoid

| Mistake | Why it breaks | Fix |
|---|---|---|
| `transform_apply(rotation=True)` on horizontal cylinder | Doubles Z offset — bar appears at z≈4m | Keep rotation as object property |
| `obj.scale = (half_sz, half_sz, L/2)` | SHS gets half the intended size | Use `(half_sz*2, half_sz*2, L)` |
| `bpy.data.libraries.write()` for piece files | Creates library-only file — opens empty | Use `save_as_mainfile()` |
| Duplicate collection names in .blend | main_scene links the empty first one | Rebuild piece file clean |
| Zone 2 rung spacing in horizontal Y | Rungs look too sparse | Measure 20cm along slope: `step_y = 0.20 × (dY/slope)` |
| Forgetting `ext1/ext2` on monkey bar SHS | Visible gaps at all angled joints | Pass `ext1=EXT, ext2=EXT` where `EXT=0.025` |
| Zone 3 rung at y=3.0 | Double rung at zone 3/4 boundary | Zone 3 ends at y=2.8, Zone 4 starts at y=3.0 |
| `sc.world is None` when rendering | Black render — no lighting | Add SUN light with `bpy.ops.object.light_add(type='SUN')` |
| Rail_Z0 as SHS | Zone 0 entry rails are grip bars — SHS has sharp edges | Rail_Z0_Cross/L/R = OD 34mm cylinder (same as rungs) |
| Editing old files in `models/` root | Not the current version | Always open from `models/final1-blender/` |

---

## Physical Constraints (from project brief)

- **Total plot**: ~6×5m = 30m²
- **Effective equipment area**: ~5×4m = 20m² (after margin)
- **Users**: adult (พี่เขา) + child (~5 years old)
- **Budget**: ~150,000 THB · ประมาณการปัจจุบัน ~89,000 THB (งบเหลือ ~61,000)
- **Outdoor**: galvanized steel ทั้งหมด — ไม่ต้องพ่นสีกันสนิม

### Safety standards (EN 1176 reference)
- Fall zone ≥ 1.5m around all equipment
- Bar spacing: <9cm or >23cm (no head-entrapment zone)
- Low bar for child: 130–140cm
- Rubber flooring: EPDM 25mm minimum under all equipment

---

## Equipment Summary

| Piece | File (in `final1-blender/`) | Height | Bar OD | Key spec |
|---|---|---|---|---|
| Pull-up bar | `pullup_bar_v2.blend` | 2.30m posts · bar z=2.20m | 34mm round | SHS 76×76mm wall 3.2mm · child bar z=1.50m |
| Snake bar | `snake_bar_v5.blend` | 2.10m posts · bar z=2.00m | 34mm grip · **42mm straight** | 2m wide · wave bar 4 U-shapes · **4 U-grips/ข้าง** (แยกชิ้น) · Bar_Straight 42mm (spec+model sync แล้ว 13/06) |
| Dip bar | `dip_bar_v3.blend` | 1.20m | 42mm round | 3 frames · 60cm + 50cm widths · nub C-handle R=80mm |
| Monkey+Flying bar | `monkey_flying_bar_v4.blend` | post tops: 1.0/2.0/2.7m | 34mm round rungs | 5m long × 1.00m wide · 5 zones · Rail_Z0 = OD 34mm |
| Floor (slab) | `floor_v1.blend` | 0.30m | — | 6×5m คอนกรีต |
| Rubber floor (PIECE 5) | — | 25mm (≈1") | — | EPDM ~20m² · = datum z=0 (ระดับยืน) · ⚠️ CFH 25mm ~1.0–1.4m → ใต้ monkey/pull-up อาจต้อง 40–50mm |

> **ฐานราก (v3 §ฐานราก):** เสา/ขาหยั่งพื้นทุกชิ้น **ตัดยาวขึ้น +25mm** (เผื่อยาง) · base plate **9mm** + anchor **M12 (1/2")×4"** + ฝาปิด **3mm** · รวมทั้งโปรเจกต์ = **21 เพลท · 72 สลัก · 15 ฝา** (SHS76→210², SHS50→180², dip foot→170×120; 4 สลัก/เสา, 2 สลัก/ขา dip)

---

## Monkey Flying Bar — Zone Reference

```
Y:  −1──────0────────1────────2────────3────────4
    Zone 0  Zone 1   Zone 2   Zone 3   Zone 4
Z:  [1.00m] [1.00m flat] [↗45°→2.00m] [2.00m flat] [↗35°→2.70m]

Post heights (tops):
  y=−1, 0, 1 → 1.00m   y=2 → 2.00m   y=3 → 2.70m (triangle apex)

Zone 0 (y=−1→0, z=1.00m) — entry frame:
  Post_pre_y0 L/R (SHS 50×50mm wall 2.3mm, h=1.00m)
  Rail_Z0_Cross (OD 34mm, cross brace y=−1) + Rail_Z0_L/R (OD 34mm, side rails)
  ← Rail_Z0 เป็น OD 34mm ไม่ใช่ SHS เพราะผู้ใช้ต้องจับ

Triangle brace (Zone 4):
  Post_y3 (vertical) + Tri_Horiz (horizontal, z=2.70m) = right angle at apex
  Rail_Z4 (hypotenuse, 35°) · Z4_04 at (y=4, z=2.70m) = cross cap
```

Round elements (grip): rungs Z1–Z4, front ladder, side ladder, **Rail_Z0_Cross/L/R**
SHS elements (structural): all posts, Rail_Z1–Z4, Tri_Horiz

---

## Pipe Size Standards (Thai market)

| Nominal | OD จริง | ใช้กับ | มาตรฐาน |
|---------|---------|--------|---------|
| 1" BSP | **34mm** | rungs, grip bars, Rail_Z0 | หาได้ทั่วไป |
| 1¼" BSP | **42mm** | dip bar frame + nub · snake Bar_Straight | หาได้ทั่วไป |
| 1½" BSP | 48mm | — (ไม่ใช้ในโปรเจกต์นี้) | — |

> OD 45mm **ไม่มีในมาตรฐานสากล** — ถ้าร้านเสนอ "45mm" = อาจวัด OD จริงหรือ nominal ผิด ให้ยืนยัน

---

## Bend Radius Reference

| OD | min R (2×OD) | standard R (3×OD) | ใช้ในโปรเจกต์ |
|----|-------------|------------------|--------------|
| 34mm | 68mm | **100mm** ← ใช้ | wave bar, side grips (100mm) |
| 42mm | 84mm | **126mm** ≈ 120mm ← ใช้ | dip frame far side (120mm), nub (80mm*) |

> *Nub R=80mm ต่ำกว่า 2×OD เล็กน้อย — ต้องใช้ light mandrel, แจ้งร้านล่วงหน้า
