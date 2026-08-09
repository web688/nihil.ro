# ARTICLE CREATION — NIHIL.RO (A to Z)

## STEP 1: Choose Category & Topic

### 1.1 Check Existing Articles
**ALWAYS first check `inventory` memory** to ensure topic doesn't already exist.

```
read_memory → inventory
```

Search for:
- Same topic (different filename = duplicate)
- Similar topic (same person/place/event)

### 1.2 Categories & Personas
| Category | Persona | Word Count |
|----------|---------|------------|
| CIUDĂȚENII | Radu Merca | 800-1500 |
| LUME LARGĂ | Ioana Flondor | 1000-1800 |
| OAMENI REMARCABILI | Cristina Dobre | 1200-2000 |
| CULTURĂ | Andrei Lazăr | 900-1600 |
| OBSESII | Alex Popa | 900-1500 |
| STIL & DESIGN | Mara Ioniță | 800-1400 |
| ROMÂNIA NEȘTIUTĂ | Vlad Cornea | 1000-1800 |

### 1.3 Topic Sources
- `subiecte.md` — available topics
- User request
- Must be verifiable, interesting, not common knowledge

---

## STEP 2: Research (Collect Facts, Don't Improvise)

### 2.1 Use Web Search
```
web_search → [topic] facts
web_search → [topic] history
web_search → [topic] statistics
```

### 2.2 Collect Specific Details
| Type | Examples |
|------|----------|
| Numbers | population, year, temperature, distance, percentage |
| Names | people, places, organizations |
| Dates | founded, discovered, happened |
| Locations | country, city, coordinates |
| Contradictions | common belief vs reality |

### 2.3 Fact Sheet Template
Before writing, fill this out:

```
TOPIC: _______________
CATEGORY: _______________

KEY FACTS:
- Fact 1: [specific number/detail]
- Fact 2: [specific number/detail]
- Fact 3: [specific number/detail]
- Fact 4: [specific number/detail]
- Fact 5: [specific number/detail]

UNIQUE ANGLE:
- What makes this interesting: _______________
- What most people don't know: _______________
- Contradiction/surprise: _______________

QUOTABLE DETAILS:
- [Specific detail that can be emphasized]
- [Another specific detail]

IMAGE SUBJECTS (for generation):
- Subject 1: [use proper names from article, e.g., "Alan Turing"]
- Subject 2: [specific location/object/person]
- Subject 3: [specific location/object/person]
```

### 2.4 Verify
- Cross-check facts with multiple sources
- No speculation, no "probably", no guessing
- If uncertain, either verify or omit

---

## STEP 3: Write (Following Persona)

### 3.1 Structure
1. **Hook** — surprising opening that grabs attention (use a specific fact)
2. **Context** — background information (when, where, who)
3. **Deep dive** — the core story/details (use collected facts)
4. **Twist/Insight** — unexpected angle (the contradiction you found)
5. **Closing** — resonant ending

### 3.2 Critical Rules
- **NO REPETITIVE PHRASES** — check `style_guide` memory
- **USE COLLECTED FACTS** — not improvisation
- **SPECIFIC > VAGUE** — "50 de grade" not "foarte cald"

### 3.3 Persona Tones

**Radu Merca (CIUDĂȚENII):** Curios, misterios, științific
**Ioana Flondor (LUME LARGĂ):** Deschis, imersiv, senzorial
**Cristina Dobre (OAMENI REMARCABILI):** Empatic, profund, uman
**Andrei Lazăr (CULTURĂ):** Analitic, explicativ
**Alex Popa (OBSESII):** Empatic, "și eu am fost acolo"
**Mara Ioniță (STIL & DESIGN):** Observațional, estetic
**Vlad Cornea (ROMÂNIA NEȘTIUTĂ):** Mândru dar critic

---

## STEP 4: Create HTML File

### 4.1 File Naming
```
[topic-name-in-romanian].html
Example: coober-pedy-orasul-subteran.html
```

### 4.2 Save Location
```
D:\Websites\nihil.ro\articole\[category]\[filename].html
```

**Category folder names:**
| Category | Folder |
|----------|--------|
| CIUDĂȚENII | `ciudatenii` |
| LUME LARGĂ | `lume-larga` |
| OAMENI REMARCABILI | `oameni-remarcabili` |
| CULTURĂ | `cultura` |
| OBSESII | `obsesii` |
| STIL & DESIGN | `stil-design` |
| ROMÂNIA NEȘTIUTĂ | `romania-nesțiuta` |

