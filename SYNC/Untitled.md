# Untitled

- **Notion ID:** 34c1ac219abd81e7b0a3ec18c2faa75d
- **URL:** https://www.notion.so/Manual-Test-Case-Scenario-Plan-CITIMAN-Web-App-34c1ac219abd81e7b0a3ec18c2faa75d
- **Last Edited:** 2026-04-24T06:43:00.000Z

---

## 📋 Manual Test Case Scenario Plan — CITIMAN

### โครงสร้าง Excel (9 Sheets)

### รายการ Bug/Risk สำคัญที่ต้องตรวจสอบ

1. [PDPA] เลขบัตรประชาชนแสดงเต็มใน User Management — ควร mask เป็น X-XXXX-XXXXX-XX-X
1. [PDPA] เลขบัตรแสดงเต็มใน Petition Detail
1. [PDPA] รายงานเกินกำหนด: ชื่อ + เบอร์โทรไม่ mask
1. [Security] ทดสอบ Access Control: Citizen ไม่ควรเข้าหน้า Officer ได้
1. [BUG/UX] Map click ครั้งแรกไม่ update React state — ปุ่ม disable ผิดปกติ
1. [BUG/Display] สถานะใน Dashboard ≠ สถานะใน Petition Detail
1. [UX] CIT-TRACK ไม่แสดงประวัติคำร้องอัตโนมัติ
1. [UX] ไม่มี Audit Trail module แยกต่างหาก
1. [Data] Test data ทุกรายการหมดอายุ SLA (ต.ค. 2568)
### Pre-conditions ก่อนทดสอบ

- URL: https://demo.oishifoods.com
- Officer account: มีบัญชี ThaID ที่ผูกกับ role เจ้าหน้าที่
- Citizen account: มีบัญชี ThaID ทั่วไป
- Email: ใช้ email จริงที่รับ OTP ได้ (สำหรับ CIT-PET flow)
- Mobile: ติดตั้งแอป ThaID บนมือถือ
- Browser: Chrome หรือ Edge (แนะนำ)
### คำแนะนำ Manual Tester

1. เปิด sheet ของ Module ที่ต้องการทดสอบ
1. ทำตาม Pre-conditions ก่อนเสมอ
1. ทำตาม Test Steps ทีละขั้นตอน
1. เปรียบเทียบกับ Expected Result
1. กรอก Actual Result + ทำเครื่องหมาย Pass/Fail
1. ถ้าพบปัญหา: จด Screenshot + URL + Error message ใน Notes
1. ให้ความสนใจพิเศษกับ sheet ⚠️ PDPA & Bug Check — เป็นจุด Critical ที่ต้องแก้ก่อน release
