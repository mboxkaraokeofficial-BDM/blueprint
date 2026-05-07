# MBX Sales & CRM Operations Hub

- **Notion ID:** 3371ac219abd81cabc64eccdfc4697a7
- **URL:** https://www.notion.so/MBX-Sales-CRM-Operations-Hub-3371ac219abd81cabc64eccdfc4697a7
- **Last Edited:** 2026-05-07T05:33:00.000Z

---

## 📊 Sales & CRM System Overview

### ระบบที่ใช้

- Airtable (MBOX CRM) — ฐานข้อมูลหลัก: Leads, Deals, Clients, Products, Tasks, Activities, Services
- Notion — Dashboard, Wiki, และเอกสารประกอบ
- MBOX Product Base — Product catalog ต้นทาง (ซิงค์มา CRM)
## 🔄 Sales Pipeline Flow

### 1. Lead Collection

- แหล่งที่มา: Facebook/IG Ads, Referral, Walk-in/โทรเข้า
- ข้อมูลที่เก็บ: ชื่อ, เบอร์โทร, Email, Line ID, บริษัท, สิ่งที่สนใจ, Budget
- Lead Status: New → Contacted → Qualified → Proposal Sent → Negotiation → Won/Lost
### 2. Sales Process (Deal)

- สร้าง Deal เชื่อมจาก Lead
- เลือก Product/Solution Set และระบุจำนวน
- Stage:  Proposal → Negotiation → Closed Won/Lost
### 3. Follow-up Auto Tasks

- Day 1: หลังปิดการขาย — ส่งข้อความขอบคุณ + แนะนำการใช้งาน (Onboarding)
- Day 7: Follow-up สอบถามความพึงพอใจ + ช่วยแก้ปัญหา
- Day 30: ติดตามความพึงพอใจระยะยาว + เสนอบริการเพิ่มเติม
### 4. Customer Database & Onboarding

- หลังปิดการขาย → ย้ายข้อมูลจาก Lead ไป Client
- Onboarding Status: Pending → In Progress → Completed
- เก็บ: ชื่อ, ที่อยู่, เบอร์โทร, Email, Line, Serial No., Customer Type
### 5. Transaction & Activity Log

- บันทึกทุกการติดต่อ: โทร, Line, Email, เยี่ยมชม, ร้องเรียน
- ทิศทาง: Inbound / Outbound
- ผลลัพธ์ + Next Action
## 📎 ตารางใน Airtable (MBOX CRM)

## 📈 KPIs ที่ติดตาม

- Lead Conversion Rate: Lead ที่ปิดการขายได้ / ทั้งหมด
- Average Deal Value: มูลค่าเฉลี่ยต่อ Deal
- Sales per Staff: ยอดขายต่อพนักงาน
- Follow-up Completion Rate: Task ที่ทำสำเร็จตามกำหนด
- Customer Satisfaction: จาก follow-up Day 7/30
- Revenue by Product: ยอดขายแยกตามสินค้า
- Revenue by Segment: Home / Restaurant / KTV / Enterprise
- Monthly Close Rate: จำนวน Deal Won / Total Deals ต่อเดือน
- Customer Lifetime Value: มูลค่ารวมที่ลูกค้าจ่ายตลอดชีวิต
- Returning Customer Rate: % ลูกค้าที่กลับมาซื้อซ้ำ
## 🔮 Sales Forecast

ใช้ฟิลด์ใน Deal table:

- Deal Value — มูลค่า Deal
- Win Probability % — โอกาสปิดการขาย
- Weighted Value = Deal Value x Win Probability (คำนวณ forecast)
- Expected Close Date — วันที่คาดว่าจะปิด
### วิธีอ่าน Forecast

- รวม Weighted Value ของ Deal ที่ยังเปิดอยู่ = ยอดขายที่คาดการณ์
- แยกตาม Expected Close Date = ดู forecast รายสัปดาห์/เดือน
- Win Probability แนะนำ: Qualified=30%, Proposal Sent=50%, Negotiation=70%
## 📋 Weekly Sales Summary (สรุปรายสัปดาห์)

ข้อมูลที่ดูทุกสัปดาห์:

1. Deals ปิดได้สัปดาห์นี้ — จำนวน + มูลค่ารวม
1. Leads ใหม่ — จำนวน + แหล่งที่มา
1. Pipeline — Deal ที่อยู่ในแต่ละ Stage + มูลค่ารวม
1. Tasks Overdue — งานที่เลยกำหนด
1. Follow-up ที่ต้องทำ — รายชื่อลูกค้าที่ต้องติดตาม
1. Close Rate เดือนนี้ — Won / (Won + Lost) x 100
## 🔁 ลูกค้าเก่ากลับมาซื้อ (Returning Customer Flow)

สำคัญ: ลูกค้าเก่าติดต่อมาซื้อบริการ ไม่ต้องสร้าง Lead ใหม่

### Flow:

1. ลูกค้าเก่าติดต่อมา → บันทึกใน Activities (ประวัติการติดต่อ)
1. สร้าง Service Order ใน Service Orders table (เชื่อม Client)
1. เลือก Order Type: Cloud Renewal / ซ่อม / อัปเกรด / ซื้อเพิ่ม
1. อัปเดต Lifetime Value และ Total Purchases ใน Client
### ตาราง Service Orders (ใหม่)

## 🛠️ Onboarding Checklist

- [ ] ส่งข้อความขอบคุณ + ยินดีต้อนรับ
- [ ] แนะนำการติดตั้ง + การใช้งานเบื้องต้น
- [ ] แนะนำการใช้ Cloud / App (M Manager, MPad)
- [ ] บันทึก Serial Number + ข้อมูลการรับประกัน
- [ ] Follow-up Day 7: สอบถามความพึงพอใจ + เเนะนำการใช้งานเพิ่มเติม เช่นการใช้ mpad / คีย์ลัดต่างๆ
- [ ] Follow-up Day 30: ติดตามระยะยาว + เสนอบริการเพิ่มเติม
- [ ] Follow-up Day 365: ติดตามการต่ออายุ Cloud
