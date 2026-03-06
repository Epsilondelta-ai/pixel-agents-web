# Pixel Agents Web

**[English](README.en.md) | [한국어](README.ko.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [Español](README.es.md) | [Português (BR)](README.pt-BR.md) | [Français](README.fr.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)**

Versão independente para navegador web do [Pixel Agents](https://github.com/pablodelucca/pixel-agents) — um escritório animado em pixel art onde agentes de codificação IA ganham vida como personagens.

![Captura de tela do Pixel Agents](../public/Screenshot.jpg)

## Funcionalidades

- **Personagens de pixel art animados** — cada agente tem seu próprio personagem com animações de andar, digitar e ler
- **Rastreamento de atividade em tempo real** — personagens se animam com base na atividade do agente (escrever código, ler arquivos, executar comandos)
- **Editor de layout do escritório** — projete seu escritório com pisos, paredes e móveis usando o editor integrado
- **Balões de fala** — indicadores visuais quando um agente está aguardando entrada ou precisa de permissão
- **Notificações sonoras** — toque opcional quando um agente termina seu turno
- **Visualização de sub-agentes** — sub-agentes aparecem como personagens separados vinculados ao seu pai
- **Layouts persistentes** — o design do seu escritório é salvo no localStorage
- **Personagens diversos** — 6 personagens diversos baseados em [JIK-A-4, Metro City](https://jik-a-4.itch.io/metrocity-free-topdown-character-pack)
- **Sem necessidade de VSCode** — funciona inteiramente no seu navegador web

<p align="center">
  <img src="../public/characters.png" alt="Personagens do Pixel Agents" width="320" height="72" style="image-rendering: pixelated;">
</p>

## Início Rápido

```bash
git clone https://github.com/pablodelucca/pixel-agents-web.git
cd pixel-agents-web
npm install
npm run dev
```

Em seguida, abra `http://localhost:5173` no seu navegador.

## Uso

1. Abra o aplicativo no seu navegador web
2. Clique em **+ Agent** para criar um personagem de demonstração
3. Observe o personagem se animar com atividade de codificação simulada
4. Clique em **Layout** para abrir o editor de escritório e personalizar seu espaço
5. Clique em **Settings** para exportar/importar layouts e alternar o som

## Build para Produção

```bash
npm run build
npm run preview
```

Os arquivos compilados estão em `dist/` — implante em qualquer hospedagem estática (Netlify, Vercel, GitHub Pages, etc.).

## Stack Tecnológica

- **React 19** com TypeScript
- **Vite** para desenvolvimento e build
- **Canvas 2D** para renderização pixel-perfect
- **Pathfinding BFS** para movimentação de personagens
- **Máquina de estados de personagens** (inativo → andar → digitar/ler)

## Como Funciona

Este é um port web independente da [extensão Pixel Agents para VSCode](https://github.com/pablodelucca/pixel-agents). A extensão original observa os arquivos de transcrição JSONL do Claude Code para rastrear a atividade dos agentes. Esta versão web:

- Carrega todos os assets (sprites de personagens, tiles de parede, tiles de piso) diretamente no navegador usando Canvas API
- Substitui a ponte de mensagens da extensão VSCode por uma ponte web independente
- Fornece um sistema de simulação demo que gera atividade realista de agentes
- Preserva renderização Canvas 2D 100% idêntica ao original

## Créditos

- Projeto original: [pablodelucca/pixel-agents](https://github.com/pablodelucca/pixel-agents)
- Sprites de personagens: [JIK-A-4, Metro City](https://jik-a-4.itch.io/metrocity-free-topdown-character-pack)

## Licença

Este projeto está licenciado sob a [Licença MIT](../LICENSE).
