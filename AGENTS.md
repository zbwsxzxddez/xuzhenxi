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

- All CSS class names, ID names, and JavaScript variable names must start with `xuzhenxi_`.
- All prompt content must be written to `xuzhenxi_prompt.md` before execution, in append mode (do not overwrite existing content).
- Each appended entry in `xuzhenxi_prompt.md` must include: timestamp in `yyyy-mm-dd-hh-mm` format, the model used, and the full prompt content.