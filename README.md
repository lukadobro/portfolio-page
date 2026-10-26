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
konfiguriert. Eine spätere Veröffentlichung muss den erzeugten Inhalt von
`dist/` bereitstellen. Pages-Einstellungen und Deployment-Workflows sind
nicht Bestandteil dieses Grundgerüsts.
