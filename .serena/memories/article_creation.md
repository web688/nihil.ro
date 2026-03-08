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
X:\Website\Utils\nihil.ro\articole\[filename].html
```

### 4.3 Copy CSS from existing article template

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

### 5.3 Naming Convention
```
[article-slug]-1.jpg
[article-slug]-2.jpg
[article-slug]-3.jpg
```

### 5.3 Prompt Template
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

### 5.4 Workflow
1. Navigate to gemini.google.com
2. Generate with prompt using proper names
3. Download
4. Copy to `images/` folder
5. Remove watermark using `remove_watermark` tool from gemini-watermark MCP

### 5.5 Image Optimization
**ALWAYS optimize before upload:**

| Target | Value |
|--------|-------|
| Max file size | 150-300KB |
| Max dimensions | 1920px width (hero), 1200px (in-article) |
| Format | JPG (quality 80-85%) |

**Optimization via MCP image-optimizer:**

Once configured in MCP settings, use:
- `optimize_image` — single image with width, quality, format
- `batch_optimize` — multiple images at once
- `auto_crop` — remove borders/whitespace

**Example:**
```
optimize_image input="images/article-1.jpg" output="images/article-1.jpg" width=1600 quality=80 format="jpeg"
```

**MCP Config:**
```json
{
  "mcpServers": {
    "image-optimizer": {
      "command": "npx",
      "args": ["mcp-image-optimizer"]
    },
    "gemini-watermark": {
      "command": "python",
      "args": ["X:\\Website\\ClaudeCode\\Remove gemini logo\\server.py"]
    }
  }
}
```

**Watermark removal tools:**
- `check_binary` — verify binary is available
- `remove_watermark` — remove watermark from single image
- `batch_remove_watermarks` — remove from all images in directory

---

## STEP 6: Insert Images in Article HTML

### 6.1 Hero Image (after subtitle, before content)
```html
<img src="../images/[article-slug]-1.jpg" alt="[Description]" class="hero-image">
```

### 6.2 In-Article Images (between paragraphs)
```html
<p>[paragraph text]</p>

<figure class="article-image">
    <img src="../images/[article-slug]-2.jpg" alt="[Description]">
</figure>

<p>[next paragraph]</p>
```

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
X:\Website\Utils\nihil.ro\[category].html
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
Check https://nihil.ro/articole/[filename].html

---

## FINAL CHECKLIST

- [ ] Checked `inventory` memory — topic doesn't exist
- [ ] Researched and collected specific facts
- [ ] Fact sheet filled with verifiable details
- [ ] Image subjects identified with proper names
- [ ] Article follows persona tone
- [ ] No repetitive phrases
- [ ] 8-10 paragraphs with specific numbers/facts
- [ ] HTML file created in `/articole/`
- [ ] 3-4 images generated using proper names + "in the style of..."
- [ ] Images optimized (150-300KB, max 1920px)
- [ ] Images inserted in article HTML
- [ ] Watermarks removed from images
- [ ] Article linked from category page
- [ ] `inventory` memory updated
- [ ] Committed and pushed to git
- [ ] Verified on live site
