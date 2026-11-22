# Arxh Evaluation Suite

This directory preserves the first public task inventory from Arxh's earlier, general AI-agent evaluation direction. It is an **exploratory, manually oriented suite**, not an automated test runner or a validated benchmark. It is not a set of Rust machine-learning experiments; the separate proposed Rust/ML agenda is documented in [`../RESEARCH-PLAN.md`](../RESEARCH-PLAN.md). The repository currently contains no runnable agent or evaluation harness.

## Status at a glance

- **30 scenario definitions** across five areas.
- **No completed runs or task-level results** have been recorded yet; result fields in `results.json` are `null`.
- Several scenarios still need fixed prompts, input files, environments, and grading rubrics before independent evaluators can reproduce them consistently.
- There is no overall score or model leaderboard.

The purpose of publishing the suite is to make the intended evaluation visible, invite scrutiny, and provide a place to learn from both successful and unsuccessful runs—not to imply that testing has already happened.

## Directory map

| Path | Contents |
|---|---|
| [`test-suite.md`](test-suite.md) | Human-readable index of all 30 task scenarios |
| [`tasks.json`](tasks.json) | Machine-readable task inventory, grouped by category |
| [`results.json`](results.json) | Per-task result ledger; unrun or unmeasured values remain `null` |
| [`week-01/research.md`](week-01/research.md) | Research & reasoning (`TEST-01`–`TEST-10`) |
| [`week-01/files.md`](week-01/files.md) | Files & documents (`TEST-11`–`TEST-15`) |
| [`week-01/coding.md`](week-01/coding.md) | Coding (`TEST-16`–`TEST-20`) |
| [`week-01/multimodal.md`](week-01/multimodal.md) | Multimodal understanding (`TEST-21`–`TEST-25`) |
| [`week-01/computer.md`](week-01/computer.md) | Browser, computer-use, and multi-step work (`TEST-26`–`TEST-30`) |
| [`week-01/report.md`](week-01/report.md) | Summary template to complete after an evaluation run |

Task definitions and outcomes are separate on purpose: keep the task set fixed during a run, and record results only after the work has been performed and checked.

## Suggested run protocol

Use this checklist before publishing or comparing results:

1. **Pin the task set.** Record the repository commit and task IDs. Do not quietly edit a prompt, fixture, or success criterion after a run begins; material changes should create a new task-set version.
2. **Record the system configuration.** Capture the agent and model provider/version, code and prompt revisions, available tools and permissions, environment, sampling settings, timeouts, retry/attempt limits, and run date.
3. **Freeze the task inputs.** Preserve the exact user request and any documents, images, code, starting state, or external sources used. Several current scenarios are high-level descriptions, so this step is necessary before they can be reproduced.
4. **Execute and preserve evidence.** Keep the final answer or artifact and, when available, the relevant tool trace, environment state, verification command/output, errors, and human interventions. Redact credentials and private information.
5. **Grade against pre-agreed criteria.** Use direct checks (for example, file state or a test command) when a criterion is objective. For qualitative work, use a written rubric and human review. If an LLM judge is used, document its model and rubric and validate its judgments against human-reviewed examples.
6. **Report what happened.** Record the result, verification status, intervention, recovery, duration, tool errors, and concrete notes. For stochastic tasks, preserve each trial and state the sample size; a single run is not a stable estimate of performance.

For a fair comparison, keep the system configuration and task conditions consistent or clearly disclose any differences. The current `results.json` is a simple per-task ledger; it does not capture all configuration metadata, evidence, or repeated trials. Keep a linked run report or supporting artifacts with any future results rather than implying that the JSON alone is sufficient for reproduction.

## Result definitions

### `PASS`

The task's important requirements were met, and the result was checked against the success criteria.

### `PARTIAL`

The agent made meaningful progress, but one or more important requirements were incomplete, incorrect, or not sufficiently verified.

### `FAIL`

The task was not completed, or the final result was not usable for its intended purpose.

A response is not a pass merely because it is confident or well written. When the result cannot be checked, say so and grade it accordingly. In `results.json`, a `null` task status means **not run or not yet recorded**; it is not a fourth result and does not mean `FAIL`. Week-level status is separate: Week 01 is currently `not_started`.

Other result fields use the values documented in `results.json`:

- `verified`: `yes`, `no`, or `partial`
- `intervention`: `none`, `minor`, or `significant`
- `recovered`: `not needed`, `recovered`, or `failed to recover`

Notes should describe observable evidence—for example, the exact test command and its output, a source that did not support a claim, or the point at which a tool failure was recovered—not just whether the response felt good.

## Coverage

| Category | Task IDs | Count |
|---|---|---:|
| Research & reasoning | `TEST-01`–`TEST-10` | 10 |
| Files & documents | `TEST-11`–`TEST-15` | 5 |
| Coding | `TEST-16`–`TEST-20` | 5 |
| Multimodal understanding | `TEST-21`–`TEST-25` | 5 |
| Browser, computer use & multi-step work | `TEST-26`–`TEST-30` | 5 |

## Improving the suite

Useful contributions include:

- a concrete prompt and fixed input for an underspecified scenario
- a fixture or clean starting environment that can be shared safely
- success criteria that are observable and can be checked independently
- a deterministic check for objective requirements, or a calibrated rubric for qualitative ones
- examples of edge cases, tool failures, recovery behavior, and known limitations

If a task changes materially, document the change and version it rather than silently rewriting a case that may already have been evaluated. Avoid adding private user data, credentials, or other sensitive information to public task fixtures.

## Design references

- [OpenAI — Evaluate agent workflows](https://developers.openai.com/api/docs/guides/agent-evals)
- [OpenAI — Evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices)
- [Anthropic — Define success criteria and build evaluations](https://docs.anthropic.com/en/docs/test-and-evaluate/define-success)
- [Inspect AI documentation](https://inspect.aisi.org.uk/)
