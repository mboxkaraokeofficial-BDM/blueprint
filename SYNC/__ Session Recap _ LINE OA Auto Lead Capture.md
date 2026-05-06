# ⚙️ Session Recap — LINE OA Auto Lead Capture 

- **Notion ID:** 34b1ac219abd81328f86e216f65a8cbd
- **URL:** https://www.notion.so/Session-Recap-LINE-OA-Auto-Lead-Capture-Make-com-23-04-2026-34b1ac219abd81328f86e216f65a8cbd
- **Last Edited:** 2026-04-23T06:13:00.000Z

---

## 📋 Session Overview

- Date: 23/04/2026
- Session Type: Make.com Scenario Build
- Status: 🟡 95% Done — Awaiting first real LINE message to complete mapping
## 🎯 What Was Built

Make.com Scenario: MBOX — LINE OA Auto Lead Capture

- Scenario ID: 5406773
- Goal: Auto-capture LINE OA leads → save to Google Sheet automatically
### Modules Built

### Column Mapping Status

## 🔧 Key Issues Resolved This Session

1. Wrong Google Sheet selected → Fixed by choosing "MBOX_Lead_Import_Template" (underscore version) instead of "MBOX Lead Import — Google Sheet"
1. displayName not in variable picker → Root cause: HTTP module had never run, so Make.com doesn't know JSON structure yet. Will resolve after first real LINE message.
1. Filter blocked test run → Queued webhook data was a LINE "follow" event, not "message" — so filter passed 0 results. Expected behavior.
1. Escape key closed dialog without saving → Reopened and re-configured from scratch
## ✅ Scenario Settings Confirmed

- Name: MBOX — LINE OA Auto Lead Capture ✅
- Scheduling: Immediately as data arrives (ON) ✅
- Saved: Yes ✅
- Connection: MBOX Google Sheets (mb...) ✅
- LINE Channel Access Token: Configured in HTTP Authorization header ✅
## 🔜 Next Action (Critical)

### To complete column B–E mapping:

1. Open LINE app
1. Send any message to MBOX LINE OA
1. Scenario auto-triggers → HTTP module runs → displayName, pictureUrl, statusMessage become available
1. Open Make.com → Scenario 5406773 → Google Sheets module (Module 3)
1. Map remaining columns:
1. Save scenario ✅
### After mapping complete:

- Test with 2-3 real LINE messages
- Verify data appears correctly in Google Sheet
- Mark Phase 2 LINE OA Lead Capture as ✅ Complete
## 📎 Resources

- Make.com Scenario: https://eu1.make.com/5406773/scenarios/editor
- Google Sheet: MBOX_Lead_Import_Template (My Drive)
- LINE Webhook URL: https://hook.eu1.make.com/1vaz2zdp7i4x3dftu4mbt5zpr83aishd
- LINE Profile API: https://api.line.me/v2/bot/profile/{userId}
