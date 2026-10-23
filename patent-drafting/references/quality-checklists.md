# Patent Quality Checklists

Use this reference when reviewing claims, specifications, abstracts, drawings, or final draft packages.

## Chinese Technical Disclosure Review

Check:

- cover information includes title, technical field, inventors/designers, drafter, and contact placeholders or local-use contact details
- technical problem is concrete and tied to a technical scenario, not only a broad industry need
- background identifies the closest existing solution or representative solution types
- shortcomings are specific enough to explain why the invention is needed
- invention purpose maps to the shortcomings of the existing technology
- basic technical solution summarizes the complete input-processing-output chain
- detailed solution discloses implementable steps, modules, variables, formulas, parameters, and figure references where relevant
- software, AI, or algorithm content includes data source, preprocessing, model or algorithm process, output, and technical use of the output
- key points are separated into core protectable features and optional fallback features
- advantages are linked to disclosed technical features, experiments, simulations, or technical reasoning
- experimental or simulation evidence states baselines, metrics, and quantitative results when available
- alternatives are considered instead of defaulting to "none" when plausible variants exist
- drawings are listed or requested for frameworks, flowcharts, module diagrams, coordinate transformations, and data/model pipelines
- English abbreviations have Chinese translations at first use
- terminology is consistent across all sections
- missing facts are marked as needing inventor confirmation instead of being invented

High-risk patterns:

- paper-style novelty claims such as "首次提出" without evidence
- only describing a principle, purpose, or function without technical means
- formulas with undefined symbols
- algorithm steps that skip inputs, update logic, termination criteria, or outputs
- advantages stated as slogans without feature-to-effect reasoning
- no alternative embodiments, even though model, sensor, threshold, optimizer, or deployment variants are technically plausible

## Claim Review

Check:

- claim numbering is continuous
- each dependent claim refers to a valid previous claim
- dependency chains make technical sense
- independent claims contain all essential features
- dependent claims add real limitations, not mere restatements
- each claim term has clear meaning in context
- every repeated element has antecedent basis
- functional language is backed by concrete means or steps
- relative terms are defined or replaced with objective criteria
- alternatives are written clearly
- no claim relies on unsupported advantages
- no feature appears only in claims without specification support

High-risk patterns:

- "configured to" without disclosed structure, algorithm, or process
- "substantially", "about", "high", "low", "fast", "optimal" without criteria
- "and/or" when alternatives should be separated
- pure result claims without technical implementation
- terms that shift between claims and specification

## Claim Support Matrix

When the claim set is substantial, create a table:

| Claim element | Specification support | Drawing support | Notes |
|---|---|---|---|
| [element] | [section/paragraph] | [figure/ref no.] | [risk/fix] |

Every independent claim element should map to at least one detailed-description passage. Dependent claim features should map to embodiments or examples.

## Specification Review

Check:

- technical problem is clear
- solution is described as technical features, not only effects
- at least one complete embodiment teaches implementation
- alternatives and variants support claim breadth
- terminology matches claims
- claimed parameters or thresholds are explained
- technical effects are causally linked to disclosed features
- drawings and reference numerals are described
- no important feature is introduced only in the summary
- no unsupported statement overpromises performance or legal effect

For software, AI, or algorithm inventions, ensure the specification discloses inputs, processing steps, model/data flow, hardware or execution environment when relevant, and output/use of results.

## Abstract Review

Check:

- single concise technical summary
- no marketing language
- no unsupported advantage
- no unnecessary legal phrasing
- includes field, core problem, solution, and key technical feature
- follows target-office length and format requirements after official verification

For CN drafts, keep the abstract compact and technical. For US drafts, verify current USPTO abstract requirements before filing.

## Drawing Review

Check:

- every figure mentioned in the brief drawing description
- every reference numeral appears consistently
- every numbered element is explained
- no unexplained element appears in a figure
- arrows and labels do not create unintended limitations
- method steps match method claims
- system blocks match apparatus/system claims

## Prior-Art Distinction Review

For each closest reference, identify:

- features disclosed by the reference
- features not disclosed
- combination risks with other references
- technical effect of the distinguishing feature
- whether the distinction belongs in claim 1 or a dependent fallback claim

Avoid absolute conclusions such as "this is patentable." Use drafting-focused conclusions such as "claim 1 currently distinguishes over Reference A by feature X, assuming Reference A does not disclose Y."

## Office-Action Response Drafting

When drafting a response:

- identify each rejection or objection separately
- quote or summarize the examiner's position briefly
- map amended claim language to specification support
- explain how amendments address the issue
- avoid admissions that a reference teaches more than necessary
- distinguish claim construction, facts, and legal argument
- recommend attorney review before filing
