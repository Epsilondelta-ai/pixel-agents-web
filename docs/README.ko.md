# Pixel Agents Web

**[English](README.en.md) | [한국어](README.ko.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [Español](README.es.md) | [Português (BR)](README.pt-BR.md) | [Français](README.fr.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)**

[Pixel Agents](https://github.com/pablodelucca/pixel-agents)의 독립형 웹 브라우저 버전 — AI 코딩 에이전트가 캐릭터로 살아 움직이는 애니메이션 픽셀 아트 오피스입니다.

![Pixel Agents 스크린샷](../public/Screenshot.jpg)

## 기능

- **애니메이션 픽셀 아트 캐릭터** — 각 에이전트는 걷기, 타이핑, 읽기 애니메이션이 있는 고유한 캐릭터를 가집니다
- **실시간 활동 추적** — 에이전트 활동(코드 작성, 파일 읽기, 명령 실행)에 따라 캐릭터가 애니메이션됩니다
- **오피스 레이아웃 편집기** — 내장 편집기로 바닥, 벽, 가구를 배치하여 오피스를 디자인하세요
- **말풍선** — 에이전트가 입력 대기 중이거나 권한이 필요할 때 시각적 표시
- **소리 알림** — 에이전트가 작업을 완료하면 선택적 알림음
- **하위 에이전트 시각화** — 하위 에이전트가 부모와 연결된 별도의 캐릭터로 생성됩니다
- **영구 레이아웃** — 오피스 디자인이 localStorage에 저장됩니다
- **다양한 캐릭터** — [JIK-A-4, Metro City](https://jik-a-4.itch.io/metrocity-free-topdown-character-pack) 기반 6종의 다양한 캐릭터
- **VSCode 불필요** — 웹 브라우저에서 완전히 동작합니다

<p align="center">
  <img src="../public/characters.png" alt="Pixel Agents 캐릭터" width="320" height="72" style="image-rendering: pixelated;">
</p>

## 빠른 시작

```bash
git clone https://github.com/pablodelucca/pixel-agents-web.git
cd pixel-agents-web
npm install
npm run dev
```

브라우저에서 `http://localhost:5173`을 열어주세요.

## 사용법

1. 웹 브라우저에서 앱을 엽니다
2. **+ Agent** 버튼을 클릭하여 데모 캐릭터를 생성합니다
3. 시뮬레이션된 코딩 활동으로 캐릭터가 움직이는 것을 확인하세요
4. **Layout**을 클릭하여 오피스 편집기를 열고 공간을 커스터마이즈하세요
5. **Settings**에서 레이아웃 내보내기/가져오기 및 소리 설정을 관리하세요

## 프로덕션 빌드

```bash
npm run build
npm run preview
```

빌드된 파일은 `dist/` 폴더에 있습니다 — Netlify, Vercel, GitHub Pages 등 정적 호스팅에 배포할 수 있습니다.

## 기술 스택

- **React 19** + TypeScript
- **Vite** — 개발 및 빌드
- **Canvas 2D** — 픽셀 퍼펙트 렌더링
- **BFS 경로 탐색** — 캐릭터 이동
- **캐릭터 상태 머신** (대기 → 걷기 → 타이핑/읽기)

## 작동 원리

이 프로젝트는 [Pixel Agents VSCode 확장](https://github.com/pablodelucca/pixel-agents)의 독립형 웹 포팅입니다. 원본 확장은 Claude Code의 JSONL 트랜스크립트 파일을 감시하여 에이전트 활동을 추적합니다. 이 웹 버전은:

- Canvas API를 사용하여 브라우저에서 직접 모든 에셋(캐릭터 스프라이트, 벽 타일, 바닥 타일)을 로드합니다
- VSCode 확장 메시지 브릿지를 독립형 웹 브릿지로 대체합니다
- 현실적인 에이전트 활동을 생성하는 데모 시뮬레이션 시스템을 제공합니다
- 원본과 100% 동일한 Canvas 2D 렌더링을 유지합니다

## 크레딧

- 원본 프로젝트: [pablodelucca/pixel-agents](https://github.com/pablodelucca/pixel-agents)
- 캐릭터 스프라이트: [JIK-A-4, Metro City](https://jik-a-4.itch.io/metrocity-free-topdown-character-pack)

## 라이선스

이 프로젝트는 [MIT 라이선스](../LICENSE)에 따라 라이선스가 부여됩니다.
