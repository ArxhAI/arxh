# Week 01 — Files & Documents

Tasks TEST-11 to TEST-15.

These tasks test the least visible part of the system: reading and editing files without losing track of what the source actually said. The failure mode here is quiet. A summary that drops a condition, an extracted table with one invented date, or an edit that silently reformats paragraphs the user never asked to touch will all look correct at a glance.

Every task in this block should be checked against the source file, not against the response.

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

## Results

Fill this in only after each task has actually been run.

| Test | Status | Verified | Intervention | Recovered | Duration | Notes |
|---|---|---|---|---|---:|---|
| TEST-11 | — | — | — | — | — | — |
| TEST-12 | — | — | — | — | — | — |
| TEST-13 | — | — | — | — | — | — |
| TEST-14 | — | — | — | — | — | — |
| TEST-15 | — | — | — | — | — | — |

**Status:** PASS / PARTIAL / FAIL
**Intervention:** none / minor / significant
**Recovered:** not needed / recovered / failed to recover

Notes should be concrete observations, not impressions. "Extracted table matched 18 of 18 amounts; one date was inferred and not marked" is useful. "The summary was good" is not.