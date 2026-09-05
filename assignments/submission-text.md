# 作业 1 提交文本（学习通文本框用）

> ⚠️ 先对着老师的作业图核对格式模板，有出入就改，别直接整段粘贴。
> 内容可全部或部分放入学习通提交框；若文本框太短，只贴「一、仓库信息」+ 仓库链接即可。

---

**《大数据与人工智能》作业 1：用 AI 构建个人概念学习资料生成 Skill**

**一、仓库信息**

- 仓库名称：`concept-skill-lab`
- 仓库地址：https://github.com/mikang-bdai/concept-skill-lab
- 可见性：public（教师可直接查看）
- 本地路径：`D:\wawa\concept-skill-lab`
- 提交历史：6 个语义清晰的 commit（init → notes → docs → materials → chore → docs），本地与远程一致

**二、Skill 设计**

- Skill 名称：`learn-a-concept`
- 类型：项目级 Skill（WorkBuddy 平台）
- 存放路径：仓库根目录下 `.workbuddy/skills/learn-a-concept/SKILL.md`
- 功能：输入任意概念 → 按 8 章节结构化模板生成学习资料，自动落盘 `notes/`
- 输出模板 8 章节：① 一句话定义 ② 解决什么问题 ③ 核心要点（5-8 条）④ 常见误解 ⑤ 跟其他概念的关系 ⑥ 一个例子/类比 ⑦ 自检 3 题 ⑧ 下一步参考来源
- 设计要素：触发条件（frontmatter description）+ 工作流 + 输出模板 + 注意事项（不编造、先读后改、编号排序），体现个人学习设计

**三、已生成的学习资料**

按作业要求调用 Skill 学习了三个概念，产出 HTML 排版版（`learning-materials/`）：

1. Agent 是什么 → https://github.com/mikang-bdai/concept-skill-lab/blob/main/learning-materials/agent.html
2. 大模型的上下文 → https://github.com/mikang-bdai/concept-skill-lab/blob/main/learning-materials/llm-context.html
3. Skill 是什么 → https://github.com/mikang-bdai/concept-skill-lab/blob/main/learning-materials/skill.html

补充「概念关系」页（作业要求的概念关系维度）：

4. Agent · 上下文 · Skill 三者关系 → https://github.com/mikang-bdai/concept-skill-lab/blob/main/learning-materials/concept-relationship.html

（另有 markdown 源稿存放于 `notes/`，可在 GitHub 直接查看渲染效果）

**四、AI 协助 + 人工核查**

AI 协助了：Skill 整体结构设计、三份学习资料的初稿生成、markdown → HTML 排版（卡片/关系图/误解对比/自检折叠/互链）、README 与作业存档整理、git/API 命令编写。

人工核查了：概念解释准确性（Agent 三件套、Skill 四件套、上下文窗口均为业界共识，无编造成分）；外链有效性（ReAct / Lost in the Middle 论文、Anthropic 官方文章均可访问）；目录结构与作业要求逐项对照；自测题可独立作答。资料来源未伪造，概念解释不是整段照搬 AI 对话。

**五、版本与安全**

- 全部内容已 commit 并 push 到 GitHub（public）
- `.gitignore` 已排除：Python/venv 缓存、临时 push 脚本、本地配置等；仓库内无 API Key、密码、个人隐私或敏感文件

---

## 自查清单（提交前快速核对）

- [ ] 学习通提交格式与老师要求模板一致（尤其有没有规定：只贴链接？还是要有文字说明？）
- [ ] 仓库是 public（https://github.com/mikang-bdai/concept-skill-lab 无痕打开可看）
- [ ] 4 个 HTML 都能打开渲染
- [ ] 目录结构与作业要求一致（.workbuddy/skills/、learning-materials/、README.md、.gitignore）
- [ ] 提交框里贴的仓库链接末尾无多余字符
