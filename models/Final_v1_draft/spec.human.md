## PIECE 1 — Pull-up Bar v2

### วัสดุที่ใช้

| ชิ้น              | รูปทรง    | สเปกสุดท้าย                               | หมายเหตุ                                        |
| ----------------- | --------- | ----------------------------------------- | ----------------------------------------------- |
| Post (ทุกต้น)     | SHS กล่อง | **3"×3" (76×76mm) wall 3.2mm galvanized** | เหล็กกล่องกัลวาไนซ์ สั่งร้านว่า "3×3 หนา 3.2mm" |
| Bar จับ (ทุกบาร์) | ท่อกลม    | **OD 34mm wall ~3.2mm galvanized**        | ท่อกลมกัลวาไนซ์ 1"                              |

> วัสดุทั้งหมดเป็น **galvanized steel** — ไม่ต้องพ่นสีกันสนิม ทนกลางแจ้งระยะยาว

---

### โครงสร้าง

| ชิ้น            | รูปทรง         | ขนาด        | ความสูง   | ตำแหน่ง X         |
| --------------- | -------------- | ----------- | --------- | ----------------- |
| Post_Left       | SHS 76×76mm    | wall 3.2mm  | 2.30m     | x = −0.75m        |
| Post_Right      | SHS 76×76mm    | wall 3.2mm  | 2.30m     | x = +0.75m        |
| Post_Child      | SHS 76×76mm    | wall 3.2mm  | 1.60m     | x = −1.75m        |
| Bar_PullUp_High | ท่อกลม OD 34mm | wall ~3.2mm | z = 2.20m | x = −0.75 → +0.75 |
| Bar_PullUp_Low  | ท่อกลม OD 34mm | wall ~3.2mm | z = 1.50m | x = −1.75 → −0.75 |

```
ด้านหน้า (มองจาก Y−):

  [Post_Child]       [Post_Left]        [Post_Right]
   x = −1.75m         x = −0.75m          x = +0.75m
   h = 1.60m          h = 2.30m           h = 2.30m
      │                   │                   │
  ────┤ Bar_Low (1.50m)   │                   │
  z=1.50m            ─────┤ Bar_High (2.20m) ─┤
                      z=2.20m
```

### จุดเชื่อม

- **Bar_PullUp_High** เชื่อมด้านข้างเสา Post_Left และ Post_Right ที่ z = 2.20m (10cm ต่ำกว่ายอดเสา)
- **Bar_PullUp_Low** เชื่อมด้านข้างเสา Post_Child และ Post_Left ที่ z = 1.50m (10cm ต่ำกว่ายอดเสา Post_Child)
- **เสาทุกต้น**: ฐาน base plate เชื่อมติดเสา + anchor bolt ยึดลงพื้นคอนกรีต

### Footprint

กว้างรวม 2.50m (x = −1.75 → +0.75), ลึก ~10cm (ความหนาเสา)

---

### Research Notes — การเลือกขนาดเหล็ก

#### 1. โจทย์ตั้งต้น

แบบ draft แรกใช้ **SHS 100×100mm wall 4.5mm** ซึ่งตั้งขนาดแบบกะๆ ไว้ก่อน พอมาถึงขั้นจะซื้อจริงก็ต้องหาว่าขนาดนี้เหมาะหรือเปล่า และถ้าเปลี่ยนเป็นกัลวาไนซ์ทั้งหมด ควรใช้ขนาดไหน

#### 2. ดูว่าสนามจริงเขาใช้อะไร

ค้นหาจากผู้ผลิต outdoor calisthenics equipment ระดับ commercial พบว่า **Deportesurbanos** (ผู้ผลิต street workout park ในยุโรป) ระบุสเปกชัดเจนว่าใช้ **ท่อกลม OD 114mm** สำหรับเสาหลัก พร้อม anchor base ขนาด 300mm — นี่คือมาตรฐาน EN 1176 สำหรับสนามสาธารณะที่ต้องรับคนหลายคนและแรงกระแทกสูง

→ **ข้อสรุป**: SHS 100×100mm ที่ draft ไว้ใกล้เคียงระดับ commercial park มากเกินไป — สำหรับบ้านส่วนตัว 1–2 คนไม่จำเป็น

#### 3. หาขนาดที่เหมาะกับบ้านส่วนตัว

