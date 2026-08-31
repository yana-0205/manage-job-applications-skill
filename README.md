# Manage Job Applications — 端到端求职申请 Codex Skill

> 上传岗位链接或 JD 文本，然后只需说一句：**“投递这个岗位。”**

从岗位分析、申请资格核查和材料定制，到文件归档与投递记录更新，这个 Skill 将原本分散的求职步骤串成一套可重复执行的端到端工作流。

## 一句话能完成什么？

1. **先核查硬性要求：** 识别 visa sponsorship、工作年限、毕业年份、学历、语言、工作地点和其他可能直接影响申请资格的条件，避免在明显不符合的岗位上盲目投入时间。

2. **系统拆解 JD 与 ATS 关键词：** 提炼岗位职责、核心要求、工具、技能和高频术语，并区分 mandatory 与 preferred 条件，帮助简历更准确地覆盖 ATS 检索信息，提高与目标岗位的相关性。

3. **判断现有简历能否直接投递：** 将 JD 要求与候选人的真实经历逐项映射，评估匹配度，并明确建议 `Use the existing resume` 或 `Create a new tailored resume`，而不是默认每个岗位都重写一遍。

4. **生成有证据支撑的定制材料：** 按照专业简历修改原则重组定位、经历顺序、项目重点和 bullet 表达，生成针对岗位的单页简历与 Cover Letter。每项重要表述都必须来源于可验证经历，不虚构技能、数字或成果。

5. **自动管理申请文件：** `present/` 始终存放当前申请岗位的标准 DOCX/PDF 文件；旧版本按照 `公司 / 岗位` 自动归档到 `history/`，同时清理重复版本和 Office 临时文件。

6. **自动维护投递记录：** 检查是否已经申请过同一岗位，复用未完成记录，并按照现有表头更新投递信息，避免重复投递或破坏原有公式与格式。

## 它不只是一个简历生成 Prompt

普通提示词通常停在“帮我改简历”。这个 Skill 管理的是完整申请过程中的决策与交付：

`岗位输入 → 重复申请检查 → 硬门槛筛选 → JD/ATS 分析 → 证据匹配 → 简历复用决策 → 材料生成 → DOCX/PDF 渲染 QA → 文件归档 → 投递记录更新`

它尤其关注生成式 AI 容易忽略的部分：先判断是否值得申请、只使用真实证据、保留可靠数据、确保最终 PDF 版式正确，以及让每次申请留下清晰可追踪的文件与记录。

> One job link. One instruction. A complete, evidence-based application workflow.

## Install

Copy the skill folder into your Codex skills directory:

```bash
cp -R manage-job-applications ~/.codex/skills/
```

Restart Codex if the skill does not appear immediately.

## Project setup

Create a job-application workspace containing:

```text
job-applications/
├── AGENTS.md
├── records-of-applications.xlsx       # optional
├── sources/                           # verified resumes and evidence
└── output/
    ├── present/
    └── history/
```

Use [`examples/AGENTS.md`](examples/AGENTS.md) as a starting point. Add your own resume source files and, if you want strict visual consistency, a DOCX resume template. Do not commit private candidate data to a public repository.

## Example prompts

```text
Analyse this JD and tell me whether I meet the hard requirements before tailoring anything.
```

```text
I want to apply for this role. Decide whether my current resume can be reused, then prepare the application materials.
```

```text
Tailor my resume to this JD, keep it to one page, and show me an evidence map before drafting.
```

```text
Clean up duplicate resume versions and update my application tracker without changing unrelated rows.
```

## Design principles

1. Eligibility before optimism.
2. Evidence before keywords.
3. One canonical editable document before PDF export.
4. Rendered output, not source text, determines whether a document is finished.
5. File operations are scoped, reversible where possible, and never cross application boundaries silently.

## Privacy

The repository contains no real resume, contact details, employment history, application tracker, or candidate-specific generation script. Keep those in your private workspace.

## License

MIT — see [`LICENSE`](LICENSE).
