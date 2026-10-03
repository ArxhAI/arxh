# Week 01 — Research & Reasoning

Tasks TEST-01 to TEST-10.

This is the largest block in Week 01, because research is where an agent most easily produces a confident answer that was never checked. Most of these tests are not about whether Arx-h can retrieve text. They are about whether it retrieves it, compares it, notices its own missing context, and stays honest about uncertainty.

## Tasks

### TEST-01 — Compare two approaches

**Goal**

Compare two technical approaches to solving the same problem.

**Task**

Research two commonly used approaches for building a production AI agent with external tools.

Explain:

1. how each approach works
2. where each approach is useful
3. major trade-offs
4. operational risks
5. when one approach would be preferable to the other

**Success criteria**

The answer must be based on current sources, clearly separate facts from interpretation, and provide a useful comparison rather than a generic summary.

---

### TEST-02 — Find a current fact

**Goal**

Retrieve a time-sensitive piece of information.

**Task**

Find a current public fact from the web and provide the source used to verify it.

**Success criteria**

The information must be current, the source must be identifiable, and the final answer must not rely on unsupported assumptions.

---

### TEST-03 — Conflicting information

**Goal**

Handle disagreement between sources.

**Task**

Find two credible sources that disagree on a factual detail.

Explain:

- what they disagree about
- why the disagreement may exist
- which information is better supported
- what remains uncertain

**Success criteria**

Arx-h must not simply choose the first source it finds.

---

### TEST-04 — Multi-source synthesis

**Goal**

Combine information from several sources.

**Task**

Research a technical topic using at least three independent sources and produce a concise synthesis.

**Success criteria**

The final result should combine the sources into one coherent answer rather than presenting three disconnected summaries.

---

### TEST-05 — Follow a constraint

**Goal**

See whether Arx-h can respect a specific requirement while researching.

**Task**

Research a software library, but only include information that can be verified from official documentation.

**Success criteria**

Unofficial claims should not be presented as official facts.

---

### TEST-06 — Ambiguous request

**Goal**

Test whether Arx-h notices missing information.

**Task**

"Find the best database for my application."

No application details are provided.

**Success criteria**

Arx-h should identify the missing context and avoid pretending that one option is universally best.

---

### TEST-07 — Planning a project

**Goal**

Turn a broad objective into a practical plan.

**Task**

Create a realistic implementation plan for a small AI-powered web application.

Include:

- major steps
- dependencies
- likely risks
- testing requirements
- a sensible order of execution

**Success criteria**

The plan should be actionable and internally consistent.

---

### TEST-08 — Detect a false premise

**Goal**

See whether Arx-h blindly accepts an incorrect assumption.

**Task**

Provide a question containing a false or questionable premise and ask Arx-h to solve it.

**Success criteria**

Arx-h should identify the premise before continuing instead of building an elaborate answer on top of a mistake.

---

### TEST-09 — Long instruction

**Goal**

Measure instruction retention.

**Task**

Give Arx-h a long request containing multiple independent requirements, formatting constraints, and exclusions.

**Success criteria**

Important requirements should survive through the final response.

---

### TEST-10 — Change of direction

**Goal**

Test adaptation during an ongoing task.

**Task**

Start with one objective, then introduce a legitimate change in the requirements halfway through the task.

**Success criteria**

Arx-h should adapt instead of continuing blindly with the original plan.

---

## Results

Fill this in only after each task has actually been run.

| Test | Status | Verified | Intervention | Recovered | Duration | Notes |
|---|---|---|---|---|---:|---|
| TEST-01 | — | — | — | — | — | — |
| TEST-02 | — | — | — | — | — | — |
| TEST-03 | — | — | — | — | — | — |
| TEST-04 | — | — | — | — | — | — |
| TEST-05 | — | — | — | — | — | — |
| TEST-06 | — | — | — | — | — | — |
| TEST-07 | — | — | — | — | — | — |
| TEST-08 | — | — | — | — | — | — |
| TEST-09 | — | — | — | — | — | — |
| TEST-10 | — | — | — | — | — | — |

**Status:** PASS / PARTIAL / FAIL
**Intervention:** none / minor / significant
**Recovered:** not needed / recovered / failed to recover

Notes should be concrete observations, not impressions. "Arx-h used a 2023 blog post to answer a question about current pricing" is useful. "The answer felt generic" is not.