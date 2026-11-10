# Memo — asistent AI pentru regulament FiveM

Versiune cu **regulament comun pe server**: administratorul pune textul o singură dată în `knowledge/regulament.txt`, iar toți utilizatorii site-ului primesc răspunsuri din aceeași bază de informații.

## Configurare

1. Încarcă toate fișierele și folderele proiectului în repository-ul GitHub.
2. În GitHub, deschide `knowledge/regulament.txt`, apasă Edit, șterge textul demonstrativ și lipește regulamentul complet. Salvează cu Commit changes.
3. Importă repository-ul în Vercel sau conectează-l la proiectul Vercel deja creat.
4. În Vercel → Settings → Environment Variables, setează `OPENAI_API_KEY`. Opțional, setează `OPENAI_MODEL` la un model disponibil în proiectul API.
5. Redeploy. După aceea, distribuie prietenilor URL-ul Vercel.

**Cheia API rămâne numai în Vercel.** Nu o pune în GitHub, în `index.html` sau în `knowledge/regulament.txt`. Configurarea contului API și orice costuri trebuie făcute cu ajutorul unui părinte/tutore.

## Cum actualizezi regulamentul

Editează `knowledge/regulament.txt` în GitHub și fă Commit changes. Vercel va porni automat o nouă publicare. Toți utilizatorii vor primi regulamentul nou după ce publicarea s-a încheiat și reîncarcă pagina.

## Cum funcționează

- Textul regulamentului este citit de funcția backend, nu salvat în browserul fiecărui prieten.
- Backend-ul împarte textul în fragmente și caută fragmente relevante pentru întrebare.
- Modelul AI formulează răspunsul pe baza fragmentelor găsite și este instruit să nu inventeze sancțiuni sau reguli.
- Nu este antrenat/fine-tuned un model; este o bază de cunoștințe consultată la fiecare întrebare.

## Limitări și protecție

- Regulamentul este inclus în proiectul publicat. Recomandat: repository GitHub privat, mai ales dacă documentul conține informații care nu trebuie distribuite public.
- Oricine are URL-ul poate folosi endpoint-ul; înainte de distribuire mai largă, adaugă autentificare și limitare de cereri pentru a preveni abuzul și costuri neașteptate.
- Căutarea este lexicală, nu semantică. Întrebările formulate cu termeni complet diferiți de cei din regulament pot rata unele pasaje.
- Fișierul este text simplu UTF-8. Copiază regulamentul fără formatare specială.
