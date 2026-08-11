# NIHIL.RO — Workflow editorial universal

## Scop

Acest workflow poate fi executat de orice AI care poate citi proiectul, documenta și scrie text, genera sau coordona imagini, modifica fișiere și verifica rezultatul. Niciun pas nu depinde de numele unui model.

Fluxul are două praguri umane obligatorii:

1. aprobarea subiectului înainte de redactare și imagini;
2. mesajul `PUBLICĂ` înainte de integrarea în rubricile site-ului.

Între aceste două praguri, AI-ul execută singur munca tehnică și editorială. Utilizatorul nu copiază prompturi între instrumente și nu administrează fișierele.

---

# 1. CEREREA INIȚIALĂ

Utilizatorul poate cere, de exemplu:

> Propune următorul articol NIHIL.RO.

> Propune următorul articol pentru rubrica FAPTE.

> Scrie un articol pentru CIUDĂȚENII despre [SUBIECT].

Dacă cererea conține comanda clară de a scrie despre un subiect precis, subiectul este aprobat. Dacă subiectul lipsește, AI-ul trebuie să îl propună și să aștepte aprobarea înainte de a continua.

---

# 2. CITIREA PROIECTULUI

Înainte de a propune o idee, AI-ul citește:

1. `AGENTS.md`;
2. `index.html`;
3. pagina rubricii vizate;
4. articolele recente din acea rubrică;
5. `personas.md`;
6. `subiecte.md` ca listă neobligatorie.

AI-ul inventariază subiectele, unghiurile și imaginile recente și caută ce lipsește, nu doar ce apare într-o listă.

---

# 3. FILTRUL DE NIȘĂ

AI-ul generează intern minimum trei idei și le testează astfel:

1. Există un fapt, o contradicție sau o perspectivă care produce reacția „stai, ce?”?
2. Motivul principal de interes este curiozitatea, nu doar importanța, tragedia, actualitatea sau utilitatea civică?
3. Subiectul este diferit de materialele recente ale rubricii?
4. Poate susține trei imagini distincte și relevante?
5. Ar suna firesc pe NIHIL.RO și nefiresc pe un portal generalist?

O idee care nu trece filtrul este eliminată chiar dacă apare în `subiecte.md`.

AI-ul prezintă o singură recomandare bine aleasă, în format scurt:

- rubrica;
- titlul de lucru;
- ideea surprinzătoare centrală;
- de ce aparține nișei NIHIL.RO;
- cele trei direcții vizuale posibile.

AI-ul nu scrie articolul și nu generează imaginile până la aprobarea utilizatorului. Dacă ideea este respinsă, propune următoarea idee, fără a produce material inutil.

---

# 4. PACHETUL ARTICOLULUI APROBAT

După aprobarea subiectului, AI-ul:

1. identifică persona și semnătura rubricii;
2. stabilește unghiul exact și ideea memorabilă;
3. documentează afirmațiile importante;
4. scrie articolul în lungimea și ritmul rubricii;
5. elimină pasajele generice, moralizatoare sau specifice unui portal generalist;
6. pregătește exact trei prompturi de imagine;
7. construiește pagina completă de test.

Autorul textului poate fi orice AI. Numele modelului nu apare în articol și nu schimbă regulile editoriale.

## Sursele

AI-ul verifică faptele și păstrează sursele în notele sale de lucru. Nu adaugă automat în articol:

- casetă „Surse”;
- bibliografie;
- notă metodologică;
- explicație că persona este fictivă;
- etichetă că imaginile sunt generate sau reconstituite.

Oricare dintre aceste elemente necesită aprobarea utilizatorului. O linie compactă de sursă poate fi propusă numai dacă formatul existent al rubricii o folosește.

---

# 5. CELE TREI IMAGINI

Fiecare articol are exact:

1. hero 16:9 — `[slug]-1.jpg`;
2. imagine interioară 4:3 — `[slug]-2.jpg`;
3. imagine interioară 4:3 — `[slug]-3.jpg`.

Pentru fiecare imagine, pachetul conține:

- rolul imaginii;
- promptul complet;
- raportul;
- numele fișierului;
- textul alternativ;
- punctul focal;
- elementele interzise.

Imaginile se generează și se validează secvențial. Fiecare imagine trebuie finalizată înainte de începerea următoarei.

## Procedura de validare și curățare

Pentru fiecare imagine:

1. generează imaginea;
2. verifică fidelitatea față de prompt;
3. verifică diferențierea față de imaginile anterioare;
4. respinge artefactele și textul accidental;
5. redimensionează la maximum 1600 px și JPEG quality 90;
6. elimină logo-ul vizibil al generatorului;
7. elimină marcajul invizibil/SynthID;
8. verifică rezultatul curățării;
9. optimizează final la JPEG quality 80;
10. salvează cu numele obligatoriu.

Implementarea Gemini de referință folosește `GeminiWatermarkTool.exe` pentru logo-ul vizibil și `noai-watermark` cu CUDA pentru SynthID. Alte instrumente sunt permise numai dacă obțin și verifică același rezultat.

---

# 6. TESTUL

După ce textul și cele trei imagini sunt complete, AI-ul actualizează numai:

- `teste/articol-1.html`;
- `teste/images/articol-1-1.jpg`;
- `teste/images/articol-1-2.jpg`;
- `teste/images/articol-1-3.jpg`.

Pagina de test trebuie să conțină:

```html
<meta name="robots" content="noindex, nofollow">
```

În această etapă AI-ul nu modifică:

- `index.html`;
- pagina rubricii;
- `arhiva.html`;
- meniul, sitemap-ul sau feed-ul;
- articolul ori imaginile finale.

Testul rămâne accesibil numai prin adresa transmisă utilizatorului. Nu se creează branch sau PR pentru un articol de test obișnuit.

AI-ul verifică pagina pe desktop și mobil, apoi prezintă:

- adresa testului;
- titlul și rubrica;
- cele trei imagini în context;
- un rezumat scurt al verificărilor;
- orice blocaj real.

---

# 7. CORECȚIILE

Observațiile utilizatorului actualizează același `teste/articol-1.html` și aceleași trei căi de imagine. Nu se creează un alt branch, alt PR sau alt flux paralel.

Dacă se schimbă subiectul, noul subiect trebuie aprobat înainte de rescriere și generare.

---

# 8. PUBLICAREA

Publicarea începe numai după mesajul:

> PUBLICĂ

AI-ul:

1. verifică faptul că aprobarea se referă la testul curent;
2. verifică versiunea curentă a lui `main` și evită suprascrierea schimbărilor fără legătură;
3. mută articolul în calea finală a rubricii;
4. mută cele trei imagini în folderul final;
5. actualizează cardul rubricii și arhiva;
6. actualizează homepage-ul numai dacă promovarea a fost aprobată sau este cerută de formatul curent;
7. elimină fișierele testului;
8. publică schimbările într-un singur set coerent;
9. verifică pagina finală pe desktop și mobil;
10. verifică site-ul live și raportează rezultatul.

`PUBLICĂ` nu autorizează refactorizări, schimbări de layout sau alte articole.

---

# 9. ADAPTOARELE DE INSTRUMENTE

Documentele dedicate unui model sau unui mediu pot explica butoane, comenzi, căi ori programe concrete. Ele nu pot modifica:

- nișa;
- aprobarea subiectului;
- cele trei imagini;
- generarea secvențială;
- eliminarea logo-ului și SynthID;
- testul din `/teste/`;
- aprobarea `PUBLICĂ`.

Dacă un AI nu poate executa o cerință, se oprește și raportează blocajul. Nu transferă munca utilizatorului și nu redefinește cerința.
