# Roberto Braga

<img src="assets/rb-home.svg" width="900" alt="Roberto Braga's personal index. An indigo wireframe aperture beside the motto: Good software gives people a way to disagree.">

**Applied AI & Automation Engineer · Cubic³ · Brazil**

[01 / Research](#research) · [02 / Project index](#project-index) · [03 / Field notes](#field-notes)

I build systems that leave people enough evidence to tell them they're wrong. In practice that means testing what changed, making retries inspectable, and leaving a way to stop when the evidence isn't there.

## Research

### Stochastic Provenance

If a model reads the same prompt 32 times to give you 32 answers, which work can you skip? You can process the prompt once. The trick is making sure each answer still gets its own random draws.

I built a check that gives each path its own draws and compares the token choices against a reference. Whether that takes less time or memory is a separate test.

<p>
  <a href="https://betobraga.github.io/stochastic-provenance/stochastic-provenance-preprint.pdf"><img src="assets/88x31-paper.svg" width="88" height="31" alt="Read the preprint PDF"></a>
  <a href="https://github.com/BetoBraga/stochastic-provenance#03--run-in-under-a-minute"><img src="assets/88x31-demo.svg" width="88" height="31" alt="Run the CPU demo"></a>
  <a href="https://github.com/BetoBraga/stochastic-provenance"><img src="assets/88x31-code.svg" width="88" height="31" alt="View the source code"></a>
</p>

[Open the research site and compare the results ↗](https://betobraga.github.io/stochastic-provenance/)

**Enough buzzwords. Here are the receipts.** All **12,288 token decisions** matched in the tested matrix. On an RTX 5060 Ti, one Qwen workload ran at **2.04×** baseline speed and used **46.7% less peak allocated GPU memory**. A decode-heavy Phi case used **28.2% less** of that memory but ran at **0.59×** baseline speed. [Inspect the evidence](https://github.com/BetoBraga/stochastic-provenance/blob/main/docs/evidence.md).

<details>
<summary><strong>Open the test log: what matched?</strong></summary>

192 of 192 trajectories matched across three models and two numerical policies. Each reference pair got the same path-local draws. These are controlled tests, not a claim about every model, workload, or device.

</details>

## Project index

| File | Question it tests | Open |
| :-- | :-- | :-- |
| Workflow Replay Lab | When a document is delivered twice, does it create two records? | [Replay a case](https://betobraga.github.io/workflow-replay-lab/) |
| ContinualKit | Did a model update break a task the old version could do? | [See the evaluation toolkit](https://github.com/BetoBraga/continualkit) |

<details>
<summary><strong>Open a failure case: the write succeeded but the reply never arrived</strong></summary>

In the Replay Lab, choose **Interrupt after durable write**, reload, and run **Interrupted delivery replay**. The second event should leave the original record alone. The demonstration stores fictional data in this browser, not in an external system.

</details>

## Field notes

<details>
<summary><strong>What would make me hold a release?</strong></summary>

A better average can hide a regression on a critical task. A fluent answer can cite a source that doesn't support it. A retry can quietly create a second record. Each needs its own test, and any one of them can be a reason to wait.

</details>

**Give me a case I missed.** [Share a fictional input and what should happen next](https://github.com/BetoBraga/workflow-replay-lab/issues) · [Portfolio](https://borerto.com/)
