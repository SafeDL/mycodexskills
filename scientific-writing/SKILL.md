---
name: scientific-writing
description: Scientific manuscript writing and revision for autonomous driving, intelligent transportation, robotics, AI safety, trajectory prediction, risk-aware planning, adversarial scenario generation, and Chinese/English top-journal or top-conference submissions. Use for IMRAD papers, LaTeX sections, abstracts, related work, methods, experiments, reviewer responses, bilingual terminology, IEEE/ACM/Nature/Elsevier/GB-T 7714 style adaptation, and publication-ready prose.
---

# Scientific Writing for Autonomous Driving Research

Write and revise scientific manuscripts for autonomous driving, intelligent transportation, robotics, and AI. Optimize for clear claims, defensible novelty, reproducible methods, strong experimental evidence, and venue-appropriate style in both English and Chinese.

## Core Rule

Final manuscript text must be polished prose, not planning bullets. Use bullets only as temporary outlines, reviewer-response matrices, or methods lists where the target venue allows them. Convert outlines into coherent paragraphs before delivery.

## Venue-Aware Writing Strategy

Adapt the manuscript to the target community:

- Transportation journals such as IEEE T-ITS, IEEE T-IV, TR-C, TR-B: emphasize traffic-domain motivation, safety interpretation, dataset realism, ODD, statistical credibility, and deployment constraints.
- Robotics venues such as ICRA, IROS, CoRL, RSS, RA-L: emphasize embodied decision-making, planning/control integration, real-time feasibility, simulation-to-real transfer, and reproducibility.
- AI/CV venues such as NeurIPS, ICML, ICLR, CVPR, ICCV, ECCV: emphasize methodological novelty, benchmark strength, ablations, scalability, and comparison with recent learning-based methods.
- Chinese top journals: emphasize rigorous Chinese academic expression, clear problem background, domestic and international research status, GB/T 7714 citations, Chinese abstract and keywords, and terminology consistency.
- Broad-impact journals: reduce field jargon, foreground why the work changes safety, mobility, or AI reliability beyond a narrow benchmark.

## Two-Stage Writing Workflow

1. Build a section outline:

- Identify the target venue and article type.
- List the central claim, evidence, figures/tables, and required citations.
- Decide the narrative order: problem, gap, method, validation, implication.

2. Convert the outline to prose:

- Write complete paragraphs with topic sentences and transitions.
- Integrate citations naturally.
- Avoid hype and unsupported causal language.
- Keep terminology, notation, and abbreviations consistent.
- End each section by reinforcing the manuscript's central contribution.

## Autonomous Driving Manuscript Structure

### Abstract

For English papers, include motivation, gap, method, evaluation setting, key quantitative result, and implication. For Chinese papers, ensure the abstract is self-contained and uses standard terms such as 自动驾驶, 轨迹预测, 风险评估, 对抗场景生成, 智能网联汽车, and 安全验证 when appropriate.

Avoid vague claims such as "significantly improves safety" unless the abstract reports the metric, dataset, and comparison.

### Introduction

Use a four-move structure:

1. Establish the safety or intelligence problem in autonomous driving.
2. Explain why existing prediction, planning, simulation, or risk methods are insufficient.
3. Identify the precise technical gap.
4. State contributions as testable claims tied to evidence.

Strong contribution statements usually specify:

- What is new: framework, model, objective, dataset, metric, theory, or validation protocol.
- Why it matters: rare-event risk, interaction realism, robustness, generalization, safety margin, or deployment feasibility.
- How it is validated: datasets, simulators, baselines, ablations, statistics, and qualitative cases.

### Related Work

Organize by problem logic rather than chronology:

- Trajectory prediction and interaction modeling.
- Risk-aware planning and decision-making.
- Scenario generation, adversarial testing, and simulation.
- Surrogate safety measures and extreme-risk modeling.
- Datasets, benchmarks, and evaluation protocols.

End each subsection with the gap your paper addresses. Do not write a citation catalog.

### Methods

Make the method reproducible:

- Define the driving scene, agents, state/action variables, map representation, time horizon, and operational assumptions.
- State model inputs, outputs, objective functions, loss terms, risk measures, and constraints.
- Explain why each component is necessary.
- If using EVT, CVaR, collision probability, TTC/PET/DRAC, or adversarial objectives, define the mathematical assumptions and interpretation.
- Include algorithm boxes or pseudocode for multi-stage pipelines, scenario generation loops, or training/evaluation procedures.
- Document implementation details, hyperparameters, random seeds, simulator versions, and computational resources when relevant.

