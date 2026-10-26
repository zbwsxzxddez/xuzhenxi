---
name: "submit-github"
description: "提交项目到 GitHub 仓库。当用户要求提交到 GitHub、commit 并推送到 GitHub、或推送到 zbwsxzxddez/xuzhenxi 仓库时调用。使用 SSH（已配置公钥）执行 git add/commit 并推送到 git@github.com:zbwsxzxddez/xuzhenxi.git。"
---

# 提交项目到 GitHub (Commit & Push to GitHub)

将所有变更暂存、提交，并推送到 GitHub 远程仓库。

## Target

- Remote name: `github`
- Remote URL (SSH): `git@github.com:zbwsxzxddez/xuzhenxi.git`
- Branch: 当前分支（默认 `master`）
- 认证方式：SSH 公钥（用户已配置）

## Workflow

所有命令都在项目目录下执行。

1. 检查状态：
   - `git status`
   - `git rev-parse --is-inside-work-tree`（如果失败则初始化）

2. 如果目录还不是 git 仓库：
   - `git init`

3. 确保 `github` 远程指向目标 SSH URL：
   - 查看现有远程：`git remote -v`
   - 如果 `github` 不存在：`git remote add github git@github.com:zbwsxzxddez/xuzhenxi.git`
   - 如果 `github` 已存在但指向其他地址：
     `git remote set-url github git@github.com:zbwsxzxddez/xuzhenxi.git`
   - 注意：本仓库可能已有 `origin` 指向 Gitee，不要覆盖 `origin`，使用独立的 `github` 远程名称。

4. 暂存所有更改：
   - `git add -A`

5. 提交：
   - `git commit -m "<简洁描述变更的信息>"`
   - 如果没有需要提交的内容，跳过此步骤继续。

6. 推送：
   - `git push -u github <branch>`（首次推送使用 `-u`）
   - 后续推送：`git push github <branch>`

## Rules

- 绝不强制推送（force-push），除非用户明确要求。
- 如果推送因远程仓库已有新提交而被拒绝，先 `git pull --rebase github <branch>`，再推送。
- 执行前，遵循 `AGENTS.md`：将用户的提示词以追加模式写入 `xuzhenxi_prompt.md`（时间戳格式 `yyyy-mm-dd-hh-mm`、使用的模型、完整的提示词内容）。
- 所有 CSS 类名、ID 名和 JS 变量名必须以 `xzx_` 开头（遵循 `AGENTS.md`）。
- **安全**：使用 SSH URL（`git@github.com:...`），禁止在 remote URL 或命令中嵌入 Token/PAT。
- 如果 SSH 连接失败，提示用户检查公钥配置，不要尝试改用 HTTPS + Token。
