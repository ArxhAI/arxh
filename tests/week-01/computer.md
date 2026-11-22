# Week 01 — Browser / Computer / Multi-step

Tasks TEST-26 to TEST-30.

These five scenarios are intended to probe end-to-end browser and computer use: interpreting a goal, planning dependent actions, selecting tools, handling tool failure, and verifying a usable outcome. Define the exact inputs and environment before comparing runs.

Long workflows can fail late. Record where and how a failure occurred, not only that it happened.

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

Arxh should:

1. understand the objective
2. determine a reasonable plan
3. choose the necessary actions
4. execute the work
5. verify the result
6. deliver the final outcome

The task should be judged primarily on the quality of the final result, not on how impressive the intermediate process looks.

---

## Results

Fill this in only after each task has actually been run.

| Test | Status | Verified | Intervention | Recovered | Duration | Notes |
|---|---|---|---|---|---:|---|
| TEST-26 | — | — | — | — | — | — |
| TEST-27 | — | — | — | — | — | — |
| TEST-28 | — | — | — | — | — | — |
| TEST-29 | — | — | — | — | — | — |
| TEST-30 | — | — | — | — | — | — |

**Status:** PASS / PARTIAL / FAIL
**Intervention:** none / minor / significant
**Recovered:** not needed / recovered / failed to recover

Notes should be concrete observations, not impressions. "Reported the outcome as done while the final step was never executed" is useful. "The workflow felt long" is not.
