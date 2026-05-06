# ⚙️ Session Recap — 

- **Notion ID:** 34a1ac219abd81ef866ef8d80a05a9e7
- **URL:** https://www.notion.so/Session-Recap-Make-com-Auto-Sync-Google-Sheet-Notion-22-04-2026-34a1ac219abd81ef866ef8d80a05a9e7
- **Last Edited:** 2026-04-22T08:47:00.000Z

---

## 🎯 เป้าหมาย Session นี้

สร้างระบบ Auto-Sync อัตโนมัติระหว่าง Google Sheet (Lead Import Template) กับ Notion Lead DB

## ✅ สิ่งที่ทำเสร็จแล้ว

### Scenario 1 — New Lead (สร้าง record ใหม่)

- ID: 5391919
- Status: 🟢 ACTIVE
- Flow: Google Sheets Watch New Rows → Filter (Notion ID ว่าง) → Notion Create Page → Write Notion ID กลับ Sheet column S
- Trigger: Polling ทุก 15 นาที
- Connection: MBOX Google Sheets + MBOX Notion (Pichaya)
### Scenario 2 — Update Lead (อัปเดต record เดิม)

- ID: 5392962
- Status: 🟢 ACTIVE
- Flow: Google Sheets Watch Changes → Filter (Notion ID มีค่า) → Notion Update a Data Source Item
- Trigger: Polling ทุก 15 นาที
- Notion Module: Update a Data Source Item (Data Source mode)
- Data Source ID: efbf330e-1e5b-4485-8842-928643421614
- Page ID mapped: {{1.Notion ID}}
- Fields mapped (18 fields): title, status, priority, customerType, channel, lineId, location, product, rooms, dealValue, phone, email, firstContact, nextMeeting, lastFollowup, lostReason, assignedTo, notes
### Google Sheet

- เพิ่ม header "Notion ID" ที่ column S row 3
- Spreadsheet ID: 1JEd2xElesLs6VwSp1_AUfgsqTzqPSZ1bw3eWkNOO3Iw
- Sheet: 📋 Lead Template (gid: 2045924386)
## 🔑 Key Information

## 🧪 วิธีทดสอบระบบ

Test Scenario 1 (New Lead):

1. เปิด Google Sheet → sheet "📋 Lead Template"
1. เพิ่มแถวใหม่ row 4+ — กรอก ชื่อ Lead, สถานะ, เบอร์โทร
1. รอ max 15 นาที
1. ✅ ดูใน Notion Lead DB — มี record ใหม่ขึ้นมา
1. ✅ column S ใน Sheet มี Notion Page ID
Test Scenario 2 (Update Lead):

1. แก้ไขแถวที่มี Notion ID แล้ว — เปลี่ยน สถานะ / priority
1. รอ max 15 นาที
1. ✅ ดูใน Notion — record นั้น update แล้ว
## 🔔 Auto Reminder — Daily Lead Digest → LINE OA (22/04/2026)

### สิ่งที่ทำ

สร้าง Google Apps Script ส่งสรุป Lead ไปยัง LINE OA ทุกเช้า 09:00 น. อัตโนมัติ

### เหตุผลที่ใช้ Google Apps Script แทน Make.com

- Make.com Free Tier จำกัด 2 Scenarios (ใช้ครบแล้ว)
- Daily Reminder ต้องใช้ Schedule trigger ซึ่งไม่สามารถรวมกับ Sheets trigger ในไฟล์เดิมได้
- Google Apps Script ฟรี 100% ไม่มีโควต้า
### Config ที่ใช้

### เนื้อหา Digest ที่ส่ง

- 📌 Lead ที่มีนัดหมายวันนี้ (nextMeeting = วันนี้)
- 🔥 Hot Lead Priority (Priority = High)
- ⚠️ Follow-up ค้างเกิน 3 วัน
### ไฟล์ Script

- ชื่อไฟล์: MBOX_Daily_Digest_LINE_OA.gs
- Deploy ที่: Google Apps Script (script.google.com)
- ฟังก์ชันทดสอบ: testSendNow()
- ฟังก์ชันตั้ง Trigger: setupDailyTrigger() (รัน 1 ครั้งเท่านั้น)
### Status

🟢 ACTIVE — ทดสอบส่ง LINE สำเร็จแล้ว

## 📌 สิ่งที่ต้องทำต่อ (Pending)

- [ ] ทดสอบ Scenario 1 จริง — เพิ่ม Lead ใหม่ใน Sheet แล้วรอดู Notion
- [ ] ทดสอบ Scenario 2 จริง — แก้ข้อมูล Lead แล้วรอดู Notion sync
- [ ] ถ้าต้องการ Instant trigger (ไม่ต้องรอ 15 นาที) → ติดตั้ง Make Add-on ใน Google Sheets
- [ ] อัปเดต Notion Lead DB fields ให้ตรงกับ Key names ใน Scenario 2 ถ้า field ไม่ match
- [ ] Run setupDailyTrigger() ใน Google Apps Script เพื่อเปิด Auto-send ทุกเช้า 09:00 น.
## 🛠️ Tech Notes

- Blueprint JSON ถูก inject ผ่าน JavaScript File object (ไม่ใช่ file upload ปกติ)
- Notion Update a Data Source Item module ใช้ Data Source mode (ไม่ใช่ Database Legacy)
- Fields ใน Scenario 2 ใช้ Key-Value format — Key = Notion property name, Value = Google Sheet column variable
- Make.com canvas ใช้ WebGL rendering — ไม่สามารถ interact ผ่าน DOM querySelector ได้ตรงๆ
- imt-coder elements ต้องใช้ change event (ไม่ใช่ input) เพื่อหลีกเลี่ยงการเปิด variable picker
