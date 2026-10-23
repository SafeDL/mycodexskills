---
name: citation-management
description: Citation management for autonomous driving, intelligent transportation, robotics, AI, and Chinese/English top-journal or top-conference manuscripts. Use when finding, verifying, deduplicating, or formatting references for trajectory prediction, planning, risk assessment, adversarial scenario generation, driving simulation, safety validation, and CAV/AV research; supports BibTeX, DOI/arXiv metadata, IEEE/ACM/Nature/Vancouver/GB-T 7714 style expectations, and reference quality control for LaTeX papers.
---

# Citation Management for Autonomous Driving Research

Manage references with emphasis on autonomous driving, intelligent transportation systems, robotics, AI, and safety-critical systems. Prioritize accurate metadata, venue-aware citation choices, reproducible search records, and publication-ready BibTeX for Chinese and English manuscripts.

## Operating Principles

- Prefer primary, peer-reviewed sources from top venues; use arXiv only when the work is unpublished, very recent, or the accepted version is unavailable.
- For fast-moving AI/AV topics, balance foundational papers with recent papers from the last 3-5 years.
- Always verify DOI, title, author order, venue, year, pages, and conference/journal status before finalizing a `.bib` entry.
- Preserve official capitalization for datasets, simulators, benchmarks, and methods, such as nuScenes, Waymo Open Dataset, Argoverse, INTERACTION, highD, NGSIM, CARLA, SUMO, Scenic, CommonRoad, IDM, MOBIL, TTC, PET, RSS, CVaR, EVT, VAE, GAN, diffusion model, transformer.
- For Chinese LaTeX manuscripts, support `gbt7714`/GB-T 7714 output expectations and keep Chinese/English author names, journal names, and conference names consistent.
- Do not invent references. If metadata cannot be verified, mark the citation as unresolved and state what identifier or source is missing.

## Recommended Search Sources

Use the source mix that matches the task:

- Broad discovery: Google Scholar, Semantic Scholar, OpenAlex, arXiv, Crossref.
- Transportation and AV venues: IEEE Xplore, ACM Digital Library, Elsevier ScienceDirect, SpringerLink, TRB/TRR, Transportation Research Part C/E, IEEE T-ITS, IEEE T-IV, IEEE T-RO, IEEE RA-L.
- AI and robotics venues: NeurIPS, ICML, ICLR, CVPR, ICCV, ECCV, CoRL, ICRA, IROS, RSS, AAAI, IJCAI.
- Chinese-language and domestic submissions: CNKI, Wanfang, VIP, CSCD/CSTPCD sources when available.
- Biomedical-only sources such as PubMed are optional and usually irrelevant unless the manuscript concerns human factors, driver behavior, ergonomics, or injury risk.

## Autonomous Driving Query Patterns

Build searches from four parts: task, method, risk/safety concept, and benchmark or venue.

Example English queries:

```text
"trajectory prediction" "autonomous driving" "interaction" transformer
"adversarial scenario generation" autonomous driving safety validation
"extreme value theory" "traffic conflict" "autonomous vehicles"
"risk-aware planning" "connected automated vehicles" "TTC"
"nuScenes" "trajectory prediction" CVPR OR NeurIPS OR ICRA
```

Example Chinese queries:

```text
自动驾驶 轨迹预测 交互建模 综述
自动驾驶 对抗场景生成 安全测试
极值理论 交通冲突 风险评估
车路协同 风险感知 轨迹规划
```

Use citation chaining deliberately:

- Backward chaining: inspect references of a high-quality paper to recover foundations.
- Forward chaining: inspect citing papers to find recent extensions and critiques.
- Venue filtering: restrict to the target community when writing for a specific venue.
- Dataset filtering: search by benchmark names when comparing methods.

## Venue Prioritization

For English top-tier submissions, prefer:

