# Contributing to Arxh

Thanks for considering a contribution. Arxh is an early-stage machine-learning-in-Rust research and learning project. Its direction is still being shaped, so the best contributions help make the questions, evidence, and next steps clearer.

You do not need to be an expert in both Rust and machine learning. A small, carefully explained contribution is welcome—especially when it helps another person reproduce an experiment or understand a trade-off.

## Ways to contribute

- **Research notes:** summarize a Rust ML library or concept using primary sources, and distinguish upstream claims from your own observations.
- **Small experiments:** add a focused Rust example that answers a stated question and can be run with documented commands.
- **Reproducibility:** improve dataset provenance, dependency pinning, setup instructions, correctness checks, or result reporting.
- **Documentation:** clarify a concept, fix a technical error, or record an obstacle encountered while learning.
- **Evaluation tasks:** improve the existing exploratory agent task set, or propose a separate Rust/ML-specific task. Keep the two scopes distinct.
- **Visual assets:** contribute original images or images with a license that permits this use; record the creator, source, and license in `assets/README.md`. Do not describe a licensed stock image as public domain, imply endorsement, or remove its provenance.

## Before opening a pull request

For a substantial change, open an issue first. A short proposal should state:

1. **Question:** What are you trying to learn or clarify?
2. **Scope:** What is included, and what is intentionally out of scope?
3. **Evidence:** Which source, test, or measurement supports the change?
4. **Reproduction:** What exact steps should another person follow?

For a Rust experiment, include the applicable details:

- Rust toolchain and target platform
- crate versions, enabled features, and `Cargo.lock`
- dataset source, license, and preprocessing steps
- command used to run the experiment
- expected output or correctness check
- baseline, metric, hardware, and measurement conditions for any performance claim
- known limitations and failed attempts that affect interpretation

Do not claim that a library or language is faster, more accurate, or production-ready based on an uncontrolled comparison. Separate correctness results from timing results, and include the conditions needed to interpret both.

## Pull request checklist

- [ ] The change has a clear research or documentation purpose.
- [ ] Statements about third-party tools link to primary sources.
- [ ] Any experiment can be reproduced from the included instructions.
- [ ] Data and models have a clear source and permitted use; no private data or credentials are included.
- [ ] Results are labeled as measured, illustrative, or planned.
- [ ] The change does not present the current exploratory agent task set as a Rust ML benchmark.

We aim to review contributions with care and respect. If a proposal is incomplete, that is an opportunity to clarify the experiment together—not a reason to disguise uncertainty or overstate what is known.
