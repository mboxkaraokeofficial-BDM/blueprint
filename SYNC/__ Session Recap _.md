# 🔧 Session Recap — 

- **Notion ID:** 34c1ac219abd8119869de41006965a92
- **URL:** https://www.notion.so/Session-Recap-Make-com-Blueprint-Fix-24-April-2026-34c1ac219abd8119869de41006965a92
- **Last Edited:** 2026-04-24T11:35:00.000Z

---

## 🎯 สรุป Session นี้

Debug และ fix Make.com Scenario #5406773 (MBOX — LINE OA Auto Lead Capture) — พบและแก้ไข 2 bugs หลักที่ทำให้ validation ล้มเหลวทุก webhook execution

## 🐛 Bugs ที่พบ (2 ตัว)

Bug #1 — Wrong spreadsheetId (7 modules)

- Module type: google-sheets:addRow
- ค่าผิด: /1JEd2xElesLs6VwSp1_AUfgsqTzqPSZ1bw3eWkNOO3Iw (Drive file ID)
- ค่าถูก: /MBOX_Lead_Import_Template (filename path)
- จำนวน modules ที่ได้รับผลกระทบ: 7
Bug #2 — Missing requestCompressedContent (19 modules)

- Module type: http:MakeRequest
- Parameter ที่ขาดหาย: requestCompressedContent
- ค่าที่ต้องการ: false
- จำนวน modules ที่ได้รับผลกระทบ: 19
- สาเหตุ: Make.com อัปเดต requirement แต่ scenario เก่าไม่มี parameter นี้
## 🔑 IDs สำคัญ

## 🛠️ วิธีที่ Fix (XHR Interceptor)

Blueprint ใน Make.com PATCH body เป็น double-encoded JSON string ต้องใช้ JSON.parse() 2 รอบ

สร้าง XHR send() interceptor ที่:

1. ดัก PATCH request ไปที่ URL ที่มี 5406773
1. Parse JSON 2 ชั้น
1. แก้ไข modules ทั้งหมดอัตโนมัติ (HTTP + Sheets)
1. Re-serialize และปล่อยผ่าน
ผลลัพธ์: {method:"double_parse", http:19, sheets:7, status:"OK"} — PATCH returns HTTP 200

## ⚠️ ปัญหาที่ยังค้างอยู่

แม้ PATCH จะ return 200 แต่ scenario ยัง fail ด้วย "Validation failed for 1 parameter(s)"

สมมติฐาน:

- PATCH endpoint อัปเดต metadata เท่านั้น — runtime blueprint อาจต้อง PUT ที่ /api/v2/scenarios/5406773/blueprint
- Angular in-memory state ส่ง data เก่าออกไปใหม่เพราะเราแก้ in-transit แต่ Angular state ไม่เปลี่ยน
- isinvalid: true flag ยังค้างจาก runs ก่อนหน้า — จะ clear เฉพาะเมื่อ execution สำเร็จ
- อาจมี Bug ที่ 3 บน module type อื่นที่ยังไม่พบ
## 📋 Next Steps ที่แนะนำ

- [ ] ลอง Import blueprint_fully_fixed.json ผ่าน Make.com UI: Scenario Settings → Import Blueprint
- [ ] ถ้ายังไม่ work: ลบ scenario แล้ว re-import ใหม่จาก blueprint_fully_fixed.json
- [ ] Re-connect connections: Google Sheets + LINE OA token + HTTP หลัง re-import
- [ ] เพิ่ม Error Handler Ignore บน HTTP modules ทุกตัว → ป้องกัน auto-deactivation
- [ ] ทดสอบทั้ง 12 routes หลัง fix สำเร็จ
- [ ] ตรวจสอบ LINE OA Bot Mode = Manual (ไม่ใช่ Auto-Reply) เสมอ
## 📁 ไฟล์ที่เกี่ยวข้อง (GDrive)

ดู MBOX_LineOA_AutoLeadCapture_Handoff_20260424.json บน Google Drive — มี script ครบถ้วนสำหรับ resume งานบนเครื่องใหม่

## 📝 Technical Notes

- Browser Extension Interference: Extension ตั้ง x-android-device header → blocks native fetch/XHR. Workaround: ใช้ XHR send() interceptor
- CSRF Protection: Make.com API ต้องการ CSRF token — GET requests ผ่าน iframe native fetch return 401
- LINE Bot Mode: ต้องเป็น Manual เสมอ — ถ้า built-in auto-reply เปิดอยู่ replyToken จะหมดอายุก่อน Make.com จะใช้งาน → 401 Unauthorized → scenario auto-deactivate
