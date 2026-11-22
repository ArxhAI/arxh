# Week 01 — Research & Reasoning

Tasks TEST-01 to TEST-10 in the separate general-agent evaluation suite.

This is the largest block in Week 01 because research is where an agent can produce a confident answer that was never checked. The tests are not about Rust or deep learning. They examine whether an agent can locate sources, evaluate their relevance and freshness, combine information, notice missing context, and keep uncertainty visible. They do not measure Arxh’s ability to train a neural network or compare ML frameworks.

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

Arxh must not simply choose the first source it finds.

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

See whether Arxh can respect a specific requirement while researching.

**Task**

Research a software library, but only include information that can be verified from official documentation.

**Success criteria**

Unofficial claims should not be presented as official facts.

---

### TEST-06 — Ambiguous request

**Goal**

Test whether Arxh notices missing information.

**Task**

“Find the best database for my application.”

No application details are provided.

**Success criteria**

Arxh should identify the missing context and avoid pretending that one option is universally best.

---

### TEST-07 — Planning a project

**Goal**

Turn a broad objective into a practical plan.

**Task**

Create a realistic implementation plan for a small AI-powered web application.

Include major steps, dependencies, likely risks, testing requirements, and a sensible order of execution.

**Success criteria**

The plan should be actionable and internally consistent.

---

### TEST-08 — Detect a false premise

**Goal**

See whether Arxh blindly accepts an incorrect assumption.

**Task**

Provide a question containing a false or questionable premise and ask Arxh to solve it.

**Success criteria**

Arxh should identify the premise before continuing instead of building an elaborate answer on top of a mistake.

---

### TEST-09 — Long instruction

**Goal**

Measure instruction retention.

**Task**

Give Arxh a long request containing multiple independent requirements, formatting constraints, and exclusions.

**Success criteria**

Important requirements should survive through the final response.

---

### TEST-10 — Change of direction

**Goal**

Test adaptation during an ongoing task.

**Task**

Start with one objective, then introduce a legitimate change in the requirements halfway through the task.

**Success criteria**

Arxh should adapt instead of continuing blindly with the original plan.

---

## Evaluation protocol for this category

Before a run, preserve the exact question, date, task-set revision, available research tools, and source requirements. “Current” has meaning only when the evaluator records the question date and checks a source that is authoritative for the fact in question. A useful source hierarchy often begins with the primary paper, official documentation, a maintained repository, or the organization responsible for the information. Secondary explanations can add context, but they should not be presented as an official statement or as independent confirmation when they merely repeat the same source.

For each material claim, an evaluator should be able to find the supporting passage or data point. Citations should identify the source, not just a homepage; time-sensitive claims should include a date or version. If two sources disagree, assess whether they refer to different versions, definitions, populations, or dates before grading the conclusion. A polished summary that cannot be traced to its evidence is not a pass.

A practical rubric can score source relevance, factual support, freshness, synthesis, treatment of counterevidence, constraint-following, and uncertainty separately. Use the rubric before running tasks, not after seeing the answer. For subjective dimensions, preserve examples and have a second reviewer apply the same criteria when feasible. If an automated judge is used, record its model, prompt, and known limitations, and do not let a judge’s unverified opinion replace source checks.

The task inventory is still exploratory. Several prompts are not fully specified for independent replication, and no runs or results have been recorded. Before comparing agents, freeze the prompts and required inputs, version any material change, record the model/tool setup, and report all attempts rather than selecting only the cleanest one. Use `null` in the shared result ledger until a task is actually executed and graded.

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

- **Status:** `PASS` / `PARTIAL` / `FAIL`
- **Intervention:** `none` / `minor` / `significant`
- **Recovered:** `not needed` / `recovered` / `failed to recover`

Notes should be concrete observations, not impressions. “Arxh used a 2023 blog post to answer a question about current pricing” is useful. “The answer felt generic” is not. A `—` here means no result has been entered, not a failed run.

## Scope and references

This category belongs to the earlier exploratory general-agent evaluation suite. It must remain separate from the proposed Rust ML study in [`../../RESEARCH-PLAN.md`](../../RESEARCH-PLAN.md). Editing these scenarios or later running them would not constitute a deep-learning experiment, a trained model, or a Rust-framework benchmark.

Evaluation design references: OpenAI’s [evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices), [agent workflow evaluation guide](https://developers.openai.com/api/docs/guides/agent-evals), and Inspect AI [documentation](https://inspect.aisi.org.uk/). These inform protocol design; they do not imply that this suite has been validated against them.
