# deep-grill

An agent skill that stress-tests a plan or design **autonomously**: the agent grills the plan itself — investigating every branch of the decision tree, naming the best answer, then arguing against it — and only brings you the genuinely subjective calls, in one consolidated batch.

It is the self-driven counterpart to interactive "grill me" sessions ([mattpocock/skills → grill-me](https://github.com/mattpocock/skills/blob/main/skills/productivity/grill-me/SKILL.md), which inspired this). Interactive grilling asks *you* one question at a time; deep-grill answers its own questions first and escalates only what it can't resolve alone.

中文：让 Agent 先自我拷问整个方案 — 逐分支调查、给出答案、再自我反驳 — 只把真正主观的分歧一次性汇总给你确认。

## Install

With the [skills CLI](https://skills.sh) (works with Claude Code, Codex, and other harnesses following the Agent Skills standard):

```sh
npx skills add nxxxsooo/deep-grill
```

Or manually, for Claude Code:

```sh
git clone https://github.com/nxxxsooo/deep-grill ~/.claude/skills/deep-grill
```

## Use

Draft or paste a plan, then say:

> deep grill this plan

The agent will:

1. Walk every branch of the decision tree, resolving dependencies one by one.
2. Investigate each question itself (docs, code, subagents), name the best answer, and argue against it before accepting it.
3. Surface only the genuinely subjective forks in one batch, each with a recommended answer.
4. Hold off on implementation until you confirm shared understanding.

## Why batch instead of interview?

One-question-at-a-time grilling is great when the answers live in your head. When most answers live in the codebase or the docs, serial interrogation just outsources the agent's homework to you. deep-grill keeps the relentlessness but moves the burden of proof back to the agent.

## License

MIT
