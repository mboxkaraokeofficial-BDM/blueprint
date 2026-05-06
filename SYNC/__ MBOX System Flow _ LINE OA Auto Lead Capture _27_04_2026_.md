# 🔄 MBOX System Flow — LINE OA Auto Lead Capture (27/04/2026)

- **Notion ID:** 34f1ac219abd81ed92c5f58e16800967
- **URL:** https://www.notion.so/MBOX-System-Flow-LINE-OA-Auto-Lead-Capture-27-04-2026-34f1ac219abd81ed92c5f58e16800967
- **Last Edited:** 2026-04-27T04:22:00.000Z

---

## 🔄 ภาพรวม Flow ทั้งระบบ

## 📡 Flow หลัก: ลูกค้าทัก LINE → ระบบตอบอัตโนมัติ + บันทึก Lead

## 🗺️ 12 Routes — แผนผังการแยกประเภท

## 🔌 การเชื่อมต่อทั้งหมด (Connections)

### 1. LINE OA → Make.com

- ประเภท: Webhook
- URL: Make.com Hook ID 2897509
- ตั้งใน: LINE Developers Console → Messaging API → Webhook URL
- ⚠️ สำคัญ: LINE OA Bot Mode ต้องเป็น Manual (ปิด built-in auto-reply)
### 2. Make.com → LINE Messaging API

- ประเภท: HTTP Request (Bearer Token)
- Endpoint: https://api.line.me/v2/bot/message/reply
- Token: LINE OA Channel Access Token (จาก LINE Developers Console)
- Modules: 19 ตัว (http:MakeRequest)
- ⚠️ Bug: ขาด parameter requestCompressedContent: false → Fix แล้วใน blueprint_fully_fixed.json
### 3. Make.com → Google Sheets

- ประเภท: Google Sheets — Add Row
- Sheet: MBOX_Lead_Import_Template
- Tabs ที่ใช้: Sales Follow-up, Service Queue, Customer Register, Admin Task Board
- Modules: 7 ตัว (google-sheets:addRow)
- ⚠️ Bug: spreadsheetId ใช้ Drive File ID แทน filename → Fix แล้วใน blueprint_fully_fixed.json
## 🐛 Bugs ที่พบและแก้ไข

### Bug #1 — Wrong spreadsheetId

### Bug #2 — Missing requestCompressedContent

### สถานะ Fix

- ✅ สร้าง blueprint_fully_fixed.json แก้ทั้ง 2 bugs (19 HTTP + 7 Sheets)
- ✅ XHR Interceptor ยืนยัน PATCH 200: {method:double_parse, http:19, sheets:7, status:OK}
- ⚠️ Runtime ยังล้ม — ต้อง Import Blueprint ผ่าน Make.com UI
## 📋 IDs สำคัญทั้งหมด

## ✅ Next Steps (เรียงลำดับ)

- [ ] Step 1: เปิด Make.com Editor
- [ ] Step 2: คลิก ⚙️ Settings → Import Blueprint
- [ ] Step 3: Upload ไฟล์ blueprint_fully_fixed.json จาก GDrive
- [ ] Step 4: Re-connect Google Sheets connection + LINE OA Channel Access Token
- [ ] Step 5: เพิ่ม Error Handler Ignore บน HTTP modules ทุกตัว (ป้องกัน auto-deactivate)
- [ ] Step 6: กด Run once แล้วส่งข้อความทาง LINE มาทดสอบ
- [ ] Step 7: ทดสอบทั้ง 12 routes ให้ครบ
## 📁 ไฟล์ที่เกี่ยวข้อง (Google Drive)

