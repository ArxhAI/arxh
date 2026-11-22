# Visual asset register and usage notes

This file records what each visual asset is, where it came from, and what terms apply. A photo being described as “free” on a stock-photo site does not mean it is public domain. The Pexels photographs below remain subject to the Pexels License; those terms do not license other files in this repository.

## Visual direction

Arxh’s imagery should look like a real, careful technical project rather than generic technology decoration. The chosen subject matter is neural-network methods and the physical computing components that make ML execution possible. The image policy is:

- use real, source-verified photographs for photographs; do not generate photo-like imagery with an image-generation model
- prefer close-ups of processors, chips, circuit traces, mathematical methods, and actual scientific plots over generic offices, people-at-laptops, server corridors, or decorative “AI brain” graphics
- include no visible people or faces in project imagery
- do not imply that a photo shows Arxh’s own hardware, that a photographer endorses the project, or that a method diagram represents a completed implementation
- write original SVG schematics directly as vector markup when a method needs explanation; label conceptual drawings as schematics and cite the papers that motivate their terminology
- give every embedded image useful alt text, a meaningful local path, a source, and license notes

The header is a project-owned brand image, not an online research photo. The two Pexels photographs are illustrative hardware context only. They do not evidence that Arxh owns a GPU or has run an experiment. The method schematics explain MLP, CNN, attention, and research-protocol concepts; they are not screenshots of a model, traces from training, or copies of figures from papers.

## Photographs

### `compute-hardware-6636476.jpg`

- **Description:** Macro photograph of a microprocessor and electronic components on a blue motherboard. No people or faces are visible in the local image used here.
- **Photographer:** [Sergei Starostin](https://www.pexels.com/@sejio402/).
- **Original source page:** [Blue and Silver Circuit Board, Pexels photo 6636476](https://www.pexels.com/photo/blue-and-silver-circuit-board-6636476/).
- **Source-page dimensions:** 5873 × 3915 px, as listed on the Pexels page.
- **Local display copy:** 1125 × 750 px JPEG. This is a reduced display copy of the source photograph.
- **License:** [Pexels License](https://www.pexels.com/license/). The page labels the photo free under Pexels’ terms.
- **Credit:** “Photo by Sergei Starostin on Pexels.”
- **Use:** Hardware context in the README. It is not described as an Arxh system, GPU, benchmark setup, or experimental result.

### `circuit-board-macro-34924856.jpg`

- **Description:** Tight macro view of a computer circuit board and components, with a warm, shallow-depth-of-field look. No people or faces are visible in the local image used here.
- **Photographer:** [Ivan Chumak](https://www.pexels.com/@iohichu/).
- **Original source page:** [Close-Up of a Computer Circuit Board, Pexels photo 34924856](https://www.pexels.com/photo/close-up-of-a-computer-circuit-board-34924856/).
- **Source-page dimensions:** 7728 × 4344 px, as listed on the Pexels page.
- **Local display copy:** 1260 × 708 px JPEG. This is a reduced display copy of the source photograph.
- **License:** [Pexels License](https://www.pexels.com/license/). The page labels the photo free under Pexels’ terms.
- **Credit:** “Photo by Ivan Chumak on Pexels.”
- **Use:** A second, close-cropped hardware visual in the README; it is not evidence of project compute or hardware ownership.

Both local photographs were visually checked for visible people/faces on 22 November 2026. Neither depicts a data center. The source pages describe the images as photographs and identify their creators; the reduced local copies are not presented as public-domain content. The public Pexels license page says Pexels photos can be used for free and modified, that attribution is appreciated but not required, and that use must not imply endorsement or redistribute the assets through stock-photo or wallpaper platforms. Check the live source page and license again before reuse, because terms and page details can change.

### `arxh-header.png`

- **Description:** Arxh wordmark banner with the text “Say hello to Arxh”; no people or faces are visible.
- **Source:** Supplied by the project owner as a brand asset.
- **License:** Project-owner asset; no separate reuse license is stated in this repository.
- **Use:** Repository header only. It is not a stock photo and is not an endorsement by a third party.

## Original vector diagrams

### `rust-ml-research-loop.svg`

An original vector schematic created for this repository. It illustrates a proposed research process: formulate a narrow question, choose a method, specify a test, and report evidence. It is a plan, not a workflow implemented by Arxh. The SVG is drawn directly with vector shapes and text; it is not an image-generation-model output and does not reproduce a published paper figure.

### `deep-learning-methods.svg`

An original vector schematic created for this repository to distinguish three conceptual method families: dense MLP layers, local convolutional filters, and token-level self-attention. The drawings are deliberately simplified for orientation and do not show exact tensor dimensions, trained parameters, benchmark data, or an Arxh implementation. Source papers motivating the terms are linked in the README and [`RESEARCH-PLAN.md`](../RESEARCH-PLAN.md): Rumelhart et al. on backpropagation, LeCun et al. on gradient-based document recognition, and Vaswani et al. on the Transformer.

## License and reuse boundaries

Pexels’ “free” license is not a public-domain dedication. It allows certain uses under its own terms, including modifications, while prohibiting uses such as selling unaltered copies, implying endorsement by people or brands in an image, or redistributing the content on stock-photo or wallpaper sites. This register is a practical attribution record, not legal advice. Anyone reusing the photos should check the current Pexels terms and the individual source page.

The repository currently has no `LICENSE` file. That means this asset register must not be interpreted as granting an open-source license to the project text, code, diagrams, or branding. Each Pexels photo has its own source license; the project header is owner-supplied; the SVGs are original project assets but have no separate reuse grant recorded here. Permission for reuse outside the specific source terms should be confirmed with the project owner.

## Maintenance checklist

When adding or replacing an asset:

1. Inspect the final local file, not only a search thumbnail or a description. Confirm no visible faces or people.
2. Open the original source page and record the creator, title, stable URL, and stated license. Do not rely on a search-result snippet alone.
3. Confirm the image is not an AI-generated imitation and is relevant to deep learning, a method, ML, neural networks, or their actual hardware context.
4. Store an appropriately sized local copy and record its dimensions. Keep the source link so readers can identify the original.
5. Add meaningful alt text and a caption stating whether the image is illustrative. Avoid implying that an image proves a claim or depicts project work.
6. Run a link check and verify the README still renders with relative asset paths.
7. Revisit license and source information if the file is recropped, replaced, or moved; update this register in the same change.

**Asset review date:** 22 November 2026. The register describes the versions currently stored in this repository; it should be updated whenever those files change.
