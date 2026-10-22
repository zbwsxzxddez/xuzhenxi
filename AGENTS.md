# AGENTS.md

## Overview

Static HTML/CSS practice site (coursework). Contains standalone HTML files, shared `css.css`, and local images under `img/`. No build tools, package managers, tests, linters, typecheckers, or CI workflows exist in this repo.

## Structure

- `index.html` — navigation/home page listing all practice pages (created per course requirements). 
- Numbered chapter files: `2-1.html`, `2-2.html`, `3-1 form.html`, `3-2 css.html`, `4-1 css2.html`, `5-1 层叠与继承.html`, `5-2 合模型.html`, `6-1 flex.html`, `6-2 一左一右.html`, `7-1 上图下文.html`, `7-2 左图右文.html`, `8-1 css3 选择器.html`, `9-1 transition.html`, `10-1 animation.html`, `10-2.html`, `10-3.html`, `10-4.html`.
- `css.css` — external stylesheet referenced by some pages (e.g., `5-1 层叠与继承.html`).
- `img/` — local image assets used by pages.

## Working with this repo

- All files are static. No compilation, bundling, or code generation. Changes are direct edits to HTML/CSS.
- Preview by opening files in a browser. For some setups, use a simple local server if relative paths behave differently, but files are self-contained and work when opened directly.
- No automated commands exist (no `package.json` scripts, Makefile, etc.). Do not assume lint/typecheck/test/build commands.
- Keep changes minimal and consistent with existing code style (vanilla HTML/CSS, no external/CDN dependencies).

## Notes

- Filenames include Chinese characters and spaces (e.g., `3-1 form.html`, `5-1 层叠与继承.html`); preserve exact names when linking/editing.
- `index.html` already contains the full course navigation and prompt text. Update it if you add/remove/reorder practice files.
- Prefer executable facts over assumptions. Since no tooling exists, verification is manual (browser preview).

## Project Rules

### 命名规范
- 所有变量名称、CSS 类名、ID 名称必须以 `xzx_` 开头。
- CSS 动画名称（@keyframes）也必须以 `xzx_` 开头。

### HTML 注释规范
- 所有 HTML 页面顶部必须包含注释：`<!-- 姓名：许镇玺，日期：<功能名称> -->`
- 其中 `<功能名称>` 替换为该页面的实际功能名称（如页面标题、章节名等）。

### 技术栈
- 项目使用原生的 HTML、CSS 和 JavaScript 实现。
- 不使用任何第三方库和 CDN。

### 图标
- 图标使用 `font` 目录下的 iconfont 图标（`font/font_5244851_6n95j09brtj/iconfont.css`）。
- 禁止使用外部图标库或 CDN 图标。

### 数据请求
- 使用 `fetch` 获取服务器端数据。

### 提示词记录
- 所有提示词内容必须在执行前以追加模式写入 `xuzhenxi_prompt.md`（不得覆盖已有内容）。
- 每条追加记录必须包含：`yyyy-mm-dd-hh-mm` 格式的时间戳、使用的模型、完整的提示词内容。