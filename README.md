# plimsolltools.com

Statische Website von Plimsoll Tools. Reines HTML/CSS, keine Abhängigkeiten, keine externen Requests.

## Struktur
- `index.html` – Startseite
- `tools/localization-text-qa/index.html` – Tool-Seite mit Doku-Gerüst (TODO-Kommentare)
- `support.html` – Support
- `impressum.html`, `datenschutz.html` – Platzhalter, vor dem Live-Schalten ausfüllen
- `assets/style.css` – einziges Stylesheet (Farben als Variablen in `:root`, Dark Mode per `prefers-color-scheme`)
- `assets/fonts/` – Barlow, selbst gehostet (SIL Open Font License, siehe `OFL.txt`)
- `CNAME` – eigene Domain für GitHub Pages
- `.nojekyll` – GitHub Pages liefert die Dateien unverändert aus

## Veröffentlichen mit GitHub Pages
1. Neues öffentliches Repository anlegen (z. B. `plimsolltools.com`), Inhalt dieses Ordners in den Branch `main` pushen.
2. Repository → Settings → Pages → Source: "Deploy from a branch", Branch `main`, Ordner `/ (root)`.
3. Unter "Custom domain" `plimsolltools.com` eintragen (steht auch schon in `CNAME`).
4. Bei Porkbun die DNS-Einträge setzen (Werte vorher in der GitHub-Doku "Managing a custom domain for your GitHub Pages site" gegenprüfen):
   - `A`-Records für `plimsolltools.com`: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
   - `AAAA`-Records: 2606:50c0:8000::153, 2606:50c0:8001::153, 2606:50c0:8002::153, 2606:50c0:8003::153
   - `CNAME` für `www` → `<dein-github-name>.github.io`
   - Porkbuns Standard-Einträge (Parking/ALIAS) für die Domain vorher entfernen; die MX-Einträge für die Mail-Weiterleitung bleiben.
5. Sobald das Zertifikat da ist: "Enforce HTTPS" einschalten.
6. GitHub → Profil-Settings → Pages → "Add a verified domain": schützt die Domain davor, von fremden Repositories übernommen zu werden.

## Vor dem Live-Schalten
- Impressum und Datenschutzerklärung vervollständigen (Platzhalter in eckigen Klammern).
- Doku-Abschnitte der Tool-Seite füllen, sobald Meilenstein 4 steht.
