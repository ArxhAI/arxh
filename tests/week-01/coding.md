# Week 01 — Coding

Tasks TEST-16 to TEST-20.

Coding tasks are the easiest to fake. A plausible-looking diff is not the same as working code, and a test file with more lines than the original is not the same as coverage. For this block, the artifact has to be run.

Record, for every task:

- the exact command used to verify
- what the command reported
- whether Arxh ran it or only described it

TEST-19 has an extra constraint worth stating explicitly: behavior must be equivalent. A refactor that also fixes a bug is not a refactor.

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

## Results

Fill this in only after each task has actually been run.

| Test | Status | Verified | Intervention | Recovered | Duration | Verification command | Notes |
|---|---|---|---|---|---:|---|---|
| TEST-16 | — | — | — | — | — | — | — |
| TEST-17 | — | — | — | — | — | — | — |
| TEST-18 | — | — | — | — | — | — | — |
| TEST-19 | — | — | — | — | — | — | — |
| TEST-20 | — | — | — | — | — | — | — |

**Status:** PASS / PARTIAL / FAIL
**Intervention:** none / minor / significant
**Recovered:** not needed / recovered / failed to recover

Notes should be concrete observations, not impressions. "Reported success without running the suite; the build was broken" is useful. "The code looked clean" is not.