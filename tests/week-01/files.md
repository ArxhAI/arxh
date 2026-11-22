# Week 01 — Files & Documents

Tasks TEST-11 to TEST-15 in the separate general-agent evaluation suite.

These tasks test a quiet but consequential part of tool use: reading and editing files without losing track of what the source actually says. A summary that drops a condition, an extracted table with one invented date, or an edit that silently reformats unrelated paragraphs can look correct at a glance. Every task in this block should be checked against the source file, not against the agent’s response. This category is not a Rust ML experiment and does not test model training, neural-network methods, or ML data pipelines.

## Tasks

### TEST-11 — Read and summarize a document

**Goal**

Extract the important information from a provided document.

**Task**

Summarize a provided document.

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

**Task**

Edit a document following explicit instructions.

**Success criteria**

Only the requested changes should be made unless additional changes are necessary for correctness.

---

### TEST-14 — Cross-file comparison

**Goal**

Compare information from two files.

**Task**

Compare two provided files.

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

## Verification protocol

A reproducible file task begins with a preserved input. Record the source file path, file type, encoding when relevant, revision or checksum for larger fixtures, and any instructions that constrain the output. Keep the original input unchanged so a reviewer can compare it with the final artifact. If a task uses more than one file, state which file is authoritative for each field and preserve their relationship in the fixture. Do not place private user documents or credentials in public test data.

For summaries, grade meaning rather than word overlap. Identify the document’s key claims, qualifications, exceptions, and uncertainty, then check whether the response preserves them. A short summary may omit background; it should not reverse the conclusion or remove a condition that changes its meaning. A good check records specific omissions, unsupported additions, and representative passages rather than saying only that the answer “looks right.”

For extraction tasks, build a reference table from the source before running the agent. Decide how to represent absent, ambiguous, approximate, or conflicting values. `Unknown` or `not stated` must not silently become an inferred value. Compare each field and each row, including units, punctuation in identifiers, date formats, category membership, and exact amounts where appropriate. If normalization is allowed, specify the rule before grading.

For editing tasks, save the original file and inspect a diff. Check that the requested changes are present, that unrelated content was not removed, and that formatting remains usable. A changed file is not automatically a correct file; a response that describes edits without delivering or saving the artifact is also not completion. For cross-file comparison, record the sources and cite a path, heading, row, or other location so a reviewer can retrace the difference.

Missing information needs special care. An evaluator should decide in advance which fields may be safely inferred from context and which require a question or explicit placeholder. A completion that invents names, dates, costs, sources, or results is not a pass simply because the output is complete-looking. The agent should surface the gap, ask for necessary context, or label a proposed value as an assumption.

## Results

Fill this in only after each task has actually been run.

| Test | Status | Verified | Intervention | Recovered | Duration | Notes |
|---|---|---|---|---|---:|---|
| TEST-11 | — | — | — | — | — | — |
| TEST-12 | — | — | — | — | — | — |
| TEST-13 | — | — | — | — | — | — |
| TEST-14 | — | — | — | — | — | — |
| TEST-15 | — | — | — | — | — | — |

- **Status:** `PASS` / `PARTIAL` / `FAIL`
- **Intervention:** `none` / `minor` / `significant`
- **Recovered:** `not needed` / `recovered` / `failed to recover`

Notes should be concrete observations, not impressions. “Extracted table matched 18 of 18 amounts; one date was inferred and not marked” is useful. “The summary was good” is not. Leave unrun tasks unreported rather than filling the table with predicted outcomes.

## Scope and references

This is an exploratory file-handling category for general-agent evaluation. It is separate from the Rust ML plan. The test inputs and outputs here do not constitute a machine-learning dataset, and a file-editing pass does not count as a model implementation or experiment. See the parent [suite guide](../README.md) for shared run metadata, status definitions, and handling of `null` results.

Evaluation design references: OpenAI’s [evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices) and Inspect AI [documentation](https://inspect.aisi.org.uk/). They provide general evaluation ideas; the current scenarios remain unrun and not independently validated.
