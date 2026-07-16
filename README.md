# deep-grill

[![Install with skills.sh](https://img.shields.io/badge/skills.sh-nxxxsooo%2Fdeep--grill-blue)](https://skills.sh)

拷问（grilling）是让 Agent 对齐你真实意图的最好方式 — 但访谈式拷问会把每个问题都抛给*你*，一次一个，哪怕那些问题 Agent 自己读读文档、翻翻代码就能回答。

**deep-grill 保留拷问的狠劲，但把举证责任还给 Agent。** 它自我拷问决策树的每一条分支，先反驳自己的答案，最后只把真正主观的分歧一次性汇总给你确认。

English: an agent skill that grills a plan autonomously — self-Q&A every branch, argue against its own answers, escalate only the subjective forks in one batch.

## 快速开始（30 秒）

1. **安装 Skill：**

   ```bash
   npx skills@latest add nxxxsooo/deep-grill
   ```

   适用于 Claude Code、Codex 以及任何遵循 Agent Skills 标准的工具。也可以为 Claude Code 手动安装：

   ```bash
   git clone https://github.com/nxxxsooo/deep-grill ~/.claude/skills/deep-grill
   ```

2. **起草或粘贴一份方案。**

3. **说：**

   > deep grill 这个方案

## 为什么需要这个 Skill

> "No one knows exactly what they want."
>
> — [The Pragmatic Programmer](https://en.wikipedia.org/wiki/The_Pragmatic_Programmer)

**问题：** 经典拷问（比如启发了本 Skill 的 [grill-me](https://github.com/mattpocock/skills/blob/main/skills/productivity/grill-me/SKILL.md)）以访谈形式一次问你一个问题。当答案在你脑子里时这很完美；但当大多数答案在代码库、文档或一次快速实验里时，串行审问只是把 Agent 的功课外包给了你 — 问到第二十个问题，做调研的人变成了你。

**解法：** 把拷问的方向反过来。Agent 自己走完决策树，逐个解决决策之间的依赖。每个问题它先自行调查 — 读文档、翻代码、派子 Agent — 给出最佳答案，再反驳一遍，站得住才算数。只有闯过这道关卡的分歧才会到你面前，一次性汇总，每条附推荐答案。在你确认达成共识之前，不动手实现。

## 参考

**模型自动触发。** 当你说「deep grill」或要求自主地压力测试一份方案时，Agent 会自动调用。它与访谈式拷问互补而非替代 — 答案在你脑子里时用访谈，答案在仓库里时用 deep-grill。

一次会话会做什么：

- 走遍决策树的每一条分支，逐个解决决策之间的依赖。
- 每个问题先自行调查，给出最佳答案，再反驳一遍才接受。
- 只把真正主观的分歧一次性汇总，每条附推荐答案。
- 在你确认达成共识之前，不动手实现。

## 许可证

MIT
