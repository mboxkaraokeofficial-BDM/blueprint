# Session Recap — 24 April 2026

- **Notion ID:** 34c1ac219abd81238ffbd3b12b30e915
- **URL:** https://www.notion.so/Session-Recap-24-April-2026-34c1ac219abd81238ffbd3b12b30e915
- **Last Edited:** 2026-04-24T03:15:00.000Z

---

## 🗓️ Session: 24 April 2026

Project: MBOX LINE OA Auto Lead Capture

Scenario: Make.com #5406773 — MBOX — LINE OA Auto Lead Capture

## ✅ สิ่งที่ทำสำเร็จวันนี้

- ค้นพบ Root Cause: LINE OA Built-in Auto Reply ใช้ replyToken ก่อน Make.com webhook → Error "Invalid reply token"
- เปลี่ยน LINE OA Response Mode → แชทแบบแมนนวล (ปิด built-in auto reply)
- Clear webhook queue 25 items ที่มี expired replyTokens
- Re-activate Scenario #5406773
- อัพเดท Notion Memory Hub
## ⚠️ งานที่ยังค้างอยู่ (Pending)

1. [CRITICAL] เพิ่ม Error Handler "Ignore" บน HTTP modules ทุกตัว (12 ตัว) ใน Make.com
1. Re-activate scenario หลังเพิ่ม error handler
1. Test ทั้ง 12 Routes
1. [NEW PROJECT] สร้าง ผู้ช่วยตอบแชท + Lead Capture → Google Sheets อัตโนมัติ
## 🔑 Key Learnings

- replyToken ใช้ได้ครั้งเดียว ภายใน 30 วินาที
- LINE OA Manager → ตั้งค่าการตอบกลับ → ต้องเลือก "แชทแบบแมนนวล" เท่านั้น (ห้ามเปิด Auto Reply ควบคู่)
- Make.com auto-deactivates scenario เมื่อ HTTP module error ไม่มี handler
- แก้ไขด้วย Error Handler "Ignore" → scenario จะ continue แม้มี error บางตัว
## 🚀 Next Session Goals

1. Fix Error Handlers บน Make.com (12 HTTP modules)
1. Full test all 12 routes
1. Design ผู้ช่วยตอบแชท flow:
## 📌 Links

- Make.com Scenario: https://eu1.make.com/1157570/scenarios/5406773/edit
- LINE OA Manager: https://manager.line.biz/account/@557avxlz
- Webhook Queue: https://eu1.make.com/1157570/hooks/2897509/queue
- Memory Hub: 🤖 Claude Memory Hub — START HERE
