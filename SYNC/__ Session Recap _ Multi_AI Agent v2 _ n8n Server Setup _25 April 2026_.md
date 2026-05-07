# 🤖 Session Recap — Multi-AI Agent v2 + n8n Server Setup (25 April 2026)

- **Notion ID:** 34d1ac219abd81838ad8c4b83a45aec2
- **URL:** https://www.notion.so/Session-Recap-Multi-AI-Agent-v2-n8n-Server-Setup-25-April-2026-34d1ac219abd81838ad8c4b83a45aec2
- **Last Edited:** 2026-04-25T07:54:00.000Z

---

## 📌 สรุปสิ่งที่ทำใน Session นี้

Session นี้ทำ 3 เรื่องหลัก: (1) ออกแบบ Multi-AI Agent System v2 ครบ 9 agents (2) ตัดสินใจย้ายจาก Make.com ไป n8n (3) สร้าง Server Setup files พร้อม deploy

## 🤖 1. Multi-AI Agent System v2 — อัปเดต Architecture

### เพิ่ม 3 Tech Agents ใหม่

### Full Agent List (9 ตัว)

- 🎯 Orchestrator — Claude API Brain (route ทุก request)
- 💼 Sales Agent
- 🎧 Support Agent
- 💰 Finance Agent
- ⚙️ Ops Agent
- 🧠 Knowledge Agent
- 🎨 Design Agent
- 🔬 R&D Agent (NEW)
- 💻 Programmer Agent (NEW)
- 🧪 QA/Tester Agent (NEW)
### Cross-agent Flows สำคัญ

- Lead Won → Ops Ticket + Finance Invoice + Dev Config (พร้อมกัน 3 ทาง)
- R&D Approved → Dev Task → QA Test Plan (อัตโนมัติ)
- Deploy Done → QA Auto Test → Pass ✅ Release / Fail ❌ Bug กลับ Dev
- Bug จากลูกค้า → Support → QA Classify → Dev + Context (ไม่ต้องอธิบายซ้ำ)
- Pamelosam แก้ไข → Knowledge Agent บันทึก Rule → ทุก Agent เรียนรู้
### Pain Point ที่แก้ได้

- พี่เก้รู้ระบบคนเดียว → Programmer Agent สร้าง System Docs อัตโนมัติ ความรู้ไม่หายแม้คนย้าย
- CITIMAN Bug → QA Agent สร้าง Structured Report พร้อม Steps/Priority ส่ง Dev ได้เลย
## ⚡ 2. ตัดสินใจ: ย้ายจาก Make.com → n8n

### เหตุผลที่ Make.com มีปัญหา

- Scenario Auto-Deactivate เมื่อ HTTP error
- LINE replyToken หมดอายุก่อน Make.com ตอบกลับ (401 Unauthorized)
- Error Handler ต้องตั้งทีละ module ทั้ง 12 ตัว
- Operation Limit — ค่าใช้จ่ายพุ่งเมื่อ Agent ทำงานบ่อย
### ทำไม n8n ดีกว่าสำหรับ MBOX

- ฟรี — MBOX จะตั้ง Server ใหม่ ติดตั้ง n8n ได้เลย ไม่มีค่าเพิ่ม
- Error Handling ดีกว่ามาก — Global + Per Node, ไม่ deactivate เองอีก
- มี AI Agent Node — เชื่อม Claude API ได้โดยตรง เหมาะกับ Multi-Agent
- ไม่จำกัด Execution — Scale เท่าไหร่ก็ได้ ไม่มีค่าเพิ่ม
- Data Privacy — ข้อมูลลูกค้าอยู่ใน Server ตัวเอง
### แผนการ Migrate

1. ตั้ง Server ใหม่ → ติดตั้ง n8n
1. Migrate LINE OA Bot ก่อน (workflow ที่มีปัญหา)
1. ทดสอบจน stable → ค่อย migrate ทั้งหมด
1. เก็บ Make.com plan ถูกสุดไว้ระหว่าง Migrate → Cancel เมื่อเสร็จ
## 🖥️ 3. Server Setup — Files พร้อม Deploy

### Server Spec ที่แนะนำ

### Services บน Server ใหม่

### ไฟล์ที่สร้างแล้ว (บันทึกใน Documents/Claude/Projects/MBOX-Server)

- docker-compose.yml — config ทุก service พร้อม run
- setup.sh — one-command install บน Ubuntu ใหม่
- backup.sh — auto backup ทุกคืน 02:00
- .env.example — template config (แก้แค่ 4 ค่า)
- SETUP_GUIDE.md — คู่มือภาษาไทยครบ step-by-step สำหรับพี่เก้
## ✅ Next Actions

- [ ] สมัคร VPS DigitalOcean Singapore — digitalocean.com
- [ ] ส่ง Setup files ให้พี่เก้ → รัน sudo ./setup.sh
- [ ] แก้ .env (N8N_HOST + Password + Gmail App Password)
- [ ] ตั้ง DNS: n8n.mboxkaraoke.com + monitor.mboxkaraoke.com → Server IP
- [ ] สมัคร Claude API Key → console.anthropic.com
- [ ] Migrate LINE OA Bot จาก Make.com → n8n (workflow แรก)
- [ ] Build Sales Agent (Orchestrator ตัวแรก)
## 💰 Budget Summary

