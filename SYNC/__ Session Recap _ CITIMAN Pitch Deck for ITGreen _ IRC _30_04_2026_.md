# 🎤 Session Recap — CITIMAN Pitch Deck for ITGreen × IRC (30/04/2026)

- **Notion ID:** 3521ac219abd817aa0b8eadbc96c860f
- **URL:** https://www.notion.so/Session-Recap-CITIMAN-Pitch-Deck-for-ITGreen-IRC-30-04-2026-3521ac219abd817aa0b8eadbc96c860f
- **Last Edited:** 2026-04-30T10:53:00.000Z

---

## 📋 Session Summary

## 🎯 โจทย์ของ Session นี้

เตรียม Pitch Deck สำหรับการประชุม IRC + ITGreen วันที่ 2 พฤษภาคม 2568 โดย:

- นำเสนอ MBOX Group Profile + ศักยภาพของทีม
- แนะนำ CITIMAN — City Management System
- เสนอ 3 รูปแบบ Partnership (Reseller / Hosting / Co-branding)
- Design Style: Dark Tech Luxury (Deep Navy-Black + Electric Blue + Champagne Gold)
## ✅ สิ่งที่ทำสำเร็จ

### 1. รวบรวม MBOX Company Profile จาก 2 ไฟล์

- Corp_Presentation_26.pptx → Official company info, Softnet (sister company), Enterprise clients: ปตท, ธปท, กฟผ, SKF
- Corp_Presentation_26_2.pptx → BeSafe, Examination Online, Monet (Billing), Software Outsourcing to USA/Korea/Japan
### 2. สร้าง PptxGenJS Pitch Deck (v1 — ก่อน Switch)

- 11 Slides: Cover, Agenda, Profile, Products, Team, CITIMAN Intro, Features, Market, Why ITGreen, Partnership Model, Next Steps
- Fix: line: { color: "080D18", pt: 0 } แทน line: { color: "none" } → ไม่มีกรอบดำ
- QA Subagent ตรวจพบและแก้: footer clipping + CitiMan.Paper truncation
- ไฟล์: MBOX_ITGreen_Pitch_2May2026.pptx (workspace)
### 3. เปลี่ยนเป็น Next.js Web Presentation (ตามที่ขอ)

สร้าง project ครบใน mbox-pitch-nextjs/:

### 4. Features ของ Web Presentation

- ✅ 11 Slides แยก component ตาม type
- ✅ Keyboard navigation: ← → Spacebar
- ✅ Touch swipe (Mobile)
- ✅ Progress bar + Slide dots
- ✅ Fullscreen mode (กด F)
- ✅ Nav auto-hide
- ✅ Dark Luxury palette: #080D18 + #3B6EF8 + #C4A860
- ✅ Google Fonts: Noto Sans Thai
- ✅ Fade-in + stagger animations
## 📁 ไฟล์ที่สร้าง

## 🏃 วิธีใช้งาน

ใช้ได้ทันที (ไม่ต้อง install):

Next.js (Production/Deploy):

## 📋 Slide Structure (11 Slides)

1. Cover — MBOX × ITGreen × IRC + CITIMAN tagline
1. Agenda — 6 หัวข้อหลัก
1. MBOX Profile — Stats, 4 Business Areas, Softnet, Outsourcing
1. Products — MBOX Karaoke, CITIMAN, BeSafe, Exam Online, Monet, Outsourcing
1. Team Capabilities — 6 ด้าน + Certifications
1. CITIMAN Intro — Big number 7,850 อปท. + 4 Pillars
1. CITIMAN Features — Finance, HR, Service, Asset, Paper
1. Market Opportunity — 7,850 อปท. breakdown + insights
1. Why ITGreen — 3 เหตุผล + Match cards
1. Partnership Model — Reseller / Hosting / Co-branding
1. Next Steps — Timeline LOI → Pilot → Launch → Scale
## ⚡ Next Actions

- [ ] เปิด MBOX_Pitch_Standalone.html ตรวจ content ก่อนประชุม
- [ ] ซักซ้อม Pitch 15–20 นาที อย่างน้อย 1 รอบ
- [ ] เตรียม Demo CITIMAN ด้วยถ้ามีเวลา
- [ ] ประชุม IRC + ITGreen — 2 พฤษภาคม 2568
- [ ] หลังประชุม: บันทึก Outcome + MOU Next Steps
