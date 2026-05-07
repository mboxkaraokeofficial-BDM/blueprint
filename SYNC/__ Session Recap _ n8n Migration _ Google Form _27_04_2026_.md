# 🚀 Session Recap — n8n Migration + Google Form (27/04/2026)

- **Notion ID:** 34f1ac219abd81d38b00dadbd57e328c
- **URL:** https://www.notion.so/Session-Recap-n8n-Migration-Google-Form-27-04-2026-34f1ac219abd81d38b00dadbd57e328c
- **Last Edited:** 2026-04-27T09:33:00.000Z

---

## 📋 สรุป Session 27 April 2026

## 🎯 งานที่ทำใน Session นี้

### Task #13 — n8n Workflow (LINE OA Auto Lead Capture)

เป้าหมาย: ย้ายระบบจาก Make.com → n8n Cloud (https://pamelosam.app.n8n.cloud)

สิ่งที่ทำ:

- ดึงข้อมูลครบ 12 routes จาก blueprint_fully_fixed.json
- สร้าง n8n workflow JSON พร้อม 23 nodes
- ครอบคลุมทุก route เหมือน Make.com 100%
Structure Workflow:

ไฟล์: n8n_mbox_line_oa.json (45KB, 23 nodes)

### Task #12 — Google Form สำหรับ Call/Walk-in

เป้าหมาย: Staff สามารถกรอกข้อมูลลูกค้าที่โทร/เดินเข้าร้าน → บันทึกลง Sheet เดียวกับ LINE OA

สิ่งที่ทำ:

- สร้าง Google Apps Script create_mbox_form.gs (154 บรรทัด)
- รัน script 1 ครั้ง → Form สร้างอัตโนมัติ พร้อม link ไปยัง Google Sheet
Form Fields (7 fields):

ไฟล์: create_mbox_form.gs (8.6KB)

## 📁 ไฟล์ทั้งหมดใน Outputs Folder

## 🔧 Next Steps ที่ต้องทำเอง (~15 นาที)

### Step 1: Import n8n Workflow

- [ ] Login https://pamelosam.app.n8n.cloud
- [ ] + Create workflow → Canvas ว่าง
- [ ] ⋮ → Import from file → เลือก n8n_mbox_line_oa.json
- [ ] ตั้งค่า LINE Token credential
- [ ] ตั้งค่า Google Sheets credential + แก้ Spreadsheet ID
- [ ] Copy Webhook URL → วางใน LINE Developers → Verify ✅
- [ ] กด Active toggle → เขียว ✅
### Step 2: สร้าง Google Form

- [ ] ไป https://script.google.com → New project
- [ ] วาง code จาก create_mbox_form.gs
- [ ] แก้ SHEET_ID = "ใส่ ID จาก MBOX_Lead_Import_Template"
- [ ] 
- [ ] Copy Form URL → แชร์ให้ staff
## ⚠️ สิ่งที่ต้องระวัง

- LINE Bot Mode: ต้องตั้งเป็น Manual (ปิด built-in auto-reply) ไม่งั้น replyToken หมดก่อน n8n ทำงาน
- n8n Trial: API endpoint (/api/v1) ถูกล็อกใน trial — ใช้ UI Import แทน
- Google Sheets ID: แต่ละ Sheets node ต้องแก้ documentId ด้วยตนเอง (มี 7 nodes)
- LINE Token: ต้องใส่ใน Authorization header ของทุก HTTP Request node (11 nodes)
## 🔗 Links

- n8n Cloud: https://pamelosam.app.n8n.cloud/home/workflows
- LINE Developers: https://developers.line.biz
- Google Apps Script: https://script.google.com
- Make.com Scenario #5406773 (เดิม): https://eu1.make.com
