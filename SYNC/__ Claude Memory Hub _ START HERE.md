# 🤖 Claude Memory Hub — START HERE

- **Notion ID:** 3381ac219abd81c1b9e0d3b92b3493af
- **URL:** https://www.notion.so/Claude-Memory-Hub-START-HERE-3381ac219abd81c1b9e0d3b92b3493af
- **Last Edited:** 2026-05-07T08:27:00.000Z

---

🤖 อ่านหน้านี้ก่อนทุก session — Claude จะดึงข้อมูลนี้เพื่อเข้าใจ context ทันที

## 👤 About Pamelosam

## 🏢 MBOX Business Context

- ธุรกิจ: ขายสินค้า + บริการ + พัฒนาระบบคาราโอเกะครบวงจร
- ก่อตั้ง: ปี 2000 — ธุรกิจครอบครัว โดย คุณพิเชษฐ ร่วมกับ American-Korean Partnership (American Engineer)
- Tagline: "No.1 Karaoke System in Thailand" | "MBOX - Make the Moment"
- 3 Business Units:
- Products หลัก: ECHO PRO 4TB, ECHO X, MINI SPARK, MPAD, MBOX SERVER, E-MENU, Karaoke Streaming, CITIMAN
- Scale: ~100 ร้าน | ~1,300 endpoints | 70,000 เพลง
- แผนกที่ดูแล: Sales & Marketing, Finance, HR, Admin, Projects, Design, Innovation Tech
- เป้าหมาย 2026: เพิ่ม Revenue + Launch Products ใหม่ + Automation + Multi-AI Agent Team
- Budget stack: Low (<5K/เดือน) — Notion + Google Workspace เป็นหลัก
- Pain points (แก้แล้ว 08/04): ไม่มี Single Source of Truth, ไม่มี Lead Mgmt, ไม่มี Service Ticket, Stock ไม่ตรง, Bottleneck ที่น้องบี, Programmer กั๊กข้อมูล
## ✅ ระบบที่สร้างเสร็จแล้ว (อัปเดต 22 April 2026)

### 🎯 Lead Management — Fields

Lead ID (auto), ชื่อ Lead/บริษัท, สถานะ (New→Won/Lost/On Hold), ช่องทาง (Line/FB/IG/Walk-in/Referral), สินค้าที่สนใจ, เบอร์โทร, Email, มูลค่าโอกาส (บาท), ผู้รับผิดชอบ, วันที่ติดต่อ, วันนัดถัดไป, หมายเหตุ

### 🎫 Service Ticket — Fields

Ticket ID (auto), หัวข้อปัญหา, ประเภท (ซ่อม/เคลม/ติดตั้ง/Support/อัปเดต/Training), สถานะ (เปิด→เสร็จ/ยกเลิก), Priority (Urgent/High/Normal/Low), ชื่อลูกค้า, เบอร์, สินค้า/รุ่น, รายละเอียด, วิธีแก้ไข, ผู้รับงาน, วันรับแจ้ง, กำหนดเสร็จ, ค่าใช้จ่าย

### 📦 Stock & Inventory — Fields

Item ID (auto), ชื่อสินค้า/วัสดุ, หมวดหมู่, สถานะ (ปกติ/ใกล้หมด/หมด/สั่งซื้อแล้ว), จำนวนคงเหลือ, Min Stock, หน่วย, ราคา/หน่วย, Supplier, ตำแหน่งจัดเก็บ, ใช้กับ Product

## 📂 Notion Structure (อัปเดต 08/04/2026)

## 🤖 Multi-AI Agent Blueprint

Next Action: Build Sales Agent ใน Make.com → Connect Claude API + LINE OA → Test auto-reply

New Tools to Add: Dify.ai (knowledge base) • Cursor (VS Code replacement) • Discord (team channel) • Vercel (website hosting)

## 🔌 Connectors & Tools

## 📁 Google Drive — MBOX (Sync Status 24/04/2026)

## 📌 Ongoing Projects

## ⚡ คำสั่งลัด Claude

## 🎯 Claude ควรทำทุก Session

1. อ่าน Memory Hub นี้ก่อน
1. เช็ค Ongoing Projects — มีอะไรต้องทำต่อ
1. ทำงานตาม Context MBOX
1. จบ Session → อัปเดต Memory Hub
## 🏢 Department Deep Dive (อัปเดต 22/04/2026)

### 🎯 Sales & Marketing

### 💰 Finance & Accounting

### 🎫 Service & Support

### 📦 Admin / Stock / Programmer & Developer

🗂️ Admin

📦 Stock & Inventory

💻 Programmer & Developer (พี่เก้)

## 🎯 Sales System Roadmap — สิ่งที่ต้องทำให้ครบ

### Phase 1 — Foundation (ทำได้เลย ไม่ต้องเขียนโค้ด)

- [ ] กรอก Lead เก่าทั้งหมดเข้า Google Sheet (Lead Template) → Make.com sync เข้า Notion อัตโนมัติ
- [ ] Invite น้องบี + ทีมขาย เข้า Notion → เทรนใช้ Lead DB
- [ ] ตั้ง SOP ว่าทุก Lead ใหม่ต้องกรอกเข้าระบบทันที
- [ ] Run setupAllTriggers() ใน Google Apps Script → เปิด Auto LINE Digest 09:00 น. ✅
### Phase 2 — Lead Capture Automation

- [ ] LINE OA → Auto Lead : ลูกค้าทัก LINE → Webhook → สร้าง Lead ใน Sheet อัตโนมัติ (Make.com) ✅ Live 23/04/2026 + Quick Reply 4 ปุ่ม
- [ ] Facebook/IG Lead Ads → Sheet : Lead Ads form → Make.com → Google Sheet
- [ ] Web Form : Google Form หรือ Typeform → Sheet (สำหรับลูกค้า Walk-in)
### Phase 3 — Quotation System (ใบเสนอราคา)

- [ ] สร้าง Template ใบเสนอราคา MBOX ใน Google Docs
- [ ] Auto-generate PDF จากข้อมูล Lead (Google Apps Script)
- [ ] ส่ง PDF อัตโนมัติ ไปยังลูกค้าทาง LINE OA หรือ Email
- [ ] Track สถานะใบเสนอราคา (ส่งแล้ว / อนุมัติ / ปฏิเสธ) ใน Notion
### Phase 4 — Follow-up Per Lead ✅ เสร็จแล้ว

