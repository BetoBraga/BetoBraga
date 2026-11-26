# Roberto Braga

Applied AI & Automation Engineer at Cubic³. I work on model evaluation and service automation.

## Good software gives people a way to disagree.

The interesting part starts after a model gives an answer. Someone has to work out what to trust, what to try again, and when to stop. I build from that moment backward: make the evidence visible, test what can change, and leave the person using the system a way to intervene.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/decision-design-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/decision-design-light.svg">
  <img width="800" alt="A decision is a handoff. Propose: what is it suggesting? Check: what supports it? Decide: who can say no?" src="assets/decision-design-dark.svg">
</picture>

<details>
<summary>What would make me hold a release?</summary>

A better average can hide a task that used to work. A convincing answer can point to a source that doesn't support it. A retry can quietly create a second record. Those are separate tests, and any one of them can be a reason to wait.

</details>

## Selected work

### Stochastic Provenance

If a model reads the same prompt 32 times to give you 32 answers, which work can you skip? You can read the prompt once. The harder part is making sure each answer still gets its own random draws.

Prefix caching saves work. I wanted a way to know it hadn't changed the experiment. So I built a check that gives each path its own draws and replays them against a reference. Same token choices? Good. Lower GPU cost? That's a separate test.

**Enough buzzwords. Here are the receipts.** All **12,288 token decisions** matched in the semantic tests. One Qwen workload ran **2.04× faster** and used **46.7% less peak allocated GPU memory** on an RTX 5060 Ti. A decode-heavy Phi run saved **28.2%** of that memory and still took **about 70% longer**. That's why I measure both.

**[Run the CPU demo](https://github.com/BetoBraga/stochastic-provenance#03--run-in-under-a-minute)** · [See how the numbers were measured](https://github.com/BetoBraga/stochastic-provenance/blob/main/docs/evidence.md)

### Other things you can try

- **[Workflow Replay Lab](https://betobraga.github.io/workflow-replay-lab/):** four fictional document deliveries. Inspect why the workflow writes, skips, or asks for review.
- **[ContinualKit](https://github.com/BetoBraga/continualkit):** an early toolkit for measuring what a model forgets after an update. See the [critical-task gate in review](https://github.com/BetoBraga/continualkit/pull/8).

**What would you make it fail on?** [Send a fictional test case](https://github.com/BetoBraga/workflow-replay-lab/issues) and say what the system should do instead.

[borerto.com](https://borerto.com/)
