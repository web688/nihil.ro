# Nano Banana Image Generation Guide

## Overview
Google AI Studio's **Nano Banana** (gemini-2.5-flash-image) generates images for NIHIL.RO articles. Free tier available.

## Quick Start

### 1. Navigate to AI Studio
```
https://aistudio.google.com/
```

### 2. Login with Google account

### 3. Playground → Image Generation → Nano Banana

### 4. Enter prompt and Run

### 5. Download and save to `/images/`

---

## NIHIL.RO Visual Style

Consistent aesthetic matching site's warm, earthy palette (`--terra`, `--crem`):

```
[Subject description], warm earthy tones, slightly desaturated, editorial documentary photography style, cinematic lighting, film grain texture, [aspect ratio]
```

### Aspect Ratios
- **Hero images**: 16:9
- **In-article**: 4:3

---

## Prompt Examples

### Places (Coober Pedy)
```
Underground house interior in Australian outback desert, dug into red sandstone rock, warm earthy tones, cozy living space carved into rock, editorial documentary photography style, cinematic lighting, 16:9
```

### Objects (Opal)
```
Australian opal gemstone close-up, vibrant rainbow colors, play of light, blue and green flashes, white opal on dark background, macro photography, dramatic lighting, 4:3
```

### Historical Figures (Alan Turing)
```
Alan Turing working on Bombe machine at Bletchley Park, 1940s, cinematic black and white, dramatic lighting, editorial documentary style, 16:9
```

---

## Model Comparison

| Model | Tier | Quality | Speed |
|-------|------|---------|-------|
| Nano Banana | Free | Good | Fast |
| Nano Banana Pro | Paid | Better | Fast |
| Nano Banana 2 | Paid | Best | Fast |

---

## File Naming

```
[article-slug]-[description].jpg

Examples:
- coober-pedy-underground.jpg
- coober-pedy-opal.jpg
- alan-turing-portrait.jpg
```

---

## Automation via Playwright MCP

```javascript
// Navigate
await page.goto('https://aistudio.google.com/');

// Select model
await page.getByRole('button', { name: 'Image Generation' }).click();
await page.getByRole('button', { name: 'Nano Banana' }).click();

// Generate
await page.getByRole('textbox', { name: 'Enter a prompt' }).fill('...');
await page.getByRole('button', { name: 'Run' }).click();

// Download
await page.getByRole('img').click();
await page.getByRole('button', { name: 'Download' }).click();
```

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| "No API Key" warning | Ignore - works on free tier |
| Image not generating | Simplify prompt, avoid policy violations |
| Wrong aspect ratio | Specify in prompt or use settings |
| Low quality | Try Nano Banana Pro (paid) |

---

## Resources

- [Google AI Studio](https://aistudio.google.com/)
- [Imagen Documentation](https://ai.google.dev/gemini-api/docs/imagen)
- [Playwright MCP](https://playwright.dev/docs/auth)

---

*Last updated: March 2026*
