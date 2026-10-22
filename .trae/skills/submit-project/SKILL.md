---
name: "submit-project"
description: "提交项目到 Gitee 仓库。当用户要求提交项目、commit 并推送代码、或推送到 Gitee 远程仓库时调用。执行 git add/commit 并推送到 https://gitee.com/xzxdsb666/xuzhenxi115.git。"
---

# 提交项目 (Commit & Push)

将所有变更暂存、提交，并推送到 Gitee 远程仓库。

## Target

- Remote name: `origin`
- Remote URL: `https://gitee.com/xzxdsb666/xuzhenxi115.git`
- Branch: 当前分支（默认 `master`）

## Workflow

所有命令都在项目目录下执行。

1. 检查状态：
   - `git status`
   - `git rev-parse --is-inside-work-tree`（如果失败则初始化）

2. 如果目录还不是 git 仓库：
   - `git init`

3. 确保 `origin` 指向目标 URL：
   - `git remote add origin https://gitee.com/xzxdsb666/xuzhenxi115.git`
   - 如果 `origin` 已存在但指向其他地址：
     `git remote set-url origin https://gitee.com/xzxdsb666/xuzhenxi115.git`

4. 暂存所有更改：
   - `git add -A`

5. 提交：
   - `git commit -m "<简洁描述变更的信息>"`
   - 如果没有需要提交的内容，跳过此步骤继续。

6. 推送：
   - `git push -u origin <branch>`（首次推送使用 `-u`）

## Rules

- 除非用户明确要求，否则绝不强制推送（force-push）。
- 如果推送因远程仓库已有新提交而被拒绝，先 pull/rebase，再推送。
- 执行前，遵循 `AGENTS.md`：将用户的提示词以追加模式写入 `xuzhenxi_prompt.md`（时间戳格式 `yyyy-mm-dd-hh-mm`、使用的模型、完整的提示词内容）。
- 所有 CSS 类名、ID 名和 JS 变量名必须以 `xuzhenxi_` 开头（遵循 `AGENTS.md`）。
