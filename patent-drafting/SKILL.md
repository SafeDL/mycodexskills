---
name: patent-drafting
description: Draft and review patent materials, especially Chinese technical disclosures and research-paper-to-patent conversions. Use for disclosure questionnaires, claims, specifications, abstracts, drawings, prior-art distinction, office-action drafts, claim-support and clarity checks, Word formula/figure QA, native threaded replies to patent-review comments, tracked-review preservation, and filing-package review. Work locally by default; search externally only when authorized or required for current legal or prior-art verification.
---

# Patent Drafting

## Operating Rules

- Treat outputs as drafting assistance, not legal advice. Recommend review by a qualified patent attorney or patent agent before filing or responding to official actions.
- Preserve confidentiality. Do not send unpublished invention details, draft claims, experimental data, source code, or business plans to external services unless the user explicitly authorizes that disclosure.
- Verify current filing rules, fees, procedures, and legal standards against official sources before stating specifics. Prefer CNIPA, USPTO, EPO, WIPO, and official law or regulation pages.
- Ask for missing invention facts before inventing technical details. Mark unavoidable assumptions explicitly.
- Keep claim scope tied to disclosed technical features. Do not add unsupported advantages, embodiments, parameters, or legal conclusions.
- Distinguish a drafting-complete artifact from a filing-ready package. Filing readiness also requires format conversion, formal drawings, official forms, fee checks, and legal review.

## Reference Routing

1. For a Chinese technical disclosure document, invention disclosure questionnaire, or conversion of research notes into a disclosure, read `references/chinese-technical-disclosure.md`.
2. For a new patent draft from an invention disclosure, read `references/drafting-workflow.md` and follow the staged workflow.
3. For claim review, antecedent basis, definiteness, claim hierarchy, specification support, embodiments, drawing descriptions, abstracts, or package validation, read `references/quality-checklists.md`.
4. For prior-art search, current legal-rule lookup, online patent databases, or confidentiality questions, read `references/privacy-and-external-search.md` before searching or calling any external service.
5. For editing a reviewed patent DOCX, replying in Word's actual reply box, migrating appended reply text into native threads, preserving tracked changes, or diagnosing Word repair warnings, read `references/word-review-threads.md` before editing.

## Invention Intake

Collect these facts before drafting when they are available:

- invention title or short name
- target jurisdiction and application type
- technical field and application scenario
- problem in existing technology
- closest known solution and its shortcomings
- core technical solution
- essential components, modules, method steps, inputs, and outputs
- novelty over known solutions
- alternative embodiments and optional features
- implementation details, parameters, data structures, algorithms, hardware, materials, or process conditions
- technical effects supported by disclosure, experiments, simulations, or use evidence
- known prior art, papers, products, patents, or internal disclosures
- inventors, assignee, priority information, and filing deadline if relevant

If the user provides only a rough idea, produce a Chinese technical disclosure questionnaire before drafting claims.

## Deliverables

For a full patent-drafting task, create or return the relevant artifacts rather than every file by default:

- Chinese technical disclosure or inventor questionnaire
- structured invention facts and assumptions
- prior-art differences and optional search plan
- independent and dependent claims
- specification sections: title, technical field, background, summary, drawings, embodiments, examples, and effects
- abstract
- drawing list, reference numerals, and drawing instructions
- review report covering support, antecedent basis, clarity, enablement, formal issues, and open risks

For Chinese patent disclosure and Chinese patent drafting, output Chinese text by default. Preserve technical English terms in parentheses only when they improve precision, and define abbreviations in Chinese at first use.

## Chinese Technical Disclosure Mode

When preparing a Chinese technical disclosure, prioritize the inventor-facing document before drafting formal claims. Use clear technical prose that a patent agent can transform into claims and a specification.

- Start with a cover table containing patent title, technical field, inventors/designers, drafter, and technical contact fields. Use placeholders for private contact details unless the user provides them for local use.
- Organize the body around: technical problem; technical background and closest existing solution; shortcomings of the existing solution and invention purpose; basic technical solution; detailed technical solution; key points and desired protection points; advantages; experimental, simulation, or use evidence; alternatives; drawings and explanations.
- For software, AI, algorithm, autonomous-driving, or data-processing inventions, describe inputs, data collection, preprocessing, model or algorithm steps, decision rules, thresholds, outputs, hardware or execution environment, and how the output changes a physical or technical process.
- Write the basic technical solution as a compact step or module summary. Write the detailed technical solution as implementable steps with variables, formulas, data structures, parameters, flowcharts, module interactions, and figure references where available.
- Convert key points into candidate protectable features, separating core independent-claim features from fallback dependent-claim features.
- Tie each stated advantage to a disclosed technical feature or experiment. Avoid unsupported absolute language such as "first", "best", or "completely solves" unless the user supplies evidence.
- Keep terminology consistent. Define abbreviations in Chinese at first use, and avoid English-only terms when a stable Chinese technical term exists.

## Research Paper Conversion And Word QA

When converting a research paper, manuscript, thesis, or experiment report into a Chinese patent technical disclosure, do not transfer the paper directly into patent form.

