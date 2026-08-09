# WORKFLOW — NIHIL.RO

## Image Generation — Two Workflows

### DECISION: Which Workflow to Use?

| Image Type | Workflow |
|------------|----------|
| Modern person portrait (living or recent) | **Stock Photo** → Alamy/Shutterstock via Playwright |
| Landscape, building, object, historical figure | **Gemini** → AI generation |

---

## ⚡ OPTIMIZE FIRST — Key Principle

**Resize images BEFORE de-watermarking for faster processing!**

| Resolution | De-watermark Time | Speedup |
|------------|-------------------|---------|
| 4000x3000 (original) | ~120s | 1x |
| 1600x1200 (optimized) | ~15s | **8x faster** |

Smaller images = faster YOLO detection + faster LaMa inpainting + faster diffusion regeneration.

---

## WORKFLOW A: Stock Photos (Modern Person Pictures)

### Step 1: Navigate to Stock Database
```
browser_navigate → https://www.alamy.com/ or https://www.shutterstock.com/
```

### Step 2: Search for Image
```
Search: [PERSON NAME] portrait editorial
```

### Step 3: Download Image
```
browser_click → Download preview/full image
```
Saves to browser downloads folder.

### Step 4: Copy to Temp Folder
```powershell
Copy-Item "$env:USERPROFILE\Downloads\[filename].jpg" "D:\Websites\nihil.ro\images\temp\[article-slug]-[n]-orig.jpg"
```

### Step 5: Crop Borders/Banners (if needed)
```powershell
& "D:\Websites\MCP\Images\watermark-remover\watermark_remover\venv\Scripts\python.exe" -c "from PIL import Image; img = Image.open(r'D:\Websites\nihil.ro\images\temp\[file]-orig.jpg'); cropped = img.crop((0, 0, img.width, img.height - 100)); cropped.save(r'D:\Websites\nihil.ro\images\temp\[file]-cropped.jpg')"
```
Adjust crop amount based on actual border size. Skip if no borders.

### Step 6: ⚡ OPTIMIZE FIRST (Resize to web size)
```
optimize_image input="D:\Websites\nihil.ro\images\temp\[article-slug]-[n]-cropped.jpg" output="D:\Websites\nihil.ro\images\temp\[article-slug]-[n].jpg" width=1600 quality=90 format="jpeg"
```
**Use quality=90 to preserve detail for watermark detection.**

### Step 7: Batch Process — Visible Watermark Removal

**Put all optimized images in input folder and batch process:**
```powershell
# Create input folder and copy all images to process
New-Item -ItemType Directory -Force -Path "D:\Websites\nihil.ro\images\temp\input"
Copy-Item "D:\Websites\nihil.ro\images\temp\[article-slug]-*.jpg" "D:\Websites\nihil.ro\images\temp\input\" -Exclude "*-orig*","*-cropped*"

# Batch watermark removal (CUDA)
& "D:\Websites\MCP\Images\watermark-remover\watermark_remover\venv\Scripts\python.exe" "D:\Websites\MCP\Images\watermark-remover\watermark_remover\watermark_remover.py" -i "D:\Websites\nihil.ro\images\temp\input" -o "D:\Websites\nihil.ro\images\temp\result" -w "D:\Websites\MCP\Images\watermark-remover\watermark_remover\yolo11x-train28-best.pt" --conf 0.1 --dilate 15
```

**MCP Tools:**
- `batch_remove_watermarks` — Process entire directory at once

### Step 8: Batch Process — Invisible Watermark Removal

```powershell
# Batch process all result images
Get-ChildItem "D:\Websites\nihil.ro\images\temp\result\*.jpg" | ForEach-Object {
    $output = $_.FullName -replace "result", "final"
    & "D:\Websites\MCP\Images\watermark-remover\watermark_remover\venv\Scripts\noai-watermark.exe" $_.FullName -o $output --strength 0.04 --device cuda
}
```

**MCP Tools:**
- `batch_remove_invisible_watermarks` — Process entire directory

### Step 9: Final Optimization
```
batch_optimize inputs=["D:\Websites\nihil.ro\images\temp\final\*.jpg"] outputDir="D:\Websites\nihil.ro\images\[category]" width=1600 quality=80
```

### Step 10: Clean Temp Folder
```powershell
Remove-Item "D:\Websites\nihil.ro\images\temp\input" -Recurse -Force -ErrorAction SilentlyContinue
Remove-Item "D:\Websites\nihil.ro\images\temp\result" -Recurse -Force -ErrorAction SilentlyContinue
Remove-Item "D:\Websites\nihil.ro\images\temp\final" -Recurse -Force -ErrorAction SilentlyContinue
Remove-Item "D:\Websites\nihil.ro\images\temp\*-orig*" -Force -ErrorAction SilentlyContinue
Remove-Item "D:\Websites\nihil.ro\images\temp\*-cropped*" -Force -ErrorAction SilentlyContinue
```

---

## WORKFLOW B: Gemini AI Generation (Landscapes, Objects, Historical Figures)

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

### Step 4: Copy to Temp Folder
```powershell
Copy-Item "C:\Users\Alex\AppData\Local\Temp\playwright-mcp-output\[timestamp]\[filename].png" "D:\Websites\nihil.ro\images\temp\[article-slug]-[n]-orig.jpg"
```

