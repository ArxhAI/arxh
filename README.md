<div align="center">
  <img src="assets/arxh-header.png" alt="Arxh — machine learning research and learning in Rust" width="100%" />
  <p><strong>Machine learning, explored with Rust. Learning in public.</strong></p>
</div>

# Arxh

Arxh is an early-stage research and learning project exploring machine learning with Rust. The goal is to understand the tools and ideas carefully, build small experiments that others can reproduce, and share both the results and the questions that remain.

We are still learning and shaping the direction. This repository does not yet contain a Rust implementation, a trained model, or an ML benchmark. It is a public place to clarify the research questions, compare possible starting points, and document the first steps without presenting plans as completed work.

## On this page

- [Research focus](#research-focus)
- [Rust ML ecosystem: starting points](#rust-ml-ecosystem-starting-points)
- [Learning roadmap](#learning-roadmap)
- [How we want to run experiments](#how-we-want-to-run-experiments)
- [What is currently in this repository](#what-is-currently-in-this-repository)
- [Contributing](#contributing)
- [Contributor guide](CONTRIBUTING.md)
- [References](#references)
- [License](#license)

## Research focus

The starting question is practical: **what does it take to learn, implement, and evaluate a small machine-learning task in Rust in a way that is understandable and repeatable?**

That question is deliberately narrower than “Is Rust better for machine learning?” That broader claim would depend on the model, library, hardware, workload, and comparison method. We do not have results to support it, and we do not want to make it before doing the work.

Instead, we plan to explore questions such as:

- How clearly can a small ML workflow be expressed in Rust—from preparing data to checking a model's output?
- Which Rust libraries make sense for classical ML, tensor operations, training, or inference, and what trade-offs do their designs introduce?
- Can a small experiment produce correct, repeatable results across runs?
- What affects the developer experience: documentation, compile times, dependency setup, hardware support, and the effort required to inspect a result?
- When performance matters, how should it be measured fairly against a clearly stated baseline?

The initial scope is intentionally modest: learn the foundations, choose a small problem, establish a baseline, and record what happens. The aim is not to promise a new framework or compete with mature ML platforms before we have a reproducible experiment.

## Rust ML ecosystem: starting points

A first step in the research is to understand what already exists. These projects are **candidates to study, not tools Arxh has already tested or recommendations for every use case**. The short descriptions below reflect their own project documentation.

| Project | Their stated focus | A useful question for an early experiment |
|---|---|---|
| [Linfa](https://github.com/rust-ml/linfa) | A Rust toolkit for machine-learning applications, with an emphasis on preprocessing and classical ML algorithms. | How approachable is a small classical-learning baseline, such as regression or classification? |
| [Candle](https://github.com/huggingface/candle) | A minimalist ML framework for Rust, with a focus on performance and ease of use; its documentation includes CPU and GPU examples. | What is a clear first tensor or inference experiment, and what does its setup require? |
| [Burn](https://github.com/tracel-ai/burn) | A tensor library and deep-learning framework for numerical computing, training, and inference. | How does a small end-to-end training example work, and what backend or hardware assumptions does it make? |

This is an initial reading list, not a complete survey. These short descriptions were checked against the upstream project pages on 22 November 2026; APIs, support, and maintenance status can change. This is not a compatibility test. Before an experiment, check the current release notes and record the crate versions, repository revision, enabled features, and environment. We will choose tools based on the question being investigated—not on a popularity contest or an unverified performance claim.

## Learning roadmap

The diagram below describes a **proposed learning loop**, not a shipped workflow. We want to start with fundamentals, try a focused Rust experiment, check it carefully, and write down the limits as well as the result.

<div align="center">
  <img src="assets/rust-ml-research-loop.svg" alt="Arxh's proposed research loop: understand ML foundations, explore Rust tools, test evidence, and share results and open questions" width="100%" />
  <p><em>A direction for future work; no Rust experiment or benchmark is published yet.</em></p>
</div>

### A possible first experiment

A useful first experiment should be small enough that the result can be checked by hand or against a simple independent reference. For example, a basic regression or classification task could help us examine data representation, numerical operations, metrics, and the shape of a Rust development loop without requiring a large model or dataset.

Before choosing the exact task, we will need to identify a suitable dataset, check its license and provenance, define a baseline, and decide what output can be verified. The experiment should then be small enough to rerun on an ordinary development machine. If the first attempt exposes a missing concept or a limitation in the tooling, that is a useful research result—not something to hide.

## How we want to run experiments

A result is only meaningful when another person can understand what was run and what the numbers mean. For each future experiment, we intend to record:

- the question and task definition, including what would count as a correct result
- the dataset source, license, preprocessing steps, and any fixed train/test split
- the Rust toolchain, crate versions, `Cargo.lock`, enabled features, and exact command
- the baseline and metric, including any tolerance used for floating-point comparisons
- the random seed and number of repeated runs, where applicable
- the hardware and relevant software environment
- correctness checks separately from runtime or throughput measurements
- failures, limitations, and changes to the next attempt

We will check correctness before drawing conclusions about speed. Any performance comparison needs the same task, comparable hardware, clear measurement boundaries, and enough context to interpret the result. A single timing or a successful compile is not evidence that one framework or language is generally faster.

## What is currently in this repository

This repository is still in its documentation and planning stage. There is no `Cargo.toml`, Rust source tree, model implementation, or ML experiment runner here yet.

The existing [`tests/`](tests/README.md) directory contains an exploratory 30-scenario task set from the project's earlier, general AI-agent evaluation direction. Those scenarios cover research, file work, coding, multimodal tasks, and computer use; **they are not Rust machine-learning experiments**. The task set has no recorded results and is not a validated benchmark. It remains documented as an earlier research artifact while the project clarifies its next direction.

The distinction matters: a roadmap describes what we may investigate; an experiment describes what we actually ran; a result should be published only when there is evidence to support it.

## Contributing

Arxh is a learning-in-public project, and thoughtful contributions are welcome from Rust developers, ML practitioners, researchers, students, and people who are learning the field. You do not need to arrive with a finished answer. A careful question, a correction backed by a primary source, or a small reproducible example can be just as useful as a larger implementation.

Good places to start include:

- reviewing the Rust ML library notes and suggesting a relevant primary source or missing trade-off
- proposing a small experiment with a clear question, dataset, baseline, and way to check the output
- building a minimal Rust example with its dependency versions and reproduction steps
- improving the existing task descriptions while keeping them clearly separate from Rust ML experiments
- documenting a limitation, failed attempt, or setup issue that another learner might encounter

For substantial changes, please open an issue first so the goal and scope are clear. The [contributor guide](CONTRIBUTING.md) explains what to include in research notes and experiment pull requests. We will not add contributor names or claim results on someone's behalf; credit should follow actual contributions and their authors' preferences.

## References

### Rust machine-learning projects

- [Burn — repository and documentation](https://github.com/tracel-ai/burn)
- [Candle — repository and documentation](https://github.com/huggingface/candle)
- [Linfa — repository and documentation](https://github.com/rust-ml/linfa)

### Evaluation and reproducibility reading

- [OpenAI — Evaluate agent workflows](https://developers.openai.com/api/docs/guides/agent-evals)
- [OpenAI — Evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices)
- [Anthropic — Define success criteria and build evaluations](https://docs.anthropic.com/en/docs/test-and-evaluate/define-success)
- [Inspect AI documentation](https://inspect.aisi.org.uk/)

These references inform the learning plan; they do not imply that Arxh has implemented or independently validated the referenced tools, methods, or benchmarks.

## License

There is currently no `LICENSE` file in this repository. No open-source reuse license has been granted; please do not assume the contents are licensed for reuse. A license should be chosen before external reuse is encouraged.
