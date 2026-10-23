---
name: peer-review
description: Structured peer review for autonomous driving, intelligent transportation, robotics, AI safety, trajectory prediction, planning, adversarial scenario generation, and Chinese/English top-journal or top-conference manuscripts. Use when reviewing or revising papers for methodology, novelty, experiments, statistics, reproducibility, datasets, simulation validity, safety claims, reporting completeness, and reviewer-response strategy.
---

# Peer Review for Autonomous Driving Research

Review manuscripts as a technically rigorous but constructive reviewer for autonomous driving, connected automated vehicles, intelligent transportation systems, robotics, and AI safety. Emphasize whether claims are supported by reproducible methods, credible datasets, appropriate baselines, valid risk metrics, and venue-appropriate positioning.

## Review Posture

- Lead with scientific validity, novelty, and reproducibility.
- Separate fatal flaws from fixable presentation or completeness issues.
- Be specific: cite sections, equations, figures, tables, datasets, metrics, and missing comparisons.
- Match expectations to the target venue: transportation journals value domain realism and safety interpretation; AI/robotics conferences value methodological novelty, ablations, and benchmark strength.
- For Chinese manuscripts, evaluate both academic rigor and compliance with Chinese journal style, terminology, GB/T 7714 references, and Chinese abstract/keyword quality.
- Do not request unnecessary experiments that exceed the manuscript scope unless they are essential to validate the central claim.

## Review Workflow

### 1. Triage the Manuscript

Identify:

- Research task: trajectory prediction, behavior modeling, motion planning, decision-making, scenario generation, simulation, perception, evaluation, risk assessment, or V2X/CAV control.
- Claimed contribution: theory, model architecture, dataset, metric, system, empirical benchmark, safety validation framework, or application study.
- Target venue and audience: IEEE/Elsevier transportation journal, robotics venue, AI/CV venue, Chinese top journal, or interdisciplinary journal.
- Main evidence: experiments, simulations, real-world data, case studies, proofs, ablations, or user/human-factor studies.

Output a concise summary of the paper's claim and your overall recommendation before detailed comments.

### 2. Novelty and Literature Positioning

Check whether the work clearly differs from:

- Trajectory prediction and interaction modeling: Social LSTM/GAN, graph neural networks, attention/transformers, diffusion/generative predictors, multimodal prediction, map-aware prediction.
- Planning and decision-making: rule-based planning, optimization, MPC, POMDP/RL, risk-aware planning, safety constraints, RSS/CBF approaches.
- Scenario generation and testing: falsification, adversarial testing, critical scenario mining, simulation-based validation, CARLA/SUMO/Scenic/CommonRoad workflows.
- Risk and safety: TTC, PET, DRAC, surrogate safety measures, collision probability, CVaR, EVT, SOTIF, ISO 26262, ISO 21448, UL 4600.
- Datasets and benchmarks: NGSIM, highD, inD, INTERACTION, Argoverse, nuScenes, Waymo, Lyft, KITTI, CommonRoad, OpenDD, exiD.

Flag missing comparisons to recent top-venue papers if the manuscript claims state-of-the-art or broad novelty.

### 3. Methodological Rigor

Evaluate whether the method is technically sound:

- Problem formulation: variables, assumptions, constraints, uncertainty, and interaction structure are explicit.
- Model design: architecture choices are justified rather than decorative.
- Risk formulation: EVT, CVaR, collision probability, surrogate safety metrics, or adversarial objectives are mathematically consistent.
- Scenario generation: generated scenarios are plausible, diverse, safety-critical, and not merely out-of-distribution artifacts.
- Simulation validity: simulator settings, traffic models, map sources, sensor assumptions, and agent behaviors are disclosed.
- Statistical analysis: significance, confidence intervals, variance across seeds, and effect sizes are reported where appropriate.
- Robustness: sensitivity to random seeds, hyperparameters, dataset splits, map regions, traffic density, and rare events is considered.

### 4. Experimental Design

Require experiments that match the central claim:

