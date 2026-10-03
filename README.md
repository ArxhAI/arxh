<div align="center">
  <img src="assets/arxh-header.png" alt="Say Hello To Arxh" width="100%" />
</div>

# arxh

Experimental AI agent research by Arxh Al, exploring how AI can understand real-world problems, work toward user goals, and deliver useful results through reasoning, computer use, persistent tasks, multimodal interaction, and connected tools. Currently in early development and testing.

## Why this repo exists

Most agent demos are written by the people building the agent. This repository exists to be harsher than that.

Arxh is given real tasks — ambiguous, multi-step, and occasionally broken — and then judged on what it produced, not on how impressive the process looked along the way. Failures are kept in the record next to successes, because a failure that gets studied is worth more than a success that gets celebrated.

The current focus is **testing**. There is no product surface here yet. There is a test suite and an honest place to put the results.

## Evaluation principle

We do not optimize the test set to make Arxh look good.

A successful run is useful. A failed run is useful too.

Each result should help answer one question:

> What should we improve next?

## Week 01 test set

30 tasks across five areas:

| Category | Tasks | Count |
|---|---|---:|
| Research & reasoning | TEST-01 – TEST-10 | 10 |
| Files & documents | TEST-11 – TEST-15 | 5 |
| Coding | TEST-16 – TEST-20 | 5 |
| Multimodal | TEST-21 – TEST-25 | 5 |
| Browser / computer / multi-step | TEST-26 – TEST-30 | 5 |
| **Total** | | **30** |

The tests are intentionally different. Some are straightforward. Some contain ambiguity. Some require multiple tools. Some are designed to expose weak verification or poor recovery.

## What we record per run

- task status
- result quality
- verification
- recovery
- intervention
- duration
- tool errors
- evaluator notes

### Result states

- **PASS** — the task was completed correctly and the important output was verified.
- **PARTIAL** — meaningful progress, but the final result was incomplete, incorrect, or insufficiently verified.
- **FAIL** — the task could not be completed, or the final result was not usable.

A task is not considered a success simply because Arxh produced an answer. The final result must be checked against the task requirements.

## Repository structure

```
arxh/
├── README.md
├── tests/
│   ├── README.md
│   ├── test-suite.md
│   ├── tasks.json
│   ├── results.json
│   └── week-01/
│       ├── research.md
│       ├── coding.md
│       ├── files.md
│       ├── multimodal.md
│       ├── computer.md
│       └── report.md
└── assets/
    └── arxh-header.png
```

### `tests/`

| Path | Contents |
|---|---|
| [`tests/README.md`](tests/README.md) | What the evaluations are for and how they are run |
| [`tests/test-suite.md`](tests/test-suite.md) | The full 30-task suite, grouped by category |
| [`tests/tasks.json`](tests/tasks.json) | Machine-readable task definitions |
| [`tests/results.json`](tests/results.json) | Recorded results, kept separate from task definitions |
| [`tests/week-01/research.md`](tests/week-01/research.md) | TEST-01 – TEST-10, research & reasoning |
| [`tests/week-01/files.md`](tests/week-01/files.md) | TEST-11 – TEST-15, files & documents |
| [`tests/week-01/coding.md`](tests/week-01/coding.md) | TEST-16 – TEST-20, coding |
| [`tests/week-01/multimodal.md`](tests/week-01/multimodal.md) | TEST-21 – TEST-25, multimodal |
| [`tests/week-01/computer.md`](tests/week-01/computer.md) | TEST-26 – TEST-30, browser / computer / multi-step |
| [`tests/week-01/report.md`](tests/week-01/report.md) | Week 01 summary report |

Task definitions and results are kept apart on purpose, so the same tasks can be run again later and compared fairly.

## Status

The current evaluation set is part of the **Week 01 public testing period**. Results in `results.json` and in the weekly notes are filled in only after tasks are actually run — expected numbers are never recorded.

## Contributing

If you find a task definition that is ambiguous, a success criterion that cannot be checked, or a way to make a test more honest, that is a useful contribution. Raise it rather than quietly fixing it in a run.

## License

See the repository for licensing details.