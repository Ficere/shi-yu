# 试玉 / Shi Yu

> “试玉要烧三日满，辨材须待七年期。”——白居易

面试是在有限时间内试玉辨材。**试玉是一项专门给面试官、招聘负责人和用人经理使用的候选人评估 Agent Skill，不是给候选人刷题或生成应试答案的工具。**

输入岗位描述（JD）和候选人信息，沿 JD 关键要求逐条对照证据，给出简明匹配结论，并生成温和中性的验证问题、工作样本和分轮面试流程。默认按初级面试官设计，兼顾候选人情绪与面试体验。

Shi Yu is an interviewer-side Agent Skill for hiring managers and recruiting teams. It is not a candidate interview-preparation or answer-generation tool. It compares candidate evidence directly against the job description and generates concise, candidate-aware questions, work samples, and a staged interview process.

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
这是岗位描述：<JD>。这是候选人简历：<简历>。请按 JD 逐条对照，给出简明结论、面试问题和流程。面试官经验较少。
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
| **JD 逐条对照** | 提取 5-8 条关键要求，直接对照简历证据，不重复分类 |
| **简明结论** | 先给是否建议进入下一轮，再列最多 3 个优势与待确认点 |
| **安全提问** | 默认 3-5 个中性问题，每题一个追问和初级面试官收口话术 |
| **面试流程** | 输出分轮流程（目标、面试官、时长、考察点、通过标准） |
| **面试类型** | 覆盖 10+ 岗位族，支持按主要/次要岗位族组合权重 |
| **候选人体验** | 识别紧张与防御信号，提供降压、澄清和停止追问建议 |
| **行为验证** | 基于具体经历的 STAR-L 证据，不做人格标签或诚信预判 |
| **coding 定制** | 真实任务映射、标准提示路径和统一评分量表，避免临场施压 |

<details>
<summary>JD 对照规则 / JD comparison rules</summary>

| JD 关键要求 | 简历证据 | 匹配判断 | 待确认点 |
|-------------|----------|----------|----------|
| Must-have 或关键产出 | 只摘录最相关事实 | 匹配 / 部分匹配 / 证据不足 / 不匹配 | 面试中确认的一件事 |

技能、经验、行为与业务影响只作为内部完整性检查，不默认重复输出。简历未写明时使用“证据不足 / 待确认”，不直接定性为“缺失”“夸大”或“红旗”。

</details>

## 目录结构 / Structure

```
shi-yu/
├── SKILL.md                          # 技能入口（Agent 自动读取）
├── assets/
│   └── brand/
│       ├── shi-yu-mark.svg           # 矢量标志
│       ├── shi-yu-mark.png           # GitHub/README 标志
│       ├── shi-yu-mark-128.png       # 小尺寸图标
│       ├── social-preview.svg        # 可编辑社交预览源文件
│       └── social-preview.png        # GitHub 社交预览图
├── references/
│   ├── resume-breakdown-framework.md # JD 逐条对照与证据规则
│   ├── behavioral-traits.md          # 行为证据链、STAR-L 与验证题库
│   ├── interviewer-safety.md         # 初级面试官安全问法与收场脚本
│   ├── interview-types.md            # 10+ 岗位族面试指南
│   ├── coding-interview.md           # coding 选题矩阵、形式与评分量表
│   ├── output-template.md            # 输出模板
│   └── examples.md                   # 15 个跨岗位场景示例
├── LICENSE
└── README.md
```

## License

MIT
