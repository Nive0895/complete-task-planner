# Complete Task Planner

将自然语言任务变成有依据的思路与分层行动计划，适配工作、研究、创作、项目、学习和生活安排。

**先看清全局，再逐层展开。** 核心是一个独立的 `SKILL.md`，共 53 行，无必装依赖。教程、示例和测试记录放在仓库中，不随每次调用加载。

## 输出长什么样

```text
大方向：目标、推荐路线、理由与关键假设
  ↓
路线总览：确定场景 → 做出样例 → 试用修正 → 完成交付
  ↓
阶段 1｜明确目标
  1.1 具体动作与直接产出
  1.2 具体动作与直接产出
  完成标志：用什么证据判断这一阶段完成
阶段 2｜做出可试用样例
  2.1 ……
  2.2 ……
  完成标志：……
  ↓
建议补充的考虑：可能遗漏什么 → 为什么重要 → 怎么补上
现在先做：一个明确的起步动作
```

普通多步任务通常分为 **3–5 个大步骤，每步 2–4 个小步骤**，按任务复杂度调整。默认约 600–1000 个中文字，复杂任务可到 1500 字；用户可以要求简版或展开指定阶段。简单请求直接回答，不强行套完整结构。

默认用清晰标题、编号和留白。有真实并行、依赖或分支时，可补充 Mermaid 流程图；客户端有相应能力时，可以提供可展开的阶段视图。所有阶段目标和关键建议保持可见，操作细节逐层展开。交互展示并非所有客户端都支持，纯文字计划始终可读。

参见 [完整输出示例](EXAMPLE.md) · [使用教程](TUTORIAL.md) · [测试记录](EVALUATION.md)。

## 安装与使用

在支持技能安装的 Codex 对话中发送：

```text
请把 https://github.com/Nive0895/complete-task-planner 中
skills/complete-task-planner 目录下的 Skill 安装到我的个人技能目录。
```

也可以将该文件夹复制到所在客户端支持的个人技能目录。安装完成后，明确点名使用：

```text
请使用 complete-task-planner 帮我规划：
我的目标是……，目前想这样做……，截止时间是……。
我已有……，能投入……，最终需要交付……。
请给出大方向、几大步和每步的小步骤，并指出我的思路可能遗漏的考虑。
```

继续细化：`只展开阶段 2，补充具体方法、材料和最小例子，保留其他阶段。`

## 验证

当前分层版本完成了 4 个场景的独立试答与内容复核：团队分享、搬家、零基础学习和直接写提醒。四例均通过本轮检查，包含时间预算、验收、遗漏建议和简单请求边界。三个规划回答分别为 933、1025、1078 个汉字；直接提醒为 19 个字符。

这是有限场景的行为检查，并非全面质量保证。此前版本的 8 场景测试及评分单独保留在 [测试记录](EVALUATION.md)，不作为当前版本的新评分。

## GitHub 设计参考

以下是 2026-09-08 查询到的**仓库级** Star 数，仅作社区认可度参考，不是单个 Skill 的效果评分。本 Skill 独立编写，吸收通用方法，不复制整套开发工作流。

| 项目 | Stars（约） | 本次采用的思路 |
|---|---:|---|
| [obra/superpowers](https://github.com/obra/superpowers/blob/main/skills/writing-plans/SKILL.md) | 283k | 阶段拆成具体小步骤，设置可验证的交付物 |
| [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) | 92.9k | [idea-refine](https://github.com/addyosmani/agent-skills/blob/main/skills/idea-refine/SKILL.md) 检查假设；[planning-and-task-breakdown](https://github.com/addyosmani/agent-skills/blob/main/skills/planning-and-task-breakdown/SKILL.md) 安排依赖与验收 |
| [markmap/markmap](https://github.com/markmap/markmap) | 13.1k | 从层级文本看全局，再展开细节 |
| [mermaid-js/mermaid](https://github.com/mermaid-js/mermaid) | 90.2k | 用简洁的文本图表达依赖、并行和分支 |

此前也参考了 [spec-driven-development](https://github.com/addyosmani/agent-skills/blob/main/skills/spec-driven-development/SKILL.md) 的目标与验收思路，以及 [planning-with-files](https://github.com/OthmanAdi/planning-with-files) 的持续记录方式。

无需安装这些参考项目。默认在对话中交付，用户要求保存时才维护计划记录；文件保存不提供后台自动跟踪或提醒。