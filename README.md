# Complete Task Planner

面向广泛任务的轻量规划 Skill：把自然语言描述变成清晰的思路与可执行计划。可用于工作事务、研究分析、内容创作、项目推进、学习与生活安排，按具体目标和约束调整方法。

**完整思考，精简呈现。** 一个独立的 `SKILL.md`，无必装依赖，核心文件 43 行。

## 输出什么

- 两句左右的推荐思路：做什么、为什么选择这条路线。
- 通常 3–5 步行动：每步有具体动作、产出和完成标准。
- 必要的关键提醒：先验证什么、何时调整路线。

默认首答控制在约 350 个中文字以内；复杂任务可到 500 字，简单或澄清任务通常 150 字以内。用户要求详细时可展开，并保留关键依赖与可行性条件。

## 安装

在 Codex 中发送：

```text
请把 https://github.com/Nive0895/complete-task-planner 中
skills/complete-task-planner 目录下的 Skill 安装到我的个人技能目录。
```

使用所在客户端支持的个人技能目录，也可以手动复制 `skills/complete-task-planner` 整个文件夹。安装完成后，在下一条消息中明确点名使用。

## 最简单的用法

```text
请使用 complete-task-planner 帮我规划：
我想完成……，截止时间是……，每周能投入……小时。
我已有……，最终需要交付……。先给我简版。
```

例如：

```text
请使用 complete-task-planner。
我下周要组织一次 10 人团队分享会，总共只有 6 小时准备。
目标是让大家理解新流程，已有一份说明文档。
帮我确定活动形式、准备顺序和完成标准，先给简版。
```

继续细化时说：“展开第一步，写清材料、方法和最小例子。”

完整示例见 [使用教程](TUTORIAL.md)。不同客户端的选择入口见 [OpenAI 官方说明](https://learn.chatgpt.com/docs/build-skills#how-chatgpt-and-codex-use-skills)。

## 验证

核心工作流此前经过 8 类场景、3 轮、24 份回答的行为测试，最终 8/8 达到当时预设门槛，独立代理定性评审平均 9.88/10。当前版本扩展了场景适配说明。测试方法、修改过程和局限见 [测试记录](EVALUATION.md)。

## 设计参考

本 Skill 为通用任务独立编写，参考了以下工作流思路：

- [idea-refine](https://github.com/addyosmani/agent-skills/blob/main/skills/idea-refine/SKILL.md)：探索方向并收敛方案。
- [spec-driven-development](https://github.com/addyosmani/agent-skills/blob/main/skills/spec-driven-development/SKILL.md)：先明确目标与验收。
- [planning-and-task-breakdown](https://github.com/addyosmani/agent-skills/blob/main/skills/planning-and-task-breakdown/SKILL.md)：按依赖拆成可验证任务。
- [planning-with-files](https://github.com/OthmanAdi/planning-with-files)：为长期任务保留计划与进度。

无需安装这些参考项目。本 Skill 默认在对话中交付；用户要求保存时才维护记录。文件记录不提供后台自动监控或提醒。
