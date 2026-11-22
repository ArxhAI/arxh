# Contributing to Arxh

Thanks for considering a contribution. Arxh is an early-stage learning and research project exploring machine learning with Rust, especially small neural-network methods. Its current state is documentation and planning: this repository has no Rust ML implementation, trained model, experiment runner, or measured Rust ML results. The founder reports that there is currently no budget to build or train a model. That constraint is user-reported; it is not a claim about compute hardware, and it must not be turned into an invented budget or benchmark.

The [proposed eight-week research plan](RESEARCH-PLAN.md) is a forward-looking agenda, not a record of completed work. Good contributions make a question more precise, improve the evidence trail, explain a method, or help design a future experiment that can be run responsibly. A careful correction or well-sourced learning note is useful even if it does not add code.

## Ways to contribute

- **Method notes:** explain a neural-network concept such as loss, initialization, convolution, residual connections, or attention. Link to the original paper or authoritative text, distinguish the source’s claim from your interpretation, and state what the concept does not tell us.
- **Rust ecosystem notes:** inspect official documentation for Burn, Candle, `tch-rs`, Linfa, or SmartCore. State the date and version/revision checked. Treat upstream capability claims as descriptions of that project until Arxh independently reproduces them.
- **Experiment proposals:** suggest a narrow task, dataset, baseline, correctness check, and measurement plan. Include the resource requirement and an explicit no-run outcome if the project cannot conduct the experiment without spending.
- **Reproducibility work:** improve environment notes, dependency/version capture, dataset provenance, test instructions, or reporting fields. Do not add a model or claim training happened without a scoped, approved change and evidence.
- **Existing evaluation suite:** improve the separate exploratory general-agent task inventory in `tests/`. Do not describe its 30 scenarios as Rust ML, deep-learning, or neural-network evaluations.
- **Visual assets:** add original technical diagrams or verified online photographs with a clear connection to ML methods or computing hardware. Keep creator, source, license, and intended use in [`assets/README.md`](assets/README.md). No portraits or visible faces, no data-center stock imagery, no generic staged coding photos, and no image-generation-model artwork. Do not call a licensed stock image public domain or imply the photographer endorses Arxh.

## Start with the question

For a substantial change, open an issue or short proposal first. It should explain:

1. **Question:** What do we want to learn, compare, or clarify?
2. **Scope:** What is included, and what is deliberately out of scope?
3. **Source or evidence:** Which paper, official document, test, or future measurement supports the change?
4. **Status:** Is the work planned, reviewed from literature, implemented, run, or independently verified?
5. **Resource fit:** Can the proposed work be completed without unapproved spending or unverified hardware assumptions?

This prevents a roadmap from quietly becoming a claimed result. It also gives reviewers a way to tell whether a new section belongs to the Rust ML research plan or to the older, separate agent-evaluation artifacts.

## Research-note format

A useful research note should let a reader trace each important statement. Include the question and date checked; the exact primary source or official project page; the source’s version, publication date, or repository revision where available; a short summary in your own words; the method or interface being discussed; limitations and counterevidence; and the next question left open. If a source is an abstract, marketing page, or secondary summary rather than the full paper, say so. Avoid turning a source’s stated capabilities into Arxh’s tested experience.

When two sources disagree, preserve the disagreement and identify what differs: task, data, implementation, version, hardware, or definition. Do not choose the more exciting number without understanding the setup. Link relevant statements close to where they appear, then provide a concise reference list. For reproducibility, the NeurIPS Paper Checklist offers prompts about experimental detail, compute resources, access to code/data, and attribution [1](https://neurips.cc/Conferences/2021/PaperInformation/PaperChecklist). It is a reference for good practice, not a certification that Arxh has completed a study.

## If proposing a future Rust experiment

An experiment pull request should state what will be run before presenting any outcome. At minimum, describe:

- task definition, expected input/output, and the single question being tested
- dataset provenance, terms, preprocessing, and fixed data split
- baseline and why it answers the same task
- model or algorithm, loss, initialization, optimizer, key hyperparameters, and seeds where applicable
- Rust toolchain, crate versions, feature flags, `Cargo.lock`, target platform, and exact command
- correctness checks that run before timing or accuracy claims
- hardware, memory, storage, runtime boundary, and any costs
- repeated-run policy, failures, limitations, and a clear distinction between observations and conclusions

No training run is required to contribute. If the required resources are unavailable, the appropriate change may be a protocol, a feasibility assessment, or a documented “not run” status. A successful compilation is not evidence that a model trained correctly; a single timing is not evidence that Rust or a framework is generally faster. If new resources become available, get agreement on the scope before using them and record the actual configuration rather than guessing.

## Visual contribution requirements

Use a real, attributable photograph only when the technical content adds value. Check the local copy for people/faces and confirm the source page and license before adding it. Store a reduced, repository-friendly local copy rather than relying on an undocumented remote hotlink. Include meaningful alt text and a caption that makes clear whether the image is illustrative. For diagrams, prefer clean, original SVGs with readable labels, a concise description, source citations for technical concepts, and an explicit “schematic” label when the drawing is not data. Avoid decorative diagrams that imply an implementation exists.

## Pull request checklist

- [ ] The change has a clear research, learning, reproducibility, or documentation purpose.
- [ ] Primary claims link to primary papers or official project documentation.
- [ ] Planned work and completed work are labeled accurately.
- [ ] No unrun experiment, model result, funding detail, contributor, or hardware access is invented.
- [ ] The general-agent task suite remains separate from Rust ML research.
- [ ] Dataset and image creator/source/license details are recorded; no visible faces are included.
- [ ] Local links, image paths, JSON, and SVG/XML are checked as applicable.
- [ ] The change does not imply that the repository has a broad reuse license; no `LICENSE` file currently exists.

We aim to review contributions with care and respect. Questions are welcome, uncertainty is expected, and corrections are part of learning in public. A contribution is not made stronger by making its claims sound more certain than its evidence allows.

## Reference

1. NeurIPS 2021 Paper Checklist Guidelines: [1](https://neurips.cc/Conferences/2021/PaperInformation/PaperChecklist).
