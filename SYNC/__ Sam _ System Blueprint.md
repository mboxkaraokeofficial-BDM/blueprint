# 🤖 Sam — System Blueprint

- **Notion ID:** 3591ac219abd81c7be42d074f8d7c710
- **URL:** https://www.notion.so/Sam-System-Blueprint-3591ac219abd81c7be42d074f8d7c710
- **Last Edited:** 2026-05-07T03:14:00.000Z

---

## Sam คืออะไร

Sam คือ Personal AI Secretary ระดับ Enterprise ของ Pichaya Sam

บุคลิก:

- ฉลาดมาก — วิเคราะห์ได้ลึก แนะนำโดยไม่ต้องถาม
- มีเสน่ห์ — พูดได้น่าฟัง ไม่แข็งกระด้าง
- มีมารยาท — สุภาพ รู้กาลเทศะ
- เอาใจเก่ง — รู้อารมณ์ ปรับ tone ได้
- แนะนำมุมมองใหม่ — ไม่แค่ทำตามสั่ง แต่ challenge และเสนอแนว
## Architecture

## n8n Workflow: Sam Brain

### Nodes:

1. Discord Webhook — รับข้อความ
1. Load Context — GET Calendar + Notion Identity + Tasks
1. Build Prompt — System Prompt + Context + User Message
1. Claude API — model: claude-sonnet-4-6
1. Tool Router — ตัดสินใจ action
1. Execute Tool — Calendar / Notion / Gmail
1. Discord Reply — ส่งกลับ
1. Save to Daily Log — บันทึกใน Notion
### Proactive Triggers:

## Discord Structure

## Implementation Phases

### Phase 1: Foundation

- [ ] สร้าง Discord Server + Bot
- [ ] สร้าง Notion Identity & Context ✅
- [ ] สร้าง Personal Dashboard ✅
- [ ] สร้าง n8n workflow บน VPS
### Phase 2: Intelligence

- [ ] เชื่อม Claude API + Context Loader
- [ ] เชื่อม Google Calendar (create + read)
- [ ] เชื่อม Notion tasks
### Phase 3: Proactive

- [ ] Morning Brief trigger
- [ ] Event reminder
- [ ] Evening Summary
### Phase 4: Scale (อนาคต)

- [ ] Sub-agents (Marketing, Finance, CRM, Content, Ops)
- [ ] FlowAccount integration
- [ ] LINE OA bridge
## Future Agent Expansion

Last updated: May 2026 · Framework by Claude for Sam AI Secretary System

