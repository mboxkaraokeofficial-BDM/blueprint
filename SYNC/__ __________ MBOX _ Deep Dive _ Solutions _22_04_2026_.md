# 🔬 ระบบการขาย MBOX — Deep Dive & Solutions (22/04/2026)

- **Notion ID:** 34a1ac219abd81708f04ef41e4efc728
- **URL:** https://www.notion.so/MBOX-Deep-Dive-Solutions-22-04-2026-34a1ac219abd81708f04ef41e4efc728
- **Last Edited:** 2026-04-28T06:16:00.000Z

---

## 🚨 Root Cause หลัก

## ⚠️ สิ่งที่เกิดขึ้นจริงในแต่ละวันของบี

ลูกค้าทักมา Line → ตอบแชท → โทรศัพท์เข้า (ไม่รู้ว่า Sales หรือ Service) → ลูกค้าขอ Proposal → ไปทำ FlowAccount → ลูกค้าถามของมีไหม → เช็ค Stock → เครื่องซ่อมเสร็จ → QC → Download เพลงจากค่าย → ตามเก็บเงิน → ลูกค้าทักใหม่ → วนซ้ำ

ผลลัพธ์: ไม่มีงานไหนทำได้อย่างเต็มที่ — Lead หาย — เงินหาย — บีหมดพลังงาน

## 🎯 7 งานของบี — วิเคราะห์แต่ละอย่าง

สรุป: บีเสียเวลา 7-9 ชม./วัน — Automate หรือ Delegate ได้อย่างน้อย 30-40%

## 🏗️ Solutions ทั้งหมด

### 📌 Solution 1 — แยก Line OA เป็น 2 Channel

ปัญหา: Line OA เดียวรับทุกอย่าง → บีไม่รู้ว่าจะตอบในโหมดไหน

### 📌 Solution 2 — Daily Time Blocking ของบี

ปัญหา: บีทำงานแบบ Reactive — ใครโทรมาก็รับ ไม่มีลำดับงาน

### 📌 Solution 3 — SOP Card บี (3 คำถามก่อนทำงานทุกอย่าง)

คำถามที่ 1: งานนี้ Sales หรือ Service?

- Sales → กรอก Lead DB ทันที
- Service → เปิด Ticket ทันที
คำถามที่ 2: งานนี้ต้องทำเอง หรือส่งต่อ?

- Technical → ส่งพี่เก้
- เอกสาร → ทำใน FlowAccount
- เงิน → แจ้ง Pamelosam
คำถามที่ 3: งานนี้ด่วนแค่ไหน?

- 🔴 ด่วน → ทำทันที (ลูกค้าต่อหน้า / เครื่องเสีย)
- 🟡 วันนี้ → ทำใน Time Block ที่กำหนด
- 🟢 รอได้ → จดไว้ใน Notion
### 📌 Solution 4 — QC Checklist ก่อนส่งเครื่องลูกค้า

เครื่องผลิตใหม่:

- [ ] เปิดเครื่องได้ปกติ
- [ ] ต่อ HDMI — ภาพ/เสียงออก TV ได้
- [ ] Login ระบบ MBOX ได้
- [ ] เพลงมีครบตาม Package ที่ซื้อ
- [ ] Remote / Mic ทดสอบแล้ว
- [ ] Serial No. บันทึกใน Notion Device DB
- [ ] ใบกำกับ + ใบรับประกัน ใส่กล่องแล้ว
เครื่องซ่อม:

- [ ] แก้ปัญหาที่แจ้งไว้แล้ว
- [ ] ทดสอบทำงาน 15 นาทีต่อเนื่อง
- [ ] บันทึกวิธีแก้ใน Service Ticket
- [ ] แจ้งราคาและรับการยืนยันก่อนส่งคืน
- [ ] แจ้งลูกค้าก่อนส่ง + ถ่ายรูปเครื่องก่อนจัดส่ง
### 📌 Solution 5 — แก้ปัญหา Download เพลง

ปัจจุบัน: ค่ายเพลง → ส่งให้บี → บี Download → ส่งต่อพี่เก้ (บีเป็นคนกลางไม่จำเป็น)

แนะนำ: ให้ค่ายเพลงส่งตรงถึง Email พี่เก้ หรือ Google Drive Shared Folder ที่พี่เก้เข้าถึงได้เอง

- Action: Pamelosam แจ้งค่ายเพลงเปลี่ยน Email รับไฟล์เป็นของพี่เก้
- ผล: บีประหยัดเวลา ~30 นาที/วัน = 10+ ชม./เดือน
### 📌 Solution 6 — AR Tracker (ตามเก็บเงินอย่างมีระบบ)

เพิ่ม Fields ใน Lead DB:

## 🚨 Priority Actions — ทำสัปดาห์นี้

## 🤖 MIBO LINE OA Bot — สถานะการพัฒนา (28/04/2026)

### ✅ ทำเสร็จแล้ว

- n8n workflow สร้างครบ — 22 Switch rules + Fallback
- Route A (บ้านพักอาศัย / ห้องคาราโอเกะ) พร้อม sub-routes ครบ
- Route B (แจ้งอาการผิดปกติ / อัพเดท / รับประกัน / บริการอื่นๆ)
- Flex Message card สินค้า 3 รุ่น: ECHO PRO, MINI SPARK, OK OKE
- LINE Channel Token ฝังใน workflow แล้ว
- Service Form URL และ Quotation Form URL ตั้งค่าครบ
- Webhook URL: https://pamelosam.app.n8n.cloud/webhook/line-oa
### 🔧 กำลังแก้ไข

- LINE Reply ยังไม่มีข้อความตอบกลับ — กำลัง debug อยู่
- Google Sheets Save nodes ต้องตั้ง credential + column mapping ใน n8n UI ทีละ node (23 nodes)
### ⬜ ยังไม่ได้ทำ

- Google Sheets → Notion / Airtable auto sync
- Google Form สำหรับลูกค้าโทร / Walk-in
- อัปเดตราคา + สเปค MINI SPARK และ OK OKE ใน Flex nodes
### 📁 ไฟล์ Workflow

C:\Users\Windows\Documents\Claude\Projects\MBX-Song DB\mibo_line_oa_full.json

### 🗂️ Google Sheet (Lead Database)

Sheet ID: 1JEd2xElesLs6VwSp1_AUfgsqTzqPSZ1bw3eWkNOO3Iw

Tabs: Customer Register | Sales Follow-up | Service Queue | Admin Task Board

## 📈 ROI ที่คาดการณ์

