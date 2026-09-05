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
- 功能：输入概念 → 生成 8 章节结构化学习资料 → 写到 `notes/<概念>.md`

## 生成的学习资料

- `notes/01-agent.md`
- `notes/02-da-mo-xing-de-shang-xia-wen.md`
- `notes/03-skill.md`

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
└── assignments/
    └── homework-1.md
```

## 提交历史

本地 2 个语义清晰的 commit；GitHub 上 7 个 commit（每个文件一个，因为 GitHub Contents API 一次只能操作一个文件）。

## 关键踩坑

1. **代理只放 `api.github.com`，不放 `github.com`**：当前环境的 `127.0.0.1:57376` 代理对 `github.com` 域名的 git 协议返 502，但 `api.github.com` OK。所以 `git push` 不通，但 `gh api` 通。
3. **绕过方法**：写 `push_via_api.py`（已加入 `.gitignore`），用 GitHub Contents API 逐文件上传。

2. **WorkBuddy 项目级 Skill 的识别时机**：Skill 物理文件写到 `<workspace>/.workbuddy/skills/<name>/SKILL.md` 后，要在 WorkBuddy 里**重新打开那个目录**才能被识别。本仓库的 Skill 在 WorkBuddy 直接打开 `D:/wawa/concept-skill-lab/` 时可用。