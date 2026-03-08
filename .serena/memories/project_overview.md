# NIHIL.RO — Project Overview

## Concept
"Curiozitatea ca act de supraviețuire"

Un anti-portal românesc despre tot ce merită să existe. Nu știri serioase, nu breaking news — ci un amalgam de ciudățenii verificate din toată lumea, povești despre oameni remarcabili, fapte care te dezechilibrează și motive concrete să nu lași viața să treacă pe lângă tine.

## Publicul țintă
Român, 25–45 ani, consumator de conținut de calitate, obosit de feed-uri identice.

## Tone of Voice
Cald, inteligent, ușor ironic. Nu moralizator. Vorbește ca un prieten bine citit care tocmai s-a întors dintr-o călătorie lungă și are lucruri de povestit.

## Tagline
"Nu e nimic de văzut aici. Ba e. E tot."

---

## Tech Stack
- Static HTML/CSS website
- No build system
- Hosted on GitHub Pages (nihil.ro)
- Python file (main.py) for Serena activation only

---

## Estetică vizuală
- Fond: crem/galben pai (#f5f0e0) — hârtie de ziar vechi
- Accent: portocaliu ars/terra cotta (#c4522a)
- Text: negru organic (#1a1710)
- Tipografie: Playfair Display (titluri), Unbounded/Spectral (corp)
- Vibe: cabinet de curiozități digital · ziar de epocă reinventat

---

## Categories & Personas

| Category | Persona | Tone |
|----------|---------|------|
| CIUDĂȚENII | Radu Merca | Curios, misterios, științific dar accesibil |
| LUME LARGĂ | Ioana Flondor | Deschis, imersiv, senzorial |
| OAMENI REMARCABILI | Cristina Dobre | Empatic, profund, uman |
| CULTURĂ | Andrei Lazăr | Analitic, explicativ, nu judecător |
| OBSESII | Alex Popa | Empatic, "și eu am fost acolo" |
| STIL & DESIGN | Mara Ioniță | Observațional, estetic, tehnic dar poetic |
| ROMÂNIA NEȘTIUTĂ | Vlad Cornea | Mândru dar critic, fascinat dar onest |

---

## Site Structure

### Main Pages
- `index.html` — AZI (homepage)
- `ciudatenii.html` — Fenomene inexplicabile
- `fa-asta-azi.html` — Acțiuni concrete zilnice
- `fapte.html` — Fapte științifice fascinante
- `lume-larga.html` — Locuri și culturi unice
- `romania-neștiută.html` — Locuri ascunse din România
- `oameni-remarcabili.html` — Portrete umane
- `cultura.html` — Fenomene culturale
- `stil-design.html` — Estetică și design
- `obsesii.html` — Comportamente obsesive

### Content
- Articles: `/articole/*.html` (68 total)
- Images: `/images/`
- Writers: `personas.md`

---

## Statistics

| Metric | Count |
|--------|-------|
| Total articles | 68 |
| Categories | 8 |
| Writers/Personas | 7 |
| Images needed | ~200+ |
| Duplicate pairs | 5 |

---

## Duplicate Articles (5 pairs to resolve)

1. holi-festivalul-culorilor.html ↔ holi-sarbatoarea-culorilor.html
2. lamu-insula-magarilor.html ↔ lamu-island-insula-magarilor.html
3. insula-pastelui.html ↔ insula-pastelui-moai-si-secretul-rapa-nui.html
4. toronto-islands-comunitate-fara-masini.html ↔ toronto-islands-comunitatea-urbana-fara-masini.html
5. william-sidis.html ↔ william-sidis-geniul-care-a-ales-sa-dispara.html

---

## File Naming
- Articles: `article-name-in-romanian.html`
- Images: `article-slug-1.jpg`, `article-slug-2.jpg` (matching article slug)
