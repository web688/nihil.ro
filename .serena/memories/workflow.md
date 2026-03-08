# WORKFLOW — NIHIL.RO

## Image Generation (Gemini Nano Banana 2)

### Step 1: Navigate
```
browser_navigate → https://gemini.google.com/
```

### Step 2: Generate Image
```
Type prompt: "Generate an image of [SUBJECT], warm earthy tones, editorial documentary photography style, slightly desaturated sepia colors, film grain texture, dramatic lighting, no borders, full frame, [16:9 or 4:3] aspect ratio"
```

### Step 3: Download
```
browser_click → Download full-sized image
```
Saves to: `C:\Users\Alex\AppData\Local\Temp\playwright-mcp-output\`

### Step 4: Copy to Project
```powershell
Copy-Item "C:\Users\Alex\AppData\Local\Temp\playwright-mcp-output\[timestamp]\[filename].png" "X:\Website\Utils\nihil.ro\images\[article-slug]-[n].jpg"
```

### Step 5: Remove Watermark
```powershell
.\GeminiWatermarkTool.exe --input "images\[article-slug]-[n].jpg"
```

---

## Task Completion Checklist

1. Test navigation works on all pages
2. Verify images load correctly
3. Check article links work
4. Run frontend-tester agent for UI changes
5. Commit changes to git

---

## Git Commands (Windows)

```powershell
git status
git add .
git commit -m "message"
git push
```

---

## File Operations (PowerShell)

```powershell
dir                    # list files
type file.txt          # read file
copy src dst           # copy
move src dst           # move
remove-item file       # delete
```
