# Visual asset register and usage notes

This register records the visual assets displayed by the project README, where they came from, their technical dimensions, and what reuse limits apply. It exists to make the origin and purpose of each image visible. A local file being present in this repository does not, by itself, grant permission to reuse it.

## Visual direction

The README's visual direction is focused on Rust as a programming language and on the proposed process of learning machine-learning concepts with Rust. It uses the project wordmark, original vector schematics, and short code-concept animations. It does not use generic hardware photographs, stock imagery, people, faces, data-center imagery, fabricated screenshots, or generated photo-like illustrations.

The technical artwork uses code-like text and simplified shapes to explain ownership, borrowing, explicit enum results, and a proposed experiment workflow. The illustrations are conceptual. They are not screenshots from a compiler, Rust application, ML framework, training run, benchmark, or deployed system. Snippets are included to communicate an idea and are not represented as compiled or tested Arxh code.

## Project wordmark

### `arxh-header.png`

- **Description:** Project banner with the Arxh wordmark.
- **Dimensions:** 1500 by 500 pixels, PNG.
- **Source:** Supplied as a project branding asset. It is not an external stock image.
- **Creator and terms:** The repository does not state a separate author credit or reuse license for this file. Do not infer a general license for the wordmark or the repository from its inclusion here.
- **Use:** Branding at the top of `README.md`. It identifies the project and does not make a claim about an ML system or result.

## Original vector schematics

The following SVGs were drawn directly for this repository with vector shapes and text. Their large 1920 by 1080 view boxes preserve crisp edges when displayed at different sizes. They do not contain borrowed research figures, photos, or model-generated illustrations.

### `rust-ml-language-patterns.svg`

- **Dimensions:** 1920 by 1080 view box, scalable SVG.
- **Description:** Three Rust language concepts applied to a simple numerical buffer: a `Vec` owns values, a slice borrows a read-only view, and an `Option` makes empty input an explicit case.
- **Purpose:** Introduce language concepts relevant to reading numerical and ML code.
- **Limitations:** This is a conceptual schematic, not a Rust tutorial, a full function implementation, a framework example, or an Arxh experiment. Its snippets have not been compiled in this repository.
- **Source and reuse:** Original project visual prepared for this README. No separate reuse license is provided. Contact the project owner for permission beyond the terms that may apply to the repository as a whole.

### `rust-ml-research-loop.svg`

- **Dimensions:** 1920 by 1080 view box, scalable SVG.
- **Description:** Four proposed stages for future work: author a crate, check the code, test known inputs, and record versions and commands.
- **Purpose:** Explain a possible evidence-oriented workflow for exploring Rust ML.
- **Limitations:** This is a proposal only. It does not show a crate, test, check, benchmark, or other completed Arxh work. The command names are examples of future steps.
- **Source and reuse:** Original vector schematic prepared for this README. No separate reuse license is provided.

## Original animated GIFs

All three GIFs were authored specifically for this README. Their scenes use vector rectangles, lines, colors, and Rust-like code text. They contain no external photos, stock illustrations, generated imagery, or screen recordings. Their vector artwork was rendered as 3840 by 2160 frames with Resvg and assembled into palette-optimized animated GIFs with ImageMagick. The animations are designed as brief concept walkthroughs for repository readers.

### `gifs/rust-ownership-animation.gif`

- **Dimensions:** 3840 by 2160 pixels per frame, 10 frames, 4K animated GIF.
- **Description:** A `Vec<f32>` owns a set of values. A shared slice provides read-only access to the same values. The final frames show the conceptual end of the borrow while the owner remains available.
- **Purpose:** Illustrate the relationship between ownership and borrowing in Rust.
- **Limitations:** The animation is an explanatory concept, not a running program or measurement. It does not claim that ownership alone guarantees speed, scientific validity, or a particular memory footprint. Its sample code has not been compiled in the project.
- **Source and reuse:** Original vector-based animation created for this repository. No separate reuse license is provided.

### `gifs/rust-result-animation.gif`

- **Dimensions:** 3840 by 2160 pixels per frame, 10 frames, 4K animated GIF.
- **Description:** A `Result<f32, &str>` value branches into `Ok` and `Err` cases, with each path highlighted as it is handled by a `match` expression.
- **Purpose:** Show how an enum and pattern matching make success and failure cases visible in Rust code.
- **Limitations:** This animation is not compiler output and is not evidence that an ML operation has succeeded. It shows one language pattern only; it does not imply that all failure modes have been handled in a real application.
- **Source and reuse:** Original vector-based animation created for this repository. No separate reuse license is provided.

### `gifs/rust-iterator-pipeline-animation.gif`

- **Dimensions:** 3840 by 2160 pixels per frame, 12 frames, 4K animated GIF.
- **Description:** A short array of `f32` values passes through an iterator example. The animation traces borrowed items, copied values, a filter that removes a negative value, a clamp operation, and collection into a `Vec<f32>`.
- **Purpose:** Introduce Rust iterator adapters and make a small data transformation easier to follow.
- **Limitations:** The value flow is conceptual. Rust iterators are lazy, and intermediate steps are not represented as separately allocated collections. The code is not presented as compiled and has not been run in the project. It is not a model pipeline or ML result.
- **Source and reuse:** Original vector-based animation created for this repository. No separate reuse license is provided.

## External sources referenced by README

The README links to external Rust documentation, research papers, and conference videos as reading material. These links are not embedded image assets. Each source remains attributed to its author, publisher, or host, and its own page and terms govern reuse. The conference videos are external talks and are described as such; they are not represented as Arxh work or endorsements.

No external photo or video thumbnail is copied into the repository. Video links point to their source pages on YouTube. The creators' recordings remain theirs, and this asset register does not grant permission to download, edit, or redistribute them.

## License and reuse boundaries

There is no `LICENSE` file in the repository at the time of this review. Consequently, this register must not be interpreted as an open-source license for the README, diagrams, animations, branding, or other repository contents. The authorship information above identifies where the displayed artwork came from; it does not create a reuse grant. Ask the project owner before reusing project-created artwork when no separate license is stated.

External reference pages are subject to their respective publishers' terms. Attribution is not a substitute for permission where permission is required. Check the original source before reproducing any excerpt, frame, visual, or other content outside a link to the source.

## Maintenance checklist

When adding, editing, or replacing a visual asset:

1. Check the final local file and its context in the README. A source description alone cannot confirm that the stored image is accurate.
2. Keep visual content relevant to Rust programming, ML concepts, or a clearly explained research workflow. Avoid decorative hardware images that do not help explain the project.
3. Prefer original diagrams drawn as vector markup and code-concept animations over generated imagery or generic stock art.
4. Give every displayed file a descriptive name, useful alt text, a caption, and an entry in this register.
5. Record exact dimensions, whether a graphic is a static or animated file, authorship, and source links where applicable.
6. Label plans, examples, and conceptual diagrams so they cannot be mistaken for executed research, compiled code, or results.
7. For external material, identify the creator or publisher, original page, and applicable terms. Do not call content public domain unless the source explicitly establishes that status.
8. Preserve the distinction between a source's reported result and an Arxh result. Do not imply endorsement by an author, conference, or platform.
9. Check that relative image paths render in the README and that animation text remains legible at normal page width.
10. Review the repository's license status and all applicable source terms before making a reuse statement.

**Asset review date:** 22 November 2026. Update this register whenever a displayed file, source, caption, or intended use changes.
