# Pixel Agents Web

**[English](README.en.md) | [한국어](README.ko.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [Español](README.es.md) | [Português (BR)](README.pt-BR.md) | [Français](README.fr.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)**

Version navigateur web autonome de [Pixel Agents](https://github.com/pablodelucca/pixel-agents) — un bureau animé en pixel art où les agents de codification IA prennent vie en tant que personnages.

![Capture d'écran de Pixel Agents](../public/Screenshot.jpg)

## Fonctionnalités

- **Personnages pixel art animés** — chaque agent possède son propre personnage avec des animations de marche, frappe et lecture
- **Suivi d'activité en direct** — les personnages s'animent selon l'activité de l'agent (écriture de code, lecture de fichiers, exécution de commandes)
- **Éditeur de bureau** — concevez votre bureau avec sols, murs et meubles grâce à l'éditeur intégré
- **Bulles de dialogue** — indicateurs visuels lorsqu'un agent attend une saisie ou a besoin d'une autorisation
- **Notifications sonores** — sonnerie optionnelle lorsqu'un agent termine son tour
- **Visualisation des sous-agents** — les sous-agents apparaissent comme des personnages séparés liés à leur parent
- **Mises en page persistantes** — votre design de bureau est sauvegardé dans le localStorage
- **Personnages diversifiés** — 6 personnages diversifiés basés sur [JIK-A-4, Metro City](https://jik-a-4.itch.io/metrocity-free-topdown-character-pack)
- **VSCode non requis** — fonctionne entièrement dans votre navigateur web

<p align="center">
  <img src="../public/characters.png" alt="Personnages Pixel Agents" width="320" height="72" style="image-rendering: pixelated;">
</p>

## Démarrage Rapide

```bash
git clone https://github.com/pablodelucca/pixel-agents-web.git
cd pixel-agents-web
npm install
npm run dev
```

Puis ouvrez `http://localhost:5173` dans votre navigateur.

## Utilisation

1. Ouvrez l'application dans votre navigateur web
2. Cliquez sur **+ Agent** pour créer un personnage de démonstration
3. Observez le personnage s'animer avec une activité de codage simulée
4. Cliquez sur **Layout** pour ouvrir l'éditeur de bureau et personnaliser votre espace
5. Cliquez sur **Settings** pour exporter/importer des mises en page et activer/désactiver le son

## Build de Production

```bash
npm run build
npm run preview
```

Les fichiers compilés sont dans `dist/` — déployez sur n'importe quel hébergement statique (Netlify, Vercel, GitHub Pages, etc.).

## Stack Technique

- **React 19** avec TypeScript
- **Vite** pour le développement et le build
- **Canvas 2D** pour un rendu pixel-perfect
- **Pathfinding BFS** pour le déplacement des personnages
- **Machine à états des personnages** (inactif → marche → frappe/lecture)

## Fonctionnement

Ce projet est un port web autonome de l'[extension Pixel Agents pour VSCode](https://github.com/pablodelucca/pixel-agents). L'extension originale surveille les fichiers de transcription JSONL de Claude Code pour suivre l'activité des agents. Cette version web :

- Charge tous les assets (sprites de personnages, tuiles de murs, tuiles de sols) directement dans le navigateur via Canvas API
- Remplace le pont de messages de l'extension VSCode par un pont web autonome
- Fournit un système de simulation démo générant une activité d'agent réaliste
- Préserve un rendu Canvas 2D 100% identique à l'original

## Crédits

- Projet original : [pablodelucca/pixel-agents](https://github.com/pablodelucca/pixel-agents)
- Sprites de personnages : [JIK-A-4, Metro City](https://jik-a-4.itch.io/metrocity-free-topdown-character-pack)

## Licence

Ce projet est sous [Licence MIT](../LICENSE).
