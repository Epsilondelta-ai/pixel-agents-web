# Pixel Agents Web

**[English](README.en.md) | [한국어](README.ko.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [Español](README.es.md) | [Português (BR)](README.pt-BR.md) | [Français](README.fr.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)**

[Pixel Agents](https://github.com/pablodelucca/pixel-agents) 的独立网页浏览器版本 — AI 编程代理在动画像素艺术办公室中化身为角色。

![Pixel Agents 截图](../public/Screenshot.jpg)

## 功能

- **动画像素艺术角色** — 每个代理都有自己的角色，具有行走、打字和阅读动画
- **实时活动追踪** — 角色根据代理活动进行动画（编写代码、读取文件、执行命令）
- **办公室布局编辑器** — 使用内置编辑器设计您的办公室，包含地板、墙壁和家具
- **对话气泡** — 代理等待输入或需要权限时的视觉指示器
- **声音通知** — 代理完成任务时可选的提示音
- **子代理可视化** — 子代理作为与父代理关联的独立角色生成
- **持久布局** — 您的办公室设计保存在 localStorage 中
- **多样化角色** — 基于 [JIK-A-4, Metro City](https://jik-a-4.itch.io/metrocity-free-topdown-character-pack) 的 6 种多样化角色
- **无需 VSCode** — 完全在网页浏览器中运行

<p align="center">
  <img src="../public/characters.png" alt="Pixel Agents 角色" width="320" height="72" style="image-rendering: pixelated;">
</p>

## 快速开始

```bash
git clone https://github.com/pablodelucca/pixel-agents-web.git
cd pixel-agents-web
npm install
npm run dev
```

然后在浏览器中打开 `http://localhost:5173`。

## 使用方法

1. 在网页浏览器中打开应用
2. 点击 **+ Agent** 生成一个演示角色
3. 观察角色通过模拟编程活动进行动画
4. 点击 **Layout** 打开办公室编辑器，自定义您的空间
5. 点击 **Settings** 导出/导入布局和切换声音

## 生产构建

```bash
npm run build
npm run preview
```

构建文件位于 `dist/` — 可部署到任何静态托管服务（Netlify、Vercel、GitHub Pages 等）。

## 技术栈

- **React 19** + TypeScript
- **Vite** — 开发和构建
- **Canvas 2D** — 像素级完美渲染
- **BFS 寻路** — 角色移动
- **角色状态机**（空闲 → 行走 → 打字/阅读）

## 工作原理

本项目是 [Pixel Agents VSCode 扩展](https://github.com/pablodelucca/pixel-agents)的独立网页移植版。原始扩展通过监视 Claude Code 的 JSONL 日志文件来追踪代理活动。本网页版本：

- 使用 Canvas API 在浏览器中直接加载所有资源（角色精灵、墙壁贴图、地板贴图）
- 用独立的网页桥接替代 VSCode 扩展消息桥接
- 提供生成逼真代理活动的演示模拟系统
- 保留与原版 100% 相同的 Canvas 2D 渲染

## 致谢

- 原始项目：[pablodelucca/pixel-agents](https://github.com/pablodelucca/pixel-agents)
- 角色精灵：[JIK-A-4, Metro City](https://jik-a-4.itch.io/metrocity-free-topdown-character-pack)

## 许可证

本项目基于 [MIT 许可证](../LICENSE) 授权。
