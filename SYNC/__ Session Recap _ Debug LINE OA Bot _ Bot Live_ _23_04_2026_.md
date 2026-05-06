# 🐛 Session Recap — Debug LINE OA Bot + Bot Live! (23/04/2026)

- **Notion ID:** 34b1ac219abd818e962bca8355b268f6
- **URL:** https://www.notion.so/Session-Recap-Debug-LINE-OA-Bot-Bot-Live-23-04-2026-34b1ac219abd818e962bca8355b268f6
- **Last Edited:** 2026-04-23T10:32:00.000Z

---

## 🎯 เป้าหมาย Session

Debug ทำไม LINE OA Bot ไม่ตอบ และทำให้ bot ทำงานได้จริง

## 🔍 ปัญหาที่พบ

อาการ: ลูกค้าส่งข้อความไปที่ LINE OA แล้วไม่มีการตอบกลับเลย

Root Cause (วิเคราะห์ได้จาก Make.com Execution History):

- Module 1–3 รันครบ (4 credits) → Webhook รับข้อมูลได้ปกติ
- Module 4 (HTTP POST → LINE Reply API) คืนค่า 401 Unauthorized
- สาเหตุ: Module 4 ใช้ token zExSKzAde... (token ใหม่จาก LINE Developers Console) แต่ token นี้ไม่ valid สำหรับ channel นี้
- Module 2 ใช้ token nIhfeFP5... (token เก่ากว่า) ที่ยังใช้งานได้
- Make.com auto-deactivate scenario เมื่อเจอ error
## 🛠️ วิธีแก้ไข

### Fix 1 — เปลี่ยน Token Module 4

ใช้ JavaScript ผ่าน Claude in Chrome:

### Fix 2 — Reactivate Scenario

- Toggle ON scenario ใน Make.com
- Delete old webhook queue data (expired replyTokens)
- Save Schedule settings → Immediately
## ✅ ผลลัพธ์

- ✅ Bot ตอบกลับแล้ว พร้อม Quick Reply 4 ปุ่ม
- ✅ Quick Reply ที่ส่ง: 🎤 สนใจสินค้า / 📋 ขอใบเสนอราคา / 🔧 บริการหลังการขาย / 👤 ติดต่อแอดมิน
- ✅ Module 1–4 รันครบทุกครั้งที่ลูกค้าส่งข้อความ
- ✅ Lead ถูกบันทึกลง Google Sheet อัตโนมัติ
- ✅ ลบ test data ออกจาก Sheet แล้ว
## 📌 Key Learnings

## ⏭️ Next Steps

- [ ] เพิ่ม Router module ใน Make.com — แยก flow ตาม Quick Reply ที่กด (สนใจสินค้า / ขอใบเสนอราคา / ฯลฯ)
- [ ] Build flow สนใจสินค้า → ส่ง catalog/ราคา
- [ ] Build flow ขอใบเสนอราคา → ถามข้อมูลเพิ่ม + แจ้งทีม
- [ ] Unify tokens — ตรวจสอบว่า Module 2 และ Module 4 ใช้ token เดียวกัน
- [ ] Phase 2 ของ Sales Roadmap: Facebook/IG Lead Ads → Sheet
