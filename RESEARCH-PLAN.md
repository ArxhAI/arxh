# Proposed Eight-Week Research Plan: Deep Learning with Rust

**Status:** proposed agenda and initial literature map. The eight weeks have not been completed. This file is not an experiment log, report of model training, or claim of results.

## Executive summary

Arxh is exploring how to learn and investigate machine learning, with a particular interest in neural-network methods implemented in Rust. The project is at an early documentation stage: the repository currently contains no `Cargo.toml`, Rust ML implementation, model, runnable experiment harness, trained weights, or measured ML result. The founder reports that there is currently no budget to build or train a model. That is a user-reported constraint, not an independently audited financial statement. No paid cloud service, GPU, dataset purchase, or other compute access is assumed in this plan.

The next two months are therefore framed as a **proposed literature-and-feasibility study**. The main deliverable is a carefully scoped experiment specification and a go/no-go decision for future implementation. If the necessary resources are not already available at no cost, it is responsible to stop before training; a well-documented protocol and a clear statement of what remains unknown are valid outcomes. The project will not fill a results table with estimates or describe a plan as completed research.

This is an initial scoping review, not a systematic literature review. The reading list below prioritizes original papers, an established textbook, and official Rust framework documentation. Source pages were consulted on 22 November 2026. The accessible material includes paper abstracts and metadata as well as project documentation; a future systematic review would need a declared search strategy, inclusion criteria, and broader coverage.

## Research questions

The plan is organized around questions narrow enough to answer with literature review and, only if feasible later, a small controlled implementation.

- **RQ1 — Method:** What concepts must be made explicit to understand a small neural-network training workflow: data representation, layers, activation functions, loss, gradients, initialization, optimizer, and evaluation?
- **RQ2 — Rust tooling:** How do selected Rust projects describe their support for tensors, automatic differentiation, neural-network layers, optimization, data pipelines, CPU execution, and model serialization? What dependencies and setup requirements are visible from their official documentation?
- **RQ3 — Feasible evidence:** Given the founder-reported lack of a model-building/training budget, what is the smallest experiment that could eventually be run without new spending, and what information would be necessary to reproduce and interpret it?

These questions do not ask whether Rust is generally better or faster than another language. A defensible language or framework comparison would need a specific workload, equivalent data and model behavior, clear measurement boundaries, versions, hardware, and repeated observations. That work is not in scope unless a later, separately approved plan supplies those conditions.

## Initial methods map

The method map is a learning scaffold, not a ranking or an assertion that Arxh has implemented any of these models.

