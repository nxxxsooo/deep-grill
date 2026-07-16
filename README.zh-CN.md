<p align="right">
  <a href="./README.md"><img src="https://img.shields.io/badge/README-English-111418?style=flat-square" alt="Read in English"></a>
</p>

<p align="center">
  <img src="./assets/release/deep-grill-launch-cn-portrait.png" alt="deep-grill——让 Agent 先拷问自己" width="560">
</p>

<h1 align="center">deep-grill</h1>

<p align="center"><strong>让 Agent 先拷问自己。</strong></p>

<p align="center">
  一个自主调查方案每条分支、反驳自身答案，<br>
  最后只把真正主观的分歧一次性交给你的 Agent Skill。
</p>

<p align="center">
  <a href="#快速开始"><img src="https://img.shields.io/badge/skills.sh-nxxxsooo%2Fdeep--grill-111418" alt="通过 skills.sh 安装"></a>
  <a href="./LICENSE"><img src="https://img.shields.io/badge/license-MIT-ff5c4d" alt="MIT 许可证"></a>
  <a href="./README.md"><img src="https://img.shields.io/badge/README-English-111418" alt="Read in English"></a>
</p>

拷问是让 Agent 对齐你真实意图的好方法。但访谈式拷问会把每个问题都抛给*你*，一次一个——包括那些 Agent 本可以通过阅读代码、检查文档或运行一次小实验自行回答的问题。

**deep-grill 保留拷问的狠劲，但把举证责任还给 Agent。** 它自己走完决策树，先调查再回答，再反驳自己的结论，最后只把真正需要人类判断的分歧一次性汇总给你。

## 正文就这么长

deep-grill 一共三段话。以下就是你要安装的完整 [`SKILL.md`](./SKILL.md) 正文：

> Interrogate every material branch yourself, resolving dependencies between decisions one by one: investigate via the code, docs, tests, tools, and subagents; choose the best answer; then argue against it and revise until it survives or becomes genuinely subjective.
>
> Spend available token budget on deeper internal investigation, not more user questions; when constrained, prioritize high-impact branches and disclose what remains unexamined.
>
> Ask only about choices that depend on the user's goals, taste, or authority, or facts unavailable after reasonable investigation. Surface them in one batch with recommendations, then wait for confirmation before enacting the plan.

三段各自的作用：

- **回答、反驳、修正。** 每个暂定答案都要扛住针对它的最强反驳——扛不住就修正，修不动才作为真正主观的分歧升级。
- **预算花在调查上。** token 用来往深处挖，而不是多问几轮；没来得及查的部分明确披露，绝不静默跳过。
- **精确的升级门槛。** 只升级取决于你的目标、品味、权限，或合理调查也拿不到的事实——一次性汇总、附推荐答案，确认前不动手实现。

## 快速开始

1. 安装 Skill：

   ```bash
   npx skills@latest add nxxxsooo/deep-grill
   ```

2. 起草或粘贴一份方案。

3. 说：

   > deep grill this plan

> [!TIP]
> 在 Claude Code、Codex 及其他兼容 Agent Skills 的工具中，直接点名 Skill 是最可靠的触发方式。

## 为什么需要它

> 「没有人一开始就完全知道自己想要什么。」
>
> ——《程序员修炼之道》

经典拷问——例如启发了本 Skill 的 [`grill-me`](https://github.com/mattpocock/skills/blob/main/skills/productivity/grill-me/SKILL.md)——很适合处理答案存在你脑子里的问题。但如果大部分答案藏在仓库、文档、测试或一次快速实验里，串行访谈只是在把 Agent 的功课外包给用户。问到第二十个问题，真正做调查的人已经变成了你。

deep-grill 把方向反过来：

- 项目事实先从代码、文档、测试和可用工具中调查。
- 每个暂定答案都要经过自我反驳才能被接受。
- 只有真正主观的选择才会升级给你。
- 所有主观分歧一次性汇总，并附推荐答案。
- 在你确认达成共识之前，不开始实现。

## 工作方式

<p align="center">
  <img src="./assets/release/deep-grill-workflow-cn.png" alt="deep-grill 工作流程：方案、证据、自我拷问循环与主观分歧" width="100%">
</p>

1. **画出决策树。** 找出分支、依赖、假设与未知项。
2. **先调查。** 阅读相关来源并运行必要检查，再决定是否询问用户。
3. **先回答，再反驳。** 给出最佳答案，并提出反对它的最强理由。
4. **只升级无法客观解决的选择。** 把主观分歧集中成一批，每条附推荐答案。
5. **等待对齐。** 在确认达成共识前，不进入实现。

## 该选哪一种拷问

<p align="center">
  <img src="./assets/release/deep-grill-comparison-cn-square.png" alt="经典拷问与 deep-grill 的中文对比" width="760">
</p>

| 答案主要在哪里 | 使用方式 | 交互模式 |
| --- | --- | --- |
| 用户的目标、审美或尚未表达的偏好里 | 访谈式拷问 | 每次询问一个聚焦的问题 |
| 仓库、文档、测试、工具或实验里 | **deep-grill** | 自主调查，再集中确认主观选择 |

deep-grill 与访谈式拷问互补，而不是取代它。

## 如何可靠触发

最通用、最明确的触发语是：

> deep grill this plan

也可以把完整意图说出来：

> 自主压力测试这个方案的每一条分支。能从仓库或文档查到的先自行调查，反驳自己的结论，最后只把真正主观的决策一次性汇总给我。

不同 Agent 工具匹配 Skill 描述的方式并不完全相同。如果需要确定触发，请直接点名 `deep-grill`。

## 手动安装

`skills` CLI 适用于 Claude Code、Codex 以及其他遵循 Agent Skills 标准的工具。为 Claude Code 手动安装：

```bash
git clone https://github.com/nxxxsooo/deep-grill ~/.claude/skills/deep-grill
```

## 许可证

[MIT](./LICENSE)
