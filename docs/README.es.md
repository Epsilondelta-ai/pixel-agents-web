# Pixel Agents Web

**[English](README.en.md) | [한국어](README.ko.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [Español](README.es.md) | [Português (BR)](README.pt-BR.md) | [Français](README.fr.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)**

Versión independiente para navegador web de [Pixel Agents](https://github.com/pablodelucca/pixel-agents) — una oficina animada de pixel art donde los agentes de codificación IA cobran vida como personajes.

![Captura de Pixel Agents](../public/Screenshot.jpg)

## Características

- **Personajes de pixel art animados** — cada agente tiene su propio personaje con animaciones de caminar, escribir y leer
- **Seguimiento de actividad en vivo** — los personajes se animan según la actividad del agente (escribir código, leer archivos, ejecutar comandos)
- **Editor de diseño de oficina** — diseña tu oficina con pisos, paredes y muebles usando el editor integrado
- **Globos de diálogo** — indicadores visuales cuando un agente espera entrada o necesita permisos
- **Notificaciones de sonido** — tono opcional cuando un agente termina su turno
- **Visualización de sub-agentes** — los sub-agentes aparecen como personajes separados vinculados a su padre
- **Diseños persistentes** — tu diseño de oficina se guarda en localStorage
- **Personajes diversos** — 6 personajes diversos basados en [JIK-A-4, Metro City](https://jik-a-4.itch.io/metrocity-free-topdown-character-pack)
- **Sin necesidad de VSCode** — funciona completamente en tu navegador web

<p align="center">
  <img src="../public/characters.png" alt="Personajes de Pixel Agents" width="320" height="72" style="image-rendering: pixelated;">
</p>

## Inicio Rápido

```bash
git clone https://github.com/pablodelucca/pixel-agents-web.git
cd pixel-agents-web
npm install
npm run dev
```

Luego abre `http://localhost:5173` en tu navegador.

## Uso

1. Abre la aplicación en tu navegador web
2. Haz clic en **+ Agent** para crear un personaje de demostración
3. Observa cómo el personaje se anima con actividad de codificación simulada
4. Haz clic en **Layout** para abrir el editor de oficina y personalizar tu espacio
5. Haz clic en **Settings** para exportar/importar diseños y alternar el sonido

## Compilación para Producción

```bash
npm run build
npm run preview
```

Los archivos compilados están en `dist/` — despliega en cualquier hosting estático (Netlify, Vercel, GitHub Pages, etc.).

## Stack Tecnológico

- **React 19** con TypeScript
- **Vite** para desarrollo y compilación
- **Canvas 2D** para renderizado pixel-perfect
- **Pathfinding BFS** para movimiento de personajes
- **Máquina de estados de personajes** (inactivo → caminar → escribir/leer)

## Cómo Funciona

Este es un port web independiente de la [extensión Pixel Agents para VSCode](https://github.com/pablodelucca/pixel-agents). La extensión original observa los archivos de transcripción JSONL de Claude Code para rastrear la actividad de los agentes. Esta versión web:

- Carga todos los assets (sprites de personajes, tiles de pared, tiles de piso) directamente en el navegador usando Canvas API
- Reemplaza el puente de mensajes de la extensión VSCode con un puente web independiente
- Proporciona un sistema de simulación demo que genera actividad realista de agentes
- Preserva un renderizado Canvas 2D 100% idéntico al original

## Créditos

- Proyecto original: [pablodelucca/pixel-agents](https://github.com/pablodelucca/pixel-agents)
- Sprites de personajes: [JIK-A-4, Metro City](https://jik-a-4.itch.io/metrocity-free-topdown-character-pack)

## Licencia

Este proyecto está licenciado bajo la [Licencia MIT](../LICENSE).
