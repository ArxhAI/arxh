# Week 01 — Coding

Tasks TEST-16 to TEST-20 in the separate general-agent evaluation suite.

Coding tasks are easy to fake. A plausible-looking diff is not working code, and a test file with more lines than the original is not meaningful coverage. For this category, the artifact has to be run in a recorded environment and checked against pre-agreed behavior. These scenarios are general coding tasks; they do not test Rust ML, neural-network implementations, model training, or the project’s future research questions.

Record for every task:

- the exact input repository or fixture revision
- the language, toolchain, operating system, and relevant dependency state
- the exact verification command and its actual output
- whether Arxh ran the command or only proposed it
- any pre-existing failures, tool errors, human intervention, or recovery step

TEST-19 has an extra constraint worth stating explicitly: behavior must be equivalent. A refactor that also fixes a bug is not a refactor-only result.

## Tasks

### TEST-16 — Small implementation

**Goal**

Implement a small coding task from a natural-language request.

**Task**

Implement a small coding task described in natural language.

**Success criteria**

The result should satisfy the requested behavior and remain readable.

---

### TEST-17 — Debug an existing program

**Goal**

Find and fix a bug.

**Task**

Diagnose and fix a bug in an existing program.

**Success criteria**

Arxh should identify the cause, make the necessary change, and explain how the fix was validated.

---

### TEST-18 — Write tests

**Goal**

Add tests to an existing implementation.

**Task**

Add tests covering the requested behavior.

**Success criteria**

The tests should cover the requested behavior rather than merely increasing the line count.

---

### TEST-19 — Refactor without changing behavior

**Goal**

Improve code structure while preserving functionality.

**Task**

Refactor an implementation while keeping behavior identical.

**Success criteria**

The implementation should remain behaviorally equivalent.

---

### TEST-20 — Recover from a failed implementation

**Goal**

Test whether Arxh can respond to a failed coding attempt.

**Task**

Allow the first implementation to fail a test.

**Success criteria**

Arxh should inspect the failure, revise its approach, and rerun the relevant checks.

---

## Verification protocol

Before changing code, record the starting state and read the relevant tests and project instructions. A fair task fixture should provide the same initial repository, requirements, and tool permissions to every system under comparison. Do not patch a task prompt after seeing a failure and then grade the original run against the new prompt. If the request changes, create a new task-set revision or clearly record a separate run.

For an implementation task, define observable acceptance criteria before evaluation. Prefer checks for behavior and edge cases over subjective judgments about style. For debugging, confirm the failure exists in the baseline and that the proposed change addresses its cause rather than bypassing the test. For test-writing, review whether the tests fail when the relevant behavior is broken, pass when it is correct, and cover expected boundary cases. Line coverage may provide context but does not prove that assertions are useful.

For a refactor, compare outputs or behavior on representative fixtures before and after. The test suite should exercise existing behavior, and any intentional behavior change must be listed separately instead of being hidden in a cleanup. For recovery tasks, preserve the first failure, subsequent edits, and rerun output so the evaluation can distinguish a real recovery from a claim of success.

Verification claims must match the evidence. If the agent says “tests pass,” the run log should contain the command and result. If the environment cannot execute the code, report that limitation and grade the deliverable accordingly; do not accept a described command as if it had been run. Preserve compiler, test, and runtime errors that are necessary to understand the result, while removing secrets or private information from public artifacts.

When a coding task changes multiple files, inspect the final diff for accidental edits, generated artifacts, lockfile changes, and unrelated formatting. Keep dependencies and versions fixed during a comparison where possible. The current suite has no automated harness, so these steps are a proposed manual protocol rather than a completed evaluation pipeline.

## Results

Fill this in only after each task has actually been run.

| Test | Status | Verified | Intervention | Recovered | Duration | Verification command | Notes |
|---|---|---|---|---|---:|---|---|
| TEST-16 | — | — | — | — | — | — | — |
| TEST-17 | — | — | — | — | — | — | — |
| TEST-18 | — | — | — | — | — | — | — |
| TEST-19 | — | — | — | — | — | — | — |
| TEST-20 | — | — | — | — | — | — | — |

- **Status:** `PASS` / `PARTIAL` / `FAIL`
- **Intervention:** `none` / `minor` / `significant`
- **Recovered:** `not needed` / `recovered` / `failed to recover`

Notes should describe observed evidence. “Reported success without running the suite; the build was broken” is useful. “The code looked clean” is not. A blank or `—` row means the task has not been recorded as run.

## Scope and references

The tasks above are general coding scenarios inherited from Arxh’s earlier agent-evaluation direction. They must not be described as Rust ML tests. The Rust deep-learning research agenda is documented separately in [`../../RESEARCH-PLAN.md`](../../RESEARCH-PLAN.md), and any future model code will need its own task-specific test plan, dataset provenance, numerical checks, and resource record.

Evaluation design references: OpenAI’s [evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices) and Inspect AI [documentation](https://inspect.aisi.org.uk/). These are references for evaluation design, not evidence that these tasks have been run or validated.
