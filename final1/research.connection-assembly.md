# งานค้นคว้าอ้างอิง — ระบบ Shop-welded Field-bolted Connection
## (เชื่อมในโรงงาน · ชุบกัลวาไนซ์แยกชิ้น · ขันน็อตหน้างาน)

| หัวข้อ | รายละเอียด |
|---|---|
| สถานะ | เอกสารค้นคว้าประกอบการตัดสินใจ — ยังไม่ใช่แบบก่อสร้าง |
| วันที่สืบค้น | 16 มิถุนายน 2569 |
| เอกสารชุดเดียวกัน | [สารบัญ](toc.md) · [แบบและข้อกำหนด](spec.full.md) · [การวิเคราะห์แรง](spec.requirement.md) |
| โจทย์ที่ตั้ง | การเชื่อมหน้างานทำให้สังกะสีบริเวณรอยเชื่อมไหม้/ล้อน · เคลือบทั้งโครงหลังเชื่อมทำให้ชิ้นใหญ่เกินรางชุบ → แก้โดย: เชื่อมแต่ละชิ้นเข้า plate ในโรงงาน → ชุบ HDG ทีละชิ้น → ขันน็อตเชื่อม plate กันหน้างาน |
| แหล่งข้อมูลหลัก | Steel Tube Institute (AISC) · EN 1993-1-8 (Eurocode 3) · Galvanizers Association of Australia (GAA) · AGA (American Galvanizers Association) · Structure Magazine |

> **คำเตือน** ตัวเลขในเอกสารนี้เป็นการประมาณการเบื้องต้นจากการค้นคว้า ยังไม่ผ่านการคำนวณรับรองโดยวิศวกร จึงยังไม่ใช่แบบสำหรับนำไปก่อสร้างโดยตรง

---

## สารบัญ

