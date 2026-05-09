# Obsidian Git Setup — Notion → Git → Obsidian

## ปัญหา: Obsidian ไม่ pull อัตโนมัติ

### วิธีแก้ (ทำใน Obsidian)

#### 1. ติดตั้ง Obsidian Git Plugin
- Settings → Community plugins → Browse → ค้นหา **"Obsidian Git"**
- Install → Enable

#### 2. ตั้งค่า Authentication (สำคัญมาก)

**วิธี HTTPS + Token (แนะนำ):**
1. ไป GitHub → Settings → Developer settings → Personal access tokens → Fine-grained
2. สร้าง token ที่มี permission: `Contents: Read and write`
3. ใน terminal ของ Obsidian vault ให้รัน:
   ```
   git remote set-url origin https://<YOUR_TOKEN>@github.com/mboxkaraokeofficial-bdm/blueprint.git
   ```

**หรือวิธี SSH:**
```bash
git remote set-url origin git@github.com:mboxkaraokeofficial-bdm/blueprint.git
```

#### 3. ตั้งค่า Auto-pull ใน Obsidian Git Plugin

Settings → Obsidian Git:
- **Auto pull interval (minutes):** `10`  ← ตั้งค่านี้ให้ pull ทุก 10 นาที
- **Pull updates on startup:** ✅ เปิด
- **Auto pull on startup:** ✅ เปิด
- **Disable push:** ✅ เปิด (ถ้าไม่ต้องการ push จาก Obsidian)
- **Pull before push:** ✅ เปิด

#### 4. ทดสอบ Manual Pull

กด `Ctrl+P` → พิมพ์ "Obsidian Git: Pull" → Enter

ถ้า pull สำเร็จ → auto-pull จะทำงานเองตามกำหนดเวลา

---

## Flow ทั้งหมด

```
Notion (แก้ไข page)
    ↓ ทุก 30 นาที
n8n Workflow
    ↓ Notion API → fetch pages
    ↓ convert to Markdown
    ↓ GitHub API → commit to SYNC/ folder
GitHub repo (mboxkaraokeofficial-bdm/blueprint)
    ↓ ทุก 10 นาที (Obsidian Git auto-pull)
Obsidian Vault
```

---

## Checklist ก่อนใช้งาน

- [ ] Obsidian vault = โฟลเดอร์นี้ (blueprint/)
- [ ] git remote ชี้ไป `github.com/mboxkaraokeofficial-bdm/blueprint`
- [ ] GitHub token ใส่ใน remote URL หรือ SSH key ตั้งค่าแล้ว
- [ ] Obsidian Git plugin: Auto pull interval = 10
- [ ] n8n workflow import แล้ว + credentials ตั้งค่าแล้ว
- [ ] n8n workflow set Active = ON
