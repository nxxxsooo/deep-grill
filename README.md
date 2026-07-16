# deep-grill

[![Install with skills.sh](https://img.shields.io/badge/skills.sh-nxxxsooo%2Fdeep--grill-blue)](https://skills.sh)

Grilling sessions are the best way to align an agent with what you actually want — but interview-style grilling asks *you* every question, one at a time, even the ones the agent could answer itself by reading the docs or the code.

**deep-grill keeps the relentlessness and moves the burden of proof back to the agent.** It self-interrogates every branch of the decision tree, argues against its own answers, and brings you only the genuinely subjective calls — in one consolidated batch.

中文：让 Agent 先自我拷问整个方案 — 逐分支调查、给出答案、再自我反驳 — 只把真正主观的分歧一次性汇总给你确认。

## Quickstart (30-second setup)

1. **Install the skill:**

   ```bash
   npx skills@latest add nxxxsooo/deep-grill
   ```

   Works with Claude Code, Codex, and any harness following the Agent Skills standard. Or install manually for Claude Code:

   ```bash
   git clone https://github.com/nxxxsooo/deep-grill ~/.claude/skills/deep-grill
   ```

2. **Draft or paste a plan.**

3. **Say:**

   > deep grill this plan

## Why This Skill Exists

> "No one knows exactly what they want."
>
> — [The Pragmatic Programmer](https://en.wikipedia.org/wiki/The_Pragmatic_Programmer)

**The Problem:** Classic grilling (like [grill-me](https://github.com/mattpocock/skills/blob/main/skills/productivity/grill-me/SKILL.md), which inspired this) interviews you one question at a time. That's perfect when the answers live in your head. But when most answers live in the codebase, the docs, or a quick experiment, serial interrogation just outsources the agent's homework to you — twenty questions deep, you're doing the research it should have done.

**The Fix:** Flip the direction of the grilling. The agent walks the decision tree itself, resolving dependencies one by one. For each question it investigates first — docs, code, subagents — names the best answer, then argues against it before accepting it. Only the forks that survive that gauntlet reach you, batched, each with a recommended answer. Nothing gets built until you confirm shared understanding.

## Reference

**Model-invoked.** The agent triggers it when you say "deep grill" or ask for a plan to be stress-tested autonomously. Pairs with, rather than replaces, interactive grilling — use an interview when the answers live in your head, deep-grill when they live in the repo.

What a session does:

- Walks every branch of the decision tree, resolving dependencies one by one.
- Investigates each question itself, names the best answer, and argues against it before accepting it.
- Surfaces only the genuinely subjective forks in one batch, each with a recommended answer.
- Holds off on implementation until you confirm shared understanding.

## License

MIT
