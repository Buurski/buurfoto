# Buur Foto — Lucas' egen fotograf-demo (portfolio)
Enkeltside-HTML i `index.html` (al CSS i `<style>`, al JS i `<script>`, intet framework/build). Live https://buurfoto.vercel.app · GitHub `Buurski/buurfoto` · Vercel-projekt `buurfoto`.
Kunde: ingen. Lucas' egen demo til at lande fotograf-kunder, beholdt som portfolio (beslutning 2026-07-31). Pitch-tekster: `facebook-pitch.md`.
Hårde regler: `C:\Users\Buur\Documents\KnowledgeOS\context\hard-rules.md` (læs først). Router: `C:\Users\Buur\Documents\Websites\AGENTS.md`.

## Opgave | læs | læs IKKE
KB = `C:\Users\Buur\Documents\KnowledgeOS`. Gæt aldrig et faktum; står det ikke her eller i filen, skriv "ved ikke".

| Opgave | læs | læs IKKE |
|---|---|---|
| Tekst/indhold på siden | `index.html`, `KB\wiki\kunder\buurfoto.md`, `KB\context\brand-og-tone.md` | `C:\Users\Buur\_Arkiv`, andre kunders sites |
| Design/CSS | `index.html` (tokens i `:root`), `claude-design-prompt.md` (oprindeligt design-brief) | nye farver/skrifter udenfor tokens |
| SEO | `index.html` (title, meta, schema), `KB\wiki\kunder\buurfoto.md` | generiske SEO-skabeloner uden at tjekke siden |
| Deploy | `C:\Users\Buur\Documents\Websites\AGENTS.md`, `KB\wiki\os\agents-detaljer.md` (afsnit "Deploy-disciplin") | `.vercel\` (projekt-id, rør ikke) |
| Kinly-priser, startpris, tilbud | `KB\context\priser.md` (kanon; hjemmeside fra 3.997 kr) | gamle tilbud i wiki; individuelle aftaler afviger |
| Kundefakta, kontakt, status, log | `KB\wiki\kunder\buurfoto.md` | `C:\Users\Buur\Documents\Kunder\`, `.send_queue\` |
| Adresser (kunder, bl.a. Ikast Autoservice), tværgående fakta (Planuko-wordmark, HQ-gates, modelvalg) | `KB\context\fakta.md` | Lucas' privatadresse må aldrig stå nogen steder |
| Selskab, CVR, adresseregel | `KB\context\selskab.md` | |
| Mails/udgående tekst til kunden | `KB\context\brand-og-tone.md`, `KB\context\forbidden-phrases.md` | |
| Alle repos og sites | `C:\Users\Buur\Documents\REPOS.md`, `C:\Users\Buur\Documents\Websites\SITES.md` | |

## Kommandoer
Ingen `package.json`, ingen build, ingen `verify`-script.
- Dev: `python -m http.server 8080` i repo-roden → http://localhost:8080
- Deploy: kun Lucas merger til `main`. `vercel deploy --prod` kun efter Lucas' ja.

## Arkitektur (kort)
- Tokens i `:root`: `--cream`, `--ink`, `--gold` (#9a7e4a), `--sand`, `--serif` (Cormorant Garamond), `--sans` (Inter). Afvig aldrig.
- Sektioner (id): `top` → `hero` (4 polaroids) → `galleri` → `ommig` → `services` → `citat` → `kontakt`.
- Billeder: 17 Unsplash-pladsholdere (images.unsplash.com) + `assets/`. `fotos/` er untracked (egne/private fotos): commit aldrig.
- Kontaktformularen `#kontaktForm` sender ingenting (JS: `preventDefault` + klassen `sent`). Lov aldrig at den leverer.

## Regler
1. Aldrig `main` uden Lucas: ny gren + Vercel-preview, Lucas merger. Samler ændringer; maks 2-3 prod-deploys/dag; `[skip vercel]` ved docs.
2. "Done" = live-check: åbn preview/prod og print HTTP-status eller screenshot; ikke kun "ser rigtigt ud i koden".
3. Udgående (Facebook-opslag, mails) er KLADDER; Lucas sender selv. Intet sendes, ingen konti, køb eller DNS.
4. Dansk. Fotografi er helten: ingen AI-slop (gradient-blobs, emoji-ikoner, fyldtekst); palet kun creme/ink/guld/sand.
5. Én kode-agent pr. worktree; commit med eksplicit `git add <sti>`, aldrig `git commit -a`; ingen stash/reset/clean.
