# Research — ขนาดเหล็ก · Base Plate · Anchor Bolt (สำหรับรีวิว spec v2)

> **สถานะ**: เอกสาร research อย่างเดียว — ยังไม่แก้ spec.human.v2.md
> **วันที่สืบค้น**: 11 มิ.ย. 2026
> **วิธีสืบค้น**: อ่านจากเอกสารต้นฉบับโดยตรง 2 ฉบับ (EN 16630:2015 ฉบับเต็ม PDF + Hilti HSA Technical Datasheet Jan-23) + หน้า product จริงของผู้ผลิต 9 ราย + ร้านวัสดุไทย
> **ข้อสรุปสั้น**: เหล็กที่ใช้อยู่ใน spec v2 **แข็งแรงพอทุกชิ้น** (มี margin 3–5 เท่า) — สิ่งที่ spec ยังขาดคือ **รายละเอียด base plate + anchor bolt** ซึ่งรวบรวมไว้ครบในเอกสารนี้แล้ว รอคุยกันก่อนใส่เข้า spec

---

## สารบัญ

1. [TL;DR — ตารางสรุปคำแนะนำ](#1-tldr--ตารางสรุปคำแนะนำ)
2. [มาตรฐาน EN 16630:2015 — ตัวเลขที่ design ต้องผ่าน](#2-มาตรฐาน-en-166302015)
3. [Brand survey — เหล็กที่ผู้ผลิตดังใช้จริง](#3-brand-survey)
4. [เทียบ brand กับ spec v2 รายชิ้น](#4-เทียบ-brand-กับ-spec-v2-รายชิ้น)
5. [Base plate — ขนาด ความหนา และหลักการเลือก](#5-base-plate)
6. [Anchor bolt — ข้อมูลเต็มจาก Hilti HSA datasheet](#6-anchor-bolt)
7. [ความหนาพื้นปูน + ระยะขอบที่ต้องมี](#7-พื้นปูน)
8. [Sanity check เชิงวิศวกรรม (ประมาณการเบื้องต้น)](#8-sanity-check)
9. [ของที่หาซื้อได้ในไทย](#9-ตลาดไทย)
10. [ประเด็นที่ต้องคุยกันก่อนแก้ spec](#10-ประเด็นค้าง)
11. [แหล่งอ้างอิงทั้งหมด](#11-แหล่งอ้างอิง)

---

## 1. TL;DR — ตารางสรุปคำแนะนำ

| เสา | ขนาดเหล็ก (spec v2) | ผลรีวิว | Base plate แนะนำ | Anchor แนะนำ |
|---|---|---|---|---|
| Pull-up Post_L/R (2.30m) | SHS 76×76 w3.2 | ✅ พอ (margin ~4×) | **200×200×9mm** เจาะ 4 รู Ø14 | **4× M12×120 wedge (HDG)** ฝัง hef 65mm |
| Pull-up Post_Child (1.60m) | SHS 76×76 w3.2 | ✅ พอ (เหลือเฟือ) | 200×200×9mm | 4× M12×120 |
| Snake Post_L/R (2.10m) | SHS 76×76 w3.2 | ✅ พอ | 200×200×9mm | 4× M12×120 |
| Monkey Post เตี้ย y−1/y0/y1 (1.00m) | SHS 50×50 w2.3 | ✅ พอ | **150×150×6mm** เจาะ 4 รู Ø12 | **4× M10×100 wedge (HDG)** ฝัง hef 50mm |
| Monkey Post_y2 (2.00m) | SHS 50×50 w2.8 | ✅ พอ (มี rail ค้ำ) | 200×200×9mm | 4× M12×120 |
| Monkey Post_y3 (2.70m) | SHS 50×50 w2.8 | ✅ พอ **เพราะมี triangle brace** (เสาเดี่ยวไม่มี brace จะไม่ผ่าน — ดู §8.3) | 200×200×9mm | 4× M12×120 |
| Dip frame ขา (×6 จุด) | ท่อ OD 42 w3.2 | ✅ พอ | **120×120×6mm**/ขา เจาะ 2–4 รู Ø12 | 2–4× M10×100 ต่อขา |
| บาร์จับทุกชิ้น OD 34 / OD 42 | — | ✅ ตรง EN 16630 grip 16–45mm พอดี | — | — |

> ทุกตัวเลขในตารางนี้มีที่มาในเอกสาร — base plate ดู §5, anchor ดู §6, การคำนวณดู §8

---

## 2. มาตรฐาน EN 16630:2015

อ่านจากต้นฉบับ **EN 16630:2015 (E) "Permanently installed outdoor fitness equipment — Safety requirements and test methods"** ([PDF ฉบับเต็ม](https://www.spartanparks.com.au/wp-content/uploads/2021/04/EN_16630_2015.pdf)) — มาตรฐานเดียวกับที่ BarManiaPro / Deportesurbanos ใช้ certify สินค้า ใช้กับผู้ใช้สูง >1,400mm (เด็ก 5 ขวบใช้ EN 1176 ควบ ซึ่ง spec v2 อ้างอยู่แล้ว)

### 2.1 โหลดออกแบบ (Clause 4.3.2, Table 1) — หัวใจของการเช็คความแข็งแรง

| จำนวนผู้ใช้ n | มวลรวม Gn (kg) | Dynamic factor Cdyn | แรงดิ่งรวม Ftot,v (N) | แรงดิ่งต่อคน (N) |
|:---:|:---:|:---:|:---:|:---:|
| 1 | 99 | 2.00 | **1,942** | 1,942 |
| 2 | 185 | 1.50 | **2,722** | 1,361 |
| 3 | 270 | 1.33 | 3,523 | 1,174 |

สูตร: `Gn = n×m + 1.64×σ×√n` โดย m = 78kg (ผู้ชายวัย 18–65 เปอร์เซ็นไทล์ 50), σ = 12.6kg และ `Cdyn = (1+n)/n`

→ แปลความ: **1 user station ต้องออกแบบรับ ~198kg (แรงดิ่ง รวม dynamic แล้ว)** — ตัวคูณ dynamic ×2 ครอบคลุม kipping/แกว่งตัวแล้วในเชิงมาตรฐาน
→ โครงของเรา: pull-up bar ออกแบบที่ n=2 (ผู้ใหญ่+เด็ก) = 2,722 N กระจาย 2 เสา · monkey bar zone หนึ่งๆ มีคนโหนได้ 1 คน = 1,942 N ต่อซี่

- เครื่องต้อง **"permanently connected to the substrate"** — ยึดพื้นถาวร (แนวทาง base plate + bolt ของมึงตรงข้อนี้)
- พิสูจน์ความแข็งแรงได้ด้วย (a) การคำนวณตาม EN 1176-1:2008 Annex A/B โดยใช้ Table 1 ข้างบน หรือ (b) ทดสอบจริง

### 2.2 ขนาด grip (Clause 4.3.12)

- ชิ้นที่ออกแบบให้ **กำมือจับ (grip)**: หน้าตัด **≥16mm และ ≤45mm** ทุกทิศทาง
  → OD 34mm (rungs, pull-up, snake) และ OD 42mm (dip) **ผ่านทั้งคู่** · OD 42 ใกล้เพดาน 45mm — ห้ามเผื่อขึ้นไป 48mm
- ชิ้นที่แค่ **เกาะ/พิง (grasp)**: กว้างได้ถึง 80mm → เสา SHS 76mm ยังอยู่ในเกณฑ์ grasp

### 2.3 Free height of fall (Clause 4.3.14.5, Table 4)

| ลักษณะใช้งาน | วัดจาก | เพดาน |
|---|---|---:|
| ยืน (standing) | พื้นรองเท้า → พื้น | 2.0m |
| ห้อยโหน (hanging) | **ระดับมือจับ − 1m** → พื้น | 3.0m |

→ ของเรา: pull-up 2.20m → fall height 1.20m ✓ · monkey apex 2.70m → 1.70m ✓ · ทุกชิ้นต่ำกว่าเพดาน 3m สบาย แต่ **ต้องมีพื้นรองรับแรงกระแทกตามระดับ fall height** (EN 1177) — แผน EPDM 25mm ใน CLAUDE.md ต้องเช็ค critical fall height ของวัสดุจริงตอนซื้อ (EPDM 25mm ทั่วไป rated ~1.0m — โซน monkey 1.7m อาจต้องหนากว่าหรือใช้ยางเม็ดหนาขึ้น — **ประเด็นค้าง §10**)

### 2.4 Foundations (Clause 4.3.15)

- ฐานราก **ห้ามเป็นจุดสะดุด/กระแทก** (tripping, impact hazard)
- กรณีพื้นวัสดุร่วน (ทราย/ยางเม็ด): ยอด footing ลึก ≥200mm ใต้ผิว หรือตัว fixing ลึก ≥400mm (Figure 12: หลุมลึก ≥400mm บากขอบ 45°)
- **ปลาย bolt/สกรูที่โผล่จากฐานต้องลึก ≥400mm หรือถูกครอบปิด**
- กรณีของมึง (base plate บนพื้นปูนเรียบ): มาตรฐานยอมรับ — เทียบ Deportesurbanos ที่ระบุวิธีติดตั้ง "expansion plugs on concrete cubes or slabs" ตรงๆ — แต่ต้องจัดการขอบ plate + หัว bolt ตาม §2.5

### 2.5 Surface finish (Clause 4.3.3) — เกี่ยวกับหัว bolt โดยตรง

- **เกลียวโผล่ต้องถูกปิดถาวร** ทุกจุดที่ผู้ใช้เข้าถึง (เช่น **dome nut / ฝาครอบ**)
- หัว nut/bolt โผล่ได้ ≤8mm เฉพาะจุดที่เข้าถึงยาก และต้องไม่มีครีบคม
- มุม/ขอบที่ยื่น >8mm ในพื้นที่เล่น ต้องลบมุม R ≥3mm
  → **base plate ทุกแผ่นควรลบมุม + หัวพุกใส่ dome cap หรือตัดเกลียวส่วนเกินแล้วครอบ** — ใส่ขั้นตอนนี้ใน quotation ช่างได้เลย

---

## 3. Brand survey

ไล่จากระดับ commercial park → prosumer → home rig (เรียงตามความใกล้เคียงกับงานเรา)

### 3.1 ตารางรวม

| Brand (ประเทศ) | ระดับ | เสา | บาร์จับ | กันสนิม | การยึดพื้น |
|---|---|---|---|---|---|
| **Deportesurbanos** (ES) | commercial park, UNE-EN 16630 | ท่อกลม **Ø114mm** galvanized | **Ø33.7mm** (มีไลน์ 25/32/38/48/60mm) | galvanized + powder coat | **anchor base Ø300mm + metal expansion plug บนพื้นคอนกรีต** หรือฝัง footing |
| **KOMPAN** (DK) | commercial park, EN 16630/1176 | **Ø101.6mm** pre-galvanized | dip/parallel grip **Ø38mm** HDG | pre-galv + HDG | in-ground footing หรือ **surface mount: steel footing + expansion bolts** |
| **BarManiaPro** (EU) | commercial street workout, NEN-EN 16630:2015 | column ยาว 3,400mm (โผล่ ~2.5m = **ฝังดิน ~0.9m**) | **Ø33.7mm** · รุ่น Basic Ø32mm | 2-coat system | ฝัง footing (มาตรฐานสนามสาธารณะ) · max user 130kg · warranty 25 ปี |
| **Kenguru Pro** (EU) | commercial, TÜV/GOST | ไลน์เก่า: ท่อโค้ง **Ø48mm** (PK series) · ไลน์ใหม่ 2024: เสา aluminum anodized + แนวนอน stainless | — | anodize / zinc primer | ฝัง footing |
| **TOLYMP** (DE) | **prosumer สวนบ้าน** — ใกล้งานเรามากสุด | **RHS 80×60mm wall 3.0mm** stainless V2A | Ø33mm (gym bar) | stainless (ไลน์เหล็ก galv มีเฉพาะ H-post) | **ฝังคอนกรีตลึก ~60cm** เทียบเสาตรง + ใช้ M12 threaded rod ตั้งระยะ · ปรับสูง-ต่ำด้วย M12 star-grip |
| **GetRXD** (US) | commercial/backyard rig | **SHS 3"×3" (76mm)** 11-gauge (~3.0mm) หรือ 7-gauge (~4.6mm) | Ø1.25" (~32mm) | **hot-dip galvanized ทั้งใน-นอก** | **base plate เจาะรูสำเร็จ + concrete anchor 4 ชุด** (แถมมากับ rig) — โมเดลเดียวกับแผนของมึงเป๊ะ |
| **Rogue** (US) | commercial rig | 3"×3" 11-gauge, hardware 5/8" (≈16mm) | Ø32–43mm | powder coat (ไลน์ in-door) | base plate + **HD concrete anchor** (สลักถอดได้ รูเจาะ 3/8") |
| **Eleiko Prestera** (SE) | commercial outdoor | โครง rig galvanized | **Ø33mm** (ระบุว่า optimal grip) | galvanized | base plate + anchor |
| **GORNATION / FitnessKIT** (DE) | prosumer dip bar | — | **Ø40mm / Ø43mm** | powder/galv | — |

### 3.2 ข้อสังเกตสำคัญจากตาราง

1. **เสา commercial park (Ø101–114mm) ใหญ่กว่าของเรา 1.5 เท่า — แต่นั่นคือสเปกรับคนพร้อมกัน 5+ คนในสวนสาธารณะ** (EN Table 1: n=5 → 5,133 N) และต้องกัน vandalism · ส่วน **rig/home segment (GetRXD, Rogue, TOLYMP) ใช้ 76mm หรือ 80×60mm wall ~3mm — ตรงรุ่นกับ SHS 76×76 w3.2 ของเราพอดี** → ขนาดเสาใน spec v2 อยู่ในไลน์เดียวกับผู้ผลิตกลุ่มที่ตรง use case
2. **บาร์จับ Ø33–34mm คือ consensus ของทั้งวงการ** (Deportesurbanos 33.7 / BarManiaPro 33.7 / Eleiko 33 / TOLYMP 33) → OD 34 ของเราถูกต้อง
3. **Dip grip 38–43mm คือ consensus** (KOMPAN 38 / GORNATION 40 / FitnessKIT 43) → OD 42 ของเราถูกต้อง
4. การยึดพื้นมี 2 ค่ายชัดเจน: **ค่ายยุโรปสนามสาธารณะนิยมฝัง footing ลึก 60–90cm** (TOLYMP, BarManiaPro) ส่วน **ค่าย rig อเมริกา + ตัวเลือก surface ของ KOMPAN/Deportesurbanos ใช้ base plate + expansion anchor บนพื้นคอนกรีต** → แผน base plate ของมึงมีผู้ผลิตระดับ commercial ทำเป็นมาตรฐานอยู่จริง ไม่ใช่ทางลัด
5. ตัวเลขอ้างอิงขนาด base ของจริง: **Deportesurbanos ใช้ anchor base Ø300mm กับเสา Ø114** (อัตราส่วน base ≈ 2.6× เสา) → เสา 76mm ตามอัตราส่วนนี้ ≈ 200mm — ตรงกับที่คำนวณใน §5

---

## 4. เทียบ brand กับ spec v2 รายชิ้น

### PIECE 1 — Pull-up Bar

| รายการ | spec v2 | Benchmark | ผล |
|---|---|---|---|
| เสา 2.30m | SHS 76×76 w3.2 | GetRXD 76mm/3.0–4.6mm (เสาสูง 12–15 ฟุต!) · TOLYMP 80×60/3.0 | ✅ อยู่กลางช่วง — เสาเราสูงแค่ 2.3m เตี้ยกว่า rig พวกนี้ครึ่งหนึ่ง |
| บาร์ z=2.20m | OD 34 w3.2 | Eleiko 33 / BarManiaPro 33.7 | ✅ ตรง |
| ความยาวบาร์ 1.50m | — | BarManiaPro crossbar 1.45m | ✅ ตรงเป๊ะ (เขา rate 130kg) |
| บาร์เด็ก z=1.50m | OD 34 | EN 1176 child grip 16–45 | ✅ |

### PIECE 2 — Snake Bar

| รายการ | spec v2 | Benchmark | ผล |
|---|---|---|---|
| เสา 2.10m | SHS 76×76 w3.2 | Deportesurbanos snake bar ใช้เสาเดียวกับ pull-up (Ø114 commercial) | ✅ logic เดียวกับ PIECE 1 |
| Wave bar | OD 34 w3.2, 8 bends R100 | Deportesurbanos/BarManiaPro Ø33.7 | ✅ R100 = 3×OD มาตรฐาน rotary-draw |
| Side U-grips | OD 34, R100 | — (ไม่มี brand เทียบตรง — custom) | ✅ grip ผ่าน EN · weld 2 จุด/ชิ้น ดู §8.4 |

### PIECE 3 — Dip Bar

| รายการ | spec v2 | Benchmark | ผล |
|---|---|---|---|
| Frame OD 42 w3.2 สูง 1.2m | — | KOMPAN grip Ø38 HDG (เสา Ø101.6 เพราะเป็น park) · GORNATION Ø40 · FitnessKIT Ø43 | ✅ 42 อยู่กลางช่วง 38–43 |
| โหลด | — | EN: dip = 1 user/ช่อง → 1,942 N | ✅ ท่อ Ø42×3.2 ยาว span 620mm รับได้สบาย (ดู §8.5) |

### PIECE 4 — Monkey + Flying Bar

| รายการ | spec v2 | Benchmark | ผล |
|---|---|---|---|
| เสาเตี้ย 1.0m | SHS 50×50 w2.3 | ไม่มี brand ไหนใช้เสาเล็กกว่า 76mm ใน standalone — **แต่ของเราเป็น portal frame เสา 10 ต้น + rail ค้ำตลอด 5m** | ✅ ดูการคำนวณ §8.3 |
| เสาสูง y2/y3 (2.0/2.7m) | SHS 50×50 w2.8 | GetRXD monkey bar rig ใช้ 76mm แต่เป็น freestanding 2–4 เสา | ✅ **ผ่านเพราะมี triangle brace** — ห้ามตัด brace ออกเด็ดขาด |
| ซี่ OD 34 ห่าง 20cm | — | สนามสาธารณะทั่วไป rung Ø33.7 ห่าง 20–30cm | ✅ |
| Rail_Z0 OD 34 | — | EN grip 16–45 | ✅ เหตุผลถูกต้องที่เปลี่ยนจาก SHS |

---

## 5. Base plate

### 5.1 หลักการเลือกขนาด (จาก engineering practice)

- **Edge distance ของ bolt บน plate**: rule of thumb ปฏิบัติ = เผื่อรอบเสา ~4d (d = เส้นผ่านศก. bolt) · ขั้นต่ำตามโค้ด (AISI S100 E.42) = 1.5d จากศูนย์ bolt ถึงขอบ plate ([Eng-Tips](https://www.eng-tips.com/threads/base-plate-design.425962/), [AWS forum](https://app.aws.org/forum/topic_show.pl?tid=8230))
- ขนาด plate ≈ หน้าเสา + 2×(ระยะวาง bolt + edge distance): เสา 76mm + 2×(40 + 22) ≈ **200mm** → สอดคล้องอัตราส่วนจริงของ Deportesurbanos (Ø300 ต่อเสา Ø114 = 2.6×; ของเรา 200/76 = 2.6× เท่ากันพอดี)
- **ความหนา**: งานรับโมเมนต์ (เสา pull-up/snake ที่รับแรงดึงเอียง) ใช้ 9–12mm · งานรับแรงกดเป็นหลัก (เสาเตี้ย, dip) 6mm พอ — ความหนา plate ควร ≥ 2× wall ของเสาเป็นอย่างต่ำเพื่อให้รอย fillet weld รอบเสาพัฒนากำลังเต็ม
- **รูเจาะบน plate** = clearance hole ตาม Hilti: M12 → **Ø14mm** · M10 → **Ø12mm** (ห้ามเจาะเผื่อหลวมกว่านี้ — wedge anchor ต้องการรูแนบ)
- weld เสา-plate: fillet รอบตัว ขา ≥ wall ของเสา (3.2mm → fillet 4–5mm) + **เจาะรูระบายน้ำ 1 รูที่ก้นเสา หรือเชื่อมปิดยอดเสา** กันน้ำขังในกล่อง (จุดตายของเสากลางแจ้ง)

### 5.2 ตารางขนาดแนะนำต่อเสา

| เสา | จำนวนต้น/จุด | Plate | รูเจาะ | Bolt pattern (ระยะศูนย์รู) | หมายเหตุ |
|---|:---:|---|---|---|---|
| Pull-up ทั้ง 3 ต้น | 3 | **200×200×9mm** | 4× Ø14 | 140×140mm | มุมลบ R≥3mm ตาม EN |
| Snake 2 ต้น | 2 | 200×200×9mm | 4× Ø14 | 140×140mm | — |
| Monkey y−1/y0/y1 (6 ต้น) | 6 | **150×150×6mm** | 4× Ø12 | 100×100mm | เสาเตี้ย โมเมนต์น้อย |
| Monkey y2/y3 (4 ต้น) | 4 | **200×200×9mm** | 4× Ø14 | 140×140mm | เสาสูง โมเมนต์หลัก |
| Dip frame (3 เฟรม × 2 ขา) | 6 | **120×120×6mm** หรือแผ่นกลม Ø120 | 2× Ø12 (แนว Y) | 80mm | ขาท่อกลม Ø42 weld ลง plate |

> รวมวัสดุ: plate 200×200×9 = 9 แผ่น · 150×150×6 = 6 แผ่น · 120×120×6 = 6 แผ่น
> ร้านไทยรับตัด+เจาะตามแบบ (ดู §9.2) — ส่งแบบ DXF/มิติให้ร้านเจาะมาเลย ช่างหน้างานไม่ต้องเจาะเอง

### 5.3 ทำไมไม่ต้องมี gusset (ครีบค้ำ)

เสาทุกต้นรับโมเมนต์สูงสุด ~2.2 kN·m (ดู §8.2) — plate 9mm ที่ยื่นจากหน้าเสา ~60mm มี bending capacity ของแผ่นเองพอรับ prying force ระดับนี้ (แรงดึง bolt ฝั่งเดียว ≤8 kN) ถ้าอยาก margin เพิ่มในเสา Post_y3 จะเติม gusset 2 ใบ (50×50×6mm) ฝั่งรับแรงก็ได้ แต่ **ไม่จำเป็นจากตัวเลข** — เก็บเป็น option ตอนคุยกับช่าง

---

## 6. Anchor bolt

### 6.1 ชนิดที่เหมาะ: wedge anchor (พุกเวดจ์/พุกตะกั่วเหล็ก)

ตรงกับที่ผู้ผลิต commercial ใช้จริง — Deportesurbanos: "metal expansion plugs on concrete slabs" · KOMPAN: "steel footings and expansion bolts" · GetRXD แถม concrete anchor มากับ rig — งานเราโหลด static + dynamic ปานกลาง พื้นคอนกรีตไม่แตกร้าว → wedge anchor มาตรฐานพอ ไม่ต้องถึง chemical anchor (เก็บ chemical ไว้เป็น fallback ถ้าเจอปูนหน้างานคุณภาพต่ำ/รูเจาะพลาด — ราคาแพงกว่าแต่ติดตั้งให้อภัยกว่า)

### 6.2 ข้อมูลเต็มจาก Hilti HSA Technical Datasheet (Jan-2023, ETA-11/0374)

อ่านจาก[ต้นฉบับ PDF](https://kalaomran.com/wp-content/uploads/2023/11/Technical-data-sheet-for-the-HSA-stud-anchor-Technical-information-ASSET-DOC-2027424.pdf) — ใช้ Hilti เป็น reference spec แล้วเทียบเกรดกับพุกไทยตอนซื้อจริง (ค่า capacity ของพุกโนเนมให้หาร 1.5–2 เผื่อไว้)

#### Setting details (คอนกรีต C20/25 ไม่แตกร้าว)

| | M10 | M12 | M16 |
|---|---|---|---|
| ความลึกฝังที่ใช้ hef (mm) | 40 / **50** / 80 | 50 / **65** / 100 | 65 / 80 / 120 |
| ความลึกเจาะรู hnom (mm) | 50 / **60** / 90 | 64 / **79** / 114 | 77 / 92 / 132 |
| ดอกสว่าน Ø (mm) | 10 | **12** | 16 |
| ความลึกรูเจาะขั้นต่ำ (mm) | 55 / 65 / 95 | 72 / **87** / 122 | 85 / 100 / 140 |
| **ความหนาปูนขั้นต่ำ hmin (mm)** | 100 / **120** / 160 | 100 / **140** / 180 | 140 / 160 / 180 |
| ระยะห่างรูขั้นต่ำ smin (mm) | 50 | **70** | 90 |
| ระยะขอบปูนขั้นต่ำ cmin (mm) | 40–50 | **55–70** | 70–80 |
| ระยะขอบเพื่อ capacity เต็ม ccr,N (mm) | 60 / 75 / 120 | 75 / **97.5** / 150 | 97.5 / 120 / 180 |
| Torque ขัน Tinst (N·m) | 25 | **50** | 80 |
| รู clearance บน plate (mm) | ≤12 | **≤14** | ≤18 |

#### Recommended loads (รวม safety factor γ=1.4 แล้ว) — ต่อ 1 ตัว

| | M10 | M12 | M16 |
|---|---|---|---|
| Tension Nrec (kN) ตาม hef | 5.9 / **8.3** / 11.9 | 8.3 / **12.3** / 16.7 | 12.3 / 16.8 / 23.8 |
| Shear Vrec (kN) | 10.8–12.9 | **16.6–16.9** | 29.1–32.3 |

→ **M12 ฝัง hef 65mm: รับดึง 12.3 kN/ตัว = ~1.2 ตัน** — เทียบ demand ของเราต่อตัวสูงสุด ~4 kN (§8.2) = margin ×3
→ เสาเตี้ย monkey ใช้ M10 hef 50 (8.3 kN/ตัว) เหลือเฟือ

#### วัสดุ + ความยาวที่ต้องสั่ง

- รุ่น **HSA ธรรมดา = ชุบซิงค์ ≥5µm — ไม่พอสำหรับกลางแจ้งถาวร** · กลางแจ้งต้องรุ่น **HSA-F (hot-dip galvanized ≥42µm)** หรือ stainless (HSA-R) — พุกไทยก็มีเกรด HDG ขาย (§9.1)
- ความยาวที่แนะนำ: **M12×120** → ฝัง hnom 79 (hef 65) เหลือโผล่ ~41mm = nut 10 + แหวน 2.5 + plate 9 → เหลือเกลียวโผล่เหนือ nut ~19mm → **ตัดทิ้ง/ครอบ dome cap ตาม EN 4.3.3**
- M10×100 → ฝัง hnom 60 (hef 50) + plate 6 + nut 8 → โผล่ ~26mm → จัดการแบบเดียวกัน
- จำนวนรวมทั้งโปรเจกต์: **M12×120 = 36 ตัว** (9 เสา × 4) + **M10×100 = 36 ตัว** (เสาเตี้ย 6×4 + dip 6×2) + spare ~10%

### 6.3 ขั้นตอนติดตั้งที่ถูกต้อง (จาก datasheet — ใส่ลง quotation ช่างได้)

1. เจาะรูด้วยดอก Ø ตรงเบอร์ ลึก ≥ hnom+5mm ตั้งฉาก 90°
2. **เป่า/ปั๊มลมทำความสะอาดรู** (ขั้นตอนที่ช่างไทยข้ามบ่อยสุด — ฝุ่นในรูลด capacity ได้ >30%)
3. สอดพุกผ่านรู plate ตอกจนแหวนสีน้ำเงิน/มาร์คจมถึงระดับ
4. **ขันด้วย torque wrench ตามค่า Tinst** (M12 = 50 N·m, M10 = 25 N·m) — ห้ามขันด้วยความรู้สึก เกิน = พุกสลิป/ปูนแตก ขาด = โยก

---

## 7. พื้นปูน

| เงื่อนไข | ค่าที่ต้องมี | ที่มา |
|---|---|---|
| ความหนา slab ขั้นต่ำ (M12 hef 65) | **≥140mm** | Hilti hmin |
| ความหนา slab ขั้นต่ำ (M10 hef 50) | ≥120mm | Hilti hmin |
| กำลังปูน | C20/25 (≈ st.210–240 ksc cube) — ปูนโครงสร้างทั่วไปผ่าน | ฐานข้อมูล Hilti ทั้งตาราง |
| ระยะ bolt → ขอบ slab | ≥70mm (ขั้นต่ำ) · **≥100mm (แนะนำ — ได้ capacity เต็ม)** | cmin / ccr,N |
| สภาพปูน | ไม่แตกร้าวบริเวณติดตั้ง | HSA เป็นพุกสำหรับ uncracked concrete |

→ floor_v1 ใน design เป็น slab 6×5m หนา 0.30m — **ผ่านทุกข้อแบบขาดลอย** ✅
→ ของจริงหน้างาน: ถ้าจุดไหนเป็นปูนเก่า ต้องวัดความหนาจริง ≥140mm ก่อน (สว่านเจาะนำเช็คได้) และเสาทุกต้นใน layout ปัจจุบันห่างขอบ slab >100mm อยู่แล้วถ้าวางตาม margin 0.5m ใน plot
→ TOLYMP เป็นข้อมูลเทียบฝั่งฝัง: footing ลึก ~60cm ต่อเสา — ถ้าอนาคตมีชิ้นไหนตั้งนอก slab ใช้สูตรนี้ (หลุม Ø30×ลึก 60cm เทปูนหุ้มเสา)

---

## 8. Sanity check

> ⚠️ ทั้ง section นี้คือ **ประมาณการเบื้องต้นมือเปล่า** (first-order estimate) เพื่อยืนยันว่า order of magnitude ถูก — ไม่ใช่ structural calculation ฉบับเซ็นแบบ · สมมติฐาน: เหล็กกล่องไทย มอก./STKR400 fy ≈ 245 MPa · โหลดจาก EN Table 1

### 8.1 คุณสมบัติหน้าตัด

| หน้าตัด | Section modulus Z (cm³) | Moment ที่จุด yield ≈ (kN·m) |
|---|---:|---:|
| SHS 76×76×3.2 | 21.7 | **5.3** |
| SHS 50×50×2.8 | 7.9 | 1.9 |
| SHS 50×50×2.3 | 6.7 | 1.6 |
| ท่อ OD 42.4×3.2 | 3.6 | 0.88 |
| ท่อ OD 34×3.2 | 2.2 | 0.55 |

### 8.2 เสา pull-up (กรณีหนักสุดของเสา 76mm)

- โหลดดิ่ง EN n=2: 2,722 N ÷ 2 เสา → axial จิ๊บจ๊อย (เสารับ axial ได้เป็นร้อย kN) — ไม่ critical
- โหลดข้างจากการแกว่ง (kipping): ประมาณ horizontal ≈ 0.5×G ≈ **1.0 kN ที่ z=2.2m** → โมเมนต์โคนเสา ≈ 2.2 kN·m แชร์ 2 เสาผ่านบาร์ → **~1.1 kN·m/เสา**
- เทียบ capacity 5.3 kN·m → **utilization ~21% → margin ≈ 4.8×** ✅ (แม้คิดเสาเดียวรับเต็มๆ ก็ 42%)
- แรงดึงพุกจาก overturning เสาเดียว: M=2.2 kN·m / lever arm 0.14m (bolt pattern 140mm) ≈ 15.7 kN ÷ 2 ตัวฝั่งดึง ≈ **7.9 kN/ตัว < 12.3 kN** ✅ (และนี่คือ case เสาเดียวรับโมเมนต์ทั้งหมดซึ่ง conservative มาก)

### 8.3 เสา monkey bar — จุดที่บางที่สุดของโปรเจกต์ (แต่ผ่าน)

- **Post_y3 (2.7m, SHS 50×50×2.8)**: คนโหน flying bar แกว่ง → horizontal ≈ 0.5–0.7 kN ที่ z=2.7m → ถ้าเสาเดี่ยวอิสระ M ≈ 1.4–1.9 kN·m ชน capacity 1.9 kN·m พอดี — **เสาเดี่ยวไม่มี brace = ไม่เหลือ margin**
- ความจริงโครงเป็น braced frame: triangle (Post_y3 + Tri_Horiz + Rail_Z4) + Rail_Z3 + ซี่ 5 ชิ้น/zone กระจายแรงไปเสาข้างเคียง → โมเมนต์จริงต่อเสาเหลือราว 1/3–1/2 → utilization ~35–50% ✅
- **ข้อสรุปเชิง design**: SHS 50 w2.8 พอ "เพราะ" โครงค้ำกันครบตาม spec v2 — **ถ้าวันไหนคิดตัด Tri_Horiz / Rail_Z4 / Rail_Z3 ออก ต้อง up เสาเป็น 76mm** · ระหว่างประกอบ ห้ามให้เสา y3 ยืนเดี่ยวโดยไม่มี rail ค้ำแล้วมีคนโหน
- เสาเตี้ย 1.0m (w2.3): M สูงสุด ≈ 1.0 kN × 1.0m = 1.0 kN·m... จริงๆ โหลด monkey ปกติคือดิ่ง 1.9 kN ลงซี่ → rail แชร์ 2 ฝั่ง เสารับ axial เป็นหลัก → utilization ต่ำมาก ✅

### 8.4 ซี่ + side grips (OD 34×3.2)

- ซี่ยาว 1.0m จับกลางคาน: จุดอ่อนสุดคือ mid-span M = PL/4 = 1.942×1.0/4 ≈ **0.49 kN·m < 0.55** — utilization ~89%?? ดูเยอะ แต่ 1.942 kN รวม dynamic ×2 แล้ว และซี่เชื่อม 2 ปลาย (fixed-ish, M จริง ≈ PL/8 = 0.24) → utilization จริง ~45% ✅ — ตรงกับที่ทั้งวงการใช้ Ø33.7 ความยาวระดับ 1.0–1.5m เป็นมาตรฐาน
- Side U-grip ยื่น 250mm: M = 1.942×0.25 ≈ 0.49 kN·m ที่จุด weld — case เหยียบเต็มน้ำหนัก+กระโดด · ปกติ grip ใช้มือจับ (โหลดน้อยกว่า) แต่เด็กอาจปีน → **จุด weld 2 จุด/ชิ้นบนหน้าเสาต้องเชื่อมเต็มรอบท่อ (full perimeter fillet)** ไม่ใช่ tack — note ให้ช่าง

### 8.5 Dip bar (OD 42.4×3.2)

- คานบน span 620mm รับ 1,942 N กลาง span (เกาะ 2 มือชิด): M ≈ PL/8–PL/4 ≈ 0.15–0.30 kN·m < 0.88 → utilization ≤34% ✅
- ขาเฟรมสูง 1.2m: แรงข้างจากการ L-sit/แกว่ง ≈ 0.3 kN → M ≈ 0.36 kN·m → ~41% ✅

### 8.6 สรุป sanity check

ทุกชิ้นมี margin ≥2× จาก first-order estimate ภายใต้โหลดมาตรฐาน EN — **ไม่มีชิ้นไหนต้อง up-size และไม่มีชิ้นไหน over-size จนเปลืองเงินเกินเหตุ** จุดที่ต้องเคารพ design เดิมเคร่งครัดมีจุดเดียวคือ triangle brace ของ Zone 4 (§8.3)

---

## 9. ตลาดไทย

### 9.1 พุกเวดจ์ (wedge anchor)

| ของ | สเปก | แหล่ง |
|---|---|---|
| MR METAL M12×100 (แพ็ค 5) ชุบซิงค์ขาว | ใช้ได้ในร่ม/ชั่วคราว | [ไทวัสดุ](https://www.thaiwatsadu.com/en/product/%E0%B8%9E%E0%B8%B8%E0%B8%81%E0%B9%80%E0%B8%A7%E0%B8%94%E0%B8%88%E0%B9%8C-MR-METAL-%E0%B8%82%E0%B8%99%E0%B8%B2%E0%B8%94-M12-x-100-%E0%B8%A1%E0%B8%A1-(%E0%B9%81%E0%B8%9E%E0%B9%87%E0%B8%81-5-%E0%B8%95%E0%B8%B1%E0%B8%A7)-%E0%B8%AA%E0%B8%B5%E0%B8%8B%E0%B8%B4%E0%B8%87%E0%B8%84%E0%B9%8C%E0%B8%82%E0%B8%B2%E0%B8%A7-60374011) |
| Wedge anchor M12×120 ชุบซิงค์ / **ชุบ Hot-dip (HDG)** | **กลางแจ้งใช้ตัว HDG** | [พุกเหล็ก.com — M12×120 HDG](https://www.xn--12caal4gxbxbo7c2db8dwa3g5e.com/product/%E0%B8%82%E0%B8%99%E0%B8%B2%E0%B8%94-m12x120mm-%E0%B8%9E%E0%B8%B8%E0%B8%81%E0%B9%80%E0%B8%A7%E0%B8%94%E0%B8%88%E0%B9%8C%E0%B8%8A%E0%B8%B8%E0%B8%9A%E0%B8%AE%E0%B8%AD%E0%B8%97%E0%B8%94%E0%B8%B4%E0%B8%9E-hdg/11000711956001552), [Stronghold Asia](https://strongholdasia.net/product/wedge-anchors-m12x120-120-mm/) |
| Siam Anchor Fastener — WA-HDG ผลิตไทย | wedge anchor hot-dip galvanized ตรงสเปกกลางแจ้ง | [fastenic.com](https://www.fastenic.com/product/detail/wedge-anchor-hot-dip-galvanized---wa-hdg) |
| พุกเคมี M12 (fallback) | กรณีปูนหน้างานแย่/รูเจาะพลาด | [PK Hardware](https://www.pkhardware.com/%E0%B8%AA%E0%B8%B4%E0%B8%99%E0%B8%84%E0%B9%89%E0%B8%B2/%E0%B8%9E%E0%B8%B8%E0%B8%81%E0%B9%80%E0%B8%84%E0%B8%A1%E0%B8%B5/%E0%B8%9E%E0%B8%B8%E0%B8%81%E0%B9%80%E0%B8%84%E0%B8%A1%E0%B8%B5%E0%B9%81%E0%B8%9A%E0%B8%9A%E0%B8%9B%E0%B8%B1%E0%B9%88%E0%B8%99-m12-chemical-anchor-bolt) |
| Hilti HSA-F แท้ | reference spec — แพงกว่าแต่มี ETA รับรอง | ตัวแทน Hilti TH |

> **ข้อควรระวัง**: พุกซิงค์ขาว (white zinc ~5µm) ไว้ใช้ในร่ม — กลางแจ้งโดนฝน **ต้องเลือกตัว HDG หรือ stainless** ให้สอดคล้องกับธีม galvanized ทั้งโปรเจกต์ ราคาต่างกันไม่กี่สิบบาท/ตัว

### 9.2 แผ่นเพลท base plate

| ของ | สเปก | แหล่ง |
|---|---|---|
| เพลทเหล็ก 150×150mm เจาะรู/สั่งตัด | หนา 6mm มีพร้อมเจาะ | [Aplus Watsadu](https://www.apluswatsadu.com/product/steel-plate-carbon-150x150/) |
| เพลทเหล็ก 200×200mm | หนา **6 / 9 / 10 / 12mm** เจาะรูตามแบบ | [Aplus Watsadu](https://www.apluswatsadu.com/product/steel-plate-carbon-200x200-mm/) |
| เพลท 4"/6"/8" ตัดตามแบบ ราคาโรงงาน | ปลีก-ส่ง | [Lerlert Corp](https://www.lerlertcorp.com/steel-plate/), [OneStockHome](https://www.onestockhome.com/th/product_categories/steel-plate), [TintSteel](https://tint-steel.com/steel-plate/) |

> เพลทที่ขายเป็น**เหล็กดำ (carbon, ไม่ชุบ)** — โปรเจกต์เราต้องเอาไป **ชุบ hot-dip galvanizing หลัง weld กับเสา** (ชุบทั้ง assembly เสา+plate ทีเดียว = มาตรฐานเดียวกับ GetRXD ที่ชุบ "inside and out") หรืออย่างน้อยพ่น cold-galvanizing spray หนาๆ ที่รอยเชื่อม — ประเด็นนี้กระทบลำดับงานช่าง (weld ก่อน ชุบทีหลัง) ต้องใส่ใน quotation

### 9.3 ของที่ spec v2 มีอยู่แล้ว (ยืนยันซ้ำ)

- SHS 76×76 w3.2 galv: Aplus Watsadu ✓ · SHS 50×50 w2.3/2.8 galv: หาง่ายทุกร้าน ✓ · ท่อกลม OD 34/42 galv: มาตรฐาน 1"/1¼" BSP ✓ (อ้างอิงใน spec.human.v2.md แล้ว)

---

## 10. ประเด็นค้าง

เรื่องที่ research แล้วเจอ แต่ต้องตัดสินใจร่วมกันก่อนแก้ spec:

1. **พื้นกันกระแทกโซน monkey/flying bar** — fall height 1.7m เกิน rating ทั่วไปของ EPDM 25mm (~1.0m) · ทางเลือก: (a) EPDM/ยางเม็ดหนาขึ้น 40–50mm เฉพาะโซนนั้น (b) ทรายหนา 200mm+ แบบสนามสาธารณะ (c) ยอมรับ risk ระดับบ้าน (มาตรฐานเป็น guideline ไม่ใช่กฎหมายไทย) — **กระทบงบ ต้องคุย**
2. **ชุบ HDG หลังเชื่อม plate หรือใช้ cold-galv spray** — ชุบจริงทนกว่ามากแต่ต้องส่งโรงชุบ (กระทบ logistics + ราคา ~30–40 บาท/kg) vs สเปรย์ถูกแต่ที่รอยเชื่อมจะเป็นจุดสนิมแรกใน 3–5 ปี
3. **เกลียวพุกโผล่เหนือ nut ~19mm** — EN บอกต้องปิด: ใช้ dome cap nut M12 (หาในไทยได้) หรือให้ช่างตัดเกลียวส่วนเกิน+แต้มซิงค์ — เลือกแบบไหนใส่ quotation
4. **Dip bar ขายึด 2 รูต่อขา พอไหม vs 4 รู** — โหลดผ่านสบาย (margin เยอะ) แต่ 4 รูกัน rocking ระยะยาวดีกว่า เพิ่มงานเจาะ 12 รู — จุดนี้กูเอียงไป 4 รูเฉพาะเฟรมนอก 2 ตัว
5. **Base plate ใต้เสา = จุดสะดุดตาม EN** — ทางแก้ระดับบ้าน: ลบมุม + ทาสีเหลืองตัดขอบ หรือถมยาง EPDM ชนขอบ plate — เลือกตอนทำพื้น
6. งบ: วัสดุใหม่ที่เพิ่ม ≈ เพลท 21 แผ่น + พุก ~80 ตัว + ค่าชุบ/สเปรย์ — ประเมินหยาบ **3,500–8,000 THB** (ขึ้นกับข้อ 2) — ไม่กระทบงบรวม (เหลือ ~61k)

---

## 11. แหล่งอ้างอิง

### เอกสารมาตรฐาน + datasheet (อ่านจากต้นฉบับเต็ม)

- [EN 16630:2015 (E) — Permanently installed outdoor fitness equipment (PDF ฉบับเต็ม)](https://www.spartanparks.com.au/wp-content/uploads/2021/04/EN_16630_2015.pdf) — Table 1 loads, clause 4.3.2/4.3.3/4.3.12/4.3.14.5/4.3.15
- [Hilti HSA Expansion Anchor — Technical Datasheet Jan-23, ETA-11/0374 (PDF)](https://kalaomran.com/wp-content/uploads/2023/11/Technical-data-sheet-for-the-HSA-stud-anchor-Technical-information-ASSET-DOC-2027424.pdf) — setting details, recommended loads, ความยาว/letter codes
- [Confast — Wedge Anchor Technical Specifications](https://www.confast.com/wedge-anchor-technical-specifications/)
- [Ferry International — M12 Anchor Bolt Load Capacity Chart](https://www.ferry-international.com/blog/126/anchor-bolt-load-capacity-chart)

### Brand product pages

- [Deportesurbanos — Outdoor Pull Up Bar DUCP-2009](https://deportesurbanos.com/en/producto/outdoor-pull-up-bar/) — เสา Ø114, anchor base Ø300, expansion plugs, UNE-EN 16630
- [BarManiaPro — Pull-up bar BMP-51007](https://barmaniapro.com/product/pull-up-bar/) — Ø33.7, column 3.4m, 130kg, NEN-EN 16630:2015
- [BarManiaPro — Pull-up bar Basic](https://barmaniapro.com/product/pull-up-bar-pro/) — Ø32
- [Kenguru Pro — PK-007](https://kengurupro.eu/equipment/pk-007/), [About](https://kengurupro.eu/about/), [Kenguru Pro Canada](https://www.kengurupro.ca/equipment/) — ท่อ Ø48 (PK line), ไลน์ใหม่ aluminum+stainless, TÜV
- [TOLYMP Towers](https://www.tolymp.de/en/stations-de-calisthenics-street-workout/tolymp-towers.html/), [TOLYMP Cross Basic](https://www.tolymp.de/en/crossfit-outdoor-gym-equipment/tolymp-cross-basic.html/) — เสา 80×60 w3.0, ฝังปูน ~60cm, M12 rods
- [KOMPAN — FPW201 Parallel Bars](https://www.kompan.com/en/int/p/fpw201) — เสา Ø101.6 pre-galv, grip Ø38 HDG (อ้างใน spec v2 แล้ว)
- [GetRXD — Galvanized Outdoor Builder Rig](https://www.getrxd.com/galvanized-outdoor-builder-rig.html) — 3"×3" 7/11-gauge, baseplate + 4 ชุด concrete anchor
- [Rogue — Monster Lite Rig 2.0](https://www.roguefitness.com/monster-lite-rig-2-0) — 3×3" 11ga, 5/8" hardware · [Rogue HD Concrete Anchors](https://www.roguefitness.com/rogue-hd-concrete-anchors)
- [Eleiko — Prestera Straight Pull-up Bar Outdoor](https://eleiko.com/en/equipment/outdoor/galvanized/3085515-01-eleiko-prestera-straight-pull-up-bar-outdoor) — bar Ø33
- [GORNATION Premium Dip Bars](https://www.gornation.com/products/premium-dip-bars) Ø40 · [FitnessKIT Premium Dip Bar](https://fitnesskit.de/en/products/premium-dip-barren-calisthenics-equipment) Ø43 (อ้างใน spec v2 แล้ว)
- [MoveStrong FitGround](https://www.movestrongfit.com/fitground-1) — in-ground anchoring standard, surface mount option

### Base plate engineering practice

- [Eng-Tips — Base Plate Design (4d rule of thumb)](https://www.eng-tips.com/threads/base-plate-design.425962/)
- [AWS Forum — Minimum Edge Distance on Base Plates (AISI 1.5d)](https://app.aws.org/forum/topic_show.pl?tid=8230)
- [SkyCiv — AISC Base Plate Design](https://skyciv.com/docs/skyciv-base-plate-design/aisc-base-plate-design-code/)
- [Hilti — Anchor Plate Dimensions Q&A](https://www.hilti.com/engineering/question/anchor-plate-dimensions/gxubit)

### ร้านไทย

- [ไทวัสดุ — พุกเวดจ์ MR METAL M12×100](https://www.thaiwatsadu.com/en/product/%E0%B8%9E%E0%B8%B8%E0%B8%81%E0%B9%80%E0%B8%A7%E0%B8%94%E0%B8%88%E0%B9%8C-MR-METAL-%E0%B8%82%E0%B8%99%E0%B8%B2%E0%B8%94-M12-x-100-%E0%B8%A1%E0%B8%A1-(%E0%B9%81%E0%B8%9E%E0%B9%87%E0%B8%81-5-%E0%B8%95%E0%B8%B1%E0%B8%A7)-%E0%B8%AA%E0%B8%B5%E0%B8%8B%E0%B8%B4%E0%B8%87%E0%B8%84%E0%B9%8C%E0%B8%82%E0%B8%B2%E0%B8%A7-60374011)
- [Stronghold Asia — Wedge Anchor M12×120](https://strongholdasia.net/product/wedge-anchors-m12x120-120-mm/) · [M12×100](https://strongholdasia.net/product/wedge-anchors-m12x100-100-mm/)
- [พุกเหล็ก.com — M12×120 HDG](https://www.xn--12caal4gxbxbo7c2db8dwa3g5e.com/product/%E0%B8%82%E0%B8%99%E0%B8%B2%E0%B8%94-m12x120mm-%E0%B8%9E%E0%B8%B8%E0%B8%81%E0%B9%80%E0%B8%A7%E0%B8%94%E0%B8%88%E0%B9%8C%E0%B8%8A%E0%B8%B8%E0%B8%9A%E0%B8%AE%E0%B8%AD%E0%B8%97%E0%B8%94%E0%B8%B4%E0%B8%9E-hdg/11000711956001552)
- [Siam Anchor Fastener — WA-HDG](https://www.fastenic.com/product/detail/wedge-anchor-hot-dip-galvanized---wa-hdg)
- [PK Hardware — พุกเคมี M12](https://www.pkhardware.com/%E0%B8%AA%E0%B8%B4%E0%B8%99%E0%B8%84%E0%B9%89%E0%B8%B2/%E0%B8%9E%E0%B8%B8%E0%B8%81%E0%B9%80%E0%B8%84%E0%B8%A1%E0%B8%B5/%E0%B8%9E%E0%B8%B8%E0%B8%81%E0%B9%80%E0%B8%84%E0%B8%A1%E0%B8%B5%E0%B9%81%E0%B8%9A%E0%B8%9A%E0%B8%9B%E0%B8%B1%E0%B9%88%E0%B8%99-m12-chemical-anchor-bolt)
- [Aplus Watsadu — เพลท 150×150](https://www.apluswatsadu.com/product/steel-plate-carbon-150x150/) · [เพลท 200×200 (หนา 6–12mm)](https://www.apluswatsadu.com/product/steel-plate-carbon-200x200-mm/)
- [Lerlert Corp — เพลทตัดตามแบบ](https://www.lerlertcorp.com/steel-plate/) · [OneStockHome — เหล็กเพลท](https://www.onestockhome.com/th/product_categories/steel-plate) · [TintSteel](https://tint-steel.com/steel-plate/)
