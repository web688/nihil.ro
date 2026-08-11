# AGENTS.md

Aceste reguli se aplică întregului repository NIHIL.RO și oricărui AI care lucrează la proiect.

## 1. Identitatea NIHIL.RO

NIHIL.RO este un anti-portal românesc de curiozitate editorială pentru cititori care vor lucruri reale, surprinzătoare și memorabile. Promisiunea site-ului este exprimată de formulele deja publicate: „Curiozitatea ca act de supraviețuire”, „Ciudățenii verificate”, „fapte care dezechilibrează” și „povești din colțuri neașteptate”.

Un subiect se potrivește numai dacă valoarea lui principală este cel puțin una dintre acestea:

- un fapt care provoacă reacția „stai, ce?”;
- o excepție reală care contrazice intuiția;
- un loc, om, obiect sau comportament puțin cunoscut și realmente neobișnuit;
- o perspectivă neașteptată asupra unui lucru familiar;
- o acțiune concretă care face ziua mai interesantă.

NIHIL.RO nu este portal generalist, site de știri, publicație ecologistă, tribună de activism sau revistă de probleme sociale. Documentarea poate fi serioasă, dar seriozitatea, importanța civică, tragedia sau actualitatea nu sunt singure motive suficiente pentru publicarea unui articol.

Dacă un material ar putea apărea aproape neschimbat pe un site generalist despre politică publică, ecologie, sănătate, educație sau societate, subiectul se respinge ori se caută un unghi NIHIL.RO autentic înainte de a fi propus.

`subiecte.md` este doar o colecție de posibilități. Prezența unei teme în acel fișier nu înseamnă aprobare și nu dovedește că tema se potrivește nișei.

## 2. Workflow independent de model

Regulile descriu rezultate și verificări, nu un furnizor. Articolul poate fi scris, ilustrat, integrat și verificat de Gemini, ChatGPT, Claude, Codex sau orice alt AI cu instrumentele necesare.

- Un singur AI poate executa toate rolurile sau mai multe AI-uri le pot împărți.
- Utilizatorul nu este folosit ca intermediar pentru copierea prompturilor între instrumente.
- Un ghid dedicat unui model sau unui program este un adaptor de implementare, nu workflow-ul de bază.
- Un AI nu poate elimina o cerință doar pentru că instrumentul său nu o poate executa.
- Dacă lipsește o capacitate obligatorie, AI-ul oprește fluxul și raportează exact blocajul.

## 3. Cele două aprobări obligatorii

### Aprobarea subiectului

Dacă utilizatorul nu a cerut explicit scrierea unui subiect concret, AI-ul analizează site-ul, alege cea mai bună idee și o propune înainte de redactare. Nu scrie articolul și nu generează imaginile până când utilizatorul aprobă clar ideea.

O cerere precum „pregătește următorul articol NIHIL.RO” sau „putem încerca un articol?” nu aprobă automat nicio temă. O comandă explicită precum „scrie un articol despre X” reprezintă aprobarea subiectului X.

### Aprobarea publicării

Testul nu devine articol public în rubrică până la mesajul explicit `PUBLICĂ`. Această comandă se aplică numai testului prezentat cel mai recent.

## 4. Documentele care trebuie citite

Înainte de propunerea unei idei:

1. `index.html` și pagina rubricii;
2. articolele recente din rubrica respectivă;
3. `personas.md`;
4. `EDITORIAL_WORKFLOW.md`;
5. `subiecte.md`, numai ca hartă orientativă.

Pentru imagini se consultă și direcția vizuală existentă. `nano_banana_guide.md` și fișierele din `backup_workflow/` pot fi folosite ca adaptoare sau referințe tehnice, dar cerințele obligatorii sunt cele din prezentul document și din `EDITORIAL_WORKFLOW.md`.

## 5. Testul simplu și protecția producției

Branch-ul `main` alimentează GitHub Pages. Pentru articole, înainte de `PUBLICĂ`, singura excepție permisă de la protecția producției este suprafața de test:

- pagina: `teste/articol-1.html`;
- imaginile: `teste/images/articol-1-1.jpg`, `articol-1-2.jpg`, `articol-1-3.jpg`;
- pagina conține `noindex, nofollow`;
- testul nu este legat din homepage, rubrică, arhivă, meniu, sitemap sau feed;
- nicio pagină publică existentă nu este modificată pentru pregătirea testului.

