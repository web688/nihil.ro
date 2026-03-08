# NIHIL.RO Site Update Plan

## OVERVIEW

| Priority | Task | Count | Status |
|----------|------|-------|--------|
| HIGH | Generate images for articles | 47 needed | In Progress |
| HIGH | Fix broken links on category pages | 10 links | Pending |
| MEDIUM | Resolve duplicate articles | 5 pairs | Pending |
| MEDIUM | Write new articles (România Neștiută) | 9 articles | Pending |
| LOW | Replace placeholder on index.html hero | 1 | Pending |
| LOW | Remove watermarks from images | As needed | User handles |

---

## PHASE 1: IMAGES (In Progress)

### Completed
| Article | Images | Status |
|---------|--------|--------|
| Coober Pedy | australia.jpg (user) | ✅ |
| Coober Pedy | coober-pedy-underground.jpg | ✅ |
| Coober Pedy | coober-pedy-opal.jpg | ✅ |
| Alan Turing | alan.jpg (user) | ✅ |

### Remaining for Proof of Concept (2 articles)
| Article | Need | Status |
|---------|------|--------|
| Coober Pedy | 1 more image | Pending |
| Alan Turing | 3 more images | Pending |

### Full Image List
- **Total articles:** 68
- **Current images:** ~25
- **Needed:** ~200+ (3-4 per article)

---

## PHASE 2: BROKEN LINKS

### stil-design.html
- **Issue:** 6 placeholder articles with `href="#"`
- **Fix:** Link to existing 5 articles in `/articole/`:
  - art-deco-frumusetea-in-geometrie-si-lux.html
  - brutalism-frumusetea-in-beton-brut.html
  - minimalism-mai-putin-inseamna-mai-mult.html
  - modernism-frumusetea-in-simplicitate-moderna.html
  - scandinavian-design-frumusetea-in-simplicitate-functionala.html

### romania-neștiută.html
- **Issue:** 6 placeholder articles + 3 special cards with `href="#"`
- **Fix Option A:** Link to existing 10 articles
- **Fix Option B:** Write 9 new articles for placeholder topics

### Other pages (featured articles)
- lume-larga.html: 1 broken link
- oameni-remarcabili.html: 1 broken link
- cultura.html: 1 broken link
- obsesii.html: 1 broken link

---

## PHASE 3: DUPLICATE ARTICLES

| Duplicate Pair | Action |
|----------------|--------|
| holi-festivalul-culorilor.html ↔ holi-sarbatoarea-culorilor.html | Merge/Keep best |
| lamu-insula-magarilor.html ↔ lamu-island-insula-magarilor.html | Merge/Keep best |
| insula-pastelui.html ↔ insula-pastelui-moai-si-secretul-rapa-nui.html | Merge/Keep best |
| toronto-islands-comunitate-fara-masini.html ↔ toronto-islands-comunitatea-urbana-fara-masini.html | Merge/Keep best |
| william-sidis.html ↔ william-sidis-geniul-care-a-ales-sa-dispara.html | Merge/Keep best |

---

## PHASE 4: NEW CONTENT

### România Neștiută (9 new articles needed)
| # | Topic | Location |
|---|-------|----------|
| 1 | Cimitirul Vesel | Săpânța |
| 2 | Marea Neagră (lac isolated) | Constanța |
| 3 | Vulcanii noroioși | Buzău |
| 4 | Sarmizegetusa Regia | Hunedoara |
| 5 | Topolnița Cave | Mehedinți |
| 6 | Poienari Fortress | Argeș |
| 7 | Călușarii (tradition) | - |
| 8 | Sfinxul din Bucegi | Bucegi |
| 9 | Penicilina (Romanian invention) | - |

---

## PHASE 5: FINAL CHECKS

1. Test navigation on all pages
2. Verify images load correctly
3. Check all article links work
4. Run frontend-tester agent
5. Commit changes to git

---

## IMMEDIATE NEXT STEPS

1. **Continue image generation** with Nano Banana 2
   - Finish Coober Pedy (1 more)
   - Finish Alan Turing (3 more)
   - User removes watermarks

2. **Fix broken links** on category pages
   - stil-design.html (link 5 existing articles)
   - romania-neștiută.html (decide: link existing or write new)

3. **Resolve duplicates** (merge or delete)

---

*Plan created: 2026-03-08*
