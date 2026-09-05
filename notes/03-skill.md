# Skill

> 一句话总结：把"做某件事的最佳实践 + 工具调用 + 输出规范"打包成一个可复用的指令包，让 AI 在合适场景自动或手动调用。

## 0. 学习目标（读完这份资料你应该能…）

- [ ] 用一句话向别人讲清楚 Skill 是什么（不超过 30 字）
- [ ] 说出 Skill 解决的核心问题：零散 prompt 难维护、好的工作流没法沉淀复用的痛点
- [ ] 列出 Skill 的 3-5 个核心要点（四件套 / 项目级 vs 用户级 / 可演进）
- [ ] 指出至少 2 个常见误解（Skill ≠ 系统提示词 / 一次写好就完事）
- [ ] 区分 Skill 跟至少 1 个相似概念（Prompt / Plugin / RAG）
- [ ] 用一个岗位 SOP 的类比演示 Skill 怎么让 AI 输出更稳定
- [ ] 回答 §7 的 3 道自检题
- [ ] 知道 Skill 深入学习该去哪儿（Anthropic Building Effective Agents / 本仓库 SKILL.md）

## 1. 一句话定义
Skill 是一份**结构化的指令文档**，告诉 AI「当遇到 X 场景时，按这套工作流办事，按这个模板输出」—— 本质上是给 AI 的一份「岗位操作手册」。

## 2. 解决什么问题
- **场景**：你经常让 AI 做某类任务（比如学概念、写周报、改代码），每次都重复讲一遍规则太啰嗦
- **痛点**：零散 prompt 难维护、跨会话丢失、不同人写的风格不一致、好的工作流没法沉淀复用
- **不解决的后果**：每次都从零讲背景，AI 输出质量参差不齐，好的方法论没人能复用

## 3. 核心要点（5-8 条）
- Skill = **触发条件（when）+ 工作流（how）+ 输出模板（what）+ 注意事项（caveats）** 四件套
- 通常以 `SKILL.md` 文件形式存储，**项目级**放 `<项目>/.workbuddy/skills/<name>/`，**用户级**放 `~/.workbuddy/skills/<name>/`
- Skill 的核心价值是**复用**：写好一次，所有人和所有会话都能用，且输出风格一致
- 一个好的 Skill 要包含：清晰的描述（让 AI 知道什么时候该触发它）、明确的步骤、确定的输出模板、明确的边界（不该做什么）
- Skill 不只是"指令"——好的 Skill 会告诉 AI **用什么工具**、**遵循什么约定**、**避免什么坑**
- Skill 是**可演进的**：用着用着发现问题就改 SKILL.md，下次自动更聪明
- Skill 的粒度要合适：太粗（"帮我干活"）没用，太细（"如何输入一句话"）难维护
- **触发机制**：有的是显式调用（`learn-a-concept: Agent`），有的是 AI 自动识别场景触发

## 4. 常见误解
- ❌ "Skill = 系统提示词" → ✅ 不准确。System prompt 是全局偏好，Skill 是按场景触发的"专项手册"
- ❌ "Skill 越多越好" → ✅ 错。Skill 多到互相重叠会让 AI 不知道该用哪个，反而降低效果
- ❌ "Skill 一次写好就完事" → ✅ 错。Skill 是用出来的，要根据实际效果反复打磨
- ❌ "Skill 跟代码无关" → ✅ 错。Skill 常常会调用工具（读文件、写文件、跑命令），跟"如何让 AI 操作代码"强相关
- ❌ "Skill 可以让 AI 学会新知识" → ✅ 错。Skill 只是给指令，不能改变模型本身的能力上限

## 5. 跟其他概念的关系
- 跟 **Prompt**：Prompt 是"一次性说的话"，Skill 是"可重复用的话术包"，Skill 通常被引用展开成 Prompt
- 跟 **Agent**：Skill 是 Agent 的"技能库"，Agent 在循环里决定什么时候用哪个 Skill
- 跟 **Workflow / SOP**：Skill 是把人类 SOP"翻译"成 AI 能执行的指令版，本质是知识工程化
- 跟 **Plugin / Tool**：Plugin 是"AI 能调的功能"，Skill 是"AI 何时该怎么调"的指南，两者常配合使用
- 跟 **RAG**：Skill 告诉 AI "**怎么**做"，RAG 给 AI "**做什么的资料**"，分工不同

## 6. 一个例子 / 类比
把 Skill 想象成公司里的**岗位 SOP（标准操作流程）**：

- 新人入职不靠老员工口口相传，而是看 SOP 文档
- SOP 里写着：什么时候触发（"客户来投诉"）、怎么做（"先记录、再道歉、再升级"）、输出什么（"投诉处理单"）、哪些坑不能踩（"不要当场承诺赔偿"）
- 写得好的 SOP，新人照做就能产出老员工 80% 的水平
- **Skill 就是给 AI 的 SOP**：写得越具体，AI 输出越稳定

跟 Agent 的关系像：**Skill 是工具箱里的扳手，Agent 是会用扳手的工人**。工人决定什么时候用哪把扳手，扳手本身不管事。

## 7. 我真的懂了吗？（自检 3 题）
1. **Skill 的四件套是什么？为什么缺一不可？**（提示：触发条件、工作流、输出模板、注意事项各自的作用）
2. **项目级 Skill 和用户级 Skill 怎么区分？分别什么时候用？**（提示：仓库根目录的 `.workbuddy/skills/` vs 用户主目录的 `~/.workbuddy/skills/`）
3. **为什么说"Skill 是一次写好就完事"是错的？**（提示：Skill 是用出来的，需要根据效果持续打磨）

## 8. 下一步能去哪儿
- 📖 **Claude / WorkBuddy 的 Skill 编写规范** —— 主流平台对 Skill frontmatter、描述、触发条件的官方约定
- 📖 **Anthropic 的 "Building Effective Agents" 文章** —— 理解 Skill 跟 Agent 工作流如何配合：[anthropic.com/research/building-effective-agents](https://www.anthropic.com/research/building-effective-agents)
- 📖 **本仓库的 `.workbuddy/skills/learn-a-concept/SKILL.md`** —— 看一个真实可运行的 Skill 长什么样

---
*生成于：2026-09-05  by `learn-a-concept` Skill*