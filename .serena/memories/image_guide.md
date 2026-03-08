# IMAGE GUIDE — NIHIL.RO

## Visual Identity

All images must have a **continuous, unified look** for brand consistency.

### Color Palette
| Property | Value |
|----------|-------|
| Primary tones | Warm, earthy |
| Palette match | Site colors (`--terra` #c4522a, `--crem` #f5f0e0, `--negru` #1a1710) |
| Saturation | Slightly desaturated |
| Feel | Film-like, organic |

### Style
| Property | Value |
|----------|-------|
| Aesthetic | Editorial / documentary |
| Mood | Real, unposed, authentic |
| Texture | Subtle film grain |
| Drama | Subtle, not over-processed |

### Technical Specs
| Property | Value |
|----------|-------|
| Hero image ratio | 16:9 or 4:3 |
| In-article images | 4:3 or 3:2 |
| Max file size | ~150-300KB (optimized) |
| Format | WebP preferred, JPG fallback |

### Images Per Article: 3-4
- 1 Hero image (top of article)
- 2-3 In-article images (throughout content)

---

## Naming Convention
```
[article-slug]-[number].jpg

Examples:
- coober-pedy-orasul-subteran-1.jpg
- coober-pedy-orasul-subteran-2.jpg
- alan-turing-geniul-care-a-salvat-lumea-1.jpg
```

---

## Prompt Template (Gemini Nano Banana 2)
```
[SUBJECT], warm earthy tones, editorial documentary photography style, slightly desaturated sepia colors, film grain texture, dramatic lighting, no borders, full frame, [ASPECT RATIO]
```

### Aspect Ratios
- Hero images: 16:9
- In-article images: 4:3

---

## Category-Specific Modifiers

| Category | Focus |
|----------|-------|
| CIUDĂȚENII | Mysterious, slightly unsettling |
| LUME LARGĂ | Expansive, cultural, atmospheric |
| OAMENI REMARCABILI | Portrait-style, human, intimate |
| CULTURĂ | Cultural artifacts, scenes, abstract |
| OBSESII | Psychological, abstract, moody |
| STIL & DESIGN | Clean, architectural, aesthetic |
| ROMÂNIA NEȘTIUTĂ | Landscape, historical, authentic Romanian |

---

## Workflow (Gemini via Browser)

1. Navigate to gemini.google.com
2. Type prompt with "Generate an image of..."
3. Download generated image
4. Copy to project: `Copy-Item [temp_path] "X:\Website\Utils\nihil.ro\images\[article-slug]-[n].jpg"`
5. Remove watermark using GeminiWatermarkTool

---

## Search Terms by Article (64 articles)

### CIUDĂȚENII (10)
| Article | Search Terms |
|---------|--------------|
| breb-satul-traditiilor-vesele | Maramures village, wooden church Romania, Romanian peasant costume |
| holi-sarbatoarea-culorilor | Holi festival colors, colored powder throwing, Indian celebration |
| lamu-island-insula-magarilor | Lamu Island Kenya, donkey transport, Swahili architecture |
| legenda-orfelinatului-din-centrul-vechi | old Bucharest street, abandoned building Romania |
| misterele-muntilor-buzauului | Buzau mountains, mysterious forest, strange rock formations |
| muntele-kailash | Mount Kailash Tibet, sacred mountain, Himalayan pilgrimage |
| okinawa-insula-fericirii | Okinawa island Japan, Japanese elderly, subtropical island |
| papua-noua-guinee-tara-limbilor | Papua New Guinea tribes, tribal face paint, indigenous people |
| todmorden-orasul-gradinilor | community garden urban, vegetable garden town, urban farming |
| toronto-islands-comunitate-fara-masini | Toronto Islands, car-free community, island ferry |

### LUME LARGĂ (12)
| Article | Search Terms |
|---------|--------------|
| coober-pedy-orasul-subteran | underground house Australia, opal gemstone, Australian outback |
| hikikomori-retragerea-sociala-din-japonia | Japanese small room, young person alone, Tokyo apartment |
| holi-festivalul-culorilor | Holi festival India, colored powder celebration |
| idyllwild-orasul-cainilor | small mountain town USA, dog in town, American forest village |
| insula-pastelui-moai-si-secretul-rapa-nui | Easter Island moai, ancient stone heads, Polynesian statues |
| la-tomatina-festivalul-luptei-cu-rosiile | La Tomatina Spain, tomato fight crowd, Spanish festival |
| lamu-insula-magarilor | Lamu Island Kenya, donkey transport, Swahili old town |
| longyearbyen-cel-mai-nordic-oras | Arctic town snow, northern lights, polar settlement |
| mackinac-island-insula-fara-masini | Mackinac Island, horse carriage, Victorian island town |
| monhegan-refugiul-artistilor | artist retreat, rocky island coast, painter at easel |
| savonlinna-campionatul-mondial-de-aruncat-telefoane | phone throwing contest, Finnish festival |
| toronto-islands-comunitatea-urbana-fara-masini | Toronto Islands, car-free neighborhood, Lake Ontario |

### OAMENI REMARCABILI (10)
| Article | Search Terms |
|---------|--------------|
| alan-turing-geniul-care-a-salvat-lumea | Alan Turing portrait, Enigma machine, Bletchley Park |
| frida-kahlo-artista-care-a-ales-durerea | Frida Kahlo portrait, Mexican artist studio |
| mahatma-gandhi-liderul-care-a-ales-nonviolenta | Mahatma Gandhi, Indian independence, spinning wheel |
| malala-yousafzai-activista-care-a-ales-educatia | Malala Yousafzai, girls education, young activist |
| marie-curie-femeia-care-a-ales-radiatia | Marie Curie portrait, vintage laboratory, woman scientist |
| mother-teresa-sfanta-care-a-ales-saracii | Mother Teresa, helping poor, Calcutta streets |
| nikola-tesla-geniul-care-a-ales-visele | Nikola Tesla portrait, Tesla coil, electrical laboratory |
| rosalind-franklin-femeia-care-a-descoperit-adn-ul | Rosalind Franklin, DNA X-ray crystallography |
| stephen-hawking-geniul-care-a-ales-viata | Stephen Hawking, wheelchair scientist, Cambridge |
| william-sidis-geniul-care-a-ales-sa-dispara | child prodigy, vintage newspaper, old books |

### CULTURĂ (10)
| Article | Search Terms |
|---------|--------------|
| algoritm-si-recomandare-ai-ul-a-schimbat-ce-consumam | Netflix recommendation screen, algorithm visualization |
| gaming-si-esports-jocurile-au-devenit-cultura-principala | esports arena, gaming competition, professional gamers |
| instagram-si-estetica-filtrele-au-redefinit-realitatea | Instagram interface, photo filters, smartphone photography |
| meme-uri-si-cultura-o-imagine-poate-schimba-lumea | internet meme, viral image, social media trend |
| netflix-si-streaming-serialul-a-devinit-epoca-noastra | Netflix screen, binge watching, streaming TV |
| podcasting-audio-a-redescoperit-povestirea | podcast microphone, recording studio, audio equipment |
| streaming-si-muzica-accesul-infinit-a-schimbat-valoarea | Spotify interface, music streaming, vinyl records |
| tiktok-si-gen-z-15-secunde-au-redefinit-cultura | TikTok interface, smartphone video, short video |
| twitter-si-conversatia-280-caractere-au-schimbat-discursul | Twitter interface, social media conversation |
| youtube-si-crearea-oricine-poate-crea-cultura | YouTube creator, video production, content creator |

### OBSESII (5)
| Article | Search Terms |
|---------|--------------|
| fomo-frica-de-a-nu-rata-nimic | smartphone anxiety, social media checking, notification overload |
| perfectiunism-cand-perfect-devine-periculos | perfectionism obsession, detailed work, obsessive organizing |
| procrastinare-de-ce-amanam-totul-pentru-maine | procrastination, clock time pressure, deadline stress |
| rutina-si-compulsie-cand-normal-devine-automat | repetitive behavior, daily routine, automatic habit |
| verificarea-constanta-cand-nu-poti-sa-te-opresti-din-verificat | phone checking, compulsive behavior, notification |

### STIL & DESIGN (5)
| Article | Search Terms |
|---------|--------------|
| art-deco-frumusetea-in-geometrie-si-lux | Art Deco building, geometric architecture, 1920s luxury |
| brutalism-frumusetea-in-beton-brut | brutalist architecture, concrete building, raw concrete |
| minimalism-mai-putin-inseamna-mai-mult | minimalist interior, empty clean room, simple living |
| modernism-frumusetea-in-simplicitate-moderna | modernist design, Bauhaus building, mid-century modern |
| scandinavian-design-frumusetea-in-simplicitate-functionala | Scandinavian interior, Nordic design, hygge living room |

### ROMÂNIA NEȘTIUTĂ (10)
| Article | Search Terms |
|---------|--------------|
| alun-satul-de-marmura | Romanian village abandoned, white marble quarry, Carpathian |
| bicfalau-satul-cu-case-traditionale | traditional Romanian houses, wooden porch, rural Transylvania |
| biserica-din-pustietate-lacasul-misterios | remote Romanian church, forest clearing, orthodox church |
| criseni-muzeul-palariilor-de-paie | straw hat making, Romanian craft, traditional workshop |
| manastirea-carta-cea-mai-estica-abatie-cisterciana | Cistercian abbey, medieval monastery Romania, gothic ruins |
| pestera-ascunsa-miracolul-sculpturii-in-calcar | limestone cave, cave formations, Romanian wilderness |
| poiana-ponor-poiana-misterioasa | karst valley, mysterious clearing, Apuseni mountains |
| rapa-rosie-micul-canion-al-romaniei | red canyon Romania, rock formations, Sebes mountains |
| sic-delta-transilvaniei | reed bed wetland, delta birds, Transylvanian nature |
| sinca-veche-templul-ursitelor | ancient rock church, cave temple, Fagaras mountains |

### ADDITIONAL (2)
| Article | Search Terms |
|---------|--------------|
| haida-gwaii | Haida Gwaii islands, Pacific Northwest, totem poles |
| orasul-unde-e-ilegal-sa-mori | Arctic town, Norwegian settlement, Longyearbyen |