1. **Multilayer perceptron and backpropagation.** A dense network composes transformations and nonlinearities; training adjusts parameters using a loss and gradients. Rumelhart, Hinton, and Williams describe backpropagation as repeatedly changing network connection weights to reduce the difference between desired and actual outputs [1](https://www.nature.com/articles/323533a0). The first useful study target is the whole computation path, including a hand-checkable forward pass and a gradient check—not the number of layers in a diagram.
2. **Initialization and optimization.** Model depth changes the behavior of signals and gradients through layers. Glorot and Bengio analyze the influence of nonlinearities and initialization on training deep feed-forward networks [2](https://proceedings.mlr.press/v9/glorot10a.html). The practical lesson for an experiment specification is to record initialization and optimizer settings rather than treating them as invisible implementation details. The paper does not establish one universally best configuration.
3. **Convolutional networks.** Convolutional models encode assumptions about spatially structured inputs through local filters and shared parameters. LeCun and colleagues describe gradient-based learning and convolutional networks in the context of document recognition [3](https://doi.org/10.1109/5.726791). A future task should have input structure for which that assumption makes sense; otherwise a CNN comparison may be uninformative.
4. **Residual networks.** Residual learning reformulates layers in relation to their inputs and was presented as a way to ease optimization of substantially deeper visual-recognition networks [4](https://openaccess.thecvf.com/content_cvpr_2016/html/He_Deep_Residual_Learning_CVPR_2016_paper.html). This provides a later architecture to study after a small baseline. It is not automatically a good first implementation under tight resource constraints.
5. **Attention and Transformers.** The Transformer paper proposes an encoder–decoder architecture based solely on attention mechanisms for sequence-transduction tasks [5](https://arxiv.org/abs/1706.03762). Attention is important in modern deep learning, but an architecture can be conceptually interesting and still be far beyond the resources or scope of a first experiment. The plan is to understand the method before considering any training.

Goodfellow, Bengio, and Courville’s online textbook organizes foundations across linear algebra, probability, numerical computation, machine-learning basics, feed-forward networks, optimization, convolution, and methodology [6](https://www.deeplearningbook.org/). It is a starting reference rather than a substitute for examining the primary paper relevant to a particular claim.

## Candidate software to inspect

No framework is selected. The review should compare a few candidates by reading their current documentation and, if the budget constraint changes, by recording a minimal installation attempt separately from any model experiment.

| Candidate | Role in the comparison | Questions to record |
|---|---|---|
| [Burn](https://burn.dev/docs/burn/) | Rust deep-learning framework. Its current documentation describes tensors, automatic differentiation, neural-network modules, optimizers, training, model storage, and selectable backends [7](https://github.com/tracel-ai/burn). | Which backend can be selected for a CPU-only prototype? Which Cargo features are necessary? What is the smallest documented training example? |
| [Candle](https://github.com/huggingface/candle) | Rust ML framework whose upstream project describes a minimalist focus [8](https://github.com/huggingface/candle). | What is provided for model definition, autodiff, training, and tensor operations? What does the example require beyond the crate itself? |
| [`tch-rs`](https://github.com/LaurentMazare/tch-rs) | Rust bindings to the C++ API of PyTorch [9](https://github.com/LaurentMazare/tch-rs). | What LibTorch version and native build setup are required? Does the external dependency fit the available environment? |
| [Linfa](https://rust-ml.github.io/linfa/rustdocs/linfa/) and [SmartCore](https://github.com/smartcorelib/smartcore) | Classical ML candidates that can help frame a simple baseline; they are not interchangeable with deep-learning frameworks [10](https://rust-ml.github.io/linfa/rustdocs/linfa/) [11](https://github.com/smartcorelib/smartcore). | Is a classical baseline appropriate for the selected task? Which baseline can be explained and checked independently? |

For each candidate, record the date checked, exact documentation or repository revision, release and crate versions if known, Rust toolchain, operating-system assumptions, feature flags, transitive/native dependencies, CPU path, data interface, model export options, testing example, and unresolved questions. A project’s own feature list is not evidence that Arxh successfully built or ran it. Compatibility and status can change after this plan is written.

## Proposed eight-week schedule

The weeks below are sequence markers for the upcoming two-month research window. They are planned activities, not completed milestones. The exit criteria are documentary and do not require claiming a training run.

| Week | Proposed focus | Planned output and exit criterion |
|---|---|---|
| **1 — Foundations** | Review tensors, affine maps, activation functions, loss functions, gradient descent, train/validation/test splits, and common sources of numerical error. Use the textbook and a small set of primary references. | A glossary and annotated source notes that distinguish definitions from Arxh’s interpretation. Explain one forward pass and the purpose of gradients in plain language. |
| **2 — Neural-network methods** | Compare MLPs, CNNs, residual connections, and attention at the level of assumptions, data shape, computation, and training questions. Do not attempt to survey every model family. | A method matrix listing the intended use, key operation, assumptions, resource implications to investigate, and one primary source per method. Mark every unresolved question. |
| **3 — Rust ecosystem reconnaissance** | Read official documentation for Burn, Candle, and `tch-rs`; inspect Linfa and SmartCore only for classical baseline context. Record version dates and setup requirements rather than accepting marketing summaries as measured evidence. | A candidate matrix with a source link for every entry, unknowns clearly marked, and no winner declared. |
| **4 — Task and data governance** | Define what makes a small classification or regression task educational and checkable. Identify candidate datasets only after verifying provenance, terms, license, format, and any redistribution restrictions. | A dataset decision record or a documented reason to use a synthetic toy fixture instead. No dataset is redistributed and no data is downloaded into the repository before its terms are understood. |
| **5 — Experiment specification** | Draft one narrow experiment card: research question, task, model, baseline, metric, data split, preprocessing, seed policy, correctness tests, and expected output. Prefer the smallest method that answers the question. | A pre-run protocol with all essential fields filled or explicitly marked “undecided.” No results or timings are entered before a run. |
| **6 — Resource-feasibility gate** | Check whether a suitable existing environment is available without new spending. Estimate memory, storage, toolchain, dependency, and time requirements from documentation. Any proposed code build or training remains conditional on permission and confirmed free resources. | A signed-off go/no-go note. If no suitable resources are confirmed, the study remains design-only; do not open a paid service, imply GPU access, or report a run. |
| **7 — Reproducibility and review** | Review the protocol for leakage, mismatched baselines, missing version information, under-specified splits, and misleading metrics. Design a result table that can distinguish correctness from runtime and single-run observation from repeated evidence. | A reproduction checklist and a second-pass review of claims against sources. Record reviewer and date only if an actual review takes place; do not invent contributors. |
| **8 — Synthesis and next decision** | Summarize what the literature and software documentation establish, what remains unknown, whether an experiment is feasible, and what funding or technical prerequisites would be needed next. | A concise readiness memo, updated bibliography, and a transparent go/no-go decision. If no model was run, say so prominently and leave performance-result fields blank. |

## Experiment card for a possible later run

This card is a template for future work. It intentionally leaves choices open until source and feasibility checks have been completed.

- **Question and claim:** What single observation would the experiment test? What would count as disconfirming evidence?
- **Task and data:** What is each input and target? Where did the data originate? What are its license, permitted use, and fixed train/validation/test split?
- **Method:** Which architecture, loss, activation, optimizer, initialization, and hyperparameters are used? Why are these appropriate to the question?
- **Baseline:** What simple, independent result can be checked by hand or with a transparent reference implementation? Is it solving exactly the same task?
- **Correctness:** Which tests validate tensor dimensions, output range, gradients or update behavior, labels, and evaluation code before timing begins?
- **Reproducibility:** What repository revision, Rust version, crate versions, feature flags, `Cargo.lock`, command, seed, and environment are required?
- **Resources:** What processor or accelerator, memory, storage, wall-clock time, and cost are used? If unavailable, say “not run.” Do not infer this information.
- **Reporting:** Which metric is primary? How many independent runs are practical? What will be reported about variance, failed attempts, and limitations?

A future metric table must not combine correctness and performance into a single vague score. For classification, accuracy alone may hide class imbalance; any metric choice should be justified from the task. Runtime needs a stated boundary—for example whether data loading, compilation, warm-up, and device transfer are included. If only one run is possible, label it a single observation and avoid broad conclusions. The NeurIPS checklist is a useful prompt for reproducibility, code/data access, compute reporting, and asset provenance [12](https://neurips.cc/Conferences/2021/PaperInformation/PaperChecklist). MLPerf Tiny’s rules are a separate benchmark reference for consistency and replicability, not an Arxh benchmark or a certification [13](https://github.com/mlcommons/tiny/blob/master/benchmark/MLPerfTiny_Rules.adoc).

## Risks, constraints, and non-claims

- **No current model-training budget.** The founder-reported constraint means no training is scheduled as a guaranteed deliverable. The plan does not assume a free GPU, cloud credits, or equipment.
- **Framework churn.** Rust ML APIs and supported backends change. Record the revision and features at the time of any future inspection; do not treat this plan’s links as permanent compatibility advice.
- **Scope expansion.** A comparison of multiple methods, libraries, datasets, and languages can quickly become unanswerable. The first experiment must hold most choices fixed and answer one question.
- **Data rights and leakage.** A dataset being downloadable does not establish permission for every use. Provenance, license, split, and preprocessing must be checked before an experiment.
- **Overclaiming from small samples.** A tiny CPU task can teach workflow and correctness. It cannot establish that Rust or a framework is faster or better across ML workloads.
- **Plans are not results.** No chart, benchmark, claim of training success, or reported error rate should appear until corresponding evidence exists and is verifiable.

The central success criterion for this two-month agenda is not a large model or an impressive score. It is a sharper research question, a source-grounded account of the methods and tooling, and a decision about what evidence can honestly be collected next. If the result is “not yet feasible without resources,” that is a useful and accurate conclusion.

## References

1. Rumelhart, Hinton, and Williams, “Learning representations by back-propagating errors,” *Nature* (1986): [1](https://www.nature.com/articles/323533a0).
2. Glorot and Bengio, “Understanding the difficulty of training deep feedforward neural networks,” PMLR (2010): [2](https://proceedings.mlr.press/v9/glorot10a.html).
3. LeCun et al., “Gradient-Based Learning Applied to Document Recognition,” *Proceedings of the IEEE* (1998): [3](https://doi.org/10.1109/5.726791).
4. He et al., “Deep Residual Learning for Image Recognition,” CVPR (2016): [4](https://openaccess.thecvf.com/content_cvpr_2016/html/He_Deep_Residual_Learning_CVPR_2016_paper.html).
5. Vaswani et al., “Attention Is All You Need,” arXiv:1706.03762 (2017): [5](https://arxiv.org/abs/1706.03762).
6. Goodfellow, Bengio, and Courville, *Deep Learning*, MIT Press (2016): [6](https://www.deeplearningbook.org/).
7. Burn documentation and repository: [7](https://github.com/tracel-ai/burn).
8. Candle repository: [8](https://github.com/huggingface/candle).
9. `tch-rs` repository: [9](https://github.com/LaurentMazare/tch-rs).
10. Linfa documentation: [10](https://rust-ml.github.io/linfa/rustdocs/linfa/).
11. SmartCore repository: [11](https://github.com/smartcorelib/smartcore).
12. NeurIPS 2021 Paper Checklist Guidelines: [12](https://neurips.cc/Conferences/2021/PaperInformation/PaperChecklist).
13. MLPerf Tiny Inference Rules: [13](https://github.com/mlcommons/tiny/blob/master/benchmark/MLPerfTiny_Rules.adoc).
