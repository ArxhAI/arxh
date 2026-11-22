# Week 01 — Multimodal

Tasks TEST-21 to TEST-25 in the separate general-agent evaluation suite.

Image understanding is where confident errors can hide: a reader cannot always tell whether a description came from visible pixels or from an expectation about what an image “usually” contains. Each task in this block should be graded against the exact image file and the written instruction. These scenarios assess general multimodal task handling; they do not test deep learning, Rust ML, neural-network training, or visual model accuracy as a research benchmark.

Two things to watch for on every run:

- **Observation vs. inference.** Did Arxh describe what is visible, or what such a screen usually contains?
- **Precision on numbers.** Charts, screenshots, and tables contain values that can be checked exactly. Approximate values should be marked as approximate.

TEST-25 depends on both the image and the written instruction. Solving the image and ignoring the instruction, or the reverse, is a partial result at best.

## Tasks

### TEST-21 — Read an image

**Goal**

Extract useful information from an image.

**Task**

Analyze a provided image.

**Success criteria**

The answer should distinguish clearly visible information from assumptions.

---

### TEST-22 — Analyze a chart

**Goal**

Interpret a chart or graph.

**Task**

Interpret a provided chart or graph.

**Success criteria**

The response must match the actual visual data and avoid unsupported conclusions.

---

### TEST-23 — Document screenshot

**Goal**

Understand information contained in a screenshot of a document or interface.

**Task**

Extract information from a screenshot of a document or interface.

**Success criteria**

Important visible details should be captured accurately.

---

### TEST-24 — Compare two images

**Goal**

Identify relevant differences between two images.

**Task**

Compare two provided images.

**Success criteria**

The response should focus on meaningful differences rather than superficial observations.

---

### TEST-25 — Multimodal reasoning

**Goal**

Combine visual information with a written instruction.

**Task**

Answer an instruction that requires both an image and written context.

**Success criteria**

The final response should correctly use both sources of information.

---

## Image fixture and grading protocol

A reproducible image task must identify the exact fixture used. Record a stable path or identifier, file format, dimensions, and any crop, rotation, compression, or preprocessing. If a chart is intentionally cropped, preserve the original and state what was removed. For a pairwise comparison task, preserve both files and record which is image A and image B. A filename or caption alone is not a substitute for the image itself.

For grading, create a reference annotation before running the agent. Separate directly visible objects, text, relationships, and measurements from interpretation. For charts, record the title, axis labels, units, range, data marks, and uncertainty before judging a trend. A claim about a value should be traceable to the chart or clearly marked as an estimate. Do not accept a plausible trend description if it reverses the actual direction or ignores a truncated axis.

For screenshots and documents, compare extracted text with the pixels; record ambiguous characters, low-resolution regions, and whether OCR would be required. A useful rubric distinguishes exact extraction, approximate reading, unsupported inference, and information not legible from the image. If a task includes written instructions, check both modalities independently and then check whether the final response uses the correct relationship between them.

Image fixtures should avoid private information and be sourced with permission appropriate to the evaluation. Keep any existing creator/source/license notes with the fixture. Do not add faces or identifiable personal data unless a legitimate task requires it and the data is handled appropriately. Arxh’s separate README image rule is stricter for project decoration: its selected visual assets contain no people or faces. That asset rule does not change the historical task set or create a claim about multimodal test performance.

When comparing two images, prioritize task-relevant differences and preserve uncertainty about hidden or cropped content. The evaluator should not reward an answer for guessing a common object or text string that cannot be seen. Where the image is ambiguous, the correct response may be a qualified description or a request for a clearer source rather than confident completion.

## Results

Fill this in only after each task has actually been run.

| Test | Status | Verified | Intervention | Recovered | Duration | Notes |
|---|---|---|---|---|---:|---|
| TEST-21 | — | — | — | — | — | — |
| TEST-22 | — | — | — | — | — | — |
| TEST-23 | — | — | — | — | — | — |
| TEST-24 | — | — | — | — | — | — |
| TEST-25 | — | — | — | — | — | — |

- **Status:** `PASS` / `PARTIAL` / `FAIL`
- **Intervention:** `none` / `minor` / `significant`
- **Recovered:** `not needed` / `recovered` / `failed to recover`

Notes should be concrete observations. “Read the axis maximum as 45; the image shows 50” is useful. “The image was understood correctly” is not. Do not fill a row with expected results before a run.

## Scope and references

This block is part of the general-agent task inventory and is not an ML benchmark. It does not measure the accuracy of a neural network or compare Rust frameworks. See the parent [suite guide](../README.md) for shared task-set versioning and run metadata.

Evaluation design references: OpenAI’s [evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices) and Inspect AI [documentation](https://inspect.aisi.org.uk/). These provide general methodological prompts; no claim of validation or completion is implied.
