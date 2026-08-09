# RESTORE GUIDE — NIHIL.ro Configuration Backup

This directory contains the original workflow configuration before the Google Pro / Gemini Web UI update.

## Backed Up Files
1. `AGENTS.md.old` — Original AGENTS.md workflow and instructions.
2. `image_guide.md.old` — Original image generation protocol with Playwright / noai-watermark.

## How to Restore
To restore the original configuration at any time, run the following commands or copy the content back:
```powershell
Copy-Item "D:\Work\Websites\nihil.ro\backup_workflow\AGENTS.md.old" "D:\Work\Websites\nihil.ro\AGENTS.md" -Force
```
