# 🗂️ Song DB Audit & v2 Schema — Apr 2026

- **Notion ID:** 34c1ac219abd81c5bee2f032a4a27787
- **URL:** https://www.notion.so/Song-DB-Audit-v2-Schema-Apr-2026-34c1ac219abd81c5bee2f032a4a27787
- **Last Edited:** 2026-04-28T01:52:00.000Z

---

## 📋 Overview

## 🔍 Audit Results Summary

## 🔢 Song ID Gaps (per Category)

ID ของหมวดไทยและสากลมีช่องว่างสูงเพราะมาจากหลาย batch ไม่ใช่ autoincrement

## 🏗️ v2 Schema Blueprint

### สิ่งที่เปลี่ยนจากระบบเดิม

### สถาปัตยกรรม 2-DB

### Performance (benchmarked on 72,267 songs)

## ⚙️ Content Management System (CMS) — Workflow Design

### Root Cause — ทำไมถึงใช้เวลา 20+ ชั่วโมง

### New CMS Workflow

### Time Savings

### System Components

### Priority Build Order

### วิธีรัน Internal Tool

Files: C:\Users\Windows\Documents\Claude\Projects\MBX-Song DB\rag\

## ✅ สิ่งที่ทำแล้ว

- [ ] Audit ครบ 12 ประเภท → full_audit_issues.csv (2,094 rows)
- [ ] Extra audit: fl_media_type, fl_hdd, cross-company duplicates, singer spacing pairs
- [ ] Singer audit: ตรวจ fl_singer ที่ไม่ใช่ชื่อศิลปินจริง
- [ ] Song ID gap analysis → song_id_gaps.csv
- [ ] Blueprint v2 schema เขียนเสร็จ (DDL + Query patterns + Migration steps)
- [ ] อัพเดท Google Sheets — tab "Full Audit (2,094)" พร้อมข้อมูลครบ
- [ ] Performance benchmark: FTS5 vs LIKE
- [ ] CMS Workflow Design — วิเคราะห์ root cause + ออกแบบ workflow ใหม่ (20h → 1.5h)
- [ ] Internal Tool v1 — Web CMS พร้อม Search, Import, Company Manager, Audit Log
- [ ] อัพเดท Notion + Memory
## 🔲 Next Steps (Migration Prerequisites)

- [ ] ระบุชื่อศิลปินจริงสำหรับ 539 เพลง (fl_singer = รวมเพลง/OST)
- [ ] ระบุชื่อศิลปินจริงสำหรับ 255 เพลง (fl_singer = ภาพยนตร์/ซีรีส์)
- [ ] Dedup 884 รายการซ้ำ
- [ ] Merge 48 คู่ชื่อศิลปินสะกดต่างกัน → canonical name
- [ ] สร้าง schema_content.sql + schema_device.sql
- [ ] สร้าง migrate_artists.js (parse fl_singer → tb_song_artist)
- [ ] สร้าง migrate_songs.js + seed_aliases.js
## 📁 Scripts & Files

All files at: C:\Users\Windows\Documents\Claude\Projects\MBX-Song DB\

