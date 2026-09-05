# concept-skill-lab

> 用 AI 构建个人概念学习资料生成 Skill ——《大数据与人工智能》课程作业 1

## 这是什么

这个仓库是一个**个人学习工具集**：

- 内置一个项目级 Skill `learn-a-concept`：把任意概念变成结构化的学习资料
- 学习资料统一放在 `notes/` 目录，方便后续翻阅
- 配合 WorkBuddy 使用，每次遇到新概念，调一次 Skill 就能沉淀一份笔记

## 目录结构

```
concept-skill-lab/
├── README.md
├── .workbuddy/
│   └── skills/
│       └── learn-a-concept/
│           └── SKILL.md        ← 项目级 Skill 定义
├── notes/                      ← 学习资料落点
├── assignments/                ← 作业存档
└── .gitignore
```

## 怎么用

### 在 WorkBuddy 中

1. 用 WorkBuddy 打开本仓库根目录（让 `.workbuddy/skills/` 被识别）
2. 直接对话：`learn-a-concept: Agent` / `learn-a-concept: 大模型的上下文` / `learn-a-concept: Skill`
3. Skill 会把资料写到 `notes/<概念>.md`

### 命令行调用

```bash
# 项目级 Skill 物理位置
cat .workbuddy/skills/learn-a-concept/SKILL.md
```

## 已生成的学习资料

- `notes/01-agent.md` — Agent 是什么
- `notes/02-da-mo-xing-de-shang-xia-wen.md` — 大模型的上下文
- `notes/03-skill.md` — Skill 是什么

## 仓库信息

- 远程：`https://github.com/mikang-bdai/concept-skill-lab`
- 协作者：mikang-bdai
- 可见性：public