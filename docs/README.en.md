# Pixel Agents Web

**[English](README.en.md) | [한국어](README.ko.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [Español](README.es.md) | [Português (BR)](README.pt-BR.md) | [Français](README.fr.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)**

A standalone web browser version of [Pixel Agents](https://github.com/pablodelucca/pixel-agents) — animated pixel art office where AI coding agents come to life as characters.

![Pixel Agents screenshot](../public/Screenshot.jpg)

## Features

- **Animated pixel art characters** — each agent gets its own character with walking, typing, and reading animations
- **Live activity tracking** — characters animate based on agent activity (writing code, reading files, running commands)
- **Office layout editor** — design your office with floors, walls, and furniture using the built-in editor
- **Speech bubbles** — visual indicators when an agent is waiting for input or needs permission
- **Sound notifications** — optional chime when an agent finishes its turn
- **Sub-agent visualization** — sub-agents spawn as separate characters linked to their parent
- **Persistent layouts** — your office design is saved in localStorage
- **Diverse characters** — 6 diverse characters based on [JIK-A-4, Metro City](https://jik-a-4.itch.io/metrocity-free-topdown-character-pack)
- **No VSCode required** — runs entirely in your web browser

<p align="center">
  <img src="../public/characters.png" alt="Pixel Agents characters" width="320" height="72" style="image-rendering: pixelated;">
</p>

## Quick Start

```bash
git clone https://github.com/pablodelucca/pixel-agents-web.git
cd pixel-agents-web
npm install
npm run dev
```

Then open `http://localhost:5173` in your browser.

## Usage

1. Open the app in your web browser
2. Click **+ Agent** to spawn a demo character
3. Watch the character animate with simulated coding activity
4. Click **Layout** to open the office editor and customize your space
5. Click **Settings** to export/import layouts and toggle sound

## Building for Production

```bash
npm run build
npm run preview
```

The built files are in `dist/` — deploy to any static hosting (Netlify, Vercel, GitHub Pages, etc.).

## Tech Stack

- **React 19** with TypeScript
- **Vite** for development and building
- **Canvas 2D** for pixel-perfect rendering
- **BFS pathfinding** for character movement
- **Character state machine** (idle → walk → type/read)

## How It Works

This is a standalone web port of the [Pixel Agents VSCode extension](https://github.com/pablodelucca/pixel-agents). The original extension watches Claude Code's JSONL transcript files to track agent activity. This web version:

- Loads all assets (character sprites, wall tiles, floor tiles) directly in the browser using Canvas API
- Replaces the VSCode extension message bridge with a standalone web bridge
- Provides a demo simulation system that generates realistic agent activity
- Preserves 100% identical Canvas 2D rendering from the original

## Credits

- Original project: [pablodelucca/pixel-agents](https://github.com/pablodelucca/pixel-agents)
- Character sprites: [JIK-A-4, Metro City](https://jik-a-4.itch.io/metrocity-free-topdown-character-pack)

## License

This project is licensed under the [MIT License](../LICENSE).
