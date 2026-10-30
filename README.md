# portfolio-page

Minimales Grundgerüst mit Vue 3, Vite und JavaScript.

Voraussetzung: Node.js 24 LTS mit npm (siehe `.nvmrc`).

Abhängigkeiten installieren:

```sh
npm install
```

Lokale Entwicklung:

```sh
npm run dev
```

Die angezeigte lokale URL öffnen, standardmässig
`http://localhost:5173/portfolio-page/`.

Produktionsbuild erstellen:

```sh
npm run build
```

Die Ausgabedateien liegen in `dist/`. Den Build lokal prüfen:

```sh
npm run preview
```

Standardadresse: `http://localhost:4173/portfolio-page/`.

Für GitHub Pages ist in `vite.config.js` der Basispfad `/portfolio-page/`
konfiguriert. Der Workflow `.github/workflows/deploy.yml` baut bei einem Push
auf `main` mit Node.js 24, `npm ci` und `npm run build` und veröffentlicht
`dist/` mit den offiziellen GitHub-Pages-Actions.

Voraussetzung im Repository: Unter **Settings → Pages → Build and deployment**
muss als Quelle **GitHub Actions** ausgewählt sein. GitHub Actions und die
verwendeten offiziellen Actions müssen erlaubt sein. Schutzregeln für die
Umgebung `github-pages` müssen Deployments von `main` zulassen.

Der Build-Job verwendet `contents: read`; der Deployment-Job erhält
`pages: write` und `id-token: write`. Zusätzliche Zugangsdaten sind nicht nötig.

Lokale Prüfung am 30.10.2026: `npm ci` und `npm run build` waren mit
Node.js 24.22.1 und Vite 8.3.5 erfolgreich. `dist/index.html` und das
JavaScript-Bundle wurden erzeugt; der Asset-Pfad beginnt mit
`/portfolio-page/`. Der GitHub-Actions-Workflow wurde dabei nicht ausgeführt;
die Pages-Einstellungen im Repository wurden nicht überprüft oder geändert.
