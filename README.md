# Awesome Tracking Performance Drift in LLMs

A curated research collection focused on detecting, measuring, and understanding performance drift in large language models (LLMs). This repository brings together research papers, datasets, tools, benchmarks, and implementations for monitoring how LLM behavior and reliability change over time.

## Table of Contents

- [Topic Overview](#topic-overview)
- [AI-Assisted Research Paper](#ai-assisted-research-paper)
- [Citation Integrity Audit](#citation-integrity-audit)
- [Curated Research Papers](#curated-research-papers)
- [Datasets](#datasets)
- [Tools and Libraries](#tools-and-libraries)
- [GitHub Implementations](#github-implementations)
- [Tutorials and Learning Resources](#tutorials-and-learning-resources)
- [License](#license)

## Topic Overview

Large language models are continuously updated, fine-tuned, deployed across different environments, and exposed to changing data and user interactions. As a result, their performance may change over time, even when the underlying model or application appears unchanged. This phenomenon, commonly referred to as **performance drift**, can affect accuracy, robustness, factuality, safety, and consistency.

Tracking performance drift is important because conventional evaluation often provides only a snapshot of model behavior. A model that performs well on a benchmark today may behave differently after a model update, prompt modification, distribution shift, or change in usage patterns. Detecting these changes requires systematic monitoring and repeated evaluation.

Key research problems include defining meaningful drift metrics, distinguishing genuine model degradation from changes in evaluation data, identifying the causes of observed drift, and designing efficient monitoring systems. Major research directions include longitudinal benchmarking, distribution-shift detection, automated evaluation, behavioral monitoring, robustness testing, and statistical methods for detecting significant changes in model performance.

This repository collects research and practical resources addressing these challenges, with an emphasis on reproducible methods for evaluating LLMs over time.

## AI-Assisted Research Paper

### Tracking Performance Drift in Large Language Models

This paper investigates methods for monitoring changes in LLM performance and behavior over time. It reviews existing approaches to longitudinal evaluation, drift detection, and model monitoring, and discusses challenges in establishing reliable indicators of performance degradation or behavioral change.

**Paper:** [`paper/AI_Assisted_Research_Paper.pdf`](paper/AI_Assisted_Research_Paper.pdf)

## Citation Integrity Audit

The references and major claims used in this repository and accompanying research paper were reviewed for citation accuracy, source relevance, and consistency between claims and cited evidence.

**Citation Audit:** [`citation-audit/Citation_Integrity_Audit.pdf`](citation-audit/Citation_Integrity_Audit.pdf)

## Curated Research Papers

Research papers are organized into categories relevant to tracking LLM performance drift.

### LLM Evaluation and Benchmarking

- Papers on systematic evaluation of LLM capabilities.
- Benchmark design and longitudinal evaluation methods.
- Automated and model-based evaluation approaches.

### Distribution Shift and Drift Detection

- Research on detecting changes in data distributions.
- Methods for identifying shifts between training and deployment environments.
- Statistical approaches to monitoring model behavior.

### LLM Reliability and Robustness

- Studies of factuality, consistency, robustness, and reliability.
- Research examining changes in model behavior under different conditions.

### LLM Monitoring and Production Evaluation

- Methods for monitoring deployed LLM systems.
- Observability and continuous evaluation techniques.
- Research on detecting regressions following model or system updates.

See the complete reference collection in [`references/references.md`](references/references.md).

## Datasets

Datasets useful for evaluating LLM behavior, robustness, factuality, and performance changes are documented in [`datasets/datasets.md`](datasets/datasets.md).

Each entry includes:

- **Dataset name and source**
- **Description**
- **Potential use for drift analysis**
- **Access link**

## Tools and Libraries

This repository collects software useful for evaluating and monitoring LLMs, including evaluation frameworks, experiment-management tools, observability platforms, and statistical analysis libraries.

See [`tools/tools.md`](tools/tools.md) for the curated collection and descriptions.

## GitHub Implementations

Existing open-source implementations relevant to LLM evaluation, benchmarking, monitoring, and drift detection are documented in [`implementations/github-repositories.md`](implementations/github-repositories.md).

The collection prioritizes projects that are actively maintained, relevant to the research topic, and useful for reproducing or extending research experiments.

## Tutorials and Learning Resources

Recommended learning resources include:

- LLM evaluation and benchmarking tutorials
- Documentation for LLM evaluation frameworks
- Lectures and courses on machine learning evaluation
- Resources on distribution shift and concept drift
- Benchmark documentation and research guides
- Tutorials on statistical monitoring and experiment design

## Repository Structure

```text
awesome-topic-name/
├── README.md
├── paper/
│   └── AI_Assisted_Research_Paper.pdf
├── citation-audit/
│   └── Citation_Integrity_Audit.pdf
├── references/
│   └── references.md
├── datasets/
│   └── datasets.md
├── tools/
│   └── tools.md
├── implementations/
│   └── github-repositories.md
└── LICENSE
