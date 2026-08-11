# AGENTS.md

Aceste reguli se aplică întregului repository NIHIL.RO.

## Producția este protejată

- Branch-ul `main` alimentează site-ul live.
- Nu modifica direct `main`.
- Orice schimbare pornește dintr-un branch nou creat din versiunea curentă a lui `main`.
- Deschide imediat un draft PR pentru schimbare.
- Nu integra PR-ul și nu publica site-ul fără aprobarea explicită a utilizatorului.
- Confirmarea standard de publicare este mesajul `PUBLICĂ`.
- Până la acea confirmare, toate textele, imaginile și modificările de layout rămân pe branch-ul de lucru.
- Păstrează schimbările fără legătură în afara PR-ului curent.

## Interfața simplă pentru utilizator

Când utilizatorul cere un articol sau o adaptare a site-ului, agentul execută singur întregul flux descris în `EDITORIAL_WORKFLOW.md`.

Utilizatorul nu trebuie să:

- creeze branch-uri sau PR-uri;
- copieze prompturi între instrumente;
- aleagă persona dacă rubrica este deja cunoscută;
- scrie separat promptul imaginilor;
- indice manual fișierele HTML care trebuie actualizate;
- verifice căile imaginilor sau comportamentul responsive.

Agentul cere clarificări numai dacă lipsește o decizie care ar schimba material rezultatul. În rest, ia decizii editoriale rezonabile și le consemnează în draftul PR.

## Documente obligatorii

Înainte de redactare sau integrare, consultă:

1. `personas.md` pentru voce, semnătură și regula surselor;
2. `nano_banana_guide.md` pentru direcția vizuală;
3. `EDITORIAL_WORKFLOW.md` pentru fluxul complet;
4. `subiecte.md` când este relevant pentru selecția temei.

Dacă un document lipsește, nu inventa conținutul lui. Continuă numai dacă lipsa nu afectează decizia cerută.

## Reguli pentru articole

- Fiecare articol folosește persona rubricii și byline-ul ei obligatoriu.
- Fiecare articol este verificat factual conform `personas.md`.
- Sursele se afișează numai în cazurile cerute de regula rubricii.
- Fiecare imagine are prompt, raport, nume de fișier, text alternativ și punct focal.
- Prompturile imaginilor se păstrează în descrierea PR-ului, nu în textul vizibil al paginii.
- Articolul, imaginile, cardurile și linkurile sunt pregătite în același branch.
- Nu publica un card care trimite către o pagină inexistentă.
- Nu inventa experiențe personale, citate, surse sau biografii.

## Reguli pentru imagini

- Generează imaginea în același flux cu articolul; nu transfera această etapă utilizatorului.
- Respectă stilul NIHIL.RO și raportul cerut de poziția imaginii.
- Verifică decuparea pe desktop și mobil.
- Nu integra imagini cu text accidental, artefacte evidente, anatomie imposibilă sau subiect diferit de articol.
- Optimizează fișierul pentru web fără degradare vizibilă.
- Dacă instrumentul necesar nu este disponibil, oprește înainte de publicare și explică exact blocajul.

## Verificare și publicare

Înainte de a cere aprobarea:

- verifică HTML-ul și căile fișierelor;
- verifică linkurile și semnătura;
- verifică desktopul și mobilul;
- verifică imaginile și textele alternative;
- verifică dacă sursele publice sunt prezente numai unde trebuie;
- oferă o previzualizare sau capturi clare;
- rezumă exact ce se va schimba pe site.

După mesajul `PUBLICĂ`:

1. rulează verificarea finală;
2. actualizează PR-ul dacă este necesar;
3. integrează schimbarea în `main`;
4. verifică publicarea pe site-ul live;
5. raportează rezultatul și orice problemă observată.
