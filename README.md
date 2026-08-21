# 试玉 / Shi Yu

> “试玉要烧三日满，辨材须待七年期。”——白居易

面试是在有限时间内试玉辨材。**试玉是一项专门给面试官、招聘负责人和用人经理使用的候选人评估 Agent Skill，不是给候选人刷题或生成应试答案的工具。**

输入岗位描述（JD）和候选人信息，按技能、经验、行为特征、业务影响四维拆解与排序，评估匹配程度，并生成关键提问、工作样本和分轮面试流程。覆盖商务、业务、研究、开发、产品、数据、设计、管理、质量合规、制造实验等岗位族。

Shi Yu is an interviewer-side Agent Skill for hiring managers and recruiting teams. It is not a candidate interview-preparation or answer-generation tool. It breaks down a resume into four ranked dimensions, evaluates fit against a job description, and generates evidence-based questions, work samples, and a staged interview process.

遵循 [Agent Skills 开放标准](https://agentskills.io)，兼容 Claude Code、Cursor、GitHub Copilot、Codex、Windsurf、Gemini CLI、Perplexity Computer 等 30+ AI Agent 平台。

## 安装 / Install

```bash
npx skills add Ficere/shi-yu
```

> 需要 Node.js。安装后 Agent 会自动发现并按需加载该技能。
>
> Requires Node.js. Once installed, your agent will auto-discover and load this skill when relevant.

<details>
<summary>其他安装方式 / Alternative methods</summary>

**手动安装 / Manual install：**

```bash
git clone https://github.com/Ficere/shi-yu.git
# 将整个目录复制到你的 Agent 的 skills 目录下即可
# Copy the directory to your agent's skills folder:
#   Claude Code:  ~/.claude/skills/
#   Cursor:       .cursor/skills/
#   Copilot:      .github/skills/
#   Codex:        ~/.codex/skills/
#   Gemini CLI:   .gemini/skills/
```

**Perplexity Computer：**

下载本仓库 zip → 在 [Skills 管理页面](https://www.perplexity.ai/computer/skills) 上传。

</details>

## 使用 / Usage

安装后由面试官直接用自然语言触发，需提供岗位描述（JD）与候选人信息，可选提供面试类型与要求：

```
这是岗位描述：<JD>。这是候选人简历：<简历>。帮我拆解简历并评估匹配度，给出面试提问和流程。
```

```
JD 是算法负责人，候选人是 5 年 AI 制药计算科学家，侧重研究，并考察 coding 能力。
```

```
帮我评估这个候选人是否适合 BD 总监岗位，侧重商务谈判能力。
```

```
候选人简历在这里，帮我设计一个分轮面试流程，要求包含系统设计轮。
```

## 功能 / Features

| 模块 | 说明 |
|------|------|
| **四维拆解** | 技能、经验、行为特征、业务影响分别列出并排序，标注证据等级 |
| **匹配评估** | 对照 JD 逐条评估，给出整体匹配度、优势、缺口、风险点 |
| **关键提问** | 按维度生成 STAR 行为面试提问，标注考察目的与红旗信号 |
| **面试流程** | 输出分轮流程（目标、面试官、时长、考察点、通过标准） |
| **面试类型** | 覆盖 10+ 岗位族，支持按主要/次要岗位族组合权重 |
| **行为验证** | 行为假设、替代解释、STAR-L 与反证追问，避免人格标签 |
| **coding 定制** | 六维选题矩阵、岗位任务映射、多种面试形式、统一评分量表 |

<details>
<summary>四维拆解细则 / Breakdown dimensions</summary>

| 维度 | 拆解内容 | 排序依据 |
|------|----------|----------|
| 技能 Skills | 硬技能、软技能、工具、领域知识、语言 | 与 JD 相关性 + 熟练度证据强度 |
| 经验 Experience | 项目、年限、行业、规模、复杂度、角色 | 与 JD 相关度 + 深度 + 时间远近 |
| 行为特征 Behavioral traits | 工作风格、价值观、协作模式、动机 | 证据强度 + 与岗位文化匹配度 |
| 业务影响 Business impact | 量化成果、可衡量贡献、ROI | 量化程度 + 与岗位目标相关性 |

每项标注证据等级：`[陈述]` 简历明确写出、`[推断]` 合理推断、`[缺失]` 材料未覆盖。

</details>

## 目录结构 / Structure

```
shi-yu/
├── SKILL.md                          # 技能入口（Agent 自动读取）
├── references/
│   ├── resume-breakdown-framework.md # 四维拆解框架与排序规则
│   ├── behavioral-traits.md          # 行为证据链、STAR-L 与验证题库
│   ├── interview-types.md            # 10+ 岗位族面试指南
│   ├── coding-interview.md           # coding 选题矩阵、形式与评分量表
│   ├── output-template.md            # 输出模板
│   └── examples.md                   # 14 个跨岗位场景示例
├── LICENSE
└── README.md
```

## License

MIT
