# Memo — chatbot cu bază de cunoștințe

Un site minimalist, în limba română, care poate salva texte lungi local în browser și poate căuta fragmente relevante în ele.

## Publicare pe GitHub Pages
1. Creează un repository nou pe GitHub.
2. Încarcă `index.html` și `README.md` în repository.
3. Intră la **Settings → Pages**.
4. La **Build and deployment**, selectează **Deploy from a branch**.
5. Alege branch-ul `main` și folderul `/ (root)`, apoi apasă **Save**.
6. După publicare, GitHub îți va afișa adresa site-ului.

## Cum se folosește
- În „Baza de cunoștințe”, lipește un text lung sau încarcă fișiere `.txt`, `.md` ori `.csv`.
- Adaugă câte documente dorești.
- Pune întrebări în chat. Aplicația împarte documentele în fragmente și caută potrivirile cele mai relevante.
- Datele rămân în IndexedDB, în browserul și pe dispozitivul în care au fost adăugate.

## Limitare importantă
Aceasta este o versiune statică, fără server și fără model AI generativ. Caută și afișează fragmente relevante din textele încărcate; nu „învață” ca un model AI și nu formulează răspunsuri noi. Pentru răspunsuri conversaționale generate de AI, este nevoie de un backend securizat și de o cheie API păstrată pe server (nu în `index.html`). GitHub Pages singur nu poate ascunde o cheie API.

## Confidențialitate
Documentele sunt salvate local în browser prin IndexedDB. Dacă ștergi datele site-ului/browserului sau schimbi dispozitivul/browserul, documentele locale pot dispărea. Nu încărca informații sensibile într-un site public.
