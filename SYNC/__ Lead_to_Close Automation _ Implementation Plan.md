# 🚀 Lead-to-Close Automation — Implementation Plan

- **Notion ID:** 34a1ac219abd81168b4ac488eaccd0b9
- **URL:** https://www.notion.so/Lead-to-Close-Automation-Implementation-Plan-34a1ac219abd81168b4ac488eaccd0b9
- **Last Edited:** 2026-04-22T04:51:00.000Z

---

## 🎯 เป้าหมายของระบบนี้

- เพิ่ม Conversion Rate จาก ~20% → 35% ภายใน 60 วัน
- ไม่มี Lead หายเงียบอีก — ทุก Lead มี Follow-up อัตโนมัติ
- บีทำงานได้เป็นระบบ ไม่ต้องจำเองทุกอย่าง
- Revenue เพิ่มขึ้น 2-5 ร้านใหม่/เดือน
## 📊 Lead Stage — 7 ขั้นตอน

## 📋 Fields ใน Lead DB (อัปเดต 22/04/2026)

## 🗓️ Implementation Timeline

### ✅ Week 1 — ปรับ Lead DB (22-28 Apr)

- [ ] เพิ่ม Fields ใหม่: Priority, ประเภทลูกค้า, จำนวนห้อง, เหตุผลที่ไม่ซื้อ, Follow-up ล่าสุด
- [ ] ปรับ Stage ให้ครบ 7 ขั้น
- [ ] กรอก Lead เก่าที่มีอยู่เข้าระบบ (บีดำเนินการ)
- [ ] สร้าง View แยก: Kanban by Stage, Hot Leads, Today's Follow-up
### 🔲 Week 2 — สร้าง Make.com Automation (29 Apr - 5 May)

- [ ] Scenario 1: Daily Morning Brief → ส่ง Line บีทุกเช้า 8:30
- [ ] Scenario 2: Lead ค้าง Alert → แจ้งเตือนเมื่อ Lead อยู่ Stage เดิมนานเกินกำหนด
- [ ] Scenario 3: Auto Proposal Email → เมื่อ Stage เปลี่ยนเป็น Proposal Sent
### 🔲 Week 3 — Message Templates (6-12 May)

- [ ] Welcome Message (Line OA)
- [ ] Qualify Questions Script
- [ ] Demo Invitation
- [ ] Proposal Follow-up (วัน 3 / วัน 7)
- [ ] On Hold Check-in (ทุก 14 วัน)
- [ ] Urgency Offer Script
### 🔲 Week 4 — Train + Monitor (13-19 May)

- [ ] สอนบีใช้ระบบ (1-2 ชม.)
- [ ] กำหนด Weekly Review ทุกวันศุกร์
- [ ] ดู KPI สัปดาห์แรก
## ⚙️ Make.com Scenario Design

### Scenario 1 — Daily Morning Brief

### Scenario 2 — Lead Overdue Alert

### Scenario 3 — Auto Proposal Email

## 📝 วิธีกรอกข้อมูล Lead (SOP สำหรับบี)

### เมื่อลูกค้าทักใหม่:

1. เปิด Notion → Lead Management DB
1. กด New → กรอก ชื่อ / เบอร์ / ช่องทาง / สินค้าที่สนใจ
1. ตั้ง Stage = 🆕 New
1. ตั้ง Priority = 🌤️ Warm (ค่อยปรับทีหลัง)
1. กรอก วันที่ติดต่อครั้งแรก = วันนี้
### เมื่อคุยแล้วรู้ความต้องการ:

1. เปลี่ยน Stage → 💬 Contacted
1. กรอก จำนวนห้อง + ประเภทลูกค้า
1. คำนวณ มูลค่าโอกาส = จำนวนห้อง × ราคาสินค้า
1. ตั้ง นัดหมายครั้งถัดไป
1. กรอก หมายเหตุ — สรุปสิ่งที่คุย
### เมื่อนัด Demo:

1. เปลี่ยน Stage → 📅 Demo Scheduled
1. กรอก นัดหมายครั้งถัดไป = วันที่นัด
1. ปรับ Priority = 🔥 Hot (ถ้ายืนยันมาดูแล้ว)
### เมื่อส่ง Proposal:

1. เปลี่ยน Stage → 📄 Proposal Sent
1. Make.com จะส่ง Email อัตโนมัติ
1. กรอก วัน Follow-up ล่าสุด = วันนี้
### เมื่อปิดการขายได้:

1. เปลี่ยน Stage → ✅ Won
1. แจ้งทีม Install
### เมื่อไม่ซื้อ:

1. เปลี่ยน Stage → ❌ Lost
1. บังคับกรอก เหตุผลที่ไม่ซื้อ — ข้อมูลนี้สำคัญมากสำหรับปรับกลยุทธ์
## 📈 KPI ที่ต้องดูทุกสัปดาห์

## 💰 ROI คาดการณ์

- ถ้าปิดเพิ่มได้ 2 ร้าน/เดือน × ECHO PRO 30,900 = +61,800 บาท/เดือน
- ถ้าปิดเพิ่มได้ 5 ร้าน/เดือน = +154,500 บาท/เดือน
- ค่าใช้จ่ายเพิ่ม: 0 บาท (ใช้ Notion + Make.com ที่มีอยู่)