- Journals: IEEE T-ITS, IEEE T-IV, IEEE T-RO, IEEE RA-L, Transportation Research Part C, Transportation Research Part B, Accident Analysis and Prevention, Nature Communications, Science Robotics.
- Conferences: CVPR, ICCV, ECCV, NeurIPS, ICML, ICLR, CoRL, ICRA, IROS, RSS, ITSC, IV, AAAI, IJCAI.

For Chinese top-tier submissions, prefer:

- Journals: 中国公路学报, 交通运输工程学报, 自动化学报, 中国科学: 信息科学, 计算机学报, 软件学报, 电子学报, 同济大学学报等领域认可期刊.
- Use Chinese citations only when they directly support domestic context, standards, datasets, policy background, or field-specific Chinese scholarship. Do not replace stronger international methodological sources with weaker domestic sources merely for language balance.

## Metadata and BibTeX Workflow

Use existing scripts in `scripts/` when identifiers are available:

```bash
python scripts/doi_to_bibtex.py 10.xxxx/example --output refs.bib
python scripts/extract_metadata.py --arxiv 2401.00000 --output refs.bib
python scripts/format_bibtex.py references.bib --deduplicate --sort year --descending --output references_clean.bib
python scripts/validate_citations.py references_clean.bib --report citation_validation.json
```

When no DOI is available:

- For conference papers, verify official proceedings metadata from IEEE, ACM, PMLR, CVF Open Access, OpenReview, or the conference website.
- For arXiv papers, check whether a later accepted version exists and cite the accepted version when possible.
- For datasets and simulators, cite the canonical dataset paper or official technical report, not only the project URL.
- For standards, cite the issuing body and standard number when relevant, such as ISO 26262, ISO 21448/SOTIF, SAE J3016, UL 4600, or RSS-related papers.

## Citation Key Conventions

Use stable, readable keys:

```bibtex
@inproceedings{alahi2016sociallstm,
@article{caesar2020nuscenes,
@inproceedings{sun2020scalability,
@article{colwell2023trafficrisk,
```

Preferred pattern: `firstauthorYYYYshorttopic`. Keep keys lowercase ASCII unless a project already uses another convention. For Chinese authors, use romanized family name plus year and topic.

## Field-Specific Validation Checklist

Before finalizing references, verify:

- Foundational AV, trajectory prediction, planning, simulation, and safety papers are represented.
- Recent SOTA papers from target venues are included when claiming novelty.
- Dataset and benchmark citations match the experiments actually used.
- Baseline method citations are the original papers, not secondary survey descriptions.
- Risk and safety metrics are cited to authoritative sources.
- Chinese and English citations use consistent bibliography style in LaTeX.
- arXiv entries are not stale when a published version exists.
- Duplicate entries are resolved by DOI, title similarity, and arXiv-to-proceedings mapping.

## Manuscript Integration

For LaTeX projects:

- Inspect the project bibliography style before editing references, especially `IEEEtran`, `gbt7714`, `natbib`, `biblatex`, or journal templates.
- Avoid changing unrelated citation keys unless necessary; preserve keys already used in `.tex`.
- After editing `.bib`, search for missing keys with `rg "\\\\cite"`.
- Compile or run the closest available LaTeX check when feasible.

For top-journal/top-conference writing:

- Use citations to position novelty, not to pad paragraphs.
- Prefer primary evidence in Introduction and Discussion; use surveys sparingly for broad context.
- In Methods, cite algorithms, datasets, simulators, metrics, and statistical/risk theory at first use.
- In Related Work, organize citations by research gap: prediction, interaction, risk, adversarial generation, simulation, validation, and deployment constraints.

## Common Pitfalls

- Citing an arXiv preprint when a CVPR/ICRA/IEEE version exists.
- Citing a dataset leaderboard page instead of the dataset paper.
- Using generic AI citations without connecting them to AV constraints.
- Missing transportation-domain sources when writing for T-ITS/T-IV/TR-C.
- Missing AI/robotics SOTA when writing for CVPR/NeurIPS/ICRA/IROS.
- Treating Chinese and English bibliographies as separate pools instead of one coherent evidence base.