- Baselines: include classical, domain-specific, and recent deep-learning baselines.
- Ablations: isolate each major component, loss term, risk module, or data augmentation step.
- Metrics: use task-appropriate metrics, such as ADE/FDE/MR/minADE/minFDE for prediction; collision rate, comfort, progress, rule violations, TTC/PET/DRAC, and intervention rate for planning/safety.
- Dataset splits: prevent scene leakage, agent leakage, route leakage, or map-region leakage.
- Rare-event evaluation: report tail performance when claims involve extreme risk or safety-critical scenarios.
- Generalization: evaluate cross-dataset, cross-map, unseen scenario, or sim-to-real transfer when claimed.
- Efficiency: report runtime, model size, inference latency, and hardware if deployment relevance is claimed.

### 5. Reproducibility and Transparency

Check:

- Code, trained models, dataset preprocessing, and configuration files are available or sufficiently specified.
- Random seeds, training details, software versions, hardware, and simulator versions are documented.
- Data licenses and ethical/privacy constraints are handled correctly.
- Generated scenarios or benchmark splits are released when central to the contribution.
- LaTeX equations, algorithms, and pseudocode are consistent with the implementation described.

### 6. Safety and Ethics

For safety-related claims, verify:

- The paper distinguishes empirical improvement from certified safety.
- The operational design domain is explicit.
- Failure cases are discussed, especially for rare events and long-tail traffic interactions.
- Human driver data, video, or location data are anonymized and license-compliant.
- Claims about real-world deployment, accident reduction, or regulatory compliance are not overstated.

### 7. Writing, Figures, and Tables

Assess:

- The title and abstract state the actual task, method, and evidence without hype.
- Contributions are concrete and defensible.
- Figures explain architecture, pipeline, scenario generation, risk model, and qualitative cases clearly.
- Tables include strong baselines, standard deviations or confidence intervals when needed, and clear best/second-best marking.
- Chinese and English terminology is consistent, especially for autonomous driving terms such as trajectory prediction, adversarial scenario, surrogate safety measure, connected automated vehicle, and operational design domain.

## Review Report Format

Use this structure unless the venue requires another format:

1. Summary and recommendation.
2. Strengths.
3. Major concerns, ordered by importance.
4. Minor comments.
5. Questions for authors.
6. Required experiments or revisions, only when justified.

For each major concern:

- State the issue.
- Explain why it affects validity, novelty, or interpretation.
- Give an actionable revision path.
- Indicate whether it is essential for acceptance.

## Severity Guide

Critical issues:

- Central claim unsupported by experiments or theory.
- Baselines are missing or clearly unfair.
- Dataset leakage or invalid evaluation split.
- Safety certification or real-world deployment claims are overstated.
- Method cannot be reproduced from the paper and no code/details are available.

Major issues:

- Weak ablations for claimed components.
- No uncertainty or variance reporting for stochastic training/evaluation.
- Limited comparison to recent top-venue work.
- Inadequate rare-event or tail-risk evaluation.
- Unclear assumptions about maps, agents, sensors, traffic rules, or ODD.

Minor issues:

- Terminology inconsistency.
- Incomplete figure captions.
- Missing dataset citation or simulator version.
- Awkward English or Chinese phrasing.
- Citation style or bibliography formatting problems.

## Revision and Reviewer-Response Support

When helping authors revise:

- Convert reviewer concerns into a response matrix.
- Propose minimal experiments that directly answer each concern.
- Draft polite, evidence-based responses in English or Chinese.
- Keep claims aligned with the revised evidence.
- Update abstract, contribution statements, limitations, and conclusion after major experimental changes.

## Final Checklist

Before finalizing a review, confirm:

- The recommendation follows from the listed evidence.
- Major comments focus on validity, novelty, reproducibility, or safety.
- Baseline, dataset, metric, and ablation concerns are explicit.
- Safety and risk claims are checked against actual evidence.
- Chinese/English writing and venue fit are considered when relevant.
- Feedback is constructive, specific, and proportionate to the paper type.
