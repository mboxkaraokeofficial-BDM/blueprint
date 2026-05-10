# Untitled

- **Notion ID:** 3561ac219abd811db7d5ddd94a5ba5b9
- **URL:** https://www.notion.so/Failed-Test-Cases-UI-Flow-Map-CITIMAN-3561ac219abd811db7d5ddd94a5ba5b9
- **Last Edited:** 2026-05-04T10:39:00.000Z

---

## ❌ Failed Test Cases + UI Flow Map

### โครงสร้าง 6 Sheets

### ❌ Failed Cases ที่คาดว่าจะเกิดจริง (ระดับ Critical)

- F-PDPA-001: เลขบัตรแสดงเต็มใน User Management
- F-PDPA-002: เลขบัตรแสดงเต็มใน Petition Detail
- F-PDPA-003: ชื่อ+เบอร์ไม่ mask ในรายงานเกินกำหนด
- F-SEC-001: Access Control — เข้าหน้า protected โดยไม่ login
- F-SEC-002: Role Separation — Citizen เข้าหน้า Officer
- F-AUTH-008: Logout แล้ว Back browser เข้า Dashboard ได้
- F-PET-006: ไม่คลิก map — ปุ่ม disabled
- F-PET-007: Map click ครั้งแรก React state bug
- F-PET-010/011: OTP ผิด / หมดอายุ
### คำแนะนำการใช้งาน

1. เริ่มจาก UI Flow Map เพื่อเข้าใจไหล + จุดเสี่ยงของแต่ละหน้า
1. ทดสอบ PDPA & Security sheet ก่อน (ความเสี่ยงสูงสุด)
1. ทดสอบ Failed Case ตาม Sheet ทีละ Module
1. ทดสอบ Boundary & Edge สุดท้าย