### Step 5: ⚡ OPTIMIZE FIRST
```
optimize_image input="D:\Websites\nihil.ro\images\temp\[article-slug]-[n]-orig.jpg" output="D:\Websites\nihil.ro\images\temp\[article-slug]-[n].jpg" width=1600 quality=90 format="jpeg"
```

### Step 6: Batch Process — Gemini Watermark Removal

```powershell
# Process all Gemini images at once
Get-ChildItem "D:\Websites\nihil.ro\images\temp\[article-slug]-*.jpg" -Exclude "*-orig*" | ForEach-Object {
    $output = $_.FullName -replace "\.jpg", "-clean.jpg"
    & "D:\Websites\nihil.ro\GeminiWatermarkTool.exe" -input $_.FullName -output $output
}
```

**MCP Tools:**
- `batch_remove_watermarks` — Directory processing for Gemini

### Step 7: Batch Process — Invisible Watermark Removal

```powershell
New-Item -ItemType Directory -Force -Path "D:\Websites\nihil.ro\images\temp\input"
Move-Item "D:\Websites\nihil.ro\images\temp\*-clean.jpg" "D:\Websites\nihil.ro\images\temp\input\"

& "D:\Websites\MCP\Images\watermark-remover\watermark_remover\venv\Scripts\python.exe" -c "import os; from noai_watermark import remove_invisible_watermark; [remove_invisible_watermark(f'D:/Websites/nihil.ro/images/temp/input/{f}', f'D:/Websites/nihil.ro/images/temp/final/{f}', strength=0.04, device='cuda') for f in os.listdir('D:/Websites/nihil.ro/images/temp/input') if f.endswith('.jpg')]"
```

Or use MCP: `batch_remove_invisible_watermarks`

### Step 8: Final Optimization & Move
```
batch_optimize inputs=["D:\Websites\nihil.ro\images\temp\final\*.jpg"] outputDir="D:\Websites\nihil.ro\images\[category]" width=1600 quality=80
```

### Step 9: Clean Temp Folder
```powershell
Remove-Item "D:\Websites\nihil.ro\images\temp\input" -Recurse -Force -ErrorAction SilentlyContinue
Remove-Item "D:\Websites\nihil.ro\images\temp\final" -Recurse -Force -ErrorAction SilentlyContinue
Remove-Item "D:\Websites\nihil.ro\images\temp\*-orig*" -Force -ErrorAction SilentlyContinue
Remove-Item "D:\Websites\nihil.ro\images\temp\*-clean*" -Force -ErrorAction SilentlyContinue
```

---

## WORKFLOW SUMMARY

| Source | Step 1 | Step 2 | Step 3 | Step 4 | Step 5 |
|--------|--------|--------|--------|--------|--------|
| **Stock** | Download | Crop borders | **⚡ Optimize** | Visible watermark | Invisible watermark |
| **Gemini** | Generate | Download | **⚡ Optimize** | Gemini watermark | Invisible watermark |

**Key change:** Optimize FIRST (1600px width, quality 90), then de-watermark on smaller images for 8x speedup.

---

## Python venv with CUDA

**Location:** `D:\Websites\MCP\Images\watermark-remover\watermark_remover\venv`

This venv has:
- PyTorch with CUDA support
- noai-watermark
- YOLO watermark detection model

**Usage:**
```powershell
# Run noai-watermark with CUDA
& "D:\Websites\MCP\Images\watermark-remover\watermark_remover\venv\Scripts\noai-watermark.exe" [input] -o [output] --strength 0.04 --device cuda

# Run watermark-remover (YOLO+LaMa)
& "D:\Websites\MCP\Images\watermark-remover\watermark_remover\venv\Scripts\python.exe" "D:\Websites\MCP\Images\watermark-remover\watermark_remover\watermark_remover.py" -i [input_dir] -o [output_dir] -w "D:\Websites\MCP\Images\watermark-remover\watermark_remover\yolo11x-train28-best.pt" --conf 0.1 --dilate 15
```

---

## Batch Operations

### Remove watermarks from all images in temp:
```
batch_remove_watermarks input_dir="D:\Websites\nihil.ro\images\temp" output_dir="D:\Websites\nihil.ro\images\temp"
```

### Optimize multiple images:
```
batch_optimize inputs=["path1.jpg", "path2.jpg"] outputDir="D:\Websites\nihil.ro\images\temp" width=1600 quality=80
```

### Clean temp folder after processing:
```powershell
# Remove all watermark-remover output folders
Get-ChildItem "D:\Websites\nihil.ro\images\temp" -Directory | Remove-Item -Recurse -Force

# Remove intermediate images (keep originals and finals only)
Get-ChildItem "D:\Websites\nihil.ro\images\temp" -Filter "*-crop*" | Remove-Item -Force
Get-ChildItem "D:\Websites\nihil.ro\images\temp" -Filter "*-cropped*" | Remove-Item -Force
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

---

## Folder Structure

```
/articole/
  /ciudatenii/
    *.html
    persona.md
  /lume-larga/
  /oameni-remarcabili/
  /cultura/
  /obsesii/
  /stil-design/
  /romania-nesțiuta/

/images/
  /ciudatenii/
  /lume-larga/
  /oameni-remarcabili/
  /cultura/
  /obsesii/
  /stil-design/
  /romania-nesțiuta/
  /temp/              ← processing folder

/Unpublished/
  /Articles/
    /[category]/
      *.md (article stubs)
  /Images/
    /[category]/
    /temp/
```