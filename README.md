# concept-skill-lab

> 用 AI 构建个人概念学习资料生成 Skill ——《大数据与人工智能》课程作业 1

## 这是什么

这是一个**个人概念学习工具集**：

- 内置一个项目级 Skill `learn-a-concept`：把任意概念变成结构化的学习资料
- 学习资料以两种形式存放：
  - `notes/` 放 **markdown 源稿**（GitHub 直接渲染，便于二次编辑）
  - `learning-materials/` 放 **HTML 排版版**（浏览器打开即看，作业要求的最终交付形式）
- 配合 WorkBuddy 使用，每次遇到新概念，调一次 Skill 就能沉淀一份可阅读、可追溯、可推送的学习资料

## 目录结构（最终）

```
concept-skill-lab/
├── README.md                                 ← 本文件
├── .gitignore                                ← 排除 Python/缓存/临时脚本
├── .workbuddy/
│   └── skills/
│       └── learn-a-concept/
│           └── SKILL.md                      ← 项目级 Skill 定义
├── notes/                                    ← 学习资料 · markdown 源稿
│   ├── 01-agent.md
│   ├── 02-da-mo-xing-de-shang-xia-wen.md
│   └── 03-skill.md
├── learning-materials/                       ← 学习资料 · HTML 排版版（作业要求）
│   ├── agent.html
│   ├── llm-context.html
│   ├── skill.html
│   └── concept-relationship.html             ← 三个概念的关系图
└── assignments/
    └── homework-1.md                         ← 作业存档（含过程踩坑）
```

## Skill 在哪 & 怎么用

### 项目级 Skill 的物理位置

```
<仓库根>/.workbuddy/skills/learn-a-concept/SKILL.md
```

也就是这个仓库里的 `.workbuddy/skills/learn-a-concept/SKILL.md`。

### 在 WorkBuddy 中调用

1. 用 WorkBuddy 打开本仓库根目录（让 `.workbuddy/skills/` 被识别）
2. 在对话里说：
   ```
   learn-a-concept: <你想学的概念>
   ```
   或者自然语言："帮我学一下 X""X 是什么""讲讲 X"
3. Skill 会生成 8 章节结构化 markdown，落到 `notes/<编号>-<概念>.md`
4. 如需 HTML 排版版，手动把 md 渲染成 HTML 放到 `learning-materials/`

### 命令行直接查看 Skill 定义

```bash
cat .workbuddy/skills/learn-a-concept/SKILL.md
```

## 已生成的学习资料

| 概念 | Markdown 源稿 | HTML 排版版 |
|---|---|---|
| Agent | [`notes/01-agent.md`](notes/01-agent.md) | [learning-materials/agent.html](learning-materials/agent.html) |
| 大模型的上下文 | [`notes/02-da-mo-xing-de-shang-xia-wen.md`](notes/02-da-mo-xing-de-shang-xia-wen.md) | [learning-materials/llm-context.html](learning-materials/llm-context.html) |
| Skill | [`notes/03-skill.md`](notes/03-skill.md) | [learning-materials/skill.html](learning-materials/skill.html) |
| **三者的关系** | — | [learning-materials/concept-relationship.html](learning-materials/concept-relationship.html) |

四份资料结构一致（8 章节模板：定义 / 解决什么问题 / 核心要点 / 误解 / 关系 / 例子 / 自检 / 下一步），可以从任意一份开始读。

## AI 协助 + 人工核查记录

**这次作业里 AI 做了什么：**
- 设计 Skill `learn-a-concept` 的整体结构（触发条件 / 工作流 / 输出模板 / 注意事项 四件套）
- 调用 Skill 生成三个概念的学习资料（markdown）
- 把 markdown 源稿转写成 HTML 排版版（带卡片 / 关系图 / 误解对比 / 自检折叠 / 互链）
- 额外补一个 `concept-relationship.html` 关系图页（作业明确要求但 Skill 默认模板里没有的"概念关系"维度）
- 整理提交历史、撰写 README 和 assignments/homework-1.md

**人工核查了什么：**
- ✅ 概念解释的准确性：Agent 的"三件套"、Skill 的"四件套"、上下文的"Lost in the Middle"都是常见共识，没有伪造成分
- ✅ 外链的有效性：ReAct 论文 (arxiv.org/abs/2210.03629)、Lost in the Middle 论文 (arxiv.org/abs/2307.03172)、Anthropic 官网文章都是真实可访问的官方/学术资源
- ✅ 目录结构与作业要求一一对照：4 个 HTML + SKILL.md + README + .gitignore 全齐
- ✅ 自我检查的三个判断题是自己能答出来的（不是机器编的）

**故意没让 AI 做的事：**
- 没有让 AI 写 README 的"作业信息"部分（仓库名 / 路径 / 提交历史）——这些是事实，不能生成

## 仓库信息

- **名称**：`concept-skill-lab`
- **远程**：`https://github.com/mikang-bdai/concept-skill-lab`
- **协作者**：`mikang-bdai`
- **可见性**：public
- **本地路径**：`D:/wawa/concept-skill-lab/`
- **创建时间**：2026-09-05

## 下一步

- 把这个 Skill 持续用起来，每学一个新概念就 `learn-a-concept: X`，资料自动沉淀
- 等下一份作业发布时再决定要不要把仓库拆分成更细分的主题
