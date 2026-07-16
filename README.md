<p align="right">
  <a href="./README.zh-CN.md"><img src="https://img.shields.io/badge/README-中文说明-ff5c4d?style=flat-square" alt="阅读中文说明"></a>
</p>

<p align="center">
  <img src="./assets/release/deep-grill-social-preview.png" alt="deep-grill — the agent grills itself first" width="100%">
</p>

<h1 align="center">deep-grill</h1>

<p align="center"><strong>The agent grills itself first.</strong></p>

<p align="center">
  An Agent Skill that investigates every branch of a plan, argues against its own answers,<br>
  and escalates only the genuinely subjective forks — in one decision batch.
</p>

<p align="center">
  <a href="#quickstart"><img src="https://img.shields.io/badge/skills.sh-nxxxsooo%2Fdeep--grill-111418" alt="Install with skills.sh"></a>
  <a href="./LICENSE"><img src="https://img.shields.io/badge/license-MIT-ff5c4d" alt="MIT License"></a>
</p>

Grilling is one of the best ways to align an agent with what you actually want. But interview-style grilling asks *you* every question, one at a time — including the questions the agent could answer by reading the code, checking the docs, or running a small experiment.

**deep-grill keeps the relentlessness and moves the burden of proof back to the agent.** It walks the decision tree itself, investigates before answering, argues against its own conclusion, and brings you only the forks that truly require human judgment.

## Quickstart

1. Install the skill:

   ```bash
   npx skills@latest add nxxxsooo/deep-grill
   ```

2. Draft or paste a plan.

3. Say:

   > deep grill this plan

> [!TIP]
> Naming the skill explicitly is the most reliable trigger across Claude Code, Codex, and other Agent Skills-compatible harnesses.

## Why this exists

> “No one knows exactly what they want.”
>
> — *The Pragmatic Programmer*

Classic grilling — such as [`grill-me`](https://github.com/mattpocock/skills/blob/main/skills/productivity/grill-me/SKILL.md), which inspired this skill — is excellent when the answers live in your head. It becomes expensive when most answers live in the repository, documentation, tests, or a quick experiment. Twenty questions later, the user is doing the agent's homework.

deep-grill reverses that direction:

- Project facts are investigated in the code, docs, tests, and available tools.
- Each provisional answer is challenged before it is accepted.
- Only genuinely subjective decisions are escalated.
- Those decisions arrive together, each with a recommended answer.
- Implementation waits until you confirm shared understanding.

## How it works

<p align="center">
  <img src="./assets/release/deep-grill-workflow.png" alt="deep-grill workflow: plan, evidence, self-grill loop, and subjective forks" width="100%">
</p>

1. **Map the decision tree.** Identify branches, dependencies, assumptions, and unknowns.
2. **Investigate first.** Read the relevant sources and run focused checks before asking the user.
3. **Answer, then argue.** Name the best answer and make the strongest case against it.
4. **Escalate the irreducible choices.** Batch only the subjective forks, each with a recommendation.
5. **Wait for alignment.** Do not implement until shared understanding is confirmed.

## Choose the right grill

<p align="center">
  <img src="./assets/release/deep-grill-comparison-square.png" alt="Classic grilling compared with deep-grill" width="760">
</p>

| Where the answers live | Use | Interaction pattern |
| --- | --- | --- |
| In the user's goals, taste, or unstated preferences | Interactive grilling | Ask one focused question at a time |
| In the repository, docs, tests, tools, or experiments | **deep-grill** | Investigate autonomously, then batch the subjective choices |

deep-grill complements interactive grilling; it does not replace it.

## Trigger it reliably

The portable, explicit trigger is:

> deep grill this plan

You can also state the full intent:

> Autonomously stress-test every branch of this plan. Investigate anything you can answer from the repository or docs, argue against your own conclusions, and bring me only the subjective decisions in one batch.

Automatic invocation depends on how each agent harness matches skill descriptions. If you need deterministic behavior, name `deep-grill` directly.

## Manual installation

The `skills` CLI works with Claude Code, Codex, and other harnesses that follow the Agent Skills standard. For a manual Claude Code installation:

```bash
git clone https://github.com/nxxxsooo/deep-grill ~/.claude/skills/deep-grill
```

## License

[MIT](./LICENSE)
