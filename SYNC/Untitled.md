# Untitled

- **Notion ID:** 34c1ac219abd81d5a409e6dcc13b573e
- **URL:** https://www.notion.so/CITIMAN-Web-App-Live-Test-Execution-34c1ac219abd81d5a409e6dcc13b573e
- **Last Edited:** 2026-04-29T09:03:00.000Z

---

## ผลการทดสอบ CITIMAN — 23-24 เมษายน 2569

### สรุป

### โมดูลที่ทดสอบ

- ✅ AUTH — ThaID QR login ทั้ง Officer และ Citizen
- ✅ OFF-DASH — Dashboard, กราฟ, SLA badge, Filter
- ✅ OFF-APPROVE — List, Search, Detail view
- ✅ OFF-CAT — จัดการหมวดหมู่และประเภทคำร้อง
- ✅ OFF-USER — จัดการสมาชิก, Modal, Audit trail
- ✅ SYS-REPORT — 7 ประเภทรายงาน + ดาวน์โหลด
- ✅ SYS-HOLIDAY — จัดการวันหยุด
- ✅ SYS-UNIT — จัดการหน่วยงาน
- ✅ SYS-AREA — GIS Zone polygon map 3 โซน
- ✅ SYS-EMAIL — 12 templates + Rich text editor
- ✅ SYS-POS — จัดการตำแหน่งงาน
- ✅ CIT-HOME — หน้าหมวดหมู่บริการ 6 หมวด
- ✅ CIT-PET — ยื่นคำร้อง end-to-end (3 steps + Email OTP)
- ✅ CIT-TRACK — ติดตามสถานะคำร้อง
- ✅ CIT-SAT — ประเมินความพึงพอใจ
### Bug/ข้อสังเกตสำคัญ

1. 🔴 [PDPA] เลขบัตรประชาชนแสดงเต็ม 3 จุด (User Mgmt / Petition Detail / Report)
1. ⚠️ [BUG/UX] map click ครั้งแรกไม่ update React state
1. ⚠️ [Display] Dashboard vs Petition Detail status inconsistency
1. ⚠️ [PDPA] รายงานเกินกำหนดไม่ mask เบอร์โทร
### ไฟล์รายงาน

- CITIMAN_Test_Report_24Apr2569.xlsx — 5 sheets (สรุป / Officer / Citizen / ข้อสังเกต / Priority Actions)


