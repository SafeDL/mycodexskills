# Patent Drafting Workflow

Use this reference for full patent creation, major rewrites, or structured patent drafting from an invention disclosure.

## 1. Choose Scope

Confirm:

- target jurisdiction: CN, PCT, US, EP, or general technical draft
- application type: invention patent, utility model, provisional, utility, or other
- mode: Chinese technical disclosure, questionnaire, guided drafting, or autonomous draft
- search posture: no external search, sanitized public search, or full external search with user permission

If the user has confidentiality concerns, keep all work local and use only user-provided prior art.

For Chinese patent work, prefer this sequence unless the user asks otherwise:

1. structure or complete the Chinese technical disclosure;
2. identify protectable features and missing facts;
3. draft claim strategy;
4. draft claims, specification, abstract, and drawings.

## 2. Structure the Invention

Create an invention summary with:

- technical field
- technical problem
- closest known solutions
- distinguishing technical features
- required components or steps
- optional features
- embodiments
- technical effects

Flag each missing item as `Needed from inventor`.

## 3. Prior-Art and Difference Analysis

When prior art is user-provided, summarize each reference:

- title or identifier
- key disclosure
- overlapping features
- missing features
- why the invention may differ
- claim-drafting implications

When external searching is requested, follow `privacy-and-external-search.md`.

Do not present patentability as a legal conclusion. Use preliminary language such as "potential novelty distinction" or "drafting distinction."

## 4. Claim Strategy

Build a claim plan before drafting:

- independent claim type: method, apparatus/system, device, medium, product, composition, process, or use
- essential features that must stay in claim 1
- fallback features for dependent claims
- embodiments that deserve separate dependent claims
- features likely needed to distinguish prior art
- features that are useful but not essential

For Chinese claims, keep wording direct and technical. Avoid unnecessary functional results unless tied to structural or procedural limitations.

## 5. Draft Claims

Recommended order:

1. Draft one broad independent claim.
2. Draft dependent claims for structural refinements, process variants, parameter ranges, data flows, configurations, and effects.
3. Add a second independent claim only if it protects a materially different statutory category or commercial angle.
4. Review dependency chains.
5. Check every term against the specification support plan.

Typical claim set sizes:

- quick internal draft: 1 independent claim plus 5-8 dependent claims
- standard filing draft: 1-3 independent claims plus 8-20 dependent claims
- complex platform invention: multiple claim families, but only when each is supported

## 6. Draft Specification

Use this order unless the target jurisdiction requires a different format:

1. Title
2. Technical Field
3. Background
4. Summary
5. Brief Description of Drawings
6. Detailed Description
7. Embodiments and examples
8. Claims
9. Abstract

For Chinese invention patents, common section labels are:

- 技术领域
- 背景技术
- 发明内容
- 附图说明
- 具体实施方式
- 权利要求书
- 摘要

Avoid locking the invention into a single embodiment. Use language that supports variations while staying technically accurate.

## 7. Drawings and Reference Numerals

Prepare:

- figure list
- short figure description
- reference numeral table
- relationships among components or steps

Use stable reference numerals. Main elements often use round numbers such as 10, 20, 30; sub-elements can use 11, 12, 21, 22.

For method inventions, prepare flowcharts. For system inventions, prepare block diagrams. For mechanical or hardware inventions, prepare structural views and detail views.

## 8. Review and Iterate

Before finalizing, produce a review report covering:

- claim support in the specification
- antecedent basis
- terminology consistency
- unclear or relative terms
- unsupported technical effects
- missing embodiments
- drawing-reference consistency
- abstract length and clarity
- unresolved prior-art risks
- facts needing inventor confirmation

## 9. Package Output

For file-based drafting, use this layout:

```text
patent-draft-YYYYMMDD/
  01-invention-disclosure.md
  02-prior-art-and-differences.md
  03-claims.md
  04-specification.md
  05-abstract.md
  06-drawings.md
  07-review-report.md
```

Mark the result as a drafting package. Do not call it filing-ready unless official forms, format conversion, drawings, fee checks, and attorney review have been completed.
