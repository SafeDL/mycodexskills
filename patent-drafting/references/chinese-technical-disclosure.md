# Chinese Technical Disclosure Drafting

Use this reference when drafting, revising, or reviewing a Chinese patent technical disclosure document (`技术交底书`) before formal patent drafting.

## Purpose

A technical disclosure should let a patent agent understand the invention, identify protectable technical features, and draft claims without inventing missing facts. It is not merely a paper abstract or project introduction.

## Standard Structure

Use this structure unless the user provides an institutional template:

1. Cover information table
   - 专利名称
   - 所属技术领域
   - 专利发明人或设计人
   - 技术交底书撰写人
   - 技术问题联系人、电话、E-mail
2. 本发明要解决的技术问题是什么？
3. 详细介绍技术背景，并描述已有的与本发明最相近似的实现方案。
4. 现有技术的缺点是什么？针对这些缺点，说明本发明的目的。
5. 本发明技术方案的基本内容。
6. 本发明技术方案的详细阐述。
7. 本发明的关键点和欲保护点是什么？
8. 与最好的现有技术相比，本发明有何优点？
9. 本发明是否经过实验、模拟、使用而证明可行，结果如何？
10. 发明的变更设计、替代方案及其它用途。
11. 附图及说明。

If private contact details are not required for the current task, use placeholders instead of real phone numbers or email addresses.

## Writing Workflow

1. Extract invention facts from the user's notes: title, field, problem, closest existing methods, defects, core solution, detailed steps, figures, experiments, alternatives, and desired protection points.
2. If facts are missing, ask targeted inventor questions or mark `待发明人补充`. Do not fabricate algorithms, thresholds, parameters, experiments, or drawings.
3. Draft the basic solution as a concise overview of the method, system, device, or storage-medium implementation.
4. Draft the detailed solution as an implementable sequence. For each step, state inputs, processing operations, intermediate variables, outputs, and how the result is used.
5. Convert the detailed solution into protection points:
   - core features likely needed in an independent claim
   - fallback features for dependent claims
   - implementation details that support enablement but may not need to enter claim 1
6. Review the disclosure for sufficiency, consistency, and claim-drafting usefulness.

## Section Guidance

### 1. Technical Problem

State the concrete technical problem in the target field. Include the deployment scenario, affected system or module, and why existing practice is insufficient.

For AI/autonomous-driving inventions, specify the task, such as perception testing, ODD definition, online monitoring, trajectory prediction, planning, control, sensor fusion, simulation, or safety validation.

### 2. Background and Closest Existing Solution

Describe the closest known solution or representative solution types, not a broad literature review. For each type, summarize:

- implementation principle
- what it can solve
- why it remains insufficient for the target problem

Avoid unsupported statements that no solution exists. Prefer "目前常见方案包括..." and identify concrete limitations.

### 3. Shortcomings and Invention Purpose

Map each shortcoming to a purpose of the invention:

- subjective or manual construction -> automated or data-driven identification
- high-dimensional search -> reduced search space or guided search
- poor explainability -> causal, interpretable, or traceable analysis
- high computation cost -> surrogate model, online update, or low-cost inference
- static offline evaluation -> online monitoring or dynamic adaptation

### 4. Basic Technical Solution

Use one paragraph or a numbered list to summarize the full technical chain.

For method inventions, use steps such as:

1. collecting or constructing data;
2. extracting variables, features, or indicators;
3. building a model, graph, index, controller, monitor, or generator;
4. calculating a result, threshold, risk value, or control command;
5. using the result to perform monitoring, generation, warning, control, or degradation.

For system inventions, identify modules and data flow among modules.

### 5. Detailed Technical Solution

Make the disclosure implementable by a person skilled in the art. Include:

- data source, sampling, labeling, cleaning, and feature extraction;
- variables and definitions;
- algorithm flow, including initialization, iteration, update, termination, and output;
- formulas with every symbol explained;
- thresholds, hyperparameters, training or fitting methods, and default ranges when known;
- hardware, sensors, computing platform, vehicle subsystem, or execution environment when relevant;
- figure references for framework diagrams, flowcharts, causal graphs, block diagrams, and coordinate diagrams.

For software or algorithm inventions, avoid describing only an abstract goal. Tie the algorithm to concrete data processing and technical outputs.

### 6. Key Points and Desired Protection Points

Separate protection points into three levels:

- Core protection: indispensable features that define the inventive concept.
- Dependent protection: optional refinements, preferred models, parameters, thresholds, data structures, module interactions, or fallback embodiments.
- Support disclosure: details that prove implementability, explain effects, or support alternatives.

Use this section to prepare later claims, but do not overclaim beyond the disclosed implementation.

### 7. Advantages

Tie every advantage to a technical feature:

| Advantage | Supporting technical feature | Evidence or reasoning |
|---|---|---|
| [effect] | [feature/step/module] | [experiment, simulation, mechanism, or assumption] |

Avoid naked advantages such as "效率高" or "效果好" without explaining why.

### 8. Experimental or Simulation Evidence

If evidence exists, state:

- dataset, simulator, test platform, or prototype environment;
- compared baseline methods;
- metrics;
- quantitative results;
- limitations or unverified assumptions.

If evidence is not available, state what evidence should be supplemented, such as ablation studies, runtime analysis, robustness tests, or field simulation.

### 9. Alternatives and Other Uses

Do not write only "无" if plausible variants exist. Consider:

- replacing a model, estimator, optimizer, sensor, simulator, controller, thresholding rule, or feature extractor;
- applying the method to another vehicle subsystem, robot, intelligent transportation system, or industrial scenario;
- changing data modality, sampling frequency, parameter range, or deployment architecture.

Mark speculative alternatives as `可选替代方案，待发明人确认`.

### 10. Drawings

For algorithm and autonomous-driving inventions, propose drawings when absent:

- overall method framework;
- data collection or dataset construction process;
- model training or inference flow;
- online monitoring or search algorithm flowchart;
- system module block diagram;
- coordinate transformation or vehicle-sensor geometry diagram;
- example input/output or result visualization.

Every figure should have a short caption and every referenced variable or module should be defined in the text.

## Chinese Drafting Rules

- Define English abbreviations with Chinese translations at first use, e.g. 操作设计域（Operational Design Domain, ODD）.
- Use one Chinese term consistently for the same concept.
- Prefer "本发明提出/本发明包括/在一种实施方式中" over paper-style language such as "本文".
- Avoid pure principle or function descriptions. State the technical means used to achieve the function.
- Avoid unsupported legal or market conclusions. Do not state that the invention is patentable.
- For formulas, explain every symbol, input, output, and calculation role.
- For thresholds and parameters, say whether they are fixed, configurable, learned, calibrated, or selected by experiment.

## Review Checklist

Before delivering a Chinese technical disclosure, check:

- The technical problem is concrete and tied to a technical field.
- The closest prior art is described at a level useful for distinguishing features.
- Each defect of the prior art maps to a purpose or effect of the invention.
- The basic solution covers the complete technical chain from input to output/use.
- The detailed solution is implementable without hidden steps.
- Key points are separated from optional fallback features.
- Advantages are causally linked to technical features or evidence.
- Abbreviations have Chinese translations at first use.
- Terminology is consistent across all sections.
- Drawings are listed or requested when they are needed to understand the invention.
- Missing facts are marked explicitly instead of being invented.
