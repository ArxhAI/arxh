# Week 01 Evaluation Report Template

Use this template to summarize Arxh’s first structured evaluation run. Complete it only after tasks have actually been run and their outcomes checked. Until then, the headings and prompts are a blank reporting structure, not findings. Do not fill the template with plausible examples that could be mistaken for real results.

Per-task results belong in [`../results.json`](../results.json). Category-level notes live in `research.md`, `files.md`, `coding.md`, `multimodal.md`, and `computer.md`. This report covers the separate exploratory general-agent evaluation suite; it does not report Rust ML or deep-learning experiments.

## Run metadata — fill after execution

- **Run identifier:** [assign a stable identifier after a run exists]
- **Date and time range:** [record actual start/end and time zone]
- **Repository revision:** [commit hash or exact task-set revision]
- **Task-set version:** [identify the exact prompts and fixtures used]
- **System under test:** [agent/model/provider/version if known]
- **Prompt and configuration revision:** [record where applicable]
- **Tools and permissions:** [list the tools actually available]
- **Environment:** [browser/OS/runtime and relevant configuration]
- **Attempt and retry policy:** [state the pre-agreed limits]
- **Tasks attempted:** [IDs and number of trials]
- **Unavailable or skipped tasks:** [IDs and reasons]

If a field is unknown, say “not recorded” rather than inventing it. If tasks were run under more than one configuration, create separate rows or reports. Do not combine different models, prompt versions, tool sets, or fixtures into one result without describing the changes.

## What we tested

The inventory contains 30 exploratory scenarios across:

- research and reasoning (`TEST-01`–`TEST-10`)
- files and documents (`TEST-11`–`TEST-15`)
- coding (`TEST-16`–`TEST-20`)
- multimodal work (`TEST-21`–`TEST-25`)
- browser, computer, and multi-step work (`TEST-26`–`TEST-30`)

List the task IDs actually attempted in this run. The presence of a task in the inventory does not mean it was executed. State any changes from the original prompt or fixture, and identify the task-set revision used for grading.

## Run procedure and evidence

[Describe the order of tasks, how inputs were supplied, and how outputs were preserved. Link only to artifacts that exist and are safe to share.]

For each result, preserve enough evidence to support the grade: final response or artifact, direct verification output where available, relevant tool failures, recovery attempts, and human intervention. Remove credentials and private user information. If an outcome cannot be independently checked, state why and reflect that in the verification field.

## Results summary — fill only after grading

| Category | Attempted tasks | Pass | Partial | Fail | Not run | Verification notes |
|---|---:|---:|---:|---:|---:|---|
| Research & reasoning | — | — | — | — | — | — |
| Files & documents | — | — | — | — | — | — |
| Coding | — | — | — | — | — | — |
| Multimodal | — | — | — | — | — | — |
| Browser / computer / multi-step | — | — | — | — | — | — |

Do not publish an overall score unless a scoring rule was specified before the run and its meaning is defensible. Report denominators, skipped tasks, repeat counts, and uncertainty. A single pass on one task is not evidence of broad system capability. If an evaluator changes a task or rubric after seeing an output, report that change and do not silently grade the original run against the revised criteria.

## What happened

[Write this section after task execution. Describe observed outcomes, not expectations.]

## Strong areas

[Include only recurring or directly supported observations. Cite task IDs and evidence.]

## Failure patterns

[Describe mistakes, missing steps, unsupported claims, or tool errors with task IDs and examples.]

## Recovery

[State which failures were recovered, which were not, and what changed in the attempt.]

## Verification and human intervention

[Describe checks performed, verification gaps, evaluator actions, and any intervention required.]

## Limitations and open questions

[Record underspecified tasks, small sample sizes, environment limitations, stochasticity, rubric uncertainty, or missing controls.]

## Next evaluation

[Propose changes based on the evidence. State which tasks should be repeated, which new fixtures are needed, and how the next task-set version will be identified. Do not change task definitions quietly if earlier runs need to remain comparable.]

## Status and scope reminder

The current suite has 30 definitions and no recorded task-level results. Until a run has occurred, leave all result fields blank or marked “not run.” This report is not a result for Rust machine learning, neural-network methods, model training, or framework performance. The separate [two-month research plan](../../RESEARCH-PLAN.md) remains proposed and must be reported independently.

## Reporting references

The protocol draws on OpenAI’s [agent workflow evaluation guide](https://developers.openai.com/api/docs/guides/agent-evals), [evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices), and Inspect AI [documentation](https://inspect.aisi.org.uk/). These are design references and do not validate the Arxh task inventory by themselves.