Nu se creează branch și PR pentru fiecare articol de test. Același slot `articol-1` este actualizat după observațiile utilizatorului.

Orice modificare în afara `teste/` rămâne interzisă până la `PUBLICĂ`. Modificările generale de layout sau infrastructură, care nu pot fi izolate în `teste/`, folosesc branch separat și previzualizare înainte de integrare.

După `PUBLICĂ`, articolul și cele trei imagini sunt mutate în căile finale, sunt actualizate numai paginile necesare, iar testul este eliminat în aceeași publicare coerentă.

## 6. Contractul articolului

- Subiectul și unghiul au fost aprobate de utilizator.
- Textul respectă nișa și persona rubricii.
- Semnătura obligatorie apare sub titlu.
- Nu se inventează experiențe personale, citate, surse sau biografii.
- Afirmațiile sunt verificate, dar cercetarea nu este transformată automat în bibliografie publică.
- Nu se adaugă o casetă publică de surse fără aprobarea utilizatorului.
- Nu se adaugă etichete precum „imagine generată”, „reconstituire editorială” sau explicații despre AI fără aprobarea utilizatorului.
- Fiecare articol are exact trei imagini: una hero și două interioare.
- Prompturile celor trei imagini sunt păstrate în pachetul de lucru și pot fi executate de orice generator compatibil.

## 7. Contractul obligatoriu al imaginilor

### Număr, raport și nume

1. `[slug]-1.jpg` — imagine hero, raport 16:9, reutilizabilă pentru card.
2. `[slug]-2.jpg` — imagine interioară, raport 4:3.
3. `[slug]-3.jpg` — imagine interioară, raport 4:3.

Cele trei imagini trebuie să arate momente, perspective sau detalii diferite. Nu sunt acceptate variații aproape identice.

### Generare secvențială

Imaginile se procesează una câte una. Pentru fiecare imagine:

1. generează;
2. verifică respectarea promptului;
3. verifică diferențierea față de imaginile deja acceptate;
4. respinge textul accidental, artefactele, anatomia imposibilă sau subiectul greșit;
5. salvează și redenumește fișierul;
6. finalizează toată curățarea și optimizarea;
7. abia apoi trece la următoarea imagine.

Generarea în lot fără verificarea fiecărei imagini este interzisă.

### Curățarea obligatorie

Pentru imaginile generate cu Gemini, procedura de referință restaurată din workflow-ul vechi este:

1. redimensionare la maximum 1600 px, JPEG quality 90;
2. eliminarea logo-ului vizibil cu `GeminiWatermarkTool.exe`;
3. eliminarea marcajului invizibil/SynthID cu `noai-watermark` și CUDA;
4. verificarea rezultatului;
5. optimizare finală JPEG quality 80;
6. mutarea în calea testului sau în calea finală aprobată.

Alt AI sau alt mediu poate folosi instrumente echivalente. Eliminarea logo-ului vizibil și a marcajului invizibil rămâne obligatorie; numai instrumentul concret poate fi înlocuit.

## 8. Sursele

Verificarea factuală este obligatorie. Afișarea surselor este o decizie editorială separată.

- Sursele sunt păstrate în notele de lucru ale AI-ului.
- Articolul nu primește implicit o secțiune „Surse”.
- O linie compactă de sursă poate fi propusă când formatul existent al rubricii o folosește deja.
- O bibliografie, o notă metodologică sau o explicație despre autorul-persona se afișează numai după aprobarea utilizatorului.

## 9. Verificarea testului

Înainte de prezentarea testului, AI-ul confirmă:

- subiect aprobat și potrivire cu nișa;
- persona și semnătura corecte;
- exact trei imagini, cu rapoartele corecte;
- logo-ul vizibil și marcajul invizibil eliminate;
- HTML, diacritice, căi și linkuri valide;
- desktop și mobil verificate vizual;
- `noindex, nofollow` prezent;
- nicio legătură din site către test;
- nicio sursă sau etichetă AI publică neaprobată;
- nicio modificare accidentală în afara `teste/`.

După `PUBLICĂ`, verificarea se repetă pe pagina finală live.
