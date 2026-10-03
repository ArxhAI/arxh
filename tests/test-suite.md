# Arxh Test Suite

30 tasks, grouped into five categories.

The same task definitions should be reused when possible so that later runs can be compared fairly.

| Category | Tasks | Count |
|---|---|---:|
| Research & reasoning | TEST-01 – TEST-10 | 10 |
| Files & documents | TEST-11 – TEST-15 | 5 |
| Coding | TEST-16 – TEST-20 | 5 |
| Multimodal | TEST-21 – TEST-25 | 5 |
| Browser / computer / multi-step | TEST-26 – TEST-30 | 5 |
| **Total** | | **30** |

---

## 01–10 — Research & Reasoning

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

"Find the best database for my application."

No application details are provided.

**Success criteria**

Arxh should identify the missing context and avoid pretending that one option is universally best.

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

## 11–15 — Files & Documents

### TEST-11 — Read and summarize a document

**Goal**

Extract the important information from a provided document.

**Success criteria**

The summary should preserve the document's important meaning without inventing content.

---

### TEST-12 — Extract structured information

**Goal**

Turn an unstructured document into structured data.

**Task**

Extract names, dates, amounts, and relevant categories into a clean table.

**Success criteria**

Values must match the source document.

---

### TEST-13 — Edit a document

**Goal**

Modify a document according to explicit instructions.

**Success criteria**

Only the requested changes should be made unless additional changes are necessary for correctness.

---

### TEST-14 — Cross-file comparison

**Goal**

Compare information from two files.

**Success criteria**

Arxh should identify meaningful differences and cite where they came from.

---

### TEST-15 — File task with missing information

**Goal**

Test whether Arxh notices incomplete input.

**Task**

Provide a partially complete document and ask Arxh to finish it.

**Success criteria**

Arxh must distinguish between missing information and information it can safely infer.

---

## 16–20 — Coding

### TEST-16 — Small implementation

**Goal**

Implement a small coding task from a natural-language request.

**Success criteria**

The result should satisfy the requested behavior and remain readable.

---

### TEST-17 — Debug an existing program

**Goal**

Find and fix a bug.

**Success criteria**

Arxh should identify the cause, make the necessary change, and explain how the fix was validated.

---

### TEST-18 — Write tests

**Goal**

Add tests to an existing implementation.

**Success criteria**

The tests should cover the requested behavior rather than merely increasing the line count.

---

### TEST-19 — Refactor without changing behavior

**Goal**

Improve code structure while preserving functionality.

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

## 21–25 — Multimodal

### TEST-21 — Read an image

**Goal**

Extract useful information from an image.

**Success criteria**

The answer should distinguish clearly visible information from assumptions.

---

### TEST-22 — Analyze a chart

**Goal**

Interpret a chart or graph.

**Success criteria**

The response must match the actual visual data and avoid unsupported conclusions.

---

### TEST-23 — Document screenshot

**Goal**

Understand information contained in a screenshot of a document or interface.

**Success criteria**

Important visible details should be captured accurately.

---

### TEST-24 — Compare two images

**Goal**

Identify relevant differences between two images.

**Success criteria**

The response should focus on meaningful differences rather than superficial observations.

---

### TEST-25 — Multimodal reasoning

**Goal**

Combine visual information with a written instruction.

**Success criteria**

The final response should correctly use both sources of information.

---

## 26–30 — Browser / Computer / Multi-step

### TEST-26 — Complete a web research task

**Goal**

Use the browser to research a specific question and return a verified result.

**Success criteria**

The final answer must be supported by the information actually found during the task.

---

### TEST-27 — Multi-step web workflow

**Goal**

Complete a sequence of dependent browser actions.

**Success criteria**

Each step should contribute toward the final objective.

---

### TEST-28 — Tool selection

**Goal**

Determine whether the agent chooses an appropriate tool for the task.

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

## Notes

Each task should be recorded in `results.json` and summarised in the weekly category notes under `week-01/`.

A task is not considered a success simply because Arxh produced an answer. The final result must be checked against the task requirements.