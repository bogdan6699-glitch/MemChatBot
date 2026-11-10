# Memo AI — chatbot cu bază de cunoștințe

Aplicație web în limba română: UI statică + API serverless Vercel + OpenAI Responses API.

## Publicare recomandată: GitHub + Vercel

GitHub Pages poate găzdui doar partea statică; funcția AI trebuie rulată pe un server. Proiectul include `api/chat.js`, compatibil cu funcțiile serverless Vercel.

1. Creează un repository GitHub și încarcă toate fișierele din acest proiect.
2. Importă repository-ul în Vercel și publică proiectul.
3. În Vercel → Project → Settings → Environment Variables, adaugă:
   - `OPENAI_API_KEY` = cheia API a proiectului tău
   - opțional `OPENAI_MODEL` = `gpt-5.5`
4. Redeploy după adăugarea variabilelor.
5. Deschide URL-ul Vercel. UI-ul și `/api/chat` vor funcționa pe același domeniu.

**Important:** nu pune cheia API în `index.html`, în GitHub sau în orice fișier public. Cheia se setează numai în variabilele de mediu ale backend-ului. Configurarea unui cont API și a eventualelor costuri trebuie făcută cu ajutorul unui părinte/tutore.

## Funcționalități

- Chat AI real prin OpenAI Responses API.
- Adăugare de texte lungi prin lipire și fișiere `.txt`, `.md`, `.csv`.
- Salvare locală în IndexedDB, inclusiv după reîncărcarea paginii.
- Împărțirea documentelor în fragmente și căutare lexicală pentru selectarea contextului relevant.
- Răspunsuri AI pe baza fragmentelor selectate, cu numele documentelor folosite.
- Istoric recent de conversație în sesiunea curentă.
- Design responsive.

## Limitări actuale

- Documentele sunt păstrate local în browserul/dispozitivul unde au fost adăugate; nu sunt sincronizate între dispozitive și nu există conturi de utilizator.
- Recuperarea fragmentelor folosește căutare lexicală, nu embeddings/vector search. Pentru biblioteci uriașe sau căutare semantică avansată, următorul pas este un index vectorial și stocare server-side.
- Sunt acceptate fișiere text `.txt`, `.md`, `.csv`. PDF/DOCX nu sunt incluse în această versiune.
- Endpoint-ul este public dacă nu adaugi autentificare/rate limiting în hosting. Pentru o aplicație publică, configurează protecție, limite de utilizare și monitorizare a costurilor.

## Rulare locală

Vercel CLI:
```bash
npm i -g vercel
vercel dev
```
Setează `OPENAI_API_KEY` în mediul local înainte de pornire. Nu comite `.env`.
