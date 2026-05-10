# 🔧 CITIMAN — Auto Changelog

- **Notion ID:** 35c1ac219abd81b19297ff60ef211887
- **URL:** https://www.notion.so/CITIMAN-Auto-Changelog-35c1ac219abd81b19297ff60ef211887
- **Last Edited:** 2026-05-10T09:45:00.000Z

---

## 🔧 Auto Changelog

## How this page is used

- Append-only. Claude pushes new entries here after meaningful edits.
- Source of truth = local files. This page is a record, not a spec.
- Human-readable. No machine-only IDs in the body.
- For session-level summaries, use 📝 Session Recaps instead.
## Conventions

- Each entry uses ### YYYY-MM-DD HH:MM — <summary> heading
- Body lists: file path · what changed · which Buddhist Method principles were applied
- File paths use markdown links when possible
## Entries

### 2026-05-10 16:45 — Board 05 prompts exported as JSON

- File: ~/Documents/claude/citiman/storyboard/board-05-prompts.json
- Changes: Extracted all 6 shots of Board 05 (Cinematic Title Card) to structured JSON. Verbatim prompts + negatives, post-production overlay specs, transitions, BGM hints, brand palette/fonts, global constraints. Total 35s. Ready for Runway/Sora/Kling/Veo input.
- Principles applied: Kalama Sutta — copied prompts verbatim from canonical HTML, no paraphrasing. Verified valid JSON via python3 -c json.load.
### 2026-05-10 16:43 — Files consolidated into ~/Documents/claude/citiman/

- Moved:
- Why: 5 scattered copies of video-prompts.html were drifting. ~/Documents/claude/ is the GitHub-tracked monorepo (already has citiman/, foodstock/, kitso/, mbox/) — single source of truth.
- Security flag: GitHub PAT ghp_km8... is exposed in plaintext in git config remote.origin.url. User to rotate + switch to SSH or git credential manager.
- Principles applied: Sati-Sampajañña (verified target was a monorepo before placing files at root); Pahāna (cut the cause of drift instead of working around it).
### 2026-05-10 16:00 — Shot 6 cleanup + Pure Black on-brand

- File: /tmp/cit/video-prompts.html
- Changes:
- Principles applied:
- Verification: grep -c Contact /tmp/cit/video-prompts.html → 0
