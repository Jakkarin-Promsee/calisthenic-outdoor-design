# Spec v3 — Calisthenic Equipment

> 🧭 [สารบัญทั้งหมด (TOC)](../../final1/toc.md) · เทียบของจริง: [Spec EXPLORE 13/06](spec.explore.13062026.md) · ราคา: [ประเมิน](quotation.predict-price.md) · [ยื่นช่าง](quotation.full.md)
>
> **อ่านฉบับนี้เป็นหลัก (v3)** — เนื้อหาสเปกครบแล้ว · v1/v2 เก็บเป็น reference เท่านั้น
>
> **Design Y coordinate**: Zone 1 เริ่มที่ y=0, วัดออกด้านหน้าโครง · **Z**: วัดจากพื้น
> **วัสดุทั้งหมด**: galvanized steel — ทนกลางแจ้ง ไม่ต้องทาสีกันสนิม

---

> ### 🧭 ระบบพิกัด (อ่านก่อน)
>
> เอกสารนี้ใช้ **คำอธิบายข้อความ + ตาราง** แทนรูป diagram (รูป ASCII ใส่ข้อมูลได้ไม่ครบ อ่านแล้ว miss ง่าย)
>
> - **x** = แกนกว้าง (ซ้าย −/ขวา +) · **y** = แกนลึก (หน้า/หลังโครง) · **z** = ความสูงจากพื้น
> - มุมมอง "จาก Y−" = ยืนด้านหน้ามองเข้าหาโครง · "จาก X+" = มองจากด้านข้าง
> - ทุกระยะที่ระบุเป็น **ค่าจริง** (หน่วย mm หรือ m ตามที่กำกับ)
> - 🟫 **พื้นยาง 25mm (≈1")**: z=0 = ผิวบนยาง (ระดับยืนจริง) · ความสูง/ค่า z ในตาราง PIECE ทุกค่า = วัด**เหนือยาง** (ไม่เปลี่ยน) · เสา/ขาทุกชิ้นที่หยั่งพื้น **ตัดยาวขึ้น +25mm** (ส่วนเกินอยู่ใต้ยาง วาง base plate บน slab) → ความยาวตัดจริงดู **§ฐานราก** ท้ายเอกสาร

---

## PIECE 1 — Pull-up Bar

3 เสา + 2 บาร์: บาร์สูง (z=2.20m) สำหรับผู้ใหญ่ + บาร์เตี้ย (z=1.50m) สำหรับเด็ก

### วัสดุที่ใช้

| ชิ้น | รูปทรง | สเปกสุดท้าย | หมายเหตุ |
|------|--------|-------------|---------|
| เสา (ทุกต้น) | SHS กล่อง | **3"×3" (76×76mm) wall 3.2mm galv** | ตรง ไม่มีข้องอ |
| บาร์จับ (ทุกบาร์) | ท่อกลม | **OD 34mm wall 3.2mm galv** | ตรง |

### รายละเอียด

| ชิ้น | รูปทรง | สเปก | ขนาด | จำนวน | หมายเหตุ |
|------|--------|------|------|:-----:|---------|
| Post_Left | SHS 76×76mm | wall 3.2mm | สูง **2.30m** | 1 | เสาหลักซ้าย |
| Post_Right | SHS 76×76mm | wall 3.2mm | สูง **2.30m** | 1 | เสาหลักขวา |
| Post_Child | SHS 76×76mm | wall 3.2mm | สูง **1.60m** | 1 | เสาบาร์เด็ก |
| Bar_PullUp_High | OD 34mm | wall 3.2mm | ยาว **1.50m** (CL–CL) | 1 | บาร์ผู้ใหญ่ z=2.20m |
| Bar_PullUp_Low | OD 34mm | wall 3.2mm | ยาว **1.00m** (CL–CL) | 1 | บาร์เด็ก z=1.50m |

### โครงสร้าง

| ชิ้น | x | สูง / z |
|------|---|---------|
| Post_Child | −1.75m | สูง 1.60m |
| Post_Left | −0.75m | สูง 2.30m |
| Post_Right | +0.75m | สูง 2.30m |
| Bar_PullUp_High | −0.75 → +0.75m | z = 2.20m (10cm ต่ำกว่ายอด) |
| Bar_PullUp_Low | −1.75 → −0.75m | z = 1.50m (10cm ต่ำกว่ายอด) |

**การจัดวาง (มองจากด้านหน้า ทิศ Y−):** เสา 3 ต้นเรียงเป็นเส้นตรงตามแกน x ห่างกันช่วงละ 1.00m
- **Post_Child** — x=−1.75m, สูง 1.60m (ซ้ายสุด)
- **Post_Left** — x=−0.75m, สูง 2.30m (กลาง · เป็นเสาร่วมของทั้งสองบาร์)
- **Post_Right** — x=+0.75m, สูง 2.30m (ขวาสุด)

บาร์ทั้งสองเชื่อม fillet ที่ด้านข้างเสา อยู่ต่ำกว่ายอดเสา 10cm:
- **Bar_Low** — z=1.50m, ยาว 1.00m, เชื่อมช่วงซ้าย (Post_Child ↔ Post_Left) → บาร์เด็ก
- **Bar_High** — z=2.20m, ยาว 1.50m, เชื่อมช่วงขวา (Post_Left ↔ Post_Right) → บาร์ผู้ใหญ่

**Footprint**: กว้าง 2.50m (x = −1.75 → +0.75) · ลึก ~10cm  
**จุดยึด**: base plate + anchor bolt ทุกต้น · บาร์เชื่อม fillet ด้านข้างเสา

---

### Research Notes — การเลือกขนาดเหล็ก

#### 1. โจทย์ตั้งต้น

แบบ draft แรกใช้ **SHS 100×100mm wall 4.5mm** ซึ่งตั้งขนาดแบบกะๆ ไว้ก่อน พอมาถึงขั้นจะซื้อจริงต้องตรวจสอบว่าขนาดนี้เหมาะหรือเปล่า และถ้าเปลี่ยนเป็นกัลวาไนซ์ทั้งหมดควรใช้ขนาดไหน

#### 2. ดูว่าสนามจริงเขาใช้อะไร

ค้นหาจากผู้ผลิต outdoor calisthenics ระดับ commercial พบว่า **Deportesurbanos** (ผู้ผลิต street workout park ในยุโรป มาตรฐาน EN 1176) ใช้ **ท่อกลม OD 114mm** สำหรับเสาหลัก พร้อม anchor base 300mm — นี่คือมาตรฐานสนามสาธารณะที่รับคนหลายคนและแรงกระแทกสูง

→ SHS 100×100mm ที่ draft ไว้ใกล้เคียงระดับ commercial park มากเกินไป สำหรับบ้านส่วนตัว 1–2 คนไม่จำเป็น

#### 3. หาขนาดที่เหมาะกับบ้านส่วนตัว

ข้อมูลจาก DIY builds และผู้ผลิต galvanized rig เช่น **GetRXD** พบว่า **OD 76mm (3") wall 3.2mm** รับน้ำหนักได้สบายสำหรับผู้ใช้ 1–2 คน รวม dynamic load (kipping pull-up ≈ 3–5× body weight) ที่เสาสูง 2–2.5m · เลือก **SHS** แทนท่อกลมเพราะเชื่อมง่ายกว่า (หน้าตัดเรียบ ตั้งฉาก 90° ได้เลย) ราคาใกล้กัน

#### 4. ตรวจสอบความหนาในตลาดไทย

SHS 3"×3" (76×76mm) กัลวาไนซ์ในไทยมีสองความหนาหลัก:
- **2.3mm** — มาตรฐาน มอก. หาง่ายทุกร้าน ใช้งานรั้ว ประตู หลังคา
- **3.2mm** — ต้องหาจากร้านเฉพาะ (เช่น Aplus Watsadu) ใช้งานโครงสร้างรับน้ำหนัก

เสา pull-up bar ต้องรับแรงดึงซ้ำๆ กลางแจ้ง 2.3mm tight เกินไป → เลือก **3.2mm** · มาตรฐาน EU/UK (EN 10210 S235) สำหรับ structural SHS ขนาดนี้ระบุ 3–4mm ตรงกัน

#### 5. บาร์จับ OD 34mm — ไม่ต้องเปลี่ยน

Eleiko ผู้ผลิต commercial pull-up bar ระดับโลก ใช้ **33mm** เป็น optimal grip diameter — 34mm ที่ใช้อยู่เหมาะมือและตรงมาตรฐานอุตสาหกรรม ไม่ต้องปรับ

### แหล่งอ้างอิง

- [Deportesurbanos — Outdoor Pull Up Bar spec (post OD 114mm)](https://deportesurbanos.com/en/producto/outdoor-pull-up-bar/)
- [Eleiko Prestera Straight Pull-up Bar (bar OD 33mm)](https://eleiko.com/en/equipment/outdoor/galvanized/3085515-01-eleiko-prestera-straight-pull-up-bar-outdoor)
- [GetRXD — Galvanized Outdoor Pull Up Rigs](https://www.getrxd.com/pull-up-rigs/galvanized-outdoor-pull-up-rigs.html)
- [The Metal Store UK — Build Your Own Galvanised Pull-Up Bar](https://www.themetalstore.co.uk/content-hub/tube-clamp-guides/pull-up-bar)
- [SB Steel TH — เหล็กกล่องเหลี่ยมกัลวาไนซ์ 3"×3" 2.3mm](https://www.sbsteel.co.th/product/%E0%B9%80%E0%B8%AB%E0%B8%A5%E0%B9%87%E0%B8%81%E0%B8%81%E0%B8%A5%E0%B9%88%E0%B8%AD%E0%B8%87%E0%B9%80%E0%B8%AB%E0%B8%A5%E0%B8%B5%E0%B9%88%E0%B8%A2%E0%B8%A1%E0%B8%81%E0%B8%B1%E0%B8%A5%E0%B8%A7-13/)
- [Aplus Watsadu TH — เหล็กกัลวาไนซ์ GI 3"×3" หนา 1.5–3.2mm](https://www.aprimeplus.com/product-page/%E0%B9%80%E0%B8%AB%E0%B8%A5-%E0%B8%81%E0%B8%81-%E0%B8%A5%E0%B8%A7%E0%B8%B2%E0%B9%84%E0%B8%99%E0%B8%8B-gi-3x3-%E0%B8%99-%E0%B8%A7-%E0%B8%AB%E0%B8%99%E0%B8%B2-2-0-%E0%B8%A1%E0%B8%A1)

---

## PIECE 2 — Snake Bar

2 เสา + 3 บาร์: Straight bar (structural) + Wave bar (ออกกำลังกาย) + Side bars ทั้งสองข้าง

### วัสดุที่ใช้

| ชิ้น | รูปทรง | สเปกสุดท้าย | หมายเหตุ |
|------|--------|-------------|---------|
| เสา (ทั้งสองต้น) | SHS กล่อง | **3"×3" (76×76mm) wall 3.2mm galv** | ตรง ไม่มีข้องอ |
| Bar_Straight | ท่อกลม | **OD 42mm wall 3.2mm galv** | ตรง · upsize 34→42mm เพิ่มความแข็งแรง |
| Bar_Wave | ท่อกลม (ดัดโค้ง) | **OD 34mm wall 3.2mm galv** | **8 bends 90° R=100mm** ในระนาบนอน (XY) |
| Side_Grip_L / Side_Grip_R | ท่อกลม (ดัดโค้ง) | **OD 34mm wall 3.2mm galv** | **2 bends 90° R=100mm** ต่ออัน · **4 อัน/ข้าง** · ยื่น 25cm × สูง 25cm |

### รายละเอียด

| ชิ้น | รูปทรง | สเปก | ขนาด | จำนวน | หมายเหตุ |
|------|--------|------|------|:-----:|---------|
| Post_Snake_L/R | SHS 76×76mm | wall 3.2mm | สูง **2.10m** | 2 | x = ±1.038m |
| Bar_Straight | OD 42mm | wall 3.2mm | ยาว **2.000m** (inner face–inner face) | 1 | z=1.962m |
| Bar_Wave | OD 34mm | wall 3.2mm | path **~5.73m** | 1 | 8 bends R=100mm · z=2.000m |
| Side_Grip_L × 4 | OD 34mm | wall 3.2mm | path **0.664m** ต่ออัน | 4 | 2 bends R=100mm · x=−1.038m |
| Side_Grip_R × 4 | OD 34mm | wall 3.2mm | path **0.664m** ต่ออัน | 4 | 2 bends R=100mm · x=+1.038m |

> **Wave bar path breakdown** (ไล่ตามแนวท่อ · verified กับ snake_bar_v5.blend):  
> ตรง 400 → arc → 338 → arc → 800 → arc → 300 → arc → 800 → arc → 300 → arc → 800 → arc → 338 → arc → 400 (หน่วย mm)  
> = ช่วงตรง 9 ท่อน รวม **4,476mm** (ปลาย 400×2 + flat นอก 338×2 + flat ใน 300×2 + ช่วงข้าม Y 800×3) + **8 arcs × 157mm = 1,257mm** → รวม **5,733mm**  
> *(400mm ปลายสองข้าง รวม 38mm ที่ปักเข้าเสาไว้แล้ว — อย่าบวกซ้ำ)*  
> **Side grip path breakdown**: 150mm (ตรง) + arc(157mm) + 50mm (flat) + arc(157mm) + 150mm (ตรง) = **664mm ต่ออัน** · 8 อัน รวม 5,312mm

### โครงสร้าง

| ชิ้น | x | z | หมายเหตุ |
|------|---|---|---------|
| Post_Snake_L | −1.038m | — | สูง 2.10m |
| Post_Snake_R | +1.038m | — | สูง 2.10m |
| Bar_Straight | −1.000 → +1.000m (inner face) | 1.962m | structural · OD 42mm · center ห่าง Wave 38mm (ผิวสัมผัสที่ z=1.983m) |
| Bar_Wave | −1.038 → +1.038m | 2.000m | wave ±50cm ในแนว Y |
| Side_Grip_L/R | x = ±1.038m | 0.10 → 1.85m | 4 U-grips **แยกชิ้น** ต่อข้าง · ยื่น −Y 25cm |

**รูปร่าง Bar_Wave (มองจากด้านบน ระนาบ XY):** ท่อเส้นเดียวพาดระหว่างเสาทั้งสอง (x=−1.038 → +1.038) วางที่ z=2.000m ปักเข้าเสาข้างละ 38mm แล้วเชื่อม fillet
- ระหว่างเสา ท่อคดเป็น **คลื่น 4 ลูก (U-shape) สลับทิศในแนว y**: U1 ออก +Y, U2 ออก −Y, U3 ออก +Y, U4 ออก −Y
- แต่ละลูก: **กว้าง ~50cm (แกน x) · ลึก 50cm (แกน y — ยื่น ±50cm จากแกนกลาง)**
- มุมโค้งทุกมุม **R=100mm เท่ากันหมด** (รวม 8 โค้ง 90°, โค้งละ ~157mm)

> ✅ **path ตรวจสอบกับ snake_bar_v5.blend แล้ว (13/06/2026)** — centerline กว้าง 2.076m (= ระยะเสา c–c ตรงกับ footprint), คลื่น 4 ลูกใช้ **8 โค้ง 90° พอดี** (ลูกละ 2 โค้ง × 4 ลูก · ปลายเข้า/ออกเสาที่ y กลางใช้โค้งร่วม จึงไม่ต้องมี 10 โค้ง) · calc_length = 5.733m ตรงกับ breakdown ด้านบน → **path พร้อมสั่งดัด**

**Side grips (มองจากด้านข้าง ระนาบ YZ) — ต่อข้าง 4 ชิ้นแยกอิสระ:** แต่ละชิ้นเป็น U-grip ยื่นออกจากเสาในทิศ −Y
- แต่ละ grip: **สูง (H) 250mm · ยื่นออก 250mm (ปลายสุดที่ y=−0.25m) · มุมโค้ง R=100mm ทั้ง 2 มุม** · tack-weld ที่หน้าเสา (y=0) 2 จุด
- เรียงซ้อน 4 ระดับ (z ของจุดเชื่อมล่าง/บนแต่ละชิ้น):
  - **Grip 1**: z=0.10 / 0.35m
  - **Grip 2**: z=0.60 / 0.85m
  - **Grip 3**: z=1.10 / 1.35m
  - **Grip 4**: z=1.60 / 1.85m
- ทำเหมือนกันทั้งข้างซ้าย (x=−1.038m) และขวา (x=+1.038m) → รวม 8 ชิ้น, เชื่อม 16 จุด

**Footprint**: กว้าง 2.00m (clear) · ลึก ~1.00m (wave bar ±50cm ในแนว Y)  
**จุดยึด**: Wave bar ปักเข้าเสา 38mm + เชื่อม fillet · Straight bar เชื่อมด้านข้างเสา · Side grips tack-weld 2 จุดต่ออัน (4 อัน × 2 ข้าง = 16 จุด รวม)

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

#### 6. Side grips — จาก bar ยาวต่อเนื่องเป็น 4 U-grips แยกชิ้น

แบบ draft เดิมมี Bar_Side_L/R เป็นท่อยาวต่อเนื่อง ~3.41m ที่ฝังเข้าเสาตลอดความสูง ปัญหาของแบบนั้นคือ: ท่อยาวดัด 8 bend ติดต่อกันในระนาบ YZ ยุ่งยากสำหรับช่าง, ฝังเข้าเสา SHS แนวท่อต้องเที่ยงตรงมาก, และถ้า weld จุดใดล้มเหลวต้องรื้อทั้งชิ้น

แก้เป็น **4 U-grips แยกชิ้นต่อข้าง** โดยแต่ละ grip = path 664mm (150mm + arc R=100 + 50mm flat + arc R=100 + 150mm) เชื่อม 2 จุดที่เสา:

- **ดัดง่ายกว่า** — 2 bends ต่อชิ้น ช่างทั่วไปทำได้ในงานเดียว
- **ติดตั้งง่ายกว่า** — วาง + tack-weld ทีละชิ้น ปรับ level ได้อิสระ
- **ซ่อมได้ทีละชิ้น** — ถ้า grip เสียหาย ตัด-เชื่อมเฉพาะอันนั้นโดยไม่กระทบชิ้นอื่น

**Straight bar (OD 42mm) อยู่ใต้ Wave (OD 34mm)**: center ห่างกัน 38mm (= r_straight 21 + r_wave 17) → ผิวสัมผัสกันที่ z=1.983m เชื่อมยึดตลอดแนว — Straight รับ structural load หลัก, Wave รับแรงจับ · **upsize 34→42mm** เพื่อเพิ่ม stiffness ของคานโครงสร้างหลัก (รอเช็กการรับน้ำหนักตามมาตรฐานอีกรอบ)

### แหล่งอ้างอิง

- [Deportesurbanos — Snake Bar spec (post OD 114mm, bar OD 33.7mm)](https://deportesurbanos.com/en/producto/snake-bar-calisthenics/)
- [BarManiaPro — Snake Bar (5 snakes OD 33.7mm)](https://barmaniapro.com/product/snake-bar/)
- [calisthenics-parks.com — Wave/Snake Bars overview](https://calisthenics-parks.com/equipments/30-en-wave-bars-snake-bars)
- [Xometry — Tube Bending Design Tips (CLR ≥ 2×OD guideline)](https://www.xometry.com/resources/tube/tube-bending-design-tips/)
- [Pro-Tools — Choosing the Right Centerline Radius](https://pro-tools.com/blogs/protoolsusa/19204299-choosing-the-right-centerline-radius-for-your-next-project)
- [Lister Tube — Tube Bending Size Guide (PDF)](https://www.listertube.com/wp-content/uploads/2022/03/ListerTube_A5-Tube-Bending-Size-Guide_digital.pdf)

---

## PIECE 3 — Dip Bar

3 frames U-shape + 3 nub (C-handle) · 2 ช่องกริป: 60cm (chest dip) + 50cm (tricep dip)

### วัสดุที่ใช้

| ชิ้น | รูปทรง | สเปกสุดท้าย | หมายเหตุ |
|------|--------|-------------|---------|
| Frame / DipBar_01–03 | ท่อกลม (ดัดโค้ง) | **OD 42mm wall 3.2mm galv** | **2 bends**: R=10mm (ฝั่ง nub — weld junction) · R=120mm (ฝั่งไกล) |
| Nub / C-handle_01–03 | ท่อกลม (ดัดโค้ง) | **OD 42mm wall 3.2mm galv** | **2 bends 90° R=80mm** · C-handle ยื่น −Y · D=250mm H=200mm |

### รายละเอียด

| ชิ้น | รูปทรง | สเปก | ขนาด | จำนวน | หมายเหตุ |
|------|--------|------|------|:-----:|---------|
| DipBar_01 | OD 42mm | wall 3.2mm | path **~3.14m** | 1 | x = 0.000m |
| DipBar_02 | OD 42mm | wall 3.2mm | path **~3.14m** | 1 | x = 0.642m |
| DipBar_03 | OD 42mm | wall 3.2mm | path **~3.14m** | 1 | x = 1.184m |
| Nub_01/02/03 | OD 42mm | wall 3.2mm | path **~0.632m** | 3 | frame ละ 1 nub |

> **Frame path breakdown** (ขา 2 ข้างยาวขึ้นข้างละ 25mm เผื่อยาง): 1215mm + arc16mm + 620mm + arc188mm + 1105mm = **3,144mm**  
> **Nub path breakdown**: 170mm + arc126mm + 40mm + arc126mm + 170mm = **632mm**

### โครงสร้าง

| ชิ้น | x (centerline) | clear gap → | ลักษณะใช้งาน |
|------|---------------|-------------|-------------|
| DipBar_01 | 0.000m | → 60cm → | outer frame ซ้าย |
| DipBar_02 | 0.642m | → 50cm → | middle frame |
| DipBar_03 | 1.184m | — | outer frame ขวา |

**รูปร่าง frame (มองจากด้านหน้า ทิศ Y−):** แต่ละ frame เป็นท่อดัดรูปตัว ⊓ (คว่ำ) ตั้งบนพื้น
- **ขา 2 ข้างหยั่งพื้นที่ z=0**: ขาฝั่ง nub อยู่ที่ y=0, ขาฝั่งไกลอยู่ที่ y=0.75m
- **คานจับด้านบนอยู่ที่ z=1.200m** ต่อด้วย 2 มุมบนที่ใช้รัศมีต่างกัน:
  - มุมฝั่ง nub (y=0) = **R=10mm** (เกือบคม — เป็น weld junction สำหรับต่อ nub)
  - มุมฝั่งไกล (y=0.75m) = **R=120mm**
- nub (C-handle) เชื่อมที่หน้า frame ฝั่งขา y=0

**รูปร่าง Nub / C-handle (มองจากด้านข้าง ระนาบ YZ):** ท่อดัดรูปตัว C เปิดเข้าหา frame (ทิศ +Y) ตัวยื่นออก −Y
- **แขน 2 ข้างขนานกัน** ห่างกันในแนวสูง H=200mm: แขนบนที่ z=1.200m, แขนล่างที่ z=1.000m
- แต่ละแขนยาว 170mm (ทิศ −Y) จากหน้า frame (y=0) ออกไปถึงปลายโค้งที่ y=−0.250m
- ด้านหลังเชื่อมแขนทั้งสองด้วยช่วงตรง 40mm คั่นด้วย **มุมโค้ง R=80mm ทั้ง 2 มุม**
- เชื่อมติด frame ที่โคนแขนทั้งสอง (y=0)

**Footprint**: กว้าง 1.226m (x = −0.021 → +1.205) · ลึก 1.00m (frame 0.75m + nub 0.25m)  
**จุดยึด**: frame แต่ละตัวยึดพื้นแยกกัน (base plate + anchor) · nub tack-weld 2 จุดที่หน้า frame

---

### Research Notes — การเลือกขนาดเหล็ก

#### 1. โจทย์ตั้งต้น

แบบ draft ระบุ OD 42mm แต่ไม่มีที่มาชัดเจน ต้องตรวจสอบสองประเด็น: (1) OD 42mm เหมาะกับ dip bar จริงหรือไม่เมื่อเทียบกับมาตรฐานผู้ผลิต และ (2) bend radius ที่ระบุว่า "80–120mm" สำหรับท่อ 42mm ทำได้จริงในไทยหรือเปล่า

#### 2. ดูว่าผู้ผลิต commercial ใช้อะไร

ค้นหาจากผู้ผลิตอุปกรณ์กลางแจ้งระดับ commercial พบข้อมูลที่ชัดเจนที่สุดจาก **KOMPAN** (ผู้ผลิต outdoor fitness park ระดับโลก มาตรฐาน EN 1176) ซึ่งระบุว่าเสา post ของ parallel bars ทำจาก Ø101.6mm pre-galvanized steel ส่วน grip bar ทำจาก hot-dip galvanized steel OD 38mm — และระบุว่า "เส้นผ่านศูนย์กลางนี้ช่วยรองรับข้อมือขณะทำ dip หรือ handstand ได้ดี"

นอกจากนี้ผู้ผลิตเฉพาะทาง เช่น GORNATION และ FitnessKIT ที่ขายอุปกรณ์ระดับ prosumer ต่างใช้ขนาด OD 40–43mm เป็นหลัก

→ **ข้อสรุป**: OD 42mm ที่ draft ไว้อยู่ในช่วง 38–43mm ซึ่งเป็น sweet spot ของ commercial และ prosumer dip bar ทุกยี่ห้อ — **ไม่ต้องเปลี่ยน**

#### 3. ทำไม OD 42mm ดีกว่า OD 34mm ที่ใช้กับ pull-up bar

Bar ที่หนาขึ้น (38–45mm) ให้ความสบายมือมากกว่า เหมาะกับมือใหญ่ และช่วยพัฒนา grip strength — ส่วน bar เล็ก (32–35mm) เหมาะกับมือเล็กหรือผู้เริ่มต้น สำหรับ dip bar ข้อมือต้องรับน้ำหนักตัวทั้งหมดในท่า neutral grip (ฝ่ามือหันเข้าหากัน) ซึ่งต่างจาก pull-up bar ที่จับแบบ overhand — ท่อที่หนาขึ้นช่วยกระจายแรงกดที่ข้อมือ ทำให้ทำ L-sit หรือ dip ได้นานขึ้น จึงใช้ขนาดที่ใหญ่กว่า pull-up bar เป็น best practice ของอุตสาหกรรม

#### 4. ระยะห่างระหว่าง frame (grip width)

ตรวจสอบ grip width มาตรฐาน พบว่าช่วงมาตรฐาน dip bar อยู่ที่ 45–60cm ซึ่งเหมาะกับผู้ใหญ่ส่วนใหญ่ — แคบกว่า (45–50cm) เน้น tricep มากขึ้น กว้างกว่า (55–60cm) เปิด chest มากขึ้น

แบบนี้ใช้ 3 frame สร้าง 2 ช่องให้เลือก: กว้าง 60cm (chest dip) และ 50cm (tricep dip) — ทั้งสองอยู่ใน sweet spot พอดี ไม่ต้องเปลี่ยน

#### 5. Bend radius สำหรับ OD 42mm — ฝั่งไกล R=120mm · ฝั่ง nub R=10mm

Frame แต่ละตัวมี 2 มุมบนซึ่งใช้ radius ต่างกัน:

**ฝั่งไกล (y=0.75m) — R=120mm:**
สำหรับ OD 42mm มาตรฐาน rotary-draw bending อยู่ที่:
- **84mm (2×OD)** — ขั้นต่ำทางทฤษฎี ต้องใช้ mandrel ช่วย มีความเสี่ยงท่อบีบ
- **126mm (3×OD)** — มาตรฐาน ช่างทั่วไปทำได้ไม่ต้อง mandrel พิเศษ

เลือก **R=120mm** (≈2.86×OD ใกล้ 3×OD) ช่างทั่วไปทำได้ มุมโค้งดูดี ไม่ต้อง mandrel พิเศษ

**ฝั่ง nub (y=0) — R=10mm (เกือบ sharp):**
จุดนี้คือ weld junction ที่ nub จะมาเชื่อมต่อ — ในทางปฏิบัติทำโดยตัด miter 45° แล้วเชื่อม butt weld:
- หากดัดโค้งด้วย R ขนาดปกติ (≥84mm) หน้าตัดท่อบริเวณโค้งจะ deform เล็กน้อย ทำให้รอยเชื่อม fillet กับ nub ไม่เต็มหน้าตัด
- R=10mm ≈ "sharp joint" แต่ช่วยป้องกัน bevel pinching ในโมเดล 3D และรักษาหน้าตัดท่อให้เรียบสำหรับ weld กับ nub

#### 6. Nub — ทำไม bend radius = 80mm (ไม่ใช่ 120mm เหมือน frame หลัก)

Nub เป็น C-handle สูง 200mm (z = 1.0–1.2m) ที่ใช้ท่อ OD 42mm เหมือน frame ซึ่งมี 2 bends 90° ในระนาบ YZ โดยที่ height span ระหว่างสองจุด bend = H = 200mm นั้นกำหนด radius ขั้นสูงที่ fit ได้:

| R | H ขั้นต่ำที่ต้องการ | vert_flat (ส่วนตรงกลาง) | ทำได้จริง? |
|---|---|---|---|
| R = 80mm (1.9×OD) | 2×80 = 160mm | 200−160 = **40mm** ✓ | ✓ fit สบาย |
| R = 100mm (2.4×OD) | 2×100 = 200mm | 200−200 = **0mm** | ✓ semicircle พอดี |
| R = 120mm (2.9×OD) | 2×120 = 240mm | 200−240 = **−40mm** | ✗ ไม่ fit ใน 200mm |

→ R=120mm (ที่ใช้กับ frame หลัก) **ไม่สามารถดัดได้ภายใน H = 200mm** — ต้องใช้ R ≤ 100mm  
→ เลือก **R = 80mm** เพราะมี vert_flat = 40mm ให้รูปทรงมีส่วนตรง ดูสะอาดกว่า R=100mm ที่โค้งตลอดแบบ semicircle

ข้อสังเกต: R=80mm ≈ 1.9×OD อยู่ต่ำกว่า threshold 2×OD (84mm) เล็กน้อย — ในทางปฏิบัติสำหรับท่อ OD 42mm wall 3.2mm (D/t ratio ≈ 13) ช่างที่มี rotary-draw bender ขนาด 42mm สามารถดัด R=80mm ได้โดยอาจต้องใช้ mandrel บาง (light mandrel) ช่วย — ซึ่งเครื่องดัดท่อระดับ workshop ทั่วไปในไทยรองรับได้

#### 7. ท่อ galvanized OD 42mm ในตลาดไทย

OD 42mm ตรงกับมาตรฐาน **1¼" nominal pipe** (OD 42.4mm จริง) ซึ่งเป็นขนาดสากลระบบ 42mm ใช้ท่อ OD 42.4mm wall 3.25mm — หาได้จากร้านเหล็กทั่วไปในไทย เป็นขนาดที่ใช้ในงานราวกันตกและโครงสร้างทั่วไป wall 3.2mm (ใกล้เคียงกับ 3.25mm มาตรฐาน) เพียงพอสำหรับโหลดของ dip bar ที่รับแรงกด static เป็นหลัก

### แหล่งอ้างอิง

- [KOMPAN FPW201 Parallel Bars spec (post OD 101.6mm, grip OD 38mm)](https://www.kompan.com/en/int/p/fpw201)
- [GORNATION Premium Dip Bars (OD 40mm)](https://www.gornation.com/products/premium-dip-bars)
- [FitnessKIT Premium Dip Bar (OD 43mm, outdoor)](https://fitnesskit.de/en/products/premium-dip-barren-calisthenics-equipment)
- [Calisthenics.com — Best Dip Bars: grip diameter guide (38–45mm)](https://calisthenics.com/best-dip-bars/)
- [gym-mikolo.com — How Wide Should Dip Bars Be (45–60cm standard)](https://gym-mikolo.com/blogs/home-gym/how-wide-should-dip-bars-be-a-practical-guide-to-dip-bar-dimensions)
- [EMS Metalworking — Pipe Bending Machine 42mm (CLR min = 3×OD)](https://ems-metalworking.com/pipe-bending-machine-max-pipe-diameter-42-mm/)
- [Key Clamp Store UK — 42mm system spec (OD 42.4mm wall 3.25mm)](https://www.keyclampstore.com/pull-up-dip-bars-key-clamp-gym)

---

## PIECE 4 — Monkey Flying Bar

โครงสร้าง 5.0m × 1.0m ต่อเนื่อง 4 zone:
Zone 0 (entry) → Zone 1 (flat z=1.00m) → Zone 2 (ramp ↗45°) → Zone 3 (flat z=2.00m) → Zone 4 (flying ↗35° → apex z=2.70m)
พร้อม front ladder (หน้า Zone 1) + side ladder (ขึ้น Zone 3, ด้านขวา)

### วัสดุที่ใช้

| ชิ้น | รูปทรง | สเปกสุดท้าย | หมายเหตุ |
|------|--------|-------------|---------|
| เสา Zone 0–2 + triangle brace | SHS กล่อง | **2"×2" (50×50mm) wall 2.3mm galv** | ตรง ไม่มีข้องอ · เสาสั้น ≤2m |
| โครงสร้าง Zone 3–4 (เสาสูง) | SHS กล่อง | **2"×2" (50×50mm) wall 2.8mm galv** | ตรง · เสา 2.00–2.70m รับ flying bar load |
| ซี่ทั้งหมด (35 ซี่) + ราว Zone 0 (3 ชิ้น) | ท่อกลม | **OD 34mm wall 3.2mm galv** | ตรง ยาว 1.00m ทุกชิ้น |

### รายละเอียด

#### SHS 50×50mm wall 2.3mm

| ชิ้น | ขนาด | จำนวน | ตำแหน่ง / หมายเหตุ |
|------|------|:-----:|--------------------|
| Post_pre_y0_L/R | สูง 1.00m | 2 | y=−1, Zone 0 entry |
| Post_y0_L/R | สูง 1.00m | 2 | y=0, Zone 0/1 |
| Post_y1_L/R | สูง 1.00m | 2 | y=1, Zone 1/2 |
| Rail_Z1_L/R | ยาว 1.00m | 2 | ราวข้าง Zone 1 |
| Rail_Z2_L/R | ยาว **~1.41m** (เฉียง 45°) | 2 | ราว Zone 2 |
| Tri_Horiz_L/R | ยาว 1.00m | 2 | แนวนอนยอด triangle z=2.70m |
| **รวม** | | **14** | |

#### SHS 50×50mm wall 2.8mm

| ชิ้น | ขนาด | จำนวน | ตำแหน่ง / หมายเหตุ |
|------|------|:-----:|--------------------|
| Post_y2_L/R | สูง 2.00m | 2 | y=2, Zone 2/3 |
| Post_y3_L/R | สูง 2.70m | 2 | y=3, triangle apex |
| Rail_Z3_L/R | ยาว 1.00m | 2 | ราวข้าง Zone 3 |
| Rail_Z4_L/R | ยาว **~1.22m** (เฉียง 35°) | 2 | ราว Zone 4 (hypotenuse) |
| **รวม** | | **8** | |

#### ท่อกลม OD 34mm wall 3.2mm — ซี่ + ราว Zone 0

| กลุ่ม | ชิ้น | ยาว | จำนวน | Y (design) | Z |
|-------|------|-----|:-----:|-----------|---|
| **Zone 0 ราว** | Rail_Z0_Cross | 1.00m | 1 | y=−1 (cross brace) | z=1.000 |
| **Zone 0 ราว** | Rail_Z0_L/R | 1.00m | 2 | y=−1→0 (side rail) | z=1.000 |
| Front ladder | FrontLad_0.20–0.80 | 1.00m | 4 | y=0.00 | z=0.20–0.80 |
| Zone 1 | Z1_00–Z1_05 | 1.00m | 6 | y=0.00–1.00 | z=1.000 |
| Zone 2 | Z2_01–Z2_06 | 1.00m | 6 | y=1.14–1.85 | z=1.141–1.849 |
| Zone 3 | Z3_00–Z3_04 | 1.00m | 5 | y=2.00–2.80 | z=2.000 |
| Zone 4 | Z4_00–Z4_04 | 1.00m | 5 | y=3.00–4.00 | z=2.000–2.700 |
| Side ladder | Lad_0.20–Lad_1.80 | 1.00m | 9 | x=+0.50 | z=0.20–1.80 |
| **รวม** | | | **38** | | |

### โครงสร้าง

**ด้านข้างทั้งโครง (มองจาก X+, ระนาบ YZ)** — โปรไฟล์แนวเดินตามแกน y ยาว 5m แบ่ง 5 ช่วง (ไล่จาก entry):
- **Zone 0 (y=−1→0) + Zone 1 (y=0→1):** ราบที่ z=1.00m
- **Zone 2 (y=1→2):** ลาดขึ้น 45° จาก z=1.00 → 2.00m
- **Zone 3 (y=2→3):** ราบที่ z=2.00m
- **Zone 4 (y=3→4):** ลาดบิน (flying) ขึ้น 35° จาก z=2.00 → 2.70m
- เสาตามแนว: y=−1, 0, 1 สูง 1.00m · y=2 สูง 2.00m · y=3 สูง 2.70m (= ยอด/apex ของ triangle brace)

#### เสาและความสูง

| Post | Y (design) | สูง | wall | หมายเหตุ |
|------|-----------|-----|------|---------|
| Post_pre_y0 L/R | y=−1 | 1.00m | 2.3mm | entry frame |
| Post_y0 L/R | y=0 | 1.00m | 2.3mm | Zone 1 start |
| Post_y1 L/R | y=1 | 1.00m | 2.3mm | Zone 1/2 boundary |
| Post_y2 L/R | y=2 | 2.00m | 2.8mm | Zone 2/3 boundary |
| Post_y3 L/R | y=3 | 2.70m | 2.8mm | triangle apex · Zone 3/4 boundary |

#### Zone breakdown

| Zone | Y range | Z | ซี่ | spacing |
|------|---------|---|-----|---------|
| 0 (entry) | −1→0 | 1.00m | — | 2 เสา + cross brace + 2 side rails |
| 1 (flat low) | 0→1 | 1.000m | Z1_00–05 (6 ซี่) | 20cm |
| 2 (ramp 45°) | 1→2 | 1.00→2.00m | Z2_01–06 (6 ซี่) | 20cm ตามลาด |
| 3 (flat high) | 2→3 | 2.000m | Z3_00–04 (5 ซี่) | 20cm |
| 4 (flying 35°) | 3→4 | 2.00→2.70m | Z4_00–04 (5 ซี่) | 25cm |

#### Zone 4 — Triangle brace

**Zone 4 — Triangle brace (มองด้านข้าง):** สามเหลี่ยมค้ำยันที่ปลายโครง โดยมุมฉาก 90° อยู่ที่ยอด Post_y3 (y=3, z=2.70m)
- **Post_y3** = ด้านตั้งฉาก (แนวตั้ง)
- **Tri_Horiz_L/R** = ด้านแนวนอนที่ z=2.70m (พาดจาก y=4 ไป y=5)
- **Rail_Z4** = ด้านตรงข้ามมุมฉาก (hypotenuse) เอียง 35°
- **Z4_04** (ซี่ปลายสุด) อยู่ที่ (y=4, z=2.70m) ทำหน้าที่ cross brace แทน Tri_Cap_B

#### บันได

| บันได | ตำแหน่ง | ซี่ | หมายเหตุ |
|-------|---------|-----|---------|
| Front ladder | y=0.00, ทิศ X | FrontLad_0.20–0.80 (4 ซี่) | ขึ้น Zone 1 |
| Side ladder | x=+0.50, ทิศ Y | Lad_0.20–Lad_1.80 (9 ซี่) | ขึ้น Zone 3 · ยึดที่ Post_y2_R / Post_y3_R |

**Footprint**: กว้าง 1.00m (x = −0.50 → +0.50) · ยาว 5.00m (y = −1.0 → +4.0)  
**จุดยึด**: เสาทุกต้น base plate + anchor bolt · ซี่เชื่อม fillet ระหว่าง Rail_L และ Rail_R

---

### Research Notes — การเลือกขนาดเหล็ก

#### 1. โจทย์ตั้งต้น

PIECE 4 ไม่มีการระบุ wall thickness ในแบบ draft มีสามคำถามหลัก: (1) SHS 50×50mm โครงสร้างหลักทุก zone ควรใช้ wall หนาเท่าไหร่ (2) แต่ละ zone ควรใช้ wall เดียวกันหรือต่างกัน และ (3) Rail_Z0 ที่ทำหน้าที่ทั้ง structural rail และ grip bar ควรเป็น SHS หรือ round bar

#### 2. เทียบกับผู้ผลิต commercial rig

ค้นหาจาก **GetRXD** (ผู้ผลิต outdoor CrossFit rig ระดับ commercial ที่ใช้กันแพร่หลายที่สุดในตลาด) พบว่า structural post และ rail ทุกชิ้นใช้ SHS 3"×3" / 7-gauge และ 11-gauge ซึ่งแปลงได้เป็น 76×76mm wall 3.0–4.6mm

ขนาดนี้ใหญ่กว่า SHS 50×50mm ใน PIECE 4 อย่างไรก็ตาม PIECE 4 เป็นโครงสร้าง portal frame ที่มีเสาและ cross rail หลายจุดค้ำกันตลอดความยาว 5m แรงจึงกระจายไปหลาย node ต่างจาก freestanding 2-post rig ของ GetRXD ที่เสาแต่ละต้นรับโหลดเดี่ยว SHS 50×50mm จึงเพียงพอสำหรับ residential use แบบนี้

#### 3. Wall thickness ตาม zone — แนวคิดหลัก

เมื่อมี dynamic load หรือ repeated stress เกี่ยวข้อง การเพิ่ม wall thickness มักได้ผลกว่าการเปลี่ยนเป็น grade เหล็กที่แข็งแรงขึ้น — นำมาใช้กับ PIECE 4 โดยแบ่งตามความสูงเสาและลักษณะโหลด:

- **Zone 0–2 (เสาสูง 1.00–2.00m)** รับ monkey bar load แบบ dynamic แต่เสาสั้น มี cross rail ค้ำถี่ → **wall 2.3mm** เพียงพอ เป็น standard มอก. หาง่ายทุกร้านในไทย
- **Zone 3–4 (เสาสูง 2.00–2.70m)** Post_y3 สูงที่สุดในโครงสร้าง รับแรงโยกจาก flying bar มุม 35° ซึ่งมีทั้ง vertical load และ horizontal component จากการแกว่งตัว → **wall 2.8mm** เพิ่มความหนาหนึ่งระดับ

ทั้ง 2.3mm และ 2.8mm มีขายในไทยชัดเจน SHS 2"×2" กัลวาไนซ์ในไทยมีขายทุกความหนาตั้งแต่ 1.1mm ถึง 3.2mm รวมถึง 2.3mm และ 2.8mm

#### 4. Triangle brace Zone 4

Post_y3 สูง 2.70m รับทั้ง vertical load และ horizontal component จาก flying bar มุม 35° triangle brace ที่ประกอบจาก Post_y3 (แนวตั้ง) + Tri_Horiz (แนวนอน) + Rail_Z4 (hypotenuse) ทำหน้าที่เป็น braced frame ลด effective length ของเสา ป้องกัน lateral buckling

Tri_Horiz เป็น compression/tension member ในโครง ไม่ได้รับ bending โดยตรง แรงกระจายตามแนวแกนของท่อ → **wall 2.3mm** เพียงพอ ไม่จำเป็นต้อง up-size ให้เท่ากับ primary post

#### 5. Rail_Z0 — เปลี่ยนจาก SHS เป็น OD 34mm

แบบ draft เดิมใช้ SHS 50×50mm wall 2.3mm สำหรับ Rail_Z0_Cross, Rail_Z0_L, Rail_Z0_R ตามโครงสร้างเดียวกับ Rail_Z1–Z4 เหตุผลที่เปลี่ยนเป็น **OD 34mm (เหมือนซี่)**:

- **ทั้ง 3 ชิ้นนี้ทำหน้าที่เป็น grip bar ด้วย** ไม่ใช่แค่ structural rail — Rail_Z0_L/R เป็นราวที่ผู้ใช้จับขณะเดินเข้าสู่ Zone 1, Rail_Z0_Cross เป็น cross brace ยอดเสา Zone 0 ที่อาจใช้จับได้เช่นกัน
- **Rail_Z1–Z4 เป็น SHS** เพราะทำหน้าที่ structural rail รับน้ำหนักซี่โดยตรง ผู้ใช้ไม่ได้จับ
- Rail_Z0 ทั้ง 3 ชิ้นอยู่ที่ z=1.0m ระดับเดียวกับซี่ Zone 1 — ผู้ใช้จะจับ/เกาะระหว่างเคลื่อนเข้า จึงควรเป็นรูปทรงกลม (round grip) ไม่ใช่ SHS ที่มีขอบ
- ขนาด OD 34mm เหมือนซี่ทุกชิ้นในโครง — ซื้อท่อท่อนเดียวกันได้ ไม่ต้องสั่ง SKU เพิ่ม

### แหล่งอ้างอิง

- [GetRXD — Galvanized Outdoor Builder Rig spec (SHS 3"×3" / 11-gauge)](https://www.getrxd.com/galvanized-outdoor-builder-rig.html)
- [GetRXD — Wall-Mount Builder Rig with Monkey Bar spec](https://www.getrxd.com/24ft-wall-mount-builder-rig-intermediate1-2ftmb.html)
- [Deportesurbanos — Calisthenics Classic Monkey Bars (post OD 114mm)](https://deportesurbanos.com/en/producto/calisthenics-classic-monkey-bars/)
- [Alibaba Sports Surge — How to Choose Steel Monkey Bars (wall thickness ≥ 2.5mm)](https://sportssurge.alibaba.com/guides/steel-monkey-bars)
- [Eastern Steels — SHS Steel Sizes: dynamic load → wall thickness guideline](https://www.eastern-steels.com/newsdetail/what-does-shs-mean-in-steel-terms-.html)
- [OneStockHome TH — เหล็กกล่อง 1½×1½ นิ้ว (38×38mm) กัลวาไนซ์](https://www.onestockhome.com/th/product_categories/steel-tube-1-1-2-x-1-1-2-inch-38x38mm)
- [Wongguru TH — เหล็กกล่อง GI กัลวาไนซ์ 2×2 ขนาด 1.1–3.2mm](https://www.wongguru.com/product/44178/)
- [Aplus Watsadu TH — เหล็กกัลวาไนซ์ GI 2"×2" หนา 1.2–3.2mm](https://en.aprimeplus.com/product-page/galvanized-steel-GI-2x2)

---

## PIECE 5 — Rubber Flooring (พื้นยาง)

พื้นยางกันกระแทกใต้และรอบอุปกรณ์ทั้งหมด — กันลื่น + ลดแรงกระแทกเวลาตก · เป็นตัวกำหนด datum **z=0 (ระดับยืนจริง)**

### สเปก

| รายการ | ค่า | หมายเหตุ |
|---|---|---|
| ความหนา | **25mm (≈1")** | กระเบื้องยาง outdoor มาตรฐาน |
| วัสดุ | EPDM ผิวหน้า บน SBR base (หรือ EPDM ตัน) | ทน UV / กลางแจ้ง |
| รูปแบบ | กระเบื้อง 50×50cm interlocking (หรือ wet-pour) | เปลี่ยนเฉพาะแผ่นที่เสียได้ |
| พื้นที่ปู | ~20 m² (เต็มพื้นที่ equipment 5×4m) | ยืนยัน m² จาก layout จริงอีกที |
| ฐานรอง | slab คอนกรีตเรียบ ลาดระบายน้ำ ~1% | ยางปูบน slab · เจาะ anchor ทะลุยางลง slab |

### ผลต่อความสูงเสา

ยาง 25mm ยกระดับยืนขึ้น 25mm → **เสา/ขาทุกชิ้นที่หยั่งพื้นตัดยาวขึ้น +25mm** เพื่อให้ความสูงใช้งานเหนือยางเท่าเดิม (base plate วางบน slab ใต้ยาง) · ดูความยาวตัดจริงใน **§ฐานราก** ถัดไป

> ⚠️ **recheck แรงกระแทก (CFH) — สำคัญ**: ยาง 25mm รับ critical fall height ได้ราว **1.0–1.4m** (อ้าง EN 1177) แต่ตกจาก Monkey bar (สูงสุด 2.70m) และ Pull-up (2.30m) เกินช่วงนี้ → **ใต้ Monkey + Pull-up ควรเพิ่มยางเป็น 40–50mm** หรือยืนยันค่า CFH กับผู้ขายก่อนสั่ง · ถ้าเพิ่มความหนาตรงไหน เสาโซนนั้นต้องตัดยาวขึ้นตามด้วย (เช่น 40mm → +40mm) · บริเวณ Dip (1.20m) ยาง 25mm พอ

---

## ฐานราก, เพลท & สลักยึด (Base Plate · Cap · Anchor Bolt)

ทุกชิ้นที่หยั่งพื้น (เสา + ขา dip) เชื่อม **base plate เหล็กหนา 9mm** ที่โคน แล้วยิง **anchor bolt 1/2" (M12) × 4"** ลง slab · ปลายบนเสากลวงปิด **ฝาเหล็ก 3mm** กันน้ำเข้า

### วิธีคิดขนาด (ใช้เหมือนกันทุกชิ้น)

- **base plate สี่เหลี่ยม (4 สลัก):** ด้าน = หน้าตัดเสา **+ 130mm** (เผื่อโคนเสา→ศูนย์สลัก 35mm + ระยะขอบ 30mm ต่อด้าน) · ระยะ gauge สลัก = หน้าตัดเสา + 70mm
- **รูสลักบนเพลท** Ø14mm (สำหรับ M12) · ศูนย์รูถึงขอบเพลท ≥ 25mm
- **สลัก M12 (1/2")×4":** ฝังคอนกรีตจริง ~70mm (พอสำหรับ wedge anchor) · ระยะขอบ slab ≥ 100mm · ระยะสลัก–สลัก ≥ 100mm
- **ฝาปิดบน 3mm** = หน้าตัดเสา + 4mm (ยื่นข้างละ 2mm) เชื่อมรอบ
- **ความยาวตัดเสา** = ความสูงออกแบบ (เหนือยาง ในตาราง PIECE) **+ 25mm**

> ✅ **recheck ความเพียงพอ:** โหลด residential calisthenics (ผู้ใช้ ~100kg, dynamic 3–5× ≈ แรงดึง/ตัด ไม่กี่ kN ต่อเสา) ต่ำกว่ากำลัง 4×M12 มาก (M12 wedge anchor ตัวเดียวรับแรงดึง/ตัดได้ราว 8–18 kN) · เพลท 9mm หนากว่าที่ M12 ต้องการ (ปกติ 6–8mm) → **bolt 1/2"×4" + เพลท 9mm = ปลอดภัย เผื่อเยอะ** สำหรับงานนี้ (ยืนยันกำลัง anchor ตามยี่ห้อ + กำลังคอนกรีต slab ≥ 20 MPa)

### PIECE 1 — Pull-up Bar · เสา SHS 76×76mm × 3

| เสา | ความยาวตัด (สูง +25mm) | base plate (9mm) | สลัก | ฝาปิดบน (3mm) |
|---|---|---|---|---|
| Post_Child | 1.625m | 210×210mm | 4 × M12×4" | 80×80mm |
| Post_Left | 2.325m | 210×210mm | 4 × M12×4" | 80×80mm |
| Post_Right | 2.325m | 210×210mm | 4 × M12×4" | 80×80mm |
| **รวม** | | **3 เพลท** | **12 สลัก** | **3 ฝา** |

### PIECE 2 — Snake Bar · เสา SHS 76×76mm × 2

| เสา | ความยาวตัด | base plate (9mm) | สลัก | ฝาปิดบน (3mm) |
|---|---|---|---|---|
| Post_Snake_L | 2.125m | 210×210mm | 4 × M12×4" | 80×80mm |
| Post_Snake_R | 2.125m | 210×210mm | 4 × M12×4" | 80×80mm |
| **รวม** | | **2 เพลท** | **8 สลัก** | **2 ฝา** |

### PIECE 3 — Dip Bar · ขาท่อกลม OD 42mm × 6 ขา

3 frame × 2 ขา = 6 ขาหยั่งพื้น · ขาเป็นท่อกลมในโครง ⊓ ที่แข็งในตัว → **2 สลัก/ขา พอ** · **ไม่มีฝาปิดบน** (โครงเป็น loop ปิด · ปลายล่างปิดด้วยเพลท)

| frame | ความยาวตัดท่อ (path) | base plate/ขา (9mm) | สลัก/ขา | จำนวนขา |
|---|---|---|---|---|
| DipBar_01 | 3.144m | 170×120mm | 2 × M12×4" | 2 |
| DipBar_02 | 3.144m | 170×120mm | 2 × M12×4" | 2 |
| DipBar_03 | 3.144m | 170×120mm | 2 × M12×4" | 2 |
| **รวม** | | **6 เพลท** | **12 สลัก** | **6 ขา** |

> path ท่อเพิ่มจาก 3.094 → **3.144m** (ขา 2 ข้างยาวขึ้นข้างละ 25mm) · grip z=1.20m เหนือยางเท่าเดิม · nub ไม่เปลี่ยน

### PIECE 4 — Monkey Flying Bar · เสา SHS 50×50mm × 10

| เสา | ความยาวตัด | base plate (9mm) | สลัก | ฝาปิดบน (3mm) |
|---|---|---|---|---|
| Post_pre_y0 L/R | 1.025m | 180×180mm | 4 × M12×4" | 55×55mm |
| Post_y0 L/R | 1.025m | 180×180mm | 4 × M12×4" | 55×55mm |
| Post_y1 L/R | 1.025m | 180×180mm | 4 × M12×4" | 55×55mm |
| Post_y2 L/R | 2.025m | 180×180mm | 4 × M12×4" | 55×55mm |
| Post_y3 L/R | 2.725m | 180×180mm | 4 × M12×4" | 55×55mm |
| **รวม (10 ต้น)** | | **10 เพลท** | **40 สลัก** | **10 ฝา** |

### 🧾 รวมทั้งโปรเจกต์ (ไว้สั่งซื้อ)

| รายการ | จำนวน | สเปก / หมายเหตุ |
|---|---|---|
| Base plate 210×210×9mm | 5 | SHS 76 (pull-up 3 + snake 2) |
| Base plate 180×180×9mm | 10 | monkey |
| Base plate 170×120×9mm | 6 | dip feet |
| **รวม base plate** | **21 แผ่น** | เหล็กเพลท 9mm ~0.67 m² (~47 kg) |
| ฝาปิด 80×80×3mm | 5 | SHS 76 |
| ฝาปิด 55×55×3mm | 10 | SHS 50 |
| **รวมฝาปิด** | **15 แผ่น** | เหล็กเพลท 3mm ~0.06 m² (~1.5 kg) |
| **Anchor bolt M12 (1/2")×4"** | **72 ตัว** | + นัต + แหวน 72 ชุด · เผื่อ +10% → สั่ง ~80 ตัว |

> ราคา anchor 1/2"×4" (ปลอกขยาย/wedge) ในไทย ~15–35 บาท/ตัว → ~80 ตัว ≈ 1,200–2,800 บาท · ราคาเพลทตัด+เจาะรู และค่าแรงเชื่อม ให้ลงในไฟล์ `quotation.*` แยก
