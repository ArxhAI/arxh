# Week 01 — Browser / Computer / Multi-step

Tasks TEST-26 to TEST-30 in the separate general-agent evaluation suite.

These five scenarios are intended to probe end-to-end browser and computer use: interpreting a goal, planning dependent actions, selecting tools, handling tool failure, and verifying a usable outcome. Define the exact inputs and environment before comparing runs. Long workflows can fail late, so record where and how a failure occurred, not only that it happened. These are general tool-use scenarios, not Rust ML experiments or evaluations of neural-network methods.

TEST-28 should make the appropriate tool choice clear, including when no tool is warranted. TEST-29 tests failure handling; preserve the error, recovery path, and final state rather than relying on a narrative claim.

## Tasks

### TEST-26 — Complete a web research task

**Goal**

Use the browser to research a specific question and return a verified result.

**Task**

Research a question in a browser and return a verified result.

**Success criteria**

The final answer must be supported by the information actually found during the task.

---

### TEST-27 — Multi-step web workflow

**Goal**

Complete a sequence of dependent browser actions.

**Task**

Complete a multi-step browser workflow where each step depends on the previous one.

**Success criteria**

Each step should contribute toward the final objective.

---

### TEST-28 — Tool selection

**Goal**

Determine whether the agent chooses an appropriate tool for the task.

**Task**

Present a task where several tools are available and observe which one is chosen.

**Success criteria**

The selected tool should be appropriate to the problem rather than used simply because it is available.

---

### TEST-29 — Recovery from tool failure

**Goal**

Test behavior when a tool fails.

**Task**

Introduce a realistic tool failure during execution.

**Success criteria**

Arxh should detect the failure, recover when possible, and avoid claiming success without completing the task.

---

### TEST-30 — Goal-to-result task

**Goal**

Test the central idea behind Arxh.

**Task**

Give Arxh a desired outcome without providing a detailed recipe for achieving it.

**Success criteria**

Arxh should understand the objective, determine a reasonable plan, choose necessary actions, execute the work, verify the result, and deliver the final outcome. The task should be judged primarily on the final result, not on how impressive the intermediate process looks.

---

## Environment and run protocol

A computer-use task is reproducible only when the starting state is defined. Record the browser or desktop environment, operating system, viewport or display settings where relevant, initial URL or application state, available tools, permission boundary, timeout, retry limit, and any fixture accounts or files. Use a clean, isolated environment when possible. Never place real passwords, access tokens, private account data, or production systems in public evaluation fixtures.

Preserve enough evidence to reconstruct the workflow: relevant URLs, task-relevant screenshots or tool outputs, actions taken, errors, recovery attempts, and the final state. Redact secrets and personal data before saving traces. A narrative claim such as “the form was submitted” is not proof; inspect the resulting confirmation or application state. For browser research, distinguish information present on the page from facts inferred from memory and record the source page actually used.

Tool choice should be judged against the task’s requirements and permissions. A browser may be unnecessary for a stable local calculation; a filesystem tool may be inappropriate for an external research request. More tool use is not inherently better. If a tool can cause external side effects—publishing, deleting, purchasing, sending, or changing account settings—define whether that action is permitted and whether confirmation is required before running the scenario. Grade a safe refusal or request for authorization appropriately when the task lacks permission.

For multi-step tasks, list the intended milestones and the final observable state before the run. Check whether intermediate actions depended on earlier outputs and whether the system noticed when an assumption failed. If a network or tool error occurs, preserve the original error and record whether recovery used a permitted alternative. Do not erase a failed attempt from the run log simply because a later retry succeeded.

For every claim of completion, verify the resulting state independently where possible. A task is not complete because the agent described a plan, opened a page, or emitted a plausible confirmation. If the environment prevents verification, record that limitation and lower the verification status rather than guessing. Keep task definitions stable for a comparison; any material change to the starting page, allowed tools, or success criteria should be versioned.

## Results

Fill this in only after each task has actually been run.

| Test | Status | Verified | Intervention | Recovered | Duration | Notes |
|---|---|---|---|---|---:|---|
| TEST-26 | — | — | — | — | — | — |
| TEST-27 | — | — | — | — | — | — |
| TEST-28 | — | — | — | — | — | — |
| TEST-29 | — | — | — | — | — | — |
| TEST-30 | — | — | — | — | — | — |

- **Status:** `PASS` / `PARTIAL` / `FAIL`
- **Intervention:** `none` / `minor` / `significant`
- **Recovered:** `not needed` / `recovered` / `failed to recover`

Notes should be concrete observations. “Reported the outcome as done while the final step was never executed” is useful. “The workflow felt long” is not. A blank or dash means that no result has been entered.

## Scope and references

This category is a proposed general-agent evaluation protocol. It is not a Rust ML benchmark and it should not be used to infer model-training ability or deep-learning performance. The separate Rust ML scope is described in [`../../RESEARCH-PLAN.md`](../../RESEARCH-PLAN.md).

Evaluation design references: OpenAI’s [agent workflow evaluation guide](https://developers.openai.com/api/docs/guides/agent-evals), [evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices), and Inspect AI [documentation](https://inspect.aisi.org.uk/). They inform the proposed run discipline; these scenarios remain unrun and unvalidated.
