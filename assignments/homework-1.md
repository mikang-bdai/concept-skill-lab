# 作业 1：用 AI 构建个人概念学习资料生成 Skill

> 大数据与人工智能 · 课程作业

## 任务

参考课堂演示流程：

1. 借助 AI 创建一个属于自己的 GitHub 仓库，并将仓库克隆到本地电脑 ✅
2. 在 WorkBuddy 中打开本地仓库，在仓库内创建一个「概念学习资料生成 Skill」 ✅
3. 将该 Skill 建立为项目级 Skill，保存到仓库根目录的 `.workbuddy/skills/` 中 ✅
4. 调用创建的 Skill，分别学习以下三个概念：**Agent**、**大模型的上下文**、**Skill** ✅
5. 检查并修改生成结果，将 Skill、学习资料和必要说明提交到本地 Git 仓库，再 push 到 GitHub ✅

## 仓库信息

- 名称：`concept-skill-lab`
- 远程：`https://github.com/mikang-bdai/concept-skill-lab`
- 路径：`D:/wawa/concept-skill-lab/`
- 可见性：public
- 创建时间：2026-09-05

## Skill 信息

- 名称：`learn-a-concept`
- 类型：项目级 Skill
- 路径：`<仓库根>/.workbuddy/skills/learn-a-concept/SKILL.md`
- 功能：输入概念 → 生成 9 章节结构化学习资料（§0 学习目标 + 8 章节正文）→ 写到 `notes/<概念>.md`

## 生成的学习资料

### Markdown 源稿（`notes/`）

- `notes/01-agent.md` — Agent
- `notes/02-da-mo-xing-de-shang-xia-wen.md` — 大模型的上下文
- `notes/03-skill.md` — Skill

### HTML 排版版（`learning-materials/`，作业要求的最终交付形式）

- `learning-materials/agent.html` — Agent
- `learning-materials/llm-context.html` — 大模型的上下文
- `learning-materials/skill.html` — Skill
- `learning-materials/concept-relationship.html` — **三个概念的关系图**（额外补的，作业明确要求"概念关系"页）

## 目录结构（最终）

```
concept-skill-lab/
├── README.md
├── .gitignore
├── .workbuddy/
│   └── skills/
│       └── learn-a-concept/
│           └── SKILL.md
├── notes/
│   ├── 01-agent.md
│   ├── 02-da-mo-xing-de-shang-xia-wen.md
│   └── 03-skill.md
├── learning-materials/
│   ├── agent.html
│   ├── llm-context.html
│   ├── skill.html
│   └── concept-relationship.html
└── assignments/
    └── homework-1.md
```

## 提交历史

- 本地 & 远程：5 个语义清晰的 commit（远程通过 git-data API 重建 + Contents API 追加，SHA 跟本地不一致但内容 1:1）
  - `init: scaffold + project-level Skill learn-a-concept`
  - `notes: add 3 concept learning materials via learn-a-concept`
  - `docs: 补充提交历史 + 把临时 push 脚本加入 .gitignore`
  - `materials: add 4 HTML 学习资料 + 更新 README 与作业存档`
  - `chore: 忽略 push_*.py 通配（workaround 脚本不入库）`

## 关键踩坑

1. **本机 `git push` 不可用**：`127.0.0.1:57376` 代理对 `github.com:443`（git 协议）返 502 拒连；取消代理直连 github.com 也超时（被网络封）。代理只放 `api.github.com`，所以必须走 GitHub REST API。
2. **绕过方法**：用 **git-data API** 重建 commit 链（POST blob/tree/commit + PATCH ref force=true），完整保留本地 commit 历史；单文件追加用 Contents API PUT。脚本 `push_via_git_data_api.py` 已加进 `.gitignore`（`push_*.py` 通配），不入库。`api.github.com` 偶尔 TLS 超时，脚本要带 6 次重试。
3. **WorkBuddy 项目级 Skill 的识别时机**：Skill 物理文件写到 `<workspace>/.workbuddy/skills/<name>/SKILL.md` 后，要在 WorkBuddy 里**重新打开那个目录**才能被识别。本仓库的 Skill 在 WorkBuddy 直接打开 `D:/wawa/concept-skill-lab/` 时可用。
4. **作业目录要求 vs 已有命名**：作业要求 `learning-materials/*.html`，但 Skill 默认输出 markdown 到 `notes/`。两个目录都保留 —— `notes/` 是源稿，GitHub 直接渲染；`learning-materials/` 是 HTML 排版版，浏览器打开即看，匹配作业目录要求。
