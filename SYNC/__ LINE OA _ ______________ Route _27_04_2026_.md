# 💬 LINE OA — ข้อความจริงทุก Route (27/04/2026)

- **Notion ID:** 34f1ac219abd8155b885edcf27de04c3
- **URL:** https://www.notion.so/LINE-OA-Route-27-04-2026-34f1ac219abd8155b885edcf27de04c3
- **Last Edited:** 2026-04-28T05:01:00.000Z

---

## 💬 ข้อความจริงๆ ที่บอท MIBO ส่งใน แต่ละ Route

## Route 0 — Fallback (ข้อความทั่วไป / ไม่ match keyword)

Trigger: ทุกข้อความที่ไม่ตรง route ใด

ข้อความที่ส่ง:

Quick Reply 4 ปุ่ม:

- 🛒 สนใจสินค้า
- 🔧 รับบริการหลังการขาย
- ℹ️ เกี่ยวกับเรา
- 📞 ติดต่อแอดมิน
บันทึกลง Sheet: Customer Register

## Route A — สนใจสินค้า

Trigger: ลูกค้าพิมพ์ "สนใจสินค้า" หรือกดปุ่ม Quick Reply

ข้อความที่ส่ง:

Quick Reply 2 ปุ่ม:

- 🏠 บ้านพักอาศัย
- 🏢 ห้องคาราโอเกะ/ร้านอาหาร
บันทึกลง Sheet: Sales Follow-up

## Route A-1 — บ้านพักอาศัย

Trigger: ลูกค้าเลือก "บ้านพักอาศัย"

ข้อความที่ส่ง:

บันทึกลง Sheet: Sales Follow-up (Type: บ้านพักอาศัย)

## Route A-2 — ห้องคาราโอเกะ/ร้านอาหาร

Trigger: ลูกค้าเลือก "ห้องคาราโอเกะ/ร้านอาหาร"

ข้อความที่ส่ง:

สอบถาม

บันทึกลง Sheet: Sales Follow-up (Type: ห้องคาราโอเกะ/ร้านอาหาร)

## Route B — รับบริการหลังการขาย

Trigger: ลูกค้าพิมพ์ "รับบริการหลังการขาย" หรือกดปุ่ม

ข้อความที่ส่ง:

Quick Reply 5 ปุ่ม:

- 🔨 แจ้งซ่อม
- 🔩 เปลี่ยนอะไหล่
- 🧹 ล้างเครื่อง
- 🛡️ สอบถามการรับประกัน
- 💬 บริการอื่นๆ
บันทึกลง Sheet: Service Queue

## Route B-1 — แจ้งซ่อม

Trigger: ลูกค้าเลือก "แจ้งซ่อม"

ข้อความที่ส่ง:

บันทึกลง Sheet: Service Queue (Type: แจ้งซ่อม)

## Route B-2 — เปลี่ยนอะไหล่

Trigger: ลูกค้าเลือก "เปลี่ยนอะไหล่"

ข้อความที่ส่ง:

บันทึกลง Sheet: Service Queue (Type: เปลี่ยนอะไหล่)

## Route B-3 — ล้างเครื่อง

Trigger: ลูกค้าเลือก "ล้างเครื่อง"

ข้อความที่ส่ง:

บันทึกลง Sheet: Service Queue (Type: ล้างเครื่อง)

## Route B-4 — สอบถามรับประกัน

Trigger: ลูกค้าเลือก "สอบถามการรับประกัน"

ข้อความที่ส่ง:

บันทึกลง Sheet: Service Queue

## Route B-5 — บริการอื่นๆ

Trigger: ลูกค้าเลือก "บริการอื่นๆ"

ข้อความที่ส่ง:

บันทึกลง Sheet: Service Queue (Type: บริการอื่นๆ)

## Route C — เกี่ยวกับเรา

Trigger: ลูกค้าพิมพ์ "เกี่ยวกับเรา"

ข้อความที่ส่ง:

บันทึกลง Sheet: Customer Register

## Route D — ติดต่อแอดมิน

Trigger: ลูกค้าพิมพ์ "ติดต่อแอดมิน" หรือกดปุ่ม

ข้อความที่ส่ง:

บันทึกลง Sheet: Admin Task Board

## 🗂️ Google Forms ที่ใช้ในระบบ

## 📋 Google Sheet Tabs ที่บันทึกข้อมูล

## ⚠️ สถานะระบบ (27/04/2026)

- ✅ Blueprint พร้อม: blueprint_fully_fixed.json (แก้ 2 bugs ครบแล้ว)
- ✅ Handoff JSON บน GDrive: ID 15UUIoS3Ow9eG0Kig3VYQOwqS53fojG7J
- ⚠️ ยังไม่ import blueprint ผ่าน Make.com UI