### 4.3 Check Persona File
Each category folder has a `persona.md` file with the writer's style:
```
D:\Websites\nihil.ro\articole\[category]\persona.md
```

### 4.4 Copy CSS from existing article template

---

## STEP 5: Generate Images (3-4 per article)

### 5.1 How to Choose Image Subjects

**Extract main ideas from the article and match to image types:**

| Article Section | Image Type | What to Show |
|-----------------|------------|--------------|
| Opening/Hook | Hero (16:9) | The setting, location, or main subject that establishes context |
| Key fact #1 | In-article (4:3) | Visual representation of first major detail |
| Key fact #2 | In-article (4:3) | Visual representation of second major detail |
| Closing/Twist | Optional | The contrast, surprise, or aftermath |

**Process:**
1. Read the article and identify 3-4 key moments/ideas
2. For each moment, ask: "What visual would help the reader understand/feel this?"
3. Use proper names from the article in prompts

**Example: Alan Turing article**

| Paragraph Content | Key Idea | Image Subject |
|-------------------|----------|---------------|
| Opening about his genius | Who is he? | Portrait of Alan Turing |
| Enigma machine work | What did he do? | Enigma machine / codebreaking |
| Bletchley Park | Where did it happen? | Bletchley Park office |

**Example: Coober Pedy article**

| Paragraph Content | Key Idea | Image Subject |
|-------------------|----------|---------------|
| Australian desert setting | Where is it? | Australian outback landscape |
| Underground living | How do they live? | Underground house interior |
| Opal mining | Why is it famous? | Opal gemstone |

### 5.2 Image Types
| # | Type | Aspect Ratio | Placement |
|---|------|--------------|-----------|
| 1 | Hero | 16:9 | Top of article, before text |
| 2 | In-article | 4:3 | After paragraph 3-4 |
| 3 | In-article | 4:3 | After paragraph 6-7 |
| 4 | Optional | 4:3 | Near the end |

### 5.3 Naming & Location
```
D:\Websites\nihil.ro\images\[category]\[article-slug]-1.jpg
D:\Websites\nihil.ro\images\[category]\[article-slug]-2.jpg
D:\Websites\nihil.ro\images\[category]\[article-slug]-3.jpg
```

**Image folder structure:**
```
/images/
  /ciudatenii/
  /lume-larga/
  /oameni-remarcabili/
  /cultura/
  /obsesii/
  /stil-design/
  /romania-nesțiuta/
  /temp/          ← processing folder (watermark removal, resize)
```

### 5.4 Prompt Template
**CRITICAL: Use proper names from the article**

```
Generate an image of [SPECIFIC NAME from article, e.g., "Alan Turing"], [additional context], in the style of editorial documentary photography, warm earthy tones, slightly desaturated sepia colors, film grain texture, dramatic lighting, no borders, full frame, [16:9 or 4:3] aspect ratio
```

### Prompt Technique: Use Article Subject as Style Reference

**If article is about X, use "in the style of X" in the prompt:**

| Article Topic | Prompt Example |
|---------------|----------------|
| Niagara Falls | "Generate a waterfall image in the style of Niagara Falls..." |
| Coober Pedy | "Generate an underground house in the style of Coober Pedy Australian outback..." |
| Alan Turing | "Generate a portrait in the style of Alan Turing 1940s Bletchley Park..." |
| Mount Kailash | "Generate a mountain landscape in the style of Mount Kailash Tibet..." |

**Template:**
```
Generate [image description] in the style of [ARTICLE SUBJECT], warm earthy tones, editorial documentary photography style, slightly desaturated sepia colors, film grain texture, dramatic lighting, no borders, full frame, [16:9 or 4:3] aspect ratio
```

**Why this works:** Using the article's subject as a style reference helps the AI generate accurate, relevant imagery that matches the topic.

### 5.4 Workflow — OPTIMIZE FIRST for Speed

**Key principle:** Resize images BEFORE de-watermarking for 8x faster processing.

| Resolution | De-watermark Time | Speedup |
|------------|-------------------|---------|
| 4000x3000 (original) | ~120s | 1x |
| 1600x1200 (optimized) | ~15s | **8x faster** |

**Workflow Steps:**

