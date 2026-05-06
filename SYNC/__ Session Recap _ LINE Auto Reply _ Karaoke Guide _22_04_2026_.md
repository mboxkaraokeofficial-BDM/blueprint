# 📋 Session Recap — LINE Auto Reply + Karaoke Guide (22/04/2026)

- **Notion ID:** 34a1ac219abd81af8d66c055c362672e
- **URL:** https://www.notion.so/Session-Recap-LINE-Auto-Reply-Karaoke-Guide-22-04-2026-34a1ac219abd81af8d66c055c362672e
- **Last Edited:** 2026-04-22T10:22:00.000Z

---

## 📋 Session Recap — 22 April 2026 (ช่วงที่ 2)

## ✅ สิ่งที่ทำสำเร็จในวันนี้

### 1. Phase 4 — Google Apps Script v2.0 ✅

- เพิ่มฟังก์ชัน sendFollowupReminder() — ส่ง LINE แจ้งเตือนทุกบ่าย 17:00
- แสดงรายชื่อ Lead ที่มีนัดพรุ่งนี้: ชื่อ, สินค้า, มูลค่า, เบอร์, ผู้รับผิดชอบ, Notes
- เพิ่ม setupAllTriggers() — ตั้ง 2 trigger ในครั้งเดียว:
- ไฟล์: MBOX_Daily_Digest_LINE_OA.gs (v2.0)
### 2. LINE OA Auto Reply ✅

- ตั้งค่า Greeting Message เมื่อ Add Friend
- ตั้งค่า Keyword Auto Reply (ไม่ต้องเขียนโค้ด — ใช้ LINE OA built-in):
- ไฟล์ Guide: MBOX_LINE_AutoReply_Setup.docx
### 3. คู่มือเปิดร้านคาราโอเกะ ✅

- สร้าง MBOX_KaraokeGuide_ForBusiness.docx — 9 บท ครอบคลุม:
## 📌 สิ่งที่ยังค้างอยู่ (Next Actions)

## 🔧 Technical Notes

- Google Apps Script trigger: UTC = Bangkok - 7 ชั่วโมง
- LINE OA Keyword Reply: case-insensitive อัตโนมัติ แนะนำเพิ่มทั้งไทยและอังกฤษ
- sendFollowupReminder() เช็ค column NEXT_MEETING — ต้องแน่ใจว่า Sheet มี column นี้ถูกต้อง
- ไฟล์ทั้งหมดอยู่ใน Cowork outputs folder
## 💡 Key Insights จาก Session นี้

- LINE OA Auto Reply แบบ built-in ไม่ต้องโค้ด ใช้ได้ทันที — เหมาะมากสำหรับทีมที่ไม่มีนักพัฒนา
- คู่มือคาราโอเกะสามารถใช้เป็น Sales Tool สำหรับ B2B ได้เลย — ส่งให้ร้านอาหาร/โรงแรมก่อนนัด Demo
- ROI 2-4 เดือนสำหรับ 2 ห้อง เป็น selling point ที่แข็งแกร่งมาก
