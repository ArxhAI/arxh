# Arx-h Evaluations

This directory contains public evaluations for Arx-h.

The goal is simple: give Arx-h a real task and see what happens.

We are interested in more than whether a task eventually succeeds. We also look at:

- whether Arx-h understood the goal correctly
- whether it chose reasonable actions
- whether tool use helped or got in the way
- whether it verified its own work
- whether it recovered from failure
- whether human intervention was required
- how long the task took

These evaluations are intentionally imperfect.

They are meant to show how Arx-h behaves in real conditions, including cases where it fails.

## Evaluation principle

We do not optimize the test set to make Arx-h look good.

A successful run is useful.

A failed run is useful too.

Each result should help answer one question:

> What should we improve next?

## Layout

| Path | Contents |
|---|---|
| `test-suite.md` | The full task suite, grouped by category |
| `tasks.json` | Machine-readable task definitions |
| `results.json` | Recorded results, kept separate from task definitions |
| `week-01/` | Per-week notes, observations, and the weekly report |

Results are recorded separately from task definitions so that the same tasks can be repeated later and compared fairly.

## Status

The current evaluation set is part of the Week 01 public testing period.

## Status definitions

### PASS

The task was completed correctly and the important output was verified.

### PARTIAL

Arx-h made meaningful progress but the final result was incomplete, incorrect, or insufficiently verified.

### FAIL

The task could not be completed or the final result was not usable.

A task is not considered a success simply because Arx-h produced an answer. The final result must be checked against the task requirements.