# NIHIL.RO — Workflow editorial cu un singur prompt

## Scop

Un singur mesaj trebuie să fie suficient pentru pregătirea completă a unui articol sau a unei adaptări a site-ului. Munca se desfășoară în afara producției, iar publicarea are o singură confirmare separată.

Pentru utilizator, fluxul are doar două mesaje:

1. cererea de lucru;
2. `PUBLICĂ`, după verificarea previzualizării.

Toate etapele tehnice și editoriale dintre ele sunt responsabilitatea agentului.

---

# PROMPTUL MINIM

Pentru un articol este suficient:

> Pregătește pentru publicare un articol pentru rubrica [RUBRICĂ] despre [SUBIECT].

Exemplu:

> Pregătește pentru publicare un articol pentru România Neștiută despre satul Geamăna.

Opțional, utilizatorul poate adăuga un unghi, o lungime sau o cerință vizuală. Dacă nu le adaugă, agentul folosește regulile rubricii și ia singur deciziile necesare.

Pentru o modificare generală a site-ului este suficient:

> Pregătește pentru publicare următoarea adaptare a site-ului: [CERINȚĂ].

Cuvintele „pregătește pentru publicare” înseamnă: implementează complet pe branch, verifică și arată previzualizarea, dar nu modifica site-ul live.

---

# CE EXECUTĂ AGENTUL AUTOMAT

## 1. Protejează producția

- verifică starea repository-ului;
- pornește din versiunea curentă a lui `main`;
- creează un branch `article/<slug>` sau `site/<descriere>`;
- deschide un draft PR;
- nu scrie direct în `main`.

## 2. Construiește articolul

- identifică persona din `personas.md`;
- stabilește unghiul editorial și miza;
- documentează și verifică afirmațiile importante;
- scrie titlul, introducerea și textul final;
- adaugă byline-ul obligatoriu;
- decide dacă articolul are nevoie de o secțiune publică de surse;
- adaptează lungimea la rubrica și subiectul ales.

Utilizatorul nu trebuie să aprobe separat planul, titlul sau documentarea, exceptând cazul în care cererea conține o ambiguitate materială.

## 3. Pregătește imaginile odată cu textul

Pentru fiecare imagine, agentul stabilește:

- rolul: hero, card sau interior;
- promptul complet;
- modelul folosit;
- raportul: de regulă 16:9 pentru hero și card, 4:3 pentru interior;
- numele fișierului;
- textul alternativ;
- punctul focal pentru decuparea pe mobil;
- elementele care trebuie evitate.

Promptul respectă `nano_banana_guide.md` și este salvat în descrierea PR-ului. Nu este afișat în articol.

În mod implicit se generează o singură imagine hero reutilizabilă pentru card. Imagini suplimentare se creează numai dacă aduc informație sau atmosferă care nu poate fi obținută din aceeași imagine.

Agentul generează, verifică, optimizează și integrează imaginile. Utilizatorul nu este folosit ca intermediar între agent și instrumentul de generare.

## 4. Adaptează site-ul

Agentul identifică singur fișierele afectate și:

- creează sau actualizează pagina articolului;
- adaugă cardul în rubrica potrivită;
- actualizează pagina principală numai dacă articolul trebuie promovat acolo;
- introduce imaginea, byline-ul, textul alternativ și eventualele surse;
- păstrează stilul și comportamentul responsive existente;
- evită refactorizările fără legătură cu articolul.

Textul, imaginile, linkurile și integrarea vizuală fac parte din același PR.

## 5. Verifică rezultatul

Agentul verifică:

- coerența editorială și diferențierea vocii;
- afirmațiile factuale importante;
- HTML-ul și linkurile;
- lipsa imaginilor sau a fișierelor nefolosite;
- desktopul și mobilul;
- decuparea imaginilor;
- diacriticele, titlul și semnătura;
- faptul că `main` nu a fost modificat.

Apoi actualizează descrierea PR-ului cu:

- rezumatul articolului;
- fișierele modificate;
- prompturile imaginilor;
- regula de surse aplicată;
- verificările efectuate;
- capturile sau previzualizarea.

## 6. Se oprește înainte de producție

Agentul prezintă utilizatorului:

- rezultatul vizual;
- titlul și rubrica;
- schimbările care vor apărea pe site;
- linkul draftului PR;
- eventualele probleme reale rămase.

Nu face merge și nu actualizează site-ul live.

---

# PUBLICAREA

Dacă rezultatul este acceptat, utilizatorul răspunde:

> PUBLICĂ

Agentul tratează acest mesaj drept aprobarea explicită pentru integrarea PR-ului prezentat. Rulează verificarea finală, face merge în `main`, urmărește publicarea GitHub Pages și verifică pagina live.

Dacă sunt necesare schimbări, utilizatorul răspunde direct, de exemplu:

> Fă imaginea mai puțin întunecată și scurtează introducerea.

Agentul actualizează același branch și același PR, repetă verificarea și prezintă o nouă previzualizare. Nu creează un flux paralel.

---

# REGULA SURSELOR

Verificarea este obligatorie; bibliografia publică nu este automată.

Regula exactă se ia din secțiunea „Când afișăm sursele” din `personas.md`. Sursele publice trebuie să fie linkuri descriptive și direct relevante. Etichete vagi precum „știință”, „istorie” sau „internet” nu sunt surse.

---

# CE NU MAI TREBUIE SĂ FACĂ UTILIZATORUL

- să ceară separat articolul și integrarea;
- să ceară separat prompturile imaginilor;
- să transfere promptul într-un alt instrument;
- să indice fiecare pagină care trebuie actualizată;
- să ceară verificarea pe mobil;
- să urmărească manual ce branch este live;
- să repete contextul editorial al rubricii;
- să autorizeze fiecare pas intermediar.

Singurul prag obligatoriu rămas este publicarea în producție.