For the user's current theme, deep extreme-risk-guided adversarial trajectory generation should explicitly connect:

- Extreme-value or tail-risk estimation.
- Risk-guided adversarial objective.
- Physical and traffic-rule plausibility constraints.
- Interaction-aware trajectory generation.
- Evaluation against safety-critical and naturalistic baselines.

### Experiments and Results

Use experiments to support each claim:

- Dataset or simulator: explain source, split, ODD, map regions, traffic density, and preprocessing.
- Baselines: include classical, transportation-domain, and recent deep-learning methods where appropriate.
- Metrics: select from ADE/FDE/MR, collision rate, TTC, PET, DRAC, comfort, route progress, rule violation, diversity, realism, tail-risk, and runtime.
- Ablations: isolate each module, loss, risk term, or generation constraint.
- Robustness: report seed variance, sensitivity, cross-scene or cross-dataset generalization when claimed.
- Qualitative cases: show why generated scenarios are critical, plausible, and interpretable.

Write Results objectively before interpreting them. Reserve mechanism and implications for Discussion.

### Discussion and Limitations

Discuss:

- Why the method works and where it fails.
- How results relate to safety validation, long-tail risk, and real-world deployment.
- What assumptions limit generalization.
- Whether simulation evidence supports only empirical safety improvement or stronger claims.
- Future work such as closed-loop validation, human behavior modeling, sensor uncertainty, real-world testing, or standardization.

Limitations should be concrete, not ceremonial.

## Bilingual Style Guidance

For English:

- Prefer precise, restrained verbs: demonstrate, indicate, reduce, improve, estimate, generate, validate.
- Avoid inflated phrases: revolutionary, unprecedented, perfectly safe, human-like in all cases.
- Use "autonomous driving" for the field, "automated vehicle" or "autonomous vehicle" for the system, and "connected automated vehicle" for CAV contexts.

For Chinese:

- Use formal academic phrasing and avoid colloquial translations.
- Preferred terms include 自动驾驶, 智能网联汽车, 轨迹预测, 运动规划, 行为决策, 风险评估, 极值理论, 对抗样本/对抗场景, 安全关键场景, 仿真测试, 交通冲突, 运行设计域.
- Keep acronyms consistent: ODD, CAV, AV, TTC, PET, DRAC, RSS, SOTIF, EVT, CVaR.
- For Chinese journals, align references with GB/T 7714 and ensure English titles, journal names, and conference names are formatted consistently.

## Figures and Tables

Use visual elements when they clarify the science, not as decoration.

Recommended figures:

- Overall framework or pipeline.
- Risk-guided adversarial trajectory generation process.
- Model architecture or optimization loop.
- Dataset/simulation setup and scenario examples.
- Quantitative comparison plots.
- Ablation and sensitivity analysis.
- Failure cases and limitations.

Recommended tables:

- Dataset statistics and split definitions.
- Baseline comparisons.
- Ablation results.
- Runtime and computational cost.
- Safety metric comparison.

Every figure caption should state what is shown, how to read it, and what conclusion is supported.

## Citation and Evidence Standards

- Cite original methods, datasets, simulators, metrics, standards, and benchmark papers.
- Use recent top-venue papers for state-of-the-art positioning.
- Use surveys only for high-level context.
- Verify references with the `citation-management` skill before submission.
- For Chinese manuscripts, balance international foundations with relevant Chinese domain literature when it adds context or authority.

## Reviewer-Response Writing

When revising after review:

- Create a response table with reviewer comment, action taken, manuscript location, and response text.
- Answer every concern directly and politely.
- Add experiments only when they address a specific validity or clarity issue.
- Update claims if new evidence narrows the contribution.
- Reflect new experiments in abstract, contribution list, results, discussion, and limitations.

## Final Manuscript Checklist

Before final delivery, verify:

- The central claim is stated consistently in title, abstract, introduction, and conclusion.
- Contributions are specific and evidence-backed.
- Methods are reproducible from the text and supplementary material.
- Experiments include appropriate baselines, ablations, and metrics.
- Safety and deployment claims are not overstated.
- Figures and tables support the narrative.
- Citations are accurate and venue-appropriate.
- Chinese and English terminology is consistent.
- The manuscript follows target venue formatting and word limits.
