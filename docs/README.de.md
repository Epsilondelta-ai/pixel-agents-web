# Pixel Agents Web

**[English](README.en.md) | [한국어](README.ko.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [Español](README.es.md) | [Português (BR)](README.pt-BR.md) | [Français](README.fr.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)**

Eigenständige Webbrowser-Version von [Pixel Agents](https://github.com/pablodelucca/pixel-agents) — ein animiertes Pixel-Art-Büro, in dem KI-Coding-Agenten als Charaktere zum Leben erwachen.

![Pixel Agents Screenshot](../public/Screenshot.jpg)

## Funktionen

- **Animierte Pixel-Art-Charaktere** — jeder Agent erhält seinen eigenen Charakter mit Geh-, Tipp- und Lese-Animationen
- **Live-Aktivitätsverfolgung** — Charaktere animieren sich basierend auf der Agentenaktivität (Code schreiben, Dateien lesen, Befehle ausführen)
- **Bürolayout-Editor** — gestalte dein Büro mit Böden, Wänden und Möbeln mit dem integrierten Editor
- **Sprechblasen** — visuelle Indikatoren, wenn ein Agent auf Eingabe wartet oder Berechtigung benötigt
- **Soundbenachrichtigungen** — optionaler Ton, wenn ein Agent seinen Zug beendet
- **Sub-Agenten-Visualisierung** — Sub-Agenten erscheinen als separate Charaktere, die mit ihrem Elternteil verbunden sind
- **Persistente Layouts** — dein Bürodesign wird im localStorage gespeichert
- **Vielfältige Charaktere** — 6 vielfältige Charaktere basierend auf [JIK-A-4, Metro City](https://jik-a-4.itch.io/metrocity-free-topdown-character-pack)
- **Kein VSCode erforderlich** — läuft vollständig in deinem Webbrowser

<p align="center">
  <img src="../public/characters.png" alt="Pixel Agents Charaktere" width="320" height="72" style="image-rendering: pixelated;">
</p>

## Schnellstart

```bash
git clone https://github.com/pablodelucca/pixel-agents-web.git
cd pixel-agents-web
npm install
npm run dev
```

Dann öffne `http://localhost:5173` in deinem Browser.

## Verwendung

1. Öffne die App in deinem Webbrowser
2. Klicke auf **+ Agent**, um einen Demo-Charakter zu erstellen
3. Beobachte, wie der Charakter mit simulierter Coding-Aktivität animiert wird
4. Klicke auf **Layout**, um den Büroeditor zu öffnen und deinen Raum anzupassen
5. Klicke auf **Settings**, um Layouts zu exportieren/importieren und Sound umzuschalten

## Produktions-Build

```bash
npm run build
npm run preview
```

Die Build-Dateien befinden sich in `dist/` — bereitstellbar auf jedem statischen Hosting (Netlify, Vercel, GitHub Pages usw.).

## Technologie-Stack

- **React 19** mit TypeScript
- **Vite** für Entwicklung und Build
- **Canvas 2D** für pixelgenaues Rendering
- **BFS-Pfadfindung** für Charakterbewegung
- **Charakter-Zustandsmaschine** (Leerlauf → Gehen → Tippen/Lesen)

## Funktionsweise

Dies ist ein eigenständiger Web-Port der [Pixel Agents VSCode-Erweiterung](https://github.com/pablodelucca/pixel-agents). Die Original-Erweiterung überwacht die JSONL-Transkriptdateien von Claude Code, um die Agentenaktivität zu verfolgen. Diese Web-Version:

- Lädt alle Assets (Charakter-Sprites, Wand-Tiles, Boden-Tiles) direkt im Browser über Canvas API
- Ersetzt die VSCode-Erweiterungs-Nachrichtenbrücke durch eine eigenständige Web-Brücke
- Bietet ein Demo-Simulationssystem, das realistische Agentenaktivität generiert
- Bewahrt 100% identisches Canvas 2D-Rendering wie das Original

## Credits

- Originalprojekt: [pablodelucca/pixel-agents](https://github.com/pablodelucca/pixel-agents)
- Charakter-Sprites: [JIK-A-4, Metro City](https://jik-a-4.itch.io/metrocity-free-topdown-character-pack)

## Lizenz

Dieses Projekt ist unter der [MIT-Lizenz](../LICENSE) lizenziert.
