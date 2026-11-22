<div align="center">
  <img src="assets/arxh-header.png" alt="Arxh — AI agent research and evaluation" width="100%" />
  <p><strong>From intent to outcomes people can verify.</strong></p>
  <p>Early-stage AI agent research by Arxh AI.</p>
</div>

# Arxh

Arxh explores how AI agents can turn open-ended requests into useful, verifiable outcomes. This repository is the public research and evaluation workspace for that work: it contains a versioned task set, evaluation guidance, and a transparent record for results when runs are performed.

> **Current stage:** This repository contains documentation and evaluation data only. It does not include a runnable agent, an evaluation runner, or published performance results. The Week 01 task set is exploratory—not a validated benchmark—and some scenarios still need fixed prompts, fixtures, and grading procedures before they can be compared reproducibly.

## Why evaluate agents this way?

A plausible answer is not the same as a completed task. For a tool-using agent, reliability also depends on whether it understands the goal, chooses appropriate actions, handles errors, follows constraints, and checks the result it delivers.

Arxh's evaluation work is designed to focus on observable outcomes and supporting evidence—not polished demonstrations. Task definitions and results are kept separate so that a task can be rerun without silently changing what success means. Failures, tool errors, recovery attempts, and human interventions matter too: they help explain what to improve next.

## Week 01 evaluation scope

The initial task inventory contains 30 scenarios across five areas:

| Evaluation area | Task IDs | Count |
|---|---|---:|
| Research & reasoning | `TEST-01`–`TEST-10` | 10 |
| Files & documents | `TEST-11`–`TEST-15` | 5 |
| Coding | `TEST-16`–`TEST-20` | 5 |
| Multimodal understanding | `TEST-21`–`TEST-25` | 5 |
| Browser, computer use & multi-step work | `TEST-26`–`TEST-30` | 5 |
| **Total** | | **30** |

These are scenario definitions, not 30 completed experiments. The suite is a starting point for structured evaluation; it should not be used to claim broad agent capability or to rank models.

## Evaluation principles

1. **Define success before a run.** Keep the task, constraints, and grading criteria explicit and stable.
2. **Judge the outcome, inspect the process.** Verify the final artifact or state. Use traces and tool records to diagnose decisions, failures, and recovery.
3. **Prefer evidence to impressions.** Check sources, files, tests, and resulting state against the task requirements.
4. **Report partial results honestly.** Distinguish completion from verification, and document intervention, errors, and uncertainty.
5. **Preserve the evaluation.** Record the task-set version and run configuration. If a task changes, give the changed task a new version rather than rewriting a measured case.

## Start here

| File | Purpose |
|---|---|
| [`tests/README.md`](tests/README.md) | Evaluation status, run guidance, scoring definitions, and limitations |
| [`tests/test-suite.md`](tests/test-suite.md) | Human-readable index of all 30 scenarios |
| [`tests/tasks.json`](tests/tasks.json) | Machine-readable task inventory |
| [`tests/results.json`](tests/results.json) | Results ledger; `null` means no result has been recorded |
| [`tests/week-01/research.md`](tests/week-01/research.md) | Research & reasoning scenarios (`TEST-01`–`TEST-10`) |
| [`tests/week-01/files.md`](tests/week-01/files.md) | Files & documents scenarios (`TEST-11`–`TEST-15`) |
| [`tests/week-01/coding.md`](tests/week-01/coding.md) | Coding scenarios (`TEST-16`–`TEST-20`) |
| [`tests/week-01/multimodal.md`](tests/week-01/multimodal.md) | Multimodal scenarios (`TEST-21`–`TEST-25`) |
| [`tests/week-01/computer.md`](tests/week-01/computer.md) | Browser, computer-use, and multi-step scenarios (`TEST-26`–`TEST-30`) |
| [`tests/week-01/report.md`](tests/week-01/report.md) | Week 01 report template; complete only after a run |

No installation is required to read the task set. To validate or inspect the JSON files locally:

```bash
python3 -m json.tool tests/tasks.json
python3 -m json.tool tests/results.json
```

## Results and current limitations

No task-level results have been recorded yet. In `tests/results.json`, an unset result is represented by `null`; it is not a score of zero and should not be interpreted as a pass or a failure. No success rate, model comparison, or capability claim is published here.

The current suite is an early, manually oriented task inventory. Some cases describe a scenario without yet fixing the exact input, environment, fixture, or grading rubric. The repository also does not provide an agent implementation, run harness, or complete run-metadata schema. Those gaps limit repeatability; they should be addressed before treating results as a formal benchmark.

For a meaningful comparison, preserve at least the task-set commit, agent and model versions, prompt/configuration revision, tools and permissions, task inputs and environment, sampling and retry settings, evaluation rubric, evidence or trace, and any duration or cost measurements. The detailed run guidance and status definitions are in [`tests/README.md`](tests/README.md).

## Contributing

Thoughtful improvements are welcome—especially concrete task prompts, reusable fixtures, measurable success criteria, objective checks, and clearly described coverage gaps. Please open an [issue](https://github.com/ArxhAI/arxh/issues) or pull request when you find an ambiguity, a result that cannot be independently checked, or a useful failure case to add.

When updating a task, keep its identifier and scope stable only if its meaning is unchanged. If the input or success criteria materially change, document the change as a new task-set version so future results remain interpretable. Never add secrets or private user data to fixtures or run artifacts.

## Evaluation design references

The evaluation approach is informed by public guidance and open tooling for agent evaluation:

- [OpenAI — Evaluate agent workflows](https://developers.openai.com/api/docs/guides/agent-evals): use traces to diagnose workflow behavior and repeatable datasets for comparisons.
- [OpenAI — Evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices): define objectives, representative data, and task-specific measures; keep evaluating as systems change.
- [Anthropic — Define success criteria and build evaluations](https://docs.anthropic.com/en/docs/test-and-evaluate/define-success): make criteria specific and measurable, and choose grading methods appropriate to each criterion.
- [Inspect AI documentation](https://inspect.aisi.org.uk/): a useful reference for separating evaluation datasets, agents/solvers, and scorers.
- [SWE-bench experiments](https://github.com/swe-bench/experiments): a public example of sharing evaluation outputs and artifacts to support transparency and reproducibility.

These references inform the methodology; they do not imply that Arxh has implemented those systems or reproduced their benchmarks.

## License

There is currently no `LICENSE` file in this repository. No open-source reuse license has been granted; please do not assume the contents are licensed for reuse. Add a license before accepting or encouraging external reuse.
