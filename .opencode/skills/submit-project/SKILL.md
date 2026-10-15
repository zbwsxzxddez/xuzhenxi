---
name: submit-project
description: Use when the user asks to 提交项目 (submit the project), commit and push the current project, or push to the Gitee repo. Runs git add/commit and pushes to https://gitee.com/xzxdsb666/xuzhenxi115.git.
---

# 提交项目 (Commit & Push)

Stage all changes, commit them, and push the project to the Gitee remote.

## Target

- Remote name: `origin`
- Remote URL: `https://gitee.com/xzxdsb666/xuzhenxi115.git`
- Branch: current branch (default `master`)

## Workflow

Run every command from the project directory.

1. Check state:
   - `git status`
   - `git rev-parse --is-inside-work-tree` (init if it fails)

2. If the directory is not yet a git repo:
   - `git init`

3. Ensure `origin` points at the target URL:
   - `git remote add origin https://gitee.com/xzxdsb666/xuzhenxi115.git`
   - If `origin` already exists but points elsewhere:
     `git remote set-url origin https://gitee.com/xzxdsb666/xuzhenxi115.git`

4. Stage everything:
   - `git add -A`

5. Commit:
   - `git commit -m "<concise message describing the change>"`
   - If there is nothing to commit, skip this step and continue.

6. Push:
   - `git push -u origin <branch>` (use `-u` on the first push)

## Rules

- Never force-push unless the user explicitly asks.
- If the push is rejected because the remote moved ahead, pull/rebase first, then push.
- Before executing, follow `AGENTS.md`: append the user's prompt to
  `xuzhenxi_prompt.md` in append mode (timestamp `yyyy-mm-dd-hh-mm`, the model
  used, and the full prompt content).
- Keep all CSS class names, ID names, and JS variable names prefixed with
  `xuzhenxi_` per `AGENTS.md`.