สำหรับ residential / home gym ข้อมูลจาก DIY builds และ galvanized rig ผู้ผลิตเช่น GetRXD พบว่า **ท่อกลม OD 76mm (3")** wall 3.2mm รับน้ำหนักได้สบายสำหรับผู้ใช้ 1–2 คน รวมถึงโหลดพลวัต (kipping pull-up ≈ 3–5× น้ำหนักตัว) ที่ความสูงเสา 2–2.5m

ตอนนี้มีสองตัวเลือก: ท่อกลม vs ท่อกล่อง — เลือก **ท่อกล่อง SHS** เพราะเชื่อมง่ายกว่า (หน้าตัดเรียบ ไม่ต้องตัดโค้งรับ), ดูสะอาดกว่า, และราคาใกล้กัน

#### 4. ตรวจสอบความหนาในตลาดไทย

SHS 3"×3" (= 76×76mm จริงๆ ไม่ใช่ 80mm เป๊ะ) กัลวาไนซ์ในไทยมีสองความหนาหลัก:

- **2.3mm** — มาตรฐาน มอก. หาง่ายทุกร้าน ใช้ในงานรั้ว ประตู หลังคา
- **3.2mm** — ต้องหาจากร้านเฉพาะ (เช่น Aplus Watsadu) แต่มีขาย ใช้ในงานโครงสร้างรับน้ำหนัก

สำหรับเสา pull-up bar ที่ต้องรับแรงดึงซ้ำๆ กลางแจ้ง 2.3mm tight เกินไป → เลือก **3.2mm**

มาตรฐาน EU/UK (EN 10210 S235) สำหรับ structural SHS ขนาดนี้ก็ระบุ 3–4mm เช่นกัน ตรงกัน

#### 5. บาร์จับ OD 34mm — ไม่ต้องเปลี่ยน

Eleiko ผู้ผลิต commercial pull-up bar ระดับโลก ใช้ **33mm** เป็น optimal grip — 34mm ในแบบเหมาะมือและตรงกับมาตรฐานอุตสาหกรรม ไม่ต้องปรับ

---

### แหล่งอ้างอิง

- [Deportesurbanos — Outdoor Pull Up Bar spec (post OD 114mm)](https://deportesurbanos.com/en/producto/outdoor-pull-up-bar/)
- [Eleiko Prestera Straight Pull-up Bar (bar OD 33mm)](https://eleiko.com/en/equipment/outdoor/galvanized/3085515-01-eleiko-prestera-straight-pull-up-bar-outdoor)
- [GetRXD — Galvanized Outdoor Pull Up Rigs](https://www.getrxd.com/pull-up-rigs/galvanized-outdoor-pull-up-rigs.html)
- [The Metal Store UK — Build Your Own Galvanised Pull-Up Bar](https://www.themetalstore.co.uk/content-hub/tube-clamp-guides/pull-up-bar)
- [SB Steel TH — เหล็กกล่องเหลี่ยมกัลวาไนซ์ 3"×3" 2.3mm](https://www.sbsteel.co.th/product/%E0%B9%80%E0%B8%AB%E0%B8%A5%E0%B9%87%E0%B8%81%E0%B8%81%E0%B8%A5%E0%B9%88%E0%B8%AD%E0%B8%87%E0%B9%80%E0%B8%AB%E0%B8%A5%E0%B8%B5%E0%B9%88%E0%B8%A2%E0%B8%A1%E0%B8%81%E0%B8%B1%E0%B8%A5%E0%B8%A7-13/)
- [Aplus Watsadu TH — เหล็กกัลวาไนซ์ GI 3"×3" หนา 1.5–3.2mm](https://www.aprimeplus.com/product-page/%E0%B9%80%E0%B8%AB%E0%B8%A5-%E0%B8%81%E0%B8%81-%E0%B8%A5%E0%B8%A7%E0%B8%B2%E0%B9%84%E0%B8%99%E0%B8%8B-gi-3x3-%E0%B8%99-%E0%B8%A7-%E0%B8%AB%E0%B8%99%E0%B8%B2-2-0-%E0%B8%A1%E0%B8%A1)

---

## PIECE 2 — Snake Bar v5

### วัสดุที่ใช้

| ชิ้น                   | รูปทรง           | สเปกสุดท้าย                               | หมายเหตุ                                                                         |
| ---------------------- | ---------------- | ----------------------------------------- | -------------------------------------------------------------------------------- |
| Post (ทั้งสองต้น)      | SHS กล่อง        | **3"×3" (76×76mm) wall 3.2mm galvanized** | เหมือน Pull-up Bar                                                               |
| Bar_Snake_Straight     | ท่อกลม           | **OD 34mm wall ~3.2mm galvanized**        | structural bar แนวนอน                                                            |
| Bar_Snake_Wave         | ท่อกลม (ดัดโค้ง) | **OD 34mm wall ~3.2mm galvanized**        | bend R=**100mm** ที่มุม U ทุกจุด — ยกเว้นปลาย U1/U4 ที่ต่อเสา: ปักตรง ไม่มี bend |
| Bar_Snake_Side_L / \_R | ท่อกลม (ดัดโค้ง) | **OD 34mm wall ~3.2mm galvanized**        | side climbing bars                                                               |

> วัสดุทั้งหมดเป็น **galvanized steel** — ไม่ต้องพ่นสีกันสนิม ทนกลางแจ้งระยะยาว

---

### โครงสร้าง

| ชิ้น               | รูปทรง         | ขนาด                     | ตำแหน่ง / ความสูง       |
| ------------------ | -------------- | ------------------------ | ----------------------- |
| Post_Snake_Left    | SHS 76×76mm    | wall 3.2mm, สูง 2.10m    | x = −1.038m             |
| Post_Snake_Right   | SHS 76×76mm    | wall 3.2mm, สูง 2.10m    | x = +1.038m             |
| Bar_Snake_Straight | ท่อกลม OD 34mm | ยาว 2.00m (clear)             | z = **1.966m** (center) — ต่ำกว่า Wave bar 1×OD = 34mm |
| Bar_Snake_Wave     | ท่อกลม OD 34mm | path **~5.73m**, bend R=100mm | z = **2.000m** — วางบน Straight bar, สัมผัสกันที่ z=1.983m |
| Bar_Snake_Side_L   | ท่อกลม OD 34mm | 4 U-grips, −Y direction  | z = 0.10 → 1.85m        |
| Bar_Snake_Side_R   | ท่อกลม OD 34mm | 4 U-grips, −Y direction  | z = 0.10 → 1.85m        |

> **Post x-position:** เสาแต่ละต้นมีขนาด 76×76mm → half-width = 38mm = 0.038m
> Center span = 2.00m ÷ 2 = 1.000m (วัดจากแกนกลางถึงหน้าเสาด้านใน)
> ดังนั้น Post centerline x = ±(1.000 + 0.038) = **±1.038m**
>
> **การวัด:**
>
> - **Bar_Snake_Straight ยาว 2.00m** = วัดจาก **หน้าเสาด้านในถึงหน้าเสาด้านใน** (clear span) · z center = **1.966m**, top = **1.983m**
> - **Bar_Snake_Wave X span** = วัดจาก **centerline เสาถึง centerline เสา** = 2.076m (ท่อปักเข้าแกนกลางเสา) · z center = **2.000m**, bottom = **1.983m**
> - **Structural design:** Straight bar อยู่ต่ำกว่า Wave bar พอดี 34mm (= 1×OD) → สัมผัสกันที่ z=1.983m → เชื่อมยึดตลอดความยาว Wave bar รับแรงดึง/ใช้งาน Straight bar รับ structural load หลัก

#### Wave bar — รูปทรงจากด้านบน (XY plane)

```
+Y  │   ╭──────U1──────╮             ╭──────U3──────╮
    │   │   (+Y peak)  │             │   (+Y peak)  │
 0  ├───┤              ├─────────────┤              ├───┤
    │   │              │  (−Y peak)  │              │  (−Y peak)
-Y  │   │              ╰──────U2─────╯              ╰──────U4────╯
    │ ↑                                                         ↑ │
  ปักตรง (38mm, ไม่มี bend)                       ปักตรง (38mm, ไม่มี bend)
    x: -1.038        -0.538         +0.038         +1.038
      (Post_L)                                     (Post_R)
```

- 4 U-shapes สลับทิศ: U1 & U3 ยื่น +Y, U2 & U4 ยื่น −Y
- แต่ละ U: กว้าง 50cm (ตามแนว X), ลึก 50cm (ตามแนว Y)
- มุมโค้ง 90° ทุกจุด, bend radius = **100mm** (CLR)
- **ยกเว้น U1 (ปลายซ้าย) และ U4 (ปลายขวา):** ปลายที่เชื่อมเสาไม่มี bend — bar วิ่งตรงตามแนว X เข้าแกนกลางเสา 38mm (x = ±1.038m) → รอยเชื่อมตั้งฉากกับหน้าเสา แข็งแรงกว่าการดัดโค้ง

#### Side bars (v5 spec)

- ทั้งสองข้างดันออก **ทิศ −Y** เหมือนกัน (ไม่ mirror)
- 4 U-grips ต่อเสา, pitch 25cm ตามแนวตั้ง
- ปลายบน z = 1.85m (15cm ต่ำกว่า wave bar), ปลายล่าง z = 0.10m (10cm เหนือพื้น)
- **ไม่ติดพื้น ไม่เชื่อมกับ wave bar** — tack-weld ที่เสาตามแนวตั้ง

---

#### Wave bar — ขนาดรายละเอียด (สำหรับงานดัดท่อ)

> ท่อ OD 34mm wall 3.2mm galvanized · ดัดในระนาบแนวนอน (XY plane) · z คงที่ที่ 2.000m ตลอด

| # | ชิ้นส่วน | ทิศทาง | ความยาว (mm) | หมายเหตุ |
|---|----------|---------|--------------|----------|
| 1 | ปักเข้าเสาซ้าย | +X (เข้าเสา) | **38** | ไม่มี bend — ปลายตรง เชื่อม fillet ที่หน้าเสา |
| 2 | ตรงต้น (ซ้าย) | +Y | **400** | จากหน้าเสาถึงจุดเริ่ม arc แรก |
| 3 | **Arc 1** (+Y → +X) | โค้ง 90° | ≈ 157 | R=100mm |
| 4 | ยอด U1 | +X | **300** | flat top |
| 5 | **Arc 2** (+X → −Y) | โค้ง 90° | ≈ 157 | R=100mm |
| 6 | ช่อง U1→U2 | −Y | **800** | ตรงยาว เชื่อมต่อ top↔bottom |
| 7 | **Arc 3** (−Y → +X) | โค้ง 90° | ≈ 157 | R=100mm |
| 8 | ล่าง U2 | +X | **300** | flat bottom |
| 9 | **Arc 4** (+X → +Y) | โค้ง 90° | ≈ 157 | R=100mm |
| 10 | ช่อง U2→U3 | +Y | **800** | ตรงยาว |
| 11 | **Arc 5** (+Y → +X) | โค้ง 90° | ≈ 157 | R=100mm |
| 12 | ยอด U3 | +X | **300** | flat top |
| 13 | **Arc 6** (+X → −Y) | โค้ง 90° | ≈ 157 | R=100mm |
| 14 | ช่อง U3→U4 | −Y | **800** | ตรงยาว |
| 15 | **Arc 7** (−Y → +X) | โค้ง 90° | ≈ 157 | R=100mm |
| 16 | ล่าง U4 | +X | **300** | flat bottom |
| 17 | **Arc 8** (+X → +Y) | โค้ง 90° | ≈ 157 | R=100mm |
| 18 | ตรงปลาย (ขวา) | +Y | **400** | |
| 19 | ปักเข้าเสาขวา | +X (เข้าเสา) | **38** | ไม่มี bend — ปลายตรง |
| | **รวม** | | **≈ 5730** | **≈ 5.73m** |

```
สรุปโปรไฟล์ wave bar (มองจากบน):

  Post_L                                               Post_R
    │←38→│←─── 400 ───→╮ 300 ╭────── 800 ──────╮ 300 ╭─── 400 ───→│←38→│
    │    │              ╰─────╯                  ╰─────╯             │    │
 z=2.0  face          Arc R=100                Arc R=100           face  z=2.0
    x: -1.038        -1.000                                        +1.000  +1.038
```

จุดสำคัญสำหรับช่าง:
- **8 bends ทั้งหมด** ทุก bend = **90° ในระนาบนอน** R=100mm (≈3×OD) → ไม่ต้อง mandrel พิเศษ
- **ปลายทั้งสองตรง** (ไม่ดัด) ยาว 38mm → สอดเข้าช่องที่เจาะในเสา SHS แล้วเชื่อม
- หลังจากดัดแต่ละ bend → **เส้นตรงต่อทันที** ไม่มีโค้งต่อเนื่อง (R fixed 100mm)

---

#### Side bar — ขนาดรายละเอียด (per bar; ซ้าย/ขวา สเปกเหมือนกัน)

> ท่อ OD 34mm wall 3.2mm galvanized · ดัดในระนาบแนวตั้ง (YZ plane) · x คงที่ที่หน้าเสา (x=±1.000m local)
> U-grips ยื่นในทิศ **−Y** (ออกจากโครงสร้างมาหาผู้ใช้) ทั้งซ้ายและขวา

| # | ชิ้นส่วน | ทิศทาง | ความยาว (mm) | z เริ่ม → จบ | หมายเหตุ |
|---|----------|---------|--------------|-------------|----------|
| – | **จุดยึดเสา** (ล่างสุด) | weld | – | z = **0.100m** | tack-weld ที่เสา |
| A1 | ตรงเข้า Grip 1 | −Y | **150** | 0.100 | จากหน้าเสา (y=0) ถึง arc เริ่ม (y=−150mm) |
| A2 | **Arc** (−Y → +Z) | โค้ง 90° | ≈ 157 | | R=100mm |
| A3 | ก้น Grip 1 | +Z | **50** | | flat bottom ที่ y=−250mm จากหน้าเสา |
| A4 | **Arc** (+Z → +Y) | โค้ง 90° | ≈ 157 | | R=100mm |
| A5 | ตรงออก Grip 1 | +Y | **150** | → 0.350m | กลับหน้าเสา |
| – | **จุดยึดเสา** Grip 1 | weld | – | z = **0.350m** | |
| B | เชื่อมขึ้นไปเสา | +Z | **250** | 0.350 → 0.600m | ตรงยาวที่หน้าเสา |
| – | **จุดยึดเสา** Grip 2 | weld | – | z = **0.600m** | |
| ↑ ทำซ้ำ Grip 3 และ 4 | | | | | z = 0.850 / 1.100 / 1.350 / 1.600m |
| – | **จุดยึดเสา** (บนสุด) | weld | – | z = **1.850m** | |

สรุปต่อ 1 bar:
- **4 U-grips** × 664mm + **3 ช่วงเชื่อมเสา** × 250mm = **≈ 3.41m** ต่อ bar (×2 = ≈6.82m รวม)
- Grip ยื่น −Y จากหน้าเสา: **250mm** (= 100+50+100 → arc + flat + arc)
- Grip span ในแนวตั้ง: **250mm** ต่อ grip (z_lo → z_hi)
- Flat bottom ของแต่ละ grip (ที่ y=−250mm): **50mm**
- Radius ทุก bend: **R=100mm**
- **8 จุดยึดเสาต่อ bar** (บน-ล่างของแต่ละ grip) → tack-weld

```
Side bar profile (มองจาก X axis, เห็น YZ plane):

  z=1.850 ─── weld ─── weld ─── weld ─── weld ─── weld ─── weld ─── weld ─── weld
  z=1.600 ──╮ (Grip 4) ─ flat 50mm ─ (arc) ──╯
  z=1.350 ──╮ (Grip 3) ─ flat 50mm ─ (arc) ──╯
  z=1.100
  z=0.850 ──╮ (Grip 2)
  z=0.600
  z=0.350 ──╮ (Grip 1) ─ flat 50mm ─ (arc) ──╯
  z=0.100 ─── weld
             y=0    y=−150  y=−250  y=−150    y=0
            (หน้าเสา)                        (หน้าเสา)
```

---

### จุดเชื่อม

- **Bar_Snake_Straight** เชื่อมด้านข้างยอดเสาทั้งสอง (10cm ต่ำจากยอด)
- **Bar_Snake_Wave** เชื่อมปลายสองข้างที่เสา (ปักตรง 38mm) + **เชื่อมด้านล่าง Bar_Snake_Straight ตลอดจุดสัมผัส** (z=1.983m) ที่ตำแหน่ง x = −0.50, 0, +0.50 อย่างน้อย
- **Side bars** tack-weld ตามความสูงเสา (ทุก U-grip จุด)
- **เสาทั้งสอง** ฐาน base plate + anchor bolt

### Footprint

กว้าง 2.00m (x = −1.0 → +1.0, clear), ลึก ~1.0m (wave bar ยื่น ±50cm ในแนว Y)

---

### Research Notes — การเลือกขนาดเหล็ก

#### 1. โจทย์ตั้งต้น

Snake bar มีสองคำถามต่างจาก pull-up bar: (1) เสาต้องรับ wave bar ที่มีน้ำหนักยื่นออกด้านข้าง ±50cm ด้วย และ (2) wave bar ดัดโค้ง — ต้องรู้ว่า bend radius เท่าไหร่ถึงจะงานได้จริงและดูดี

#### 2. ขนาดเสา

ค้นหาจาก Deportesurbanos (ผู้ผลิต commercial street workout park) พบว่า snake bar ใช้เสาเดียวกับ pull-up bar ทุกประการ — **round galvanized OD 114mm** สำหรับระดับสาธารณะ สรุปว่าโหลดของ snake bar ไม่ได้ต่างจาก pull-up bar มากนัก เสา SHS 76×76mm wall 3.2mm ที่เลือกแล้วจึงเพียงพอเช่นกัน

#### 3. ขนาด wave bar

Deportesurbanos และ BarManiaPro ระบุตรงกันว่า snake bar ใช้ท่อกลม **OD 33.7mm** ซึ่งเป็นขนาดมาตรฐาน 1" BSP/NPS — ตรงกับ 34mm ในแบบทุกประการ ไม่ต้องเปลี่ยน

#### 4. Bend radius — ประเด็นหลัก

สำหรับท่อ OD 34mm มีสามระดับของ bend radius ที่ต้องรู้:

- **68mm (2×OD)** — ขั้นต่ำสุด ต้องใช้ mandrel ช่วย มุมโค้งแน่น อาจบีบท่อ
- **100mm (3×OD)** — มาตรฐาน rotary-draw bending ทั่วไป โค้งสวย ไม่บีบ ช่างงานทั่วไปทำได้
- **150mm+ (4.5×OD)** — หลวมเกิน มุมดูกว้าง ไม่เหมาะกับ U-shape ที่ต้องการชัดเจน

spec เดิมระบุ "80–100mm" ซึ่งค่าล่าง (80mm ≈ 2.35×OD) อยู่ระหว่าง 2D และ 3D — อาจเป็นปัญหาถ้าช่างไม่ใช้ mandrel จึงปรับเป็น **100mm fixed** เพื่อให้ชัดเจนและทำงานได้โดยไม่ต้องพึ่ง mandrel พิเศษ

#### 5. U-depth 50cm

BarManiaPro commercial snake bar มี 5 snakes ที่ depth ใกล้เคียงกัน — 50cm เป็น standard สำหรับ adult user ใช้ได้ ไม่ต้องเปลี่ยน

---

### แหล่งอ้างอิง

- [Deportesurbanos — Snake Bar spec (post OD 114mm, bar OD 33.7mm)](https://deportesurbanos.com/en/producto/snake-bar-calisthenics/)
- [BarManiaPro — Snake Bar (5 snakes OD 33.7mm)](https://barmaniapro.com/product/snake-bar/)
- [calisthenics-parks.com — Wave/Snake Bars overview](https://calisthenics-parks.com/equipments/30-en-wave-bars-snake-bars)
- [Xometry — Tube Bending Design Tips (CLR ≥ 2×OD guideline)](https://www.xometry.com/resources/tube/tube-bending-design-tips/)
- [Pro-Tools — Choosing the Right Centerline Radius](https://pro-tools.com/blogs/protoolsusa/19204299-choosing-the-right-centerline-radius-for-your-next-project)
- [Lister Tube — Tube Bending Size Guide (PDF)](https://www.listertube.com/wp-content/uploads/2022/03/ListerTube_A5-Tube-Bending-Size-Guide_digital.pdf)

---

## PIECE 3 — Dip Bar v3

### วัสดุที่ใช้

| ชิ้น                | รูปทรง           | สเปกสุดท้าย                        | หมายเหตุ                                       |
| ------------------- | ---------------- | ---------------------------------- | ---------------------------------------------- |
| Frame (ทั้ง 3 ชิ้น) | ท่อกลม (ดัดโค้ง) | **OD 42mm wall ~3.2mm galvanized** | ท่อกลมกัลวาไนซ์ 1¼" — 1 ชิ้นต่อเนื่องต่อ frame |

> วัสดุทั้งหมดเป็น **galvanized steel** — ไม่ต้องพ่นสีกันสนิม ทนกลางแจ้งระยะยาว

---

### โครงสร้าง

> **การวัดตำแหน่ง frame:** ระยะห่างระหว่าง frame วัดจาก **หน้าท่อด้านนอกถึงหน้าท่อด้านนอก** (clear distance)
> OD 42mm → center-to-center = clear + 42mm

| ชิ้น      | รูปทรง                  | ขนาด        | ความสูง | ตำแหน่ง X (centerline) |
| --------- | ----------------------- | ----------- | ------- | ---------------------- |
| DipBar_01 | ท่อกลม OD 42mm, ∩ frame | กว้าง 0.75m | 1.20m   | x = 0.000m             |
| DipBar_02 | ท่อกลม OD 42mm, ∩ frame | กว้าง 0.75m | 1.20m   | x = 0.642m             |
| DipBar_03 | ท่อกลม OD 42mm, ∩ frame | กว้าง 0.75m | 1.20m   | x = 1.184m             |

```
ด้านหน้า (มองจาก Y−):

  ┐────────────╮  ← z=1.20m (top grip)
  │ sharp(nub) ╰ R=120mm
  │              │
  │              │
  ○              ○ ← z=0.00m (พื้น)
 y=0           y=0.75m
```

> **Corner asymmetric:**
> - y = 0 (ฝั่ง nub): **sharp joint** — ไม่มี bend ที่นี่ เพราะ Nub จะมาเชื่อมต่อตรงจุดนี้พอดี (weld junction)
> - y = 0.75 (ฝั่งไกล): **R = 120mm** (≈ 3×OD — ช่างทำได้ไม่ต้อง mandrel พิเศษ)

### ระยะห่างระหว่าง frame

| ช่วง        | Clear distance | Center-to-center | ลักษณะการใช้งาน             |
| ----------- | -------------- | ---------------- | --------------------------- |
| Frame 1 → 2 | **60cm**       | 64.2cm           | grip กว้าง — chest/wide dip |
| Frame 2 → 3 | **50cm**       | 54.2cm           | grip แคบ — tricep dip       |

> Clear distance = ระยะห่างระหว่างหน้าท่อด้านนอกของ frame สองชิ้นที่อยู่ติดกัน

### Nub — Handle ด้านข้าง (ต่อ frame ×3)

> Nub = C-handle โผล่ออก −Y จากหน้านอก frame แต่ละตัว ทำหน้าที่ **mounting-assist grip** — จับเพื่อขึ้น/ลงท่า dip และเกี่ยว resistance band

| ชิ้น      | รูปทรง              | สเปก                            | ตำแหน่ง                          |
| --------- | ------------------- | ------------------------------- | -------------------------------- |
| Nub_01/02/03 | ท่อกลม OD 42mm, C-handle | wall ~3.2mm galvanized | ติดหน้านอก frame (y = 0) แต่ละตัว |

#### ขนาดรายละเอียด

| พารามิเตอร์ | ค่า | หมายเหตุ |
|---|---|---|
| Tube OD | **42mm** | เหมือน frame หลัก (ไม่ต้องสั่งท่อเพิ่ม) |
| Protrusion D | **250mm** | ยื่นในทิศ −Y จากหน้า frame; ช่องจับหลัง centerline ≈ 229mm → มือเต็มๆ ผ่านสบาย |
| Height H | **200mm** | z = 1.000m → 1.200m (ตั้งแต่ 20cm ต่ำจากยอดถึงยอด frame) |
| Corner radius R | **80mm** | 2 bends 90° ในระนาบ YZ (ดูเหตุผลใน Research Notes ด้านล่าง) |

#### โปรไฟล์ทาง YZ (มองจาก X axis)

```
z=1.200 ── 170mm ──╮                  ╰── 170mm ─── z=1.200
                    ╰─ arc R=80 ─ 40mm ─ arc R=80 ─╯
                       (−Y→−Z)         (−Z→+Y)
z=1.000 ─────────────────────────────────────────── z=1.000
y=0                  y=−0.250                       y=0
```

#### ตารางเส้นทางท่อ (1 nub)

| # | ส่วน | ทิศ | ความยาว (mm) |
|---|------|-----|--------------|
| 1 | เชื่อมหน้า frame ถึงจุดเริ่ม arc | −Y | **170** |
| 2 | **Arc บน** (−Y → −Z) 90° | โค้ง | ≈ **126** (= π/2 × 80) |
| 3 | ตรงแนวตั้ง | −Z | **40** |
| 4 | **Arc ล่าง** (−Z → +Y) 90° | โค้ง | ≈ **126** |
| 5 | กลับหน้า frame | +Y | **170** |
| | **รวม 1 nub** | | **≈ 632mm** |
| | **รวม 3 nub** | | **≈ 1,896mm ≈ 1.9m** |

#### จุดยึด

- เชื่อม fillet ที่หน้านอก frame (y = 0) ที่ z = 1.000m และ z = 1.200m (2 จุดต่อ nub)
- Nub อยู่ที่ **centerline x** ของ frame ตัวนั้น (x = 0.000 / 0.642 / 1.184m)

---

### จุดยึด

- Frame ทั้ง 3 ชิ้น: ฐานยึดพื้นแยกกัน (ไม่มีโครงเชื่อมกัน)
- Nub: tack-weld 2 จุดต่อ nub ที่หน้านอก frame

### Footprint

กว้าง 1.226m (outer edge to outer edge: x = 0 − 0.021 → 1.184 + 0.021), ลึก 0.75m + nub 0.25m = **ลึกรวม 1.00m** (ฝั่ง −Y ของ Frame 1)

---

### Research Notes — การเลือกขนาดเหล็ก

#### 1. โจทย์ตั้งต้น

แบบ draft ระบุ OD 42mm แต่ไม่มีที่มาชัดเจน ต้องตรวจสอบสองประเด็น: (1) OD 42mm เหมาะกับ dip bar จริงหรือไม่เมื่อเทียบกับมาตรฐานผู้ผลิต และ (2) bend radius ที่ระบุว่า "80–120mm" สำหรับท่อ 42mm ทำได้จริงในไทยหรือเปล่า

#### 2. ดูว่าผู้ผลิต commercial ใช้อะไร

ค้นหาจากผู้ผลิตอุปกรณ์กลางแจ้งระดับ commercial พบข้อมูลที่ชัดเจนที่สุดจาก **KOMPAN** (ผู้ผลิต outdoor fitness park ระดับโลก มาตรฐาน EN 1176) ซึ่งระบุว่าเสา post ของ parallel bars ทำจาก Ø101.6mm pre-galvanized steel ส่วน grip bar ทำจาก hot-dip galvanized steel OD 38mm — และระบุว่า "เส้นผ่านศูนย์กลางนี้ช่วยรองรับข้อมือขณะทำ dip หรือ handstand ได้ดี"

นอกจากนี้ผู้ผลิตเฉพาะทาง เช่น GORNATION และ FitnessKIT ที่ขายอุปกรณ์ระดับ prosumer ต่างใช้ขนาดOD 40–43mm เป็นหลัก

→ **ข้อสรุป**: OD 42mm ที่ draft ไว้อยู่ในช่วง 38–43mm ซึ่งเป็น sweet spot ของ commercial และ prosumer dip bar ทุกยี่ห้อ — **ไม่ต้องเปลี่ยน**

#### 3. ทำไม OD 42mm ดีกว่า OD 34mm ที่ใช้กับ pull-up bar

Bar ที่หนาขึ้น (38–45mm) ให้ความสบายมือมากกว่า เหมาะกับมือใหญ่ และช่วยพัฒนา grip strength — ส่วน bar เล็ก (32–35mm) เหมาะกับมือเล็กหรือผู้เริ่มต้น สำหรับ dip bar ข้อมือต้องรับน้ำหนักตัวทั้งหมดในท่า neutral grip (ฝ่ามือหันเข้าหากัน) ซึ่งต่างจาก pull-up bar ที่จับแบบ overhand — ท่อที่หนาขึ้นช่วยกระจายแรงกดที่ข้อมือ ทำให้ทำ L-sit หรือ dip ได้นานขึ้น จึงใช้ขนาดที่ใหญ่กว่า pull-up bar เป็น best practice ของอุตสาหกรรม

#### 4. ระยะห่างระหว่าง frame (grip width)

ตรวจสอบ grip width มาตรฐาน พบว่าช่วงมาตรฐาน dip bar อยู่ที่ 45–60cm ซึ่งเหมาะกับผู้ใหญ่ส่วนใหญ่ — แคบกว่า (45–50cm) เน้น tricep มากขึ้น กว้างกว่า (55–60cm) เปิด chest มากขึ้น

แบบนี้ใช้ 3 frame สร้าง 2 ช่องให้เลือก: กว้าง 60cm (chest dip) และ 50cm (tricep dip) — ทั้งสองอยู่ใน sweet spot พอดี ไม่ต้องเปลี่ยน

#### 5. Bend radius สำหรับ OD 42mm

แบบระบุ "80–120mm" ต้องเช็คว่าค่าล่าง 80mm ทำได้จริงหรือไม่ สำหรับ OD 42mm:

- **84mm (2×OD)** — ขั้นต่ำทางทฤษฎี ต้องใช้ mandrel ช่วย มีความเสี่ยงท่อบีบ
- **126mm (3×OD)** — มาตรฐาน rotary-draw ทั่วไป ช่างงานทั่วไปทำได้ไม่ต้อง mandrel พิเศษradius ขั้นต่ำสำหรับการดัดท่อ OD 42mm คือ 3 เท่าของเส้นผ่านศูนย์กลาง

ตรรกะเดียวกับ Snake Bar — ค่าล่างของช่วงที่ draft ไว้ (80mm) แน่นเกินไปสำหรับช่างทั่วไป จึงปรับเป็น **120mm fixed** ซึ่งอยู่ที่ ≈2.86×OD — ใกล้ 3×OD พอที่ช่างส่วนใหญ่จะทำได้โดยไม่พึ่ง mandrel พิเศษ และยังให้มุมโค้งที่คม สวยงาม

#### 6. Nub — ทำไม bend radius = 80mm (ไม่ใช่ 120mm เหมือน frame หลัก)

Nub เป็น C-handle สูง 200mm (z = 1.0–1.2m) ที่ใช้ท่อ OD 42mm เหมือน frame ซึ่งมี 2 bends 90° ในระนาบ YZ โดยที่ height span ระหว่างสองจุด bend = H = 200mm นั้นกำหนด radius ขั้นสูงที่ fit ได้:

| R | H ขั้นต่ำที่ต้องการ | vet_flat (ส่วนตรงกลาง) | ทำได้จริง? |
|---|---|---|---|
| R = 80mm (1.9×OD) | 2×80 = 160mm | 200−160 = **40mm** ✓ | ✓ fit สบาย |
| R = 100mm (2.4×OD) | 2×100 = 200mm | 200−200 = **0mm** | ✓ semicircle พอดี |
| R = 120mm (2.9×OD) | 2×120 = 240mm | 200−240 = **−40mm** | ✗ ไม่ fit ใน 200mm |

→ R=120mm (ที่ใช้กับ frame หลัก) **ไม่สามารถดัดได้ภายใน H = 200mm** — ต้องใช้ R ≤ 100mm
→ เลือก **R = 80mm** เพราะมี vert_flat = 40mm ให้รูปทรงมีส่วนตรง ดูสะอาดกว่า R=100mm ที่โค้งตลอดแบบ semicircle

ข้อสังเกต: R=80mm ≈ 1.9×OD อยู่ต่ำกว่า threshold 2×OD (84mm) เล็กน้อย — ในทางปฏิบัติสำหรับท่อ OD 42mm wall 3.2mm (D/t ratio ≈ 13) ช่างที่มี rotary-draw bender ขนาด 42mm สามารถดัด R=80mm ได้โดยอาจต้องใช้ mandrel บาง (light mandrel) ช่วย — ซึ่งเครื่องดัดท่อระดับ workshop ทั่วไปในไทยรองรับได้

#### 7. ท่อ galvanized OD 42mm ในตลาดไทย

OD 42mm ตรงกับมาตรฐาน **1¼" nominal pipe** (OD 42.4mm จริง) ซึ่งเป็นขนาดสากลระบบ 42mm ใช้ท่อ OD 42.4mm wall 3.25mm — หาได้จากร้านเหล็กทั่วไปในไทย เป็นขนาดที่ใช้ในงานราวกันตกและโครงสร้างทั่วไป wall 3.2mm (ใกล้เคียงกับ 3.25mm มาตรฐาน) เพียงพอสำหรับโหลดของ dip bar ที่รับแรงกด static เป็นหลัก

---

### แหล่งอ้างอิง

- [KOMPAN FPW201 Parallel Bars spec (post OD 101.6mm, grip OD 38mm)](https://www.kompan.com/en/int/p/fpw201)
- [GORNATION Premium Dip Bars (OD 40mm)](https://www.gornation.com/products/premium-dip-bars)
- [FitnessKIT Premium Dip Bar (OD 43mm, outdoor)](https://fitnesskit.de/en/products/premium-dip-barren-calisthenics-equipment)
- [Calisthenics.com — Best Dip Bars: grip diameter guide (38–45mm)](https://calisthenics.com/best-dip-bars/)
- [gym-mikolo.com — How Wide Should Dip Bars Be (45–60cm standard)](https://gym-mikolo.com/blogs/home-gym/how-wide-should-dip-bars-be-a-practical-guide-to-dip-bar-dimensions)
- [EMS Metalworking — Pipe Bending Machine 42mm (CLR min = 3×OD)](https://ems-metalworking.com/pipe-bending-machine-max-pipe-diameter-42-mm/)
- [Key Clamp Store UK — 42mm system spec (OD 42.4mm wall 3.25mm)](https://www.keyclampstore.com/pull-up-dip-bars-key-clamp-gym)

---

---

## PIECE 4 — Monkey Flying Bar v4

### วัสดุที่ใช้

| ชิ้น                                  | รูปทรง    | สเปกสุดท้าย                                 | หมายเหตุ                                                      |
| ------------------------------------- | --------- | ------------------------------------------- | ------------------------------------------------------------- |
| Post + Rail Zone 0–2                  | SHS กล่อง | **2"×2" (50×50mm) wall 2.3mm galvanized**   | เสาสั้น ≤2m — standard มอก. หาง่ายทุกร้าน                     |
| Post + Rail Zone 3–4                  | SHS กล่อง | **2"×2" (50×50mm) wall 2.8mm galvanized**   | เสาสูง 2.00–2.70m + dynamic flying bar load                   |
| Triangle brace (Tri_Horiz, Tri_Cap_B) | SHS กล่อง | **2"×2" (50×50mm) wall 2.3mm galvanized**   | compression member, ไม่รับ bending โดยตรง                     |
| Ladder rail (Lad_Rail_F, Lad_Rail_B)  | SHS กล่อง | **2"×2" (50×50mm) wall 2.3mm galvanized**   | ใช้ขนาดเดียวกับโครงหลัก — เชื่อมง่ายกว่า ไม่ต้องสั่ง SKU เพิ่ม |
| ซี่ทุก zone                           | ท่อกลม    | **OD 34mm wall ~3.2mm galvanized**          | fixed — เหมือน Pull-up Bar                                    |

> วัสดุทั้งหมดเป็น **galvanized steel** — ไม่ต้องพ่นสีกันสนิม ทนกลางแจ้งระยะยาว

---

### ภาพรวม

- ความยาวรวม: **5.00m** (y = −1.0 → 4.0, รวม Zone 0)
- ความกว้าง: **1.00m** (x = −0.50 → +0.50)
- วัสดุหลัก: SHS 50×50mm (โครงสร้างทั้งหมด — เสา, ราว, ราวบันได), ท่อกลม OD 34mm (ซี่/บาร์จับ)

---

### Zone 0 — Entry frame (y = −1.0 → 0)

| ชิ้น          | รูปทรง                 | ขนาด      | หมายเหตุ                           |
| ------------- | ---------------------- | --------- | ---------------------------------- |
| Post_pre_y0_L | SHS 50×50mm wall 2.3mm | สูง 1.00m | y=−1.0, x=−0.50                    |
| Post_pre_y0_R | SHS 50×50mm wall 2.3mm | สูง 1.00m | y=−1.0, x=+0.50                    |
| Rail_Z0_Cross | SHS 50×50mm wall 2.3mm | ยาว 1.00m | cross brace ยอดเสา y=−1.0, z=1.00m |
| Rail_Z0_L     | SHS 50×50mm wall 2.3mm | ยาว 1.00m | ราวข้างซ้าย y=−1→0, z=1.00m        |
| Rail_Z0_R     | SHS 50×50mm wall 2.3mm | ยาว 1.00m | ราวข้างขวา y=−1→0, z=1.00m         |

จุดเชื่อม: Rail_Z0_Cross ต่อยอดเสา Zone 0 ทั้งสองข้าง | Rail_Z0_L/R เชื่อม Post_pre_y0 → Post_y0 (Zone 1)

---

### Zone 1 — Low flat section (y = 0 → 1, z = 1.00m)

| ชิ้น                  | รูปทรง                     | ขนาด                  |
| --------------------- | -------------------------- | --------------------- |
| Post_y0_L / Post_y0_R | SHS 50×50mm wall 2.3mm     | สูง 1.00m, y=0        |
| Post_y1_L / Post_y1_R | SHS 50×50mm wall 2.3mm     | สูง 1.00m, y=1        |
| Rail_Z1_L / Rail_Z1_R | SHS 50×50mm wall 2.3mm     | ยาว 1.00m, z=1.00m    |
| Z1_00 → Z1_05         | ท่อกลม OD 34mm wall ~3.2mm | ยาว 1.00m × **6 ซี่** |

ตำแหน่งซี่ (z = 1.000m คงที่, ทิศ X, ยาว 1.00m):

| ชื่อ  | Y (m) | Z (m) |
|-------|------:|------:|
| Z1_00 | 0.00  | 1.000 |
| Z1_01 | 0.20  | 1.000 |
| Z1_02 | 0.40  | 1.000 |
| Z1_03 | 0.60  | 1.000 |
| Z1_04 | 0.80  | 1.000 |
| Z1_05 | 1.00  | 1.000 |

รวม **6 ซี่** · ระยะห่าง 20cm

---

### Zone 2 — Diagonal ramp (y = 1 → 2, z = 1.00 → 2.00m)

| ชิ้น                  | รูปทรง                     | ขนาด                          |
| --------------------- | -------------------------- | ----------------------------- |
| Rail_Z2_L / Rail_Z2_R | SHS 50×50mm wall 2.3mm     | เฉียง ~1.41m (ΔY=1.0, ΔZ=1.0) |
| Z2_01 → Z2_06         | ท่อกลม OD 34mm wall ~3.2mm | ยาว 1.00m × **6 ซี่**         |

ตำแหน่งซี่ (ทิศ X, ยาว 1.00m, ลาด 45°):

| ชื่อ  | Y (m) | Z (m) |
|-------|------:|------:|
| Z2_01 | 1.141 | 1.141 |
| Z2_02 | 1.283 | 1.283 |
| Z2_03 | 1.424 | 1.424 |
| Z2_04 | 1.566 | 1.566 |
| Z2_05 | 1.707 | 1.707 |
| Z2_06 | 1.849 | 1.849 |

รวม **6 ซี่** · ระยะห่าง 200mm ตามแนวลาด (step_y ≈ 141mm, step_z ≈ 141mm)

---

### Zone 3 — High flat section (y = 2 → 3, z = 2.00m)

| ชิ้น                      | รูปทรง                     | ขนาด                    |
| ------------------------- | -------------------------- | ----------------------- |
| Post_y2_L / Post_y2_R     | SHS 50×50mm wall 2.8mm     | สูง 2.00m, y=2          |
| Rail_Z3_L / Rail_Z3_R     | SHS 50×50mm wall 2.8mm     | ยาว 1.00m, z=2.00m      |
| Z3_00 → Z3_04             | ท่อกลม OD 34mm wall ~3.2mm | ยาว 1.00m × **5 ซี่**   |
| Lad_Rail_F                | SHS 50×50mm wall 2.3mm     | สูง 2.00m, y=2, x=+0.50 |
| Lad_Rail_B                | SHS 50×50mm wall 2.3mm     | สูง 2.00m, y=3, x=+0.50 |
| Lad_0.20 → Lad_1.90 (ยอด) | ท่อกลม OD 34mm wall ~3.2mm | ยาว 1.00m × **10 ซี่**  |

ตำแหน่งซี่แนวนอน (z = 2.000m คงที่, ทิศ X, ยาว 1.00m):

| ชื่อ  | Y (m) | Z (m) |
|-------|------:|------:|
| Z3_00 | 2.00  | 2.000 |
| Z3_01 | 2.20  | 2.000 |
| Z3_02 | 2.40  | 2.000 |
| Z3_03 | 2.60  | 2.000 |
| Z3_04 | 2.80  | 2.000 |

รวม **5 ซี่** · ระยะห่าง 20cm (y=3.00 เป็น Z4_00 ของ Zone 4)

ตำแหน่งบันไดข้าง (x = +0.50, ทิศ Y, ยาว 1.00m, ระหว่าง Lad_Rail_F → Lad_Rail_B):

| ชื่อ     | Z (m) |
|----------|------:|
| Lad_0.20 | 0.200 |
| Lad_0.40 | 0.400 |
| Lad_0.60 | 0.600 |
| Lad_0.80 | 0.800 |
| Lad_1.00 | 1.000 |
| Lad_1.20 | 1.200 |
| Lad_1.40 | 1.400 |
| Lad_1.60 | 1.600 |
| Lad_1.80 | 1.800 |
| Lad_2.00 | 2.000 |

รวม **10 ซี่** · ระยะห่าง 20cm · z = 0.20 → 2.00m

---

### Zone 4 — Flying bar (y = 3 → 4, z = 2.00 → 2.70m, มุม 35°)

| ชิ้น                      | รูปทรง                     | ขนาด                                    |
| ------------------------- | -------------------------- | --------------------------------------- |
| Post_y3_L / Post_y3_R     | SHS 50×50mm wall 2.8mm     | สูง **2.70m**, y=3 (ถึง triangle apex)  |
| Rail_Z4_L / Rail_Z4_R     | SHS 50×50mm wall 2.8mm     | เฉียง ~1.22m (ΔY=1.0, ΔZ=0.70, มุม 35°) |
| Z4_00 → Z4_04             | ท่อกลม OD 34mm wall ~3.2mm | ยาว 1.00m × **5 ซี่**                   |
| Tri_Horiz_L / Tri_Horiz_R | SHS 50×50mm wall 2.3mm     | ยาว 1.00m, z=2.70m (แนวนอน)             |
| Tri_Cap_B                 | SHS 50×50mm wall 2.3mm     | ยาว 1.00m, y=4, z=2.70m (cross brace)   |

ตำแหน่งซี่ (ทิศ X, ยาว 1.00m, ลาด 35°):

| ชื่อ  | Y (m) | Z (m) |
|-------|------:|------:|
| Z4_00 | 3.00  | 2.000 |
| Z4_01 | 3.25  | 2.175 |
| Z4_02 | 3.50  | 2.350 |
| Z4_03 | 3.75  | 2.525 |
| Z4_04 | 4.00  | 2.700 |

รวม **5 ซี่** · ระยะห่าง 25cm ตามแนว Y (step_z ≈ 175mm, มุม 35°)
Triangle brace: Post_y3 (แนวตั้ง) + Tri_Horiz (แนวนอน) + Rail_Z4 (ด้านเฉียง = hypotenuse) → มุมฉากอยู่ที่ยอด Post_y3 (z=2.70m)

> **Post_y3 เป็นเสาร่วมระหว่าง Zone 3 และ Zone 4** — ไม่ต้องทำเสาซ้ำสองต้น ใช้ต้นเดียวร่วมกัน

---

### Front ladder (y = 0, หน้าสุด)

| ชิ้น                            | รูปทรง                     | ขนาด                  |
| ------------------------------- | -------------------------- | --------------------- |
| FrontLad_0.20, 0.40, 0.60, 0.80 | ท่อกลม OD 34mm wall ~3.2mm | ยาว 1.00m × **4 ซี่** |

ตำแหน่ง (y = 0.00, ทิศ X, ยาว 1.00m):

| ชื่อ          | Y (m) | Z (m) |
|---------------|------:|------:|
| FrontLad_0.20 | 0.00  | 0.200 |
| FrontLad_0.40 | 0.00  | 0.400 |
| FrontLad_0.60 | 0.00  | 0.600 |
| FrontLad_0.80 | 0.00  | 0.800 |

รวม **4 ซี่** · ระยะห่าง 20cm · z = 0.20 → 0.80m

---

### สรุปซี่ทั้งหมด (ท่อกลม OD 34mm)

| ส่วน | วัตถุ | ทิศ | จำนวน | Z range | หมายเหตุ |
|------|-------|-----|------:|---------|----------|
| Front ladder | FrontLad_0.20–0.80 | X | **4** | 0.20–0.80m | ที่ y=0.00 |
| Zone 1 | Z1_00–Z1_05 | X | **6** | 1.000m | y=0.00–1.00 |
| Zone 2 | Z2_01–Z2_06 | X | **6** | 1.141–1.849m | y=1.14–1.85, ลาด 45° |
| Zone 3 | Z3_00–Z3_04 | X | **5** | 2.000m | y=2.00–2.80 |
| Zone 4 | Z4_00–Z4_04 | X | **5** | 2.000–2.700m | y=3.00–4.00, ลาด 35° |
| Side ladder | Lad_0.20–Lad_2.00 | Y | **10** | 0.20–2.00m | ที่ x=+0.50 |
| **รวม** | | | **36** | | |

> Y ทุกค่าในตารางนี้ใช้ design coordinates (Zone 1 เริ่มที่ y=0)

---

### จุดเชื่อม

- **ซี่ทุก zone**: เชื่อมขวางระหว่าง Rail_L และ Rail_R ตามแนว X
- **Rail_Z2, Rail_Z4**: เชื่อมระหว่าง Post ต้นต่ำและต้นสูงเป็นด้านเฉียง
- **Triangle brace**: Tri_Horiz เชื่อมยอด Post_y3 กับยอด Post_y4, Tri_Cap_B เชื่อมสองด้านแนว X ที่ z=2.70m
- **Ladder rail**: Lad_Rail_F/B tack-weld ที่เสา Post_y2 ตามแนวตั้ง
- **เสาทุกต้น**: ฐาน base plate + anchor bolt ยึดลงพื้นคอนกรีต

### Footprint

กว้าง 1.00m (x = −0.50 → +0.50), ยาว 5.00m (y = −1.0 → +4.0)

---

### Research Notes — การเลือกขนาดเหล็ก

#### 1. โจทย์ตั้งต้น

PIECE 4 ไม่มีการระบุ wall thickness ในแบบ draft มีสามคำถามหลัก: (1) SHS 50×50mm โครงสร้างหลักทุก zone ควรใช้ wall หนาเท่าไหร่ (2) SHS 40×40mm ราวบันไดพอไหม และ (3) triangle brace ใน Zone 4 ที่เสาสูง 2.70m ควรใช้ wall เท่าไหร่

#### 2. เทียบกับผู้ผลิต commercial rig

ค้นหาจาก **GetRXD** (ผู้ผลิต outdoor CrossFit rig ระดับ commercial ที่ใช้กันแพร่หลายที่สุดในตลาด) พบว่าstructural post และ rail ทุกชิ้นใช้ SHS 3"×3" / 7-gauge และ 11-gauge ซึ่งแปลงได้เป็น 76×76mm wall 3.0–4.6mm

ขนาดนี้ใหญ่กว่า SHS 50×50mm ใน PIECE 4 อย่างไรก็ตาม PIECE 4 เป็นโครงสร้าง portal frame ที่มีเสาและ cross rail หลายจุดค้ำกันตลอดความยาว 5m แรงจึงกระจายไปหลาย node ต่างจาก freestanding 2-post rig ของ GetRXD ที่เสาแต่ละต้นรับโหลดเดี่ยว SHS 50×50mm จึงเพียงพอสำหรับ residential use แบบนี้

#### 3. Wall thickness ตาม zone — แนวคิดหลัก

เมื่อมี dynamic load หรือ repeated stress เกี่ยวข้อง การเพิ่ม wall thickness มักได้ผลกว่าการเปลี่ยนเป็น grade เหล็กที่แข็งแรงขึ้น — นำมาใช้กับ PIECE 4 โดยแบ่งตามความสูงเสาและลักษณะโหลด:

- **Zone 0–2 (เสาสูง 1.00–2.00m)** รับ monkey bar load แบบ dynamic แต่เสาสั้น มี cross rail ค้ำถี่ → **wall 2.3mm** เพียงพอ เป็น standard มอก. หาง่ายทุกร้านในไทย
- **Zone 3–4 (เสาสูง 2.00–2.70m)** Post_y3 สูงที่สุดในโครงสร้าง รับแรงโยกจาก flying bar มุม 35° ซึ่งมีทั้ง vertical load และ horizontal component จากการแกว่งตัว → **wall 2.8mm** เพิ่มความหนาหนึ่งระดับ

ทั้ง 2.3mm และ 2.8mm มีขายในไทยชัดเจน SHS 2"×2" กัลวาไนซ์ในไทยมีขายทุกความหนาตั้งแต่ 1.1mm ถึง 3.2mm รวมถึง 2.3mm และ 2.8mm

#### 4. Ladder rail — ปรับเป็น 50×50mm (เหมือนโครงหลัก)

แบบ draft ระบุ SHS 40×40mm ซึ่งไม่มีขายจริงในไทย (ขนาดที่มีคือ 38×38mm = 1½") แต่การใช้ขนาดต่างจากโครงหลัก (50×50mm) ทำให้เชื่อมยากกว่า เพราะเหล็กกล่องกลวง (SHS) ต้องตัดปลายให้พอดีกับหน้าท่อของอีกขนาด — ถ้าใช้ขนาดเดียวกัน (50×50mm) ทุกชิ้น ช่างสามารถตัดตั้งฉาก 90° แล้วเชื่อม fillet ได้ทันที ไม่ต้องแต่ง coping

→ **ปรับ Lad_Rail เป็น SHS 50×50mm wall 2.3mm** เหมือนโครงหลัก Zone 0–2

#### 5. Triangle brace Zone 4

Post_y3 สูง 2.70m รับทั้ง vertical load และ horizontal component จาก flying bar มุม 35° triangle brace ที่ประกอบจาก Post_y3 (แนวตั้ง) + Tri_Horiz (แนวนอน) + Rail_Z4 (hypotenuse) ทำหน้าที่เป็น braced frame ลด effective length ของเสา ป้องกัน lateral buckling

Tri_Horiz และ Tri_Cap_B เป็น compression/tension member ในโครง ไม่ได้รับ bending โดยตรง แรงกระจายตามแนวแกนของท่อ → **wall 2.3mm** เพียงพอ ไม่จำเป็นต้อง up-size ให้เท่ากับ primary post

---

### แหล่งอ้างอิง

- [GetRXD — Galvanized Outdoor Builder Rig spec (SHS 3"×3" / 11-gauge)](https://www.getrxd.com/galvanized-outdoor-builder-rig.html)
- [GetRXD — Wall-Mount Builder Rig with Monkey Bar spec](https://www.getrxd.com/24ft-wall-mount-builder-rig-intermediate1-2ftmb.html)
- [Deportesurbanos — Calisthenics Classic Monkey Bars (post OD 114mm)](https://deportesurbanos.com/en/producto/calisthenics-classic-monkey-bars/)
- [Alibaba Sports Surge — How to Choose Steel Monkey Bars (wall thickness ≥ 2.5mm)](https://sportssurge.alibaba.com/guides/steel-monkey-bars)
- [Eastern Steels — SHS Steel Sizes: dynamic load → wall thickness guideline](https://www.eastern-steels.com/newsdetail/what-does-shs-mean-in-steel-terms-.html)
- [OneStockHome TH — เหล็กกล่อง 1½×1½ นิ้ว (38×38mm) กัลวาไนซ์](https://www.onestockhome.com/th/product_categories/steel-tube-1-1-2-x-1-1-2-inch-38x38mm)
- [Wongguru TH — เหล็กกล่อง GI กัลวาไนซ์ 2×2 ขนาด 1.1–3.2mm](https://www.wongguru.com/product/44178/)
- [Aplus Watsadu TH — เหล็กกัลวาไนซ์ GI 2"×2" หนา 1.2–3.2mm](https://en.aprimeplus.com/product-page/galvanized-steel-GI-2x2)