1. [TL;DR — ตารางสรุปคำตอบ](#1-tldr)
2. [หลักการและตัวอย่างจากอุตสาหกรรมอื่น](#2-หลักการ)
3. [รูปแบบการต่อสำหรับโครงการนี้](#3-รูปแบบการต่อ)
4. [การออกแบบ End Plate — ขนาดและตำแหน่ง Bolt](#4-end-plate)
5. [การเลือก Bolt — เกรด ขนาด จำนวน กำลัง](#5-bolt)
6. [ข้อกำหนดการชุบ HDG — Vent Hole และลำดับงาน](#6-galvanizing)
7. [Torque ที่ใช้ขัน](#7-torque)
8. [ข้อแนะนำรายชิ้น (PIECE 1–4)](#8-รายชิ้น)
9. [ต้องปรับโครงสร้างเหล็กอะไรบ้าง](#9-การปรับโครงสร้าง)
10. [ประเด็นที่ต้องยืนยันกับวิศวกร](#10-ประเด็นค้าง)
11. [แหล่งอ้างอิง](#11-อ้างอิง)

---

## 1. TL;DR

| ประเด็น | คำตอบ |
|---|---|
| วิธีนี้ทำได้ไหม | ได้ — เป็นมาตรฐานอุตสาหกรรม "shop-welded, field-bolted" ใช้ในสะพาน โครงเหล็กอาคาร และสนามเด็กเล่น |
| ต้องเปลี่ยนขนาดเหล็กไหม | ไม่ต้อง — SHS/ท่อเดิมแข็งแรงพอเกินพอ อาจเพิ่ม plate เสริมที่หน้าเสาเท่านั้น |
| Plate ขนาดอะไร | SHS 76: **100×100×10 mm** · SHS 50: **80×80×8 mm** · OD 34/42: **80×80×8 mm** |
| Bolt ขนาดอะไร | **M12 Grade 8.8 HDG** ทุกจุดหลัก · M10 Grade 8.8 สำหรับซี่ monkey bar |
| จำนวน Bolt | **4 ตัว/จุดต่อ** ชิ้นหลัก · **2 ตัว/ปลาย** ซี่ |
| เจาะรูเท่าไหร่ | Ø15 mm สำหรับ M12 · Ø13 mm สำหรับ M10 (เจาะก่อนชุบ ไม่ต้อง re-tap) |
| Vent hole | ต้องมีทุกชิ้นปิดสนิท: SHS76 → **Ø32 mm** · SHS50 → **Ø25 mm** · OD34 → **Ø14 mm** · OD42 → **Ø18 mm** |
| Torque M12 HDG | **100–115 N·m** (เพิ่ม 25% จาก bare steel เพราะแรงเสียดทานของสังกะสี) |
| Monkey bar 35 ซี่ | **ไม่ต้อง plate ทีละซี่** — เชื่อมซี่เข้า rail section ก่อน → ชุบทั้ง section → bolt section เข้าเสา |
| รอยเชื่อมเล็กที่ซ่อมหน้างาน | Cold zinc spray (ASTM A780, สังกะสี ≥ 93%) ทาทับรอยตัด/เชื่อมเล็กน้อย |

---

## 2. หลักการ

### 2.1 ทำไมการเชื่อมถึงทำให้กัลวาไนซ์พัง

การชุบ HDG (Hot-Dip Galvanizing) สร้างชั้นสังกะสี-เหล็กอัลลอยด์ที่ยึดเกาะแน่นที่อุณหภูมิ 450–460°C ความร้อนจากการเชื่อม (800–1,400°C) ทำให้:

1. สังกะสีไหม้หายในบริเวณ Heat-Affected Zone (HAZ) กว้างประมาณ 30–50 mm รอบแนวเชื่อม
2. บริเวณที่ไม่มีสังกะสีเกิดสนิมได้ภายในไม่กี่สัปดาห์ในสภาวะกลางแจ้ง

วิธีแก้มาตรฐานในอุตสาหกรรม:
- **วิธี A (เล็ก):** เชื่อม → ใช้ cold zinc spray ซ่อมจุดที่สังกะสีหาย — ป้องกันได้บางส่วน แต่บางกว่า HDG ~5–10 เท่า
- **วิธี B (กลาง):** เชื่อมทุกอย่างก่อน → ชุบ HDG ทั้งชุด — ดีที่สุดด้านการเคลือบ แต่ชิ้นงานต้องพอดีกับรางชุบ (ไทยทั่วไปลึก 3–4 m)
- **วิธี C (โครงการนี้ใช้):** เชื่อม sub-assembly ขนาดเล็ก → ชุบ HDG ทีละ sub-assembly → ขันน็อต plate กันหน้างาน — ได้ทั้งการเคลือบคุณภาพสูงและประกอบหน้างานง่าย

### 2.2 ตัวอย่างจากอุตสาหกรรมอื่น

| อุตสาหกรรม | วิธีที่ใช้ | เหตุผล |
|---|---|---|
| สะพานเหล็กเล็ก | Bolted end plate (ชิ้น 3–6 m) | ชุบแยกชิ้น → ขนส่งง่าย |
| Pre-engineered Building (PEB) | Shop-welded frame → field bolts แผ่น end plate | มาตรฐาน MB/AISC |
| สนามเด็กเล่นสำเร็จรูป (Easyfit, Berliner) | Galvanized fittings + bolt assembly | ไม่มีการเชื่อมหน้างาน |
| Tower crane mast | Bolted flanged section | ต่อชิ้นสูงขึ้นได้ทีละ section |
| อุปกรณ์ออกกำลังกาย EN 16630 (BarManiaPro) | Post แยกชิ้น bolt ลง anchor → bar ขันเข้า bracket | ถอด-ประกอบซ่อมได้ |

### 2.3 หลักการ T-stub (EN 1993-1-8)

การออกแบบ end plate connection ตามมาตรฐานยุโรปใช้ "T-stub equivalent" โดยมี 3 โหมดความเสียหาย:

```
Mode 1: Plate hinge (plate บางเกินไป)
  → plate โก่งที่รอยเชื่อม + bolt ยืดออก
  → ต้องการ plate หนาขึ้น

Mode 2: Bolt fracture + prying (plate หนาปานกลาง)
  → bolt รับแรงดึง + แรง prying จาก plate โก่ง
  → ต้องการ bolt ขนาดใหญ่ขึ้น หรือ plate หนาขึ้น

Mode 3: Bolt fracture only (plate หนาพอ)
  → plate แข็งไม่โก่ง · bolt รับแรงตรง
  → สภาวะที่ดีที่สุด → ต้องการ plate หนา ≥ 9–12 mm
```

สำหรับโหลด EN 16630 ที่ 1,942 N (≈ 0.2 ตัน) ต่อจุด **โหลดต่ำมาก** — plate 8–10 mm จะอยู่ใน Mode 3 ทุกกรณี ความหนาที่กำหนดขับเคลื่อนด้วยความต้องการ geometric (พื้นที่ขันน็อต) ไม่ใช่กำลังโครงสร้าง

---

## 3. รูปแบบการต่อ

โครงการนี้มีสามรูปแบบการต่อที่เหมาะสม:

### Type A — End Plate บน Bar + Face Plate บนหน้าเสา

```
   [เสา SHS 76]
   |           |
   |  [face    |  ← plate 100×100×10 mm เชื่อมที่หน้าเสา (shop)
   |   plate]  |     มี 4 รู Ø15 ตรงกับ end plate ของบาร์
   |           |
        ↕ bolt 4× M12
   [bar OD34/42]
   [   end     ]  ← plate 100×100×10 mm เชื่อมที่ปลายบาร์ (shop)
   [   plate   ]     มี 4 รู Ø15 + vent hole Ø14
```

ใช้กับ: **Pull-up Bar_High / Bar_Low · Snake Bar_Straight · Side_Grip**

### Type B — Through-bolt ผ่าน Rail Section (monkey bar)

```
   [Rail SHS 50]
   |           |
   ●           ●  ← เจาะทะลุทั้งสองผนัง Ø13
   |           |
   [bolt M10 + nut ด้านใน/ด้านนอก]
   |
   [rung OD34]
   [end plate] ← Ø80×8 mm เชื่อมปลายซี่ (ถ้าต้องการ)
```

ใช้กับ: **Monkey bar rungs** (แต่แนะนำใช้ Rail section approach แทน — ดู §8)

### Type C — Base Plate (ใช้อยู่แล้วในแบบ)

```
   [เสา SHS]
   |       |
   [base plate] SHS76: 210×210×9 mm · SHS50: 180×180×9 mm
   ||||||||||||  ← 4× M12 anchor bolt ลงพื้นคอนกรีต
```

ใช้กับ: **ทุกเสา** (กำหนดแล้วใน spec.summary.md — ไม่เปลี่ยน)

---

## 4. End Plate — ขนาดและตำแหน่ง Bolt

### 4.1 หลักเกณฑ์ระยะห่าง (EN 1993-1-8 Table 3.3)

| พารามิเตอร์ | สูตรขั้นต่ำ | ค่าที่ใช้ (M12) | ค่าที่ใช้ (M10) |
|---|---|---|---|
| Edge distance e₁ (ปลายแผ่น ตามทิศแรง) | ≥ 1.2 × d₀ | ≥ 15.6 mm → **ใช้ 25 mm** | ≥ 13.2 mm → **ใช้ 20 mm** |
| Edge distance e₂ (ข้างแผ่น ตั้งฉากแรง) | ≥ 1.2 × d₀ | ≥ 15.6 mm → **ใช้ 25 mm** | ≥ 13.2 mm → **ใช้ 20 mm** |
| Bolt pitch p₁ (ระยะห่างระหว่าง bolt ตามแรง) | ≥ 2.2 × d₀ | ≥ 28.6 mm → **ใช้ 50 mm** | ≥ 24.2 mm → **ใช้ 40 mm** |
| Bolt pitch p₂ (ตั้งฉากแรง) | ≥ 2.4 × d₀ | ≥ 31.2 mm → **ใช้ 50 mm** | ≥ 26.4 mm → **ใช้ 40 mm** |

> d₀ = diameter รูเจาะ: M12 → d₀ = 13 mm (standard) หรือ 15 mm (หลังชุบ HDG) · M10 → d₀ = 11 mm หรือ 13 mm

### 4.2 ตารางขนาด Plate แนะนำ

| หน้าตัดที่ต่อ | ประเภท plate | ขนาด (กว้าง×สูง×หนา) | Pattern bolt | ช่องว่างปลาย bolt ถึงขอบ |
|---|---|---|---|---|
| SHS 76×76 — End plate บน bar | End plate | **100 × 100 × 10 mm** | 4× M12 ในกรอบ 50×50 mm | 25 mm ทุกด้าน |
| SHS 76×76 — Face plate บนเสา | Face plate | **100 × 100 × 10 mm** | รูตรงกับ end plate | 25 mm |
| SHS 50×50 — Rail section end | End plate | **80 × 80 × 8 mm** | 4× M10 ในกรอบ 40×40 mm | 20 mm ทุกด้าน |
| OD 34 — ปลายบาร์/ซี่ | End cap plate | **80 × 80 × 8 mm** | 2× M10 · pitch 40 mm | 20 mm |
| OD 42 — ปลายบาร์ dip/snake | End cap plate | **90 × 90 × 10 mm** | 2× M12 · pitch 50 mm | 20 mm |

> **ข้อสังเกต:** plate 100×100 mm บน SHS76 ยื่นเกินหน้าเสา (100−76)/2 = 12 mm ทุกด้าน — ยอมรับได้ ไม่มีผลต่อกำลัง

### 4.3 ตรวจสอบ Bearing บนผนัง SHS (กรณี through-bolt)

กรณี M10 through-bolt ผ่านผนัง SHS 50×50×2.3 mm:

```
Fb,Rd = 2.5 × αb × fu × d × t / γM2
      = 2.5 × 0.61 × 360 MPa × 10 mm × 2.3 mm / 1.25
      = 10,062 N / 1.25
      = 8,050 N (8.1 kN) ต่อ bolt ต่อผนัง 1 ชั้น

ผนัง 2 ชั้น × 2 bolt = 4 × 8.1 = 32.4 kN >> 1.942 kN → ผ่าน (margin 16×)
```

---

## 5. Bolt — เกรด ขนาด จำนวน และกำลัง

### 5.1 เลือก Grade 8.8 HDG

| Grade | fub (MPa) | ราคาเทียบ | ความเหมาะสม |
|---|---|---|---|
| 4.6 | 400 | ถูก | ไม่แนะนำ — กำลังต่ำ · ต้องใช้มากตัว |
| **8.8** | **800** | **กลาง** | **แนะนำ** — มาตรฐาน structural · หาได้ทั่วไปในไทย |
| 10.9 | 1,000 | แพงกว่า | เกินความจำเป็น |
| A2-70 (SS) | 700 | แพง | ดีมากด้าน corrosion แต่แพงกว่า HDG 8.8 ~3–5× |

> ใช้ **Grade 8.8 Hot-Dip Galvanized (HDG)** ตลอดโครงการ เหมือนกับ anchor bolt ที่ spec กำหนดอยู่แล้ว

### 5.2 กำลัง bolt ต่อตัว (EN 1993-1-8, γM2 = 1.25)

| ขนาด | As (mm²) | Fv,Rd (เฉือน/ตัว) | Ft,Rd (ดึง/ตัว) |
|---|---|---|---|
| M10 G8.8 | 58.0 | **22.3 kN** | **33.4 kN** |
| M12 G8.8 | 84.3 | **32.4 kN** | **48.6 kN** |

### 5.3 Margin เทียบกับโหลดออกแบบ

| จุดต่อ | โหลดออกแบบ | กำลัง (ต่ำสุด) | Safety margin |
|---|---|---|---|
| 4× M12 — บาร์ดึงข้อเข้าเสา | 1,942 N | 4×32.4 kN = 129.6 kN | **67×** |
| 2× M10 — ซี่ monkey เข้า rail | 1,942 N | 2×22.3 kN = 44.6 kN | **23×** |
| 4× M10 — rail section เข้าเสา | 1,942 N | 4×22.3 kN = 89.2 kN | **46×** |

> โหลดต่ำมากเมื่อเทียบกับกำลัง bolt — plate/bolt ที่เลือกขับเคลื่อนด้วยเงื่อนไข geometric (มีพื้นที่ขัน) ไม่ใช่กำลังโครงสร้าง

### 5.4 Washer

ใช้ **washer แบน HDG** ทุกจุด (หนา ≥ 3 mm) เพื่อกระจายแรงบน plate หัวบาง และป้องกัน bolt head จมลงใน plate

---

## 6. การชุบ HDG — Vent Hole และลำดับงาน

### 6.1 ทำไม Vent Hole ถึงสำคัญ

เมื่อชุบ HDG ชิ้นงานจะถูกจุ่มลงใน zinc bath อุณหภูมิ ~450°C อากาศและ flux ที่อยู่ในชิ้นส่วนปิดสนิทจะขยายตัวจนกลายเป็นไอ หากไม่มีทางออก:
- ไอขยายแรง → ชิ้นงานระเบิด/พุ่งออกจากราง (**อันตรายถึงชีวิต**)
- บางกรณี: coating ไม่สม่ำเสมอด้านใน → เกิดสนิมจากข้างใน

### 6.2 ขนาด Vent Hole ขั้นต่ำ

ขนาดรู ≥ 25% ของพื้นที่ภายในหน้าตัด (GAA / ASTM A385):

| หน้าตัด | พื้นที่ภายใน | 25% | Ø รู (กลม) | คำแนะนำ |
|---|---|---|---|---|
| SHS 76×76×3.2 | 69.6² = 4,844 mm² | 1,211 mm² | Ø39.3 → **Ø40 mm** | เจาะ 1 รูใน base plate ใกล้ผนัง |
| SHS 50×50×2.3 | 45.4² = 2,061 mm² | 515 mm² | Ø25.6 → **Ø26 mm** (ใช้ **Ø28 mm**) | เจาะ 1 รูใน base plate หรือ end cap |
| OD 34×3.2 | π×13.8² = 598 mm² | 150 mm² | Ø13.8 → **Ø14 mm** | เจาะ 1 รูใน end plate |
| OD 42×3.2 | π×17.8² = 995 mm² | 249 mm² | Ø17.8 → **Ø18 mm** | เจาะ 1 รูใน end plate |

> **ตำแหน่งรู:** ห้ามเจาะตรงกลาง plate — เจาะชิดผนังท่อด้านใน ห่างจากแนวเชื่อม ≥ 10 mm ทุกกรณี (เพื่อให้ flux ออกได้และไม่ขังระหว่างผนังกับรู)

### 6.3 ลำดับงาน

```
[โรงตัด/ดัด]
  1. ตัด SHS/ท่อตามขนาด
  2. เจาะรู bolt Ø15 mm (M12) หรือ Ø13 mm (M10)
  3. เจาะ vent hole ตามตาราง §6.2

[ช่างเชื่อม — shop]
  4. เชื่อม end plate เข้าปลายบาร์/ซี่ (sub-assembly ขนาดเล็ก)
  5. เชื่อม face plate เข้าหน้าเสา (ที่ตำแหน่งจุดต่อบาร์)
  6. เชื่อม base plate เข้าปลายล่างเสา
  7. ตรวจสอบรอยเชื่อม (ต้องรอบและต่อเนื่อง ไม่มีรู)
  8. ทำความสะอาด สกัดสะเก็ด flux

[ร้านชุบ HDG]
  9. ชุบ HDG ทีละ sub-assembly (แยกชิ้น ไม่ประกอบก่อนชุบ)
 10. ตรวจ coating หลังชุบ (ขั้นต่ำ 85 μm ตาม EN ISO 1461)

[หน้างาน]
 11. ยึด anchor bolt + base plate เสาลงพื้นคอนกรีต
 12. ประกอบชิ้นส่วน: วาง face plate เสา ↔ end plate บาร์ ให้รูตรงกัน
 13. ใส่ bolt + washer ทุกตัว ขันมือก่อน (snug-tight)
 14. ขันด้วย torque wrench ตาม §7
 15. ทาสี cold zinc spray บริเวณรอยตัดหรือรอยเชื่อมหน้างาน (ถ้ามี)
```

### 6.4 รู Bolt หลังชุบ

HDG เพิ่มความหนา ~50–85 μm ต่อผิว → รูขนาด Ø15 mm (สำหรับ M12) และ Ø13 mm (สำหรับ M10) ยังคงรับ bolt ผ่านได้โดยไม่ต้อง re-tap:

| Bolt | เจาะก่อนชุบ | หลังชุบ (เสีย ~0.2 mm รัศมี) | M bolt เส้นผ่านศูนย์กลาง | Clearance ที่เหลือ |
|---|---|---|---|---|
| M12 | Ø15 mm | ≈ Ø14.6 mm | 12.7 mm (พร้อมชุบ) | ~0.95 mm/ข้าง |
| M10 | Ø13 mm | ≈ Ø12.6 mm | 10.6 mm (พร้อมชุบ) | ~1.0 mm/ข้าง |

> ถ้า bolt เข้าไม่ได้: ใช้ดอกสว่าน Ø15.5 mm คว้านเบา ๆ หรือลวดทำความสะอาดรู (ไม่ต้อง tap ใหม่เพราะรูไม่ใช่รูเกลียว)

---

## 7. Torque

### 7.1 ค่า Torque แนะนำ

HDG เพิ่ม K-factor (ค่าแรงเสียดทาน thread) จาก 0.20 (bare) เป็น ~0.25 (HDG) → torque ที่ต้องใช้สูงขึ้น ~25%:

| Bolt | Grade | สภาพ | Torque เป้าหมาย |
|---|---|---|---|
| M10 | 8.8 | HDG (ไม่ทา lubricant) | **52–65 N·m** |
| M12 | 8.8 | HDG (ไม่ทา lubricant) | **100–115 N·m** |
| M12 | 8.8 | HDG + ทา anti-seize | ~85–91 N·m |

> ถ้าต้องการลด torque และถอดประกอบง่ายขึ้น: ทา **anti-seize compound** ที่เกลียว nut ก่อนขัน → K-factor กลับใกล้ 0.20 → torque ≈ bare steel

### 7.2 ลำดับการขัน

1. ใส่ bolt ทุกตัวในจุดต่อ ขันด้วยมือจนไม่หลวม (snug-tight)
2. ขันไขว้ดาว (crisscross pattern) ในรอบ 50% → 100% torque
3. ตรวจ: หัก bolt เล็ก (tension indicator) หรือใช้ marker เส้นตรงตรวจการหมุน

---

## 8. ข้อแนะนำรายชิ้น

### 8.1 PIECE 1 — Pull-up Bar

Sub-assemblies:
- **Post_Left / Right / Child** (แต่ละต้นแยกกัน): เสา + base plate + **2 face plate** (ที่ตำแหน่ง z=2.20 m และ z=1.50 m)
- **Bar_High** (บาร์ผู้ใหญ่): ท่อ OD34×1.50 m + **2 end plate** ที่ปลาย
- **Bar_Low** (บาร์เด็ก): ท่อ OD34×1.00 m + **2 end plate** ที่ปลาย

Face plate บนเสา (ที่ z=2.20 m และ z=1.50 m):
- ขนาด **100×100×10 mm** เชื่อมแบน flush กับหน้าเสา SHS 76 ด้านที่บาร์เชื่อม
- รู 4× Ø15 mm ในกรอบ 50×50 mm centered
- เชื่อมรอบขอบ plate กับหน้า SHS (fillet weld ≥ 5 mm)

End plate บนบาร์:
- ขนาด **100×100×10 mm** เชื่อมตั้งฉากกับแนวท่อ OD34 ที่ปลายบาร์
- รู 4× Ø15 mm ในกรอบ 50×50 mm centered (ตรงกับ face plate เสา)
- vent hole **Ø14 mm** offset จากศูนย์กลาง ชิดผนังท่อ

Bolt: **4× M12 × 40 mm G8.8 HDG** ต่อปลาย (รวม 8 ตัว/บาร์)

### 8.2 PIECE 2 — Snake Bar

Sub-assemblies:
- **Post_L / R**: เสา + base plate + face plate สำหรับ Bar_Straight (z=1.962 m)
- **Bar_Straight** (OD42×2.00 m): + **2 end plate 90×90×10 mm**
- **Bar_Wave** (OD34): เชื่อมแนบ Bar_Straight ตลอดแนว → ชุบเป็น unit เดียวกับ Bar_Straight (ไม่ต้องแยก plate)
- **Side_Grip** (8 ชิ้น, OD34): แต่ละชิ้น + **2 end plate 80×80×8 mm** weld เข้าปลาย

> Side_Grip มีจุดเชื่อม 2 จุดต่อชิ้น (บน-ล่าง) หน้า Post_L หรือ R ต้องมี 4 face plate/ต้น (= 8 face plate ทั้งสองต้น) แต่ละ face plate 80×80×8 mm พร้อม 2×M10

### 8.3 PIECE 3 — Dip Bar

DipBar frame (โครง ⊓): ท่อ OD42 ดัดรูปตัว U → ขายึดพื้น 2 จุด

Sub-assemblies: **แต่ละโครง DipBar_01/02/03 เป็น sub-assembly เดียว** ชุบ HDG ทั้งโครง (ชิ้นไม่ใหญ่ ~120×75 cm)

ขาหยั่งมีฐานตามแบบเดิม (base plate 120×120×6 mm · 2× M10/ขา) → **ไม่เปลี่ยน**

Nub (มือจับ C): เชื่อมเข้าโครง DipBar ก่อนชุบ — อยู่ใน sub-assembly เดียวกัน → **ไม่ต้อง plate แยก**

### 8.4 PIECE 4 — Monkey + Flying Bar (กรณีพิเศษ)

**ปัญหา:** มี 35 ซี่ OD34 ยาว 1.0 m — ทำ plate ทีละซี่ = 70 end plate + 140 bolt → ซับซ้อนและแพง

**วิธีที่แนะนำ: Rail Section approach**

แบ่ง rail ออกเป็น section ตามช่วงเสา (1 m/section) → เชื่อมซี่เข้า rail section ในโรงงาน → ชุบ HDG ทั้ง section → bolt section เข้าเสาหน้างาน:

```
Section ตัวอย่าง (Zone 1):
  [Rail_Z1_L] SHS 50×50 ยาว 1.0 m
  ├── rung ①  OD34 × 1.0 m  เชื่อมที่ y=0.00
  ├── rung ②  OD34 × 1.0 m  เชื่อมที่ y=0.20
  ├── rung ③  OD34 × 1.0 m  เชื่อมที่ y=0.40
  ├── rung ④  OD34 × 1.0 m  เชื่อมที่ y=0.60
  └── rung ⑤  OD34 × 1.0 m  เชื่อมที่ y=0.80
  → ชุบ HDG ทั้ง section → bolt end plate เข้าเสา
```

End plate ปลาย rail section: **80×80×8 mm** · 4× M10 G8.8 · กรอบ 40×40 mm

Post face plate (บนหน้าเสา SHS 50 ที่รับ rail): **80×80×8 mm** · รูตรงกัน

Vent hole ของ rail section SHS 50: เจาะ **Ø28 mm** ที่ end plate ทั้งสองปลาย (off-center ชิดผนัง)

**จำนวน rail section ทั้งหมด (Monkey bar):**

| Zone | Rail L | Rail R | Section/ด้าน |
|---|---|---|---|
| Zone 0 (y=−1→0) | 1 | 1 | — (ท่อกลม) |
| Zone 1 (y=0→1) | 1 | 1 | 5 ซี่/section |
| Zone 2 (y=1→2, เอียง 45°) | 1 | 1 | ซี่เว้น ~25 cm ตามความลาด |
| Zone 3 (y=2→3) | 1 | 1 | 5 ซี่/section |
| Zone 4 (y=3→4, เอียง 35°) | 1 | 1 | ซี่เว้น ~25 cm |

รวม ~10 rail section + triangle brace → ชุบ 10 ชิ้น แทนที่จะเป็น 35 ชิ้นแยก

---

## 9. ต้องปรับโครงสร้างเหล็กอะไรบ้าง

| รายการ | ปรับหรือไม่ | รายละเอียด |
|---|---|---|
| ขนาด SHS 76×76×3.2 | ไม่ปรับ | แข็งแรงเกินพอ margin ≥ 20× |
| ขนาด SHS 50×50×2.3/2.8 | ไม่ปรับ | — |
| ขนาดท่อ OD34/OD42 | ไม่ปรับ | — |
| Base plate + anchor bolt | ไม่ปรับ | ใช้ตามแบบเดิม (210×210×9, M12) |
| **Face plate เพิ่มที่หน้าเสา** | **เพิ่ม** | 100×100×10 mm เชื่อมที่หน้าเสาทุกจุดต่อบาร์ |
| **End plate เพิ่มที่ปลายบาร์** | **เพิ่ม** | ขนาดตาม §4.2 |
| **Vent hole ในทุก base plate** | **เพิ่ม** | SHS76: Ø40 mm · SHS50: Ø28 mm (เดิมมี bolt hole แต่ไม่พอ) |
| **Vent hole ใน end plate บาร์** | **เพิ่ม** | OD34: Ø14 mm · OD42: Ø18 mm |
| ความยาวเสา/บาร์ | ตรวจสอบ | end plate แต่ละปลายเพิ่มความยาวรวม +10 mm/จุดต่อ — ปกติไม่มีผล แต่ให้ระบุในแบบ |
| Triangle brace (Monkey Zone 4) | ไม่ปรับ | ยังคงต้องมีตามแบบเดิม |

---

## 10. ประเด็นที่ต้องยืนยันกับวิศวกร

1. **Weld throat ที่ face plate → เสา:** fillet weld 5 mm รอบ 100×100 plate เพียงพอหรือต้องใช้ full penetration?
2. **Plate thickness ใน prying check ละเอียด:** 10 mm เพียงพอหรือต้องการ 12 mm? (ประเมินเบื้องต้นพอแต่ยังไม่ได้คำนวณ T-stub)
3. **Bearing บน SHS wall (through-bolt monkey):** ผนัง 2.3 mm ผ่านตามประมาณ §4.3 — วิศวกรควรยืนยันอีกครั้ง
4. **SHS50 สำหรับ rail section end plate:** 4× M10 ใน 40×40 mm อาจชิดกว่ามาตรฐาน (e₂ ≈ 20 mm ใกล้ขั้นต่ำ) — พิจารณาใช้ plate 90×90 mm แทน
5. **ลำดับประกอบหน้างาน:** ต้องประกอบเสาก่อนหรือบาร์ก่อน? End plate อาจบล็อกการเข้าถึงบางจุด
6. **Vent hole ใน base plate SHS76:** Ø40 mm ขนาดใหญ่ — ตรวจสอบว่ากระทบกำลัง plate หรือไม่ (สำหรับขนาด plate 210×210×9 mm น่าจะไม่กระทบ แต่ควรยืนยัน)

---

## 11. แหล่งอ้างอิง

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