- Reframe the work from models, experiments, metrics, and performance into the patent chain of "technical problem - technical means - technical effect". Decompose the method into protectable steps, modules, inputs, outputs, thresholds, risk variables, estimation processes, and implementation flows.
- Maintain a document-wide terminology and symbol registry. Use one Chinese term and one symbol for each object, define every symbol at first appearance, and include body text, formulas, tables, figure captions, legends, indices, sets, mappings, distributions, sample counts, thresholds, weights, update variables, confidence/error metrics, and experimental metrics such as F1 or nAUC in the audit.
- For every formula block, provide a concise Chinese explanation of each symbol's meaning, input/output role, and calculation role. Keep explanatory prose outside equation objects; equations should contain mathematical expressions only, with no Chinese text or Chinese punctuation.
- In Word deliverables, use Word's native equation editor for inline and standalone notation with subscripts, superscripts, Greek letters, sets, probabilities, distributions, thresholds, mappings, operators, function calls, interval powers, hatted/barred variables, or estimator notation. Do not leave math as plain `_`, `^`, Unicode subscript/superscript characters, `Pr(...)`, or compact function notation in normal text.
- Use Times New Roman for non-equation Latin text, English abbreviations, and simple non-mathematical labels. Match inline equation size to body text and center standalone equations without disrupting line height.
- Work in modern `.docx`, not legacy `.doc`, when formulas matter. Confirm modern compatibility mode, real `m:oMath`/`m:oMathPara` formulas, no `equationxml`, no `w:pict`, and no image-formula remnants. Treat any Word warning that formulas will be converted to images as a blocking defect.
- For formula edits, prefer Word-native insertion or minimal targeted OOXML patches. After OOXML edits, verify ZIP/XML validity, open the file in Word, confirm formula counts, and avoid broad `document.xml` reserialization when namespace or relationship corruption is possible.
- Use patent figures to explain invention logic, not every experimental detail. When regenerating research figures, create separate `_patent` scripts/assets, preserve original figures, use Chinese black/white or grayscale labels, and ensure legends match actual line, marker, hatch, or fill encodings rather than color alone.
- Finish with layout QA. Prefer PDF/page-image rendering and inspect formulas, captions, tables, pagination, spacing, and abnormal blanks. If visual rendering is unavailable, disclose the limitation and run structural QA instead: Word open check, formula object counts, old-equation-field absence, no Chinese text/punctuation inside equations, no unrendered math in normal text, image/media counts, font checks, and consistent spacing around tables, figures, captions, equations, and body paragraphs.

## Word Review-Thread Editing

Treat the user's requested Word interaction as part of the deliverable, not merely as text placement.

- Interpret “在回复框中回复”, “直接回复该批注”, or an indicated reply field as a native child reply in the existing comment thread. Do not satisfy it by appending `zhengmin 回复：...` to the parent comment body or by creating a new top-level comment.
- Preserve the reviewer comment, its anchor, and its author. Add one reply to the corresponding parent comment and set the requested reply author explicitly; do not assume the signed-in Office account name will match.
- Use the Microsoft Word object model to create threaded replies when desktop Word is available. Let Word generate `commentsExtended.xml`, `commentsIds.xml`, `commentsExtensible.xml`, people metadata, relationships, and content types. Do not handcraft modern thread metadata for a production deliverable.
- Work on a new output copy and keep the source untouched. Preserve existing tracked changes and review settings unless the user explicitly asks to accept or reject them.
- Treat any Word repair, unreadable-content, compatibility, or formula-conversion warning as a blocking defect. Discard that output, return to the last clean source, and regenerate through Word-native APIs or a compatibility-safe method.
- Save, close, and reopen the output with Word before delivery. Verify the exact parent/reply counts, parent-to-reply mapping, reply author, absence of inline fallback markers, tracked-change preservation, ZIP/XML integrity, and comment-thread relationships.
- Use rendering for page layout, but never use PDF or page images as proof that comments or reply threads are correct. Validate comments structurally and through Word's object model; disclose any visual-QA limitation.

## Claim Drafting Principles

- Start with the broadest supportable independent claim. Use dependent claims for fallbacks, embodiments, parameter ranges, optional modules, and preferred implementations.
- Draft at least one apparatus/system claim or one method claim according to the invention type. Add storage-medium, device, or computer-program-product claims only when supported and appropriate for the target jurisdiction.
- Maintain clear antecedent basis: introduce an element before referring to it again.
- Avoid purely result-oriented limitations unless paired with concrete technical means.
- Avoid ambiguous relative terms unless the specification defines objective criteria.
- Keep every claim element supported by the detailed description and, when applicable, by drawings.

## Specification Drafting Principles

- Ensure the detailed description teaches how to make and use the invention without relying on hidden knowledge.
- Include multiple embodiments when they help broaden support, but keep each embodiment traceable to the core inventive concept.
- State technical effects as consequences of disclosed technical features, not unsupported marketing advantages.
- Use consistent terminology across claims, specification, abstract, and drawings.
- For drawings, keep reference numerals stable and mention every numbered element in the text.

## Final Response Style

When completing a patent task:

- State the drafting stage completed.
- List unresolved technical facts needed from the inventor.
- Separate legal/procedural uncertainty from drafting uncertainty.
- Provide the next practical step, such as inventor review, prior-art search, claim narrowing, drawing preparation, or attorney review.