1. Navigate to gemini.google.com
2. Generate with prompt using proper names
3. Download to temp folder
4. **⚡ OPTIMIZE FIRST** — resize to web size (1600px, quality 90)
5. Remove Gemini watermark using `remove_watermark` tool
6. Remove invisible watermark using `noai-watermark` tool
7. Final optimize (quality 80) and move to category folder

### 5.5 Image Optimization

**Two optimization passes:**

| Pass | When | Settings | Purpose |
|------|------|----------|---------|
| **Pass 1** | BEFORE de-watermark | width=1600, quality=90 | Shrink for faster processing |
| **Pass 2** | AFTER de-watermark | quality=80 | Final compression for web |

**MCP Tools:**
- `optimize_image` — single image
- `batch_optimize` — multiple images at once

**Batch Processing (recommended):**

1. Generate all 3 images for an article
2. Optimize all at once (Pass 1)
3. Run Gemini watermark removal on all
4. Run invisible watermark removal on all
5. Final optimize (Pass 2) and move to category folder

**MCP Config:**
```json
{
  "mcpServers": {
    "image-optimizer": {
      "command": "npx",
      "args": ["mcp-image-optimizer"]
    }
  }
}
```

**Watermark removal (CLI with CUDA):**
```powershell
# Gemini watermark
& "D:\Websites\nihil.ro\GeminiWatermarkTool.exe" -input [file] -output [file-clean]

# Invisible watermark (noai)
& "D:\Websites\MCP\Images\watermark-remover\watermark_remover\venv\Scripts\noai-watermark.exe" [file] -o [output] --strength 0.04 --device cuda
```

**MCP watermark tools:**
- `gemini-watermark` → `remove_watermark`, `batch_remove_watermarks`
- `noai-watermark` → `remove_invisible_watermark`, `batch_remove_invisible_watermarks`

---

## STEP 6: Insert Images in Article HTML

### 6.1 Hero Image (after subtitle, before content)
```html
<img src="../../images/[category]/[article-slug]-1.jpg" alt="[Description]" class="hero-image">
```

### 6.2 In-Article Images (between paragraphs)
```html
<p>[paragraph text]</p>

<figure class="article-image">
    <img src="../../images/[category]/[article-slug]-2.jpg" alt="[Description]">
</figure>

<p>[next paragraph]</p>
```

**Path explanation:**
- Article is in `/articole/[category]/`
- Image is in `/images/[category]/`
- So path from article to image: `../../images/[category]/`

### 6.3 CSS for Images (add to article style)
```css
.hero-image {
    width: 100%;
    height: auto;
    margin-bottom: 2rem;
    border-radius: 2px;
}

.article-image {
    margin: 2rem 0;
}

.article-image img {
    width: 100%;
    height: auto;
    border-radius: 2px;
}
```

---

## STEP 7: Link from Category Page

### 7.1 Open Category File
```
D:\Websites\nihil.ro\[category].html
```

### 7.2 Add Article Card
Copy existing card structure, modify:
- Title, subtitle, image path, link, author

---

## STEP 8: Update Inventory Memory

Add new article to `inventory` memory under correct category.

---

## STEP 9: Publish (Git)

### 9.1 Stage Changes
```powershell
git status
git add .
```

### 9.2 Commit
```powershell
git commit -m "Add [article-name] article"
```

### 9.3 Push
```powershell
git push
```

### 9.4 Verify
Check https://nihil.ro/articole/[category]/[filename].html

---

## FINAL CHECKLIST

- [ ] Checked `inventory` memory — topic doesn't exist
- [ ] Researched and collected specific facts
- [ ] Fact sheet filled with verifiable details
- [ ] Image subjects identified with proper names
- [ ] Article follows persona tone
- [ ] No repetitive phrases
- [ ] 8-10 paragraphs with specific numbers/facts
- [ ] HTML file created in `/articole/[category]/`
- [ ] 3-4 images generated using proper names + "in the style of..."
- [ ] Images saved to `/images/temp/`
- [ ] **⚡ OPTIMIZE FIRST** — resize to 1600px (quality 90)
- [ ] Gemini watermarks removed
- [ ] Invisible watermarks removed (noai-watermark with CUDA)
- [ ] Final optimize (quality 80)
- [ ] Images moved to `/images/[category]/`
- [ ] Images inserted in article HTML with correct paths `../../images/[category]/`
- [ ] Article linked from category page
- [ ] `inventory` memory updated
- [ ] Committed and pushed to git
- [ ] Verified on live site
