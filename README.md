# Tracking Performance Drift in Large Language Models Across Successive Version Updates

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

The following papers provide key perspectives on how LLM performance and behavior can change over time, across interaction settings, and across different tasks.

## 1. Survey and Review Papers

### 1. Liu, M., Liu, R., Zhu, Y., et al. (2024).
*A Survey on the Real Power of ChatGPT.*  
*arXiv.*  
This survey reviews the capabilities and limitations of ChatGPT across different application areas and evaluation settings. It provides broader context for understanding how LLM performance should be measured and compared across tasks and models.  
[DOI](https://doi.org/10.48550/arXiv.2405.00704)

### 2. Liang, P., Bommasani, R., Lee, T., et al. (2022).
*Holistic Evaluation of Language Models.*  
*arXiv.*  
This paper presents a comprehensive framework for evaluating language models across multiple dimensions, including accuracy, robustness, fairness, bias, and efficiency. It highlights the importance of evaluating LLMs beyond conventional task-specific performance metrics.  
[DOI](https://doi.org/10.48550/arXiv.2211.09110)


## 2. Foundational Papers

### 3. Bender, E. M., Gebru, T., McMillan-Major, A., & Shmitchell, S. (2021).
*On the Dangers of Stochastic Parrots: Can Language Models Be Too Big?*  
*Proceedings of the 2021 ACM Conference on Fairness, Accountability, and Transparency (FAccT), 610–623.*  
This paper examines the risks associated with increasingly large language models, including biases, environmental costs, and limitations in understanding language. It provides a foundational discussion of the societal and technical challenges involved in developing and evaluating LLMs.  
[DOI](https://doi.org/10.1145/3442188.3445922)

### 4. Chen, L., Zaharia, M., & Zou, J. (2024).
*How Is ChatGPT’s Behavior Changing Over Time?*  
*Harvard Data Science Review, 6(2).*  
This study directly investigates changes in ChatGPT's behavior over time by evaluating the model on multiple tasks and comparing performance across different periods. It provides important evidence that LLM behavior can change even without users explicitly changing their prompts or evaluation procedures.  
[DOI](https://doi.org/10.1162/99608f92.5317da47)

### 5. Chen, M., Tworek, J., Jun, H., et al. (2021).
*Evaluating Large Language Models Trained on Code.*  
*arXiv.*  
This paper introduces an evaluation of language models trained on code, focusing on their ability to generate functional programs. It presents the HumanEval benchmark and discusses the challenges of assessing code-generation capabilities, providing a foundation for evaluating LLM performance on programming tasks.  
[DOI](https://doi.org/10.48550/arXiv.2107.03374)

### 6. Hendrycks, D., Burns, C., Basart, S., et al. (2021).
*Measuring Massive Multitask Language Understanding.*  
*International Conference on Learning Representations (ICLR).*  
This paper introduces the Massive Multitask Language Understanding (MMLU) benchmark, which evaluates language models across a broad range of academic and professional subjects. It provides a standardized approach to measuring knowledge and reasoning capabilities across multiple domains.

### 7. Lin, S., Hilton, J., & Evans, O. (2022).
*TruthfulQA: Measuring How Models Mimic Human Falsehoods.*  
*Proceedings of the 60th Annual Meeting of the Association for Computational Linguistics (ACL), 3214–3252.*  
This paper introduces TruthfulQA, a benchmark designed to evaluate whether language models generate truthful answers to questions that commonly elicit misconceptions. It highlights the distinction between generating plausible responses and providing factually accurate information.  
[DOI](https://doi.org/10.18653/v1/2022.acl-long.229)

### 8. OpenAI, Achiam, J., Adler, S., Agarwal, S., et al. (2023).
*GPT-4 Technical Report.*  
*arXiv.*  
This technical report describes GPT-4's capabilities, limitations, and evaluation results across various academic and professional benchmarks. It also discusses safety evaluation and the challenges of assessing advanced language models across different tasks.  
[DOI](https://doi.org/10.48550/arXiv.2303.08774)

### 9. Ouyang, L., Wu, J., Jiang, X., et al. (2022).
*Training Language Models to Follow Instructions with Human Feedback.*  
*Advances in Neural Information Processing Systems (NeurIPS), 35, 27730–27744.*  
This paper introduces instruction-following language models trained using reinforcement learning from human feedback (RLHF). It demonstrates how human preferences can be incorporated into training and examines their effects on model behavior and instruction-following performance.  
[DOI](https://doi.org/10.52202/068431-2011)


## 3. Recent Research Papers

### 10. Dongre, V., Rossi, R. A., Lai, V. D., et al. (2025).
*Drift No More? Context Equilibria in Multi-Turn LLM Interactions.*  
*arXiv.*  
This work examines changes in LLM behavior during multi-turn interactions and introduces the idea of context equilibria. It is particularly relevant to understanding how accumulated conversational context can influence model behavior and potentially contribute to observed performance drift.  
[DOI](https://doi.org/10.48550/arXiv.2510.07777)

### 11. Pelrine, K., Imouza, A., Thibault, C., et al. (2023).
*Towards Reliable Misinformation Mitigation: Generalization, Uncertainty, and GPT-4.*  
*arXiv.*  
This research examines GPT-4's reliability in misinformation-related tasks, focusing on generalization and uncertainty. It is relevant to understanding how reliability and uncertainty can change across datasets and deployment conditions.  
[DOI](https://doi.org/10.48550/arXiv.2305.14928)


## 4. Methods / Algorithms

### 12. Zheng, L., Chiang, W.-L., Sheng, Y., et al. (2023).
*Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena.*  
*Advances in Neural Information Processing Systems (NeurIPS), Datasets and Benchmarks Track.*  
This paper investigates the use of powerful language models as evaluators of other language models. It introduces MT-Bench and Chatbot Arena to assess model responses and compare their performance. The study also examines the strengths and limitations of LLM-based evaluation.  
[DOI](https://doi.org/10.48550/arXiv.2306.05685)


## 5. Applications

### 13. Tian, H., Lu, W., Li, T.-O., et al. (2023).
*Is ChatGPT the Ultimate Programming Assistant – How Far Is It?*  
*arXiv.*  
This study evaluates ChatGPT's effectiveness as a programming assistant across different programming tasks. It demonstrates the importance of task-specific evaluation when assessing LLM performance and provides a useful reference for tracking changes in coding-related capabilities.  
[DOI](https://doi.org/10.48550/arXiv.2304.11938)

For the complete bibliographic information and citation collection, see [`references/references.md`](references/references.md).


## Datasets

Datasets useful for evaluating LLM behavior, robustness, factuality, and performance changes are documented in [`datasets/datasets.md`](datasets/datasets.md).

1)LLMDrift Dataset from Chen, Zaharia & Zou / Stanford

2)HELM Benchmark Suite from Stanford Center for Research on Foundation Models (CRFM)

3)MTEB (Massive Text Embedding Benchmark)	from Hugging Face / MTEB

## Tools and Libraries

This repository collects software useful for evaluating and monitoring LLMs, including evaluation frameworks, experiment-management tools, observability platforms, and statistical analysis libraries.

| Tool | Purpose | Relevance |
|---|---|---|
| **OpenAI Evals** | Framework for running standardized and custom LLM evaluations. | Provides consistent evaluations for comparing model performance across versions and time. |
| **DeepEval** | LLM testing framework with metrics for correctness, relevance, hallucination, and regression testing. | Helps detect behavioral and performance regressions after model or prompt changes. |
| **Arize Phoenix** | Open-source observability evaluation platform for LLM applications. | supports tracing, evaluation, hallucination detection, relevance analysis, and other LLM quality metrics. |
| **SciPy** | Python library for statistical analysis and hypothesis testing. | Supports statistical validation of whether observed performance changes represent significant drift. |
| **MLflow** | Experiment tracking and model evaluation platform. | Stores and compares evaluation metrics across experiments, model versions, and time periods. |

See [`tools/tools.md`](tools/tools.md) for the curated collection and descriptions.

## GitHub Implementations

Existing open-source implementations relevant to LLM evaluation, benchmarking, monitoring, and drift detection are documented in [`implementations/github-repositories.md`](implementations/github-repositories.md).

| Repository | What It Implements | Why It Is Relevant |
|---|---|---|
| **openai/evals** | Reusable framework for standardized and custom LLM evaluations. | Provides a consistent evaluation pipeline for longitudinal model comparison. |
| **confident-ai/deepeval** | Automated LLM evaluation, testing, and regression detection. | Useful for identifying changes in correctness, relevance, hallucination, and other behaviors. |
| **vibrantlabsai/ragas** | Evaluation of RAG and LLM applications using quality and retrieval metrics. | Helps identify performance changes in both generation and retrieval components. |
| **saranshhalwai/drift-detector** | Proof-of-concept system that establishes a baseline, re-evaluates an LLM, calculates drift, and tracks historical changes. | Directly supports longitudinal LLM drift detection using baseline-versus-current comparisons. |
| **egnaro9/model-drift** | Lightweight LLM regression tracker using a fixed evaluation suite and multiple behavioral metrics. | Useful for reproducible monitoring of accuracy, latency, reliability, verbosity, and refusal behavior over time. |

## Tutorials and Learning Resources

The following resources provide practical and theoretical guidance for learning about LLM evaluation, model monitoring, behavioral changes, and performance drift.

### LLM Evaluation

- **Stanford HELM — Holistic Evaluation of Language Models**  
  A comprehensive framework for evaluating language models across multiple scenarios, models, and metrics. HELM is particularly useful for understanding how to design systematic and reproducible LLM evaluations.  
  [HELM](https://crfm.stanford.edu/helm/index.html) SStanford CRFM


- **HELM Instruct — Instruction-Following Evaluation**  
  A practical example of multidimensional LLM evaluation using criteria such as helpfulness, completeness, conciseness, and harmlessness.  
  [HELM Instruct](https://crfm.stanford.edu/helm/instruct/latest/) SStanford CRFM+1


- **Hugging Face Evaluate Documentation**  
  A hands-on guide to evaluating machine-learning models and datasets using metrics, comparisons, and measurements. It includes tutorials, how-to guides, and conceptual material.  
  [Hugging Face Evaluate](https://huggingface.co/docs/evaluate/) HHugging Face+1


- **Hugging Face Lighteval**  
  An evaluation toolkit designed specifically for LLMs. It supports multiple backends and provides detailed sample-level evaluation results, making it useful for repeated and comparative evaluations.  
  [Lighteval Documentation](https://huggingface.co/docs/lighteval/) HHugging Face


### Model Monitoring and Drift

- **Google Machine Learning Crash Course — Production ML Systems: Monitoring**  
  Introduces production ML monitoring, including monitoring data, model quality, training-serving skew, and real-world performance. These concepts provide a strong foundation for understanding LLM performance monitoring.  
  [Production ML Systems: Monitoring](https://developers.google.com/machine-learning/crash-course/production-ml-systems/monitoring) GGoogle for Developers


- **Evidently — Data and ML Checks**  
  A practical introduction to monitoring machine-learning systems, including prediction quality, data quality, and data/prediction drift. The concepts are directly applicable to monitoring changes in LLM inputs and outputs.  
  [Evidently ML Monitoring Quickstart](https://docs.evidentlyai.com/quickstart_ml) DDocumentation


- **Evidently — Data Drift Methods**  
  Explains methods for detecting distribution changes and using drift as a signal when monitoring model performance, particularly when ground-truth labels are unavailable.  
  [Data Drift Documentation](https://docs.evidentlyai.com/metrics/preset_data_drift) DDocumentation


### Practical LLM Evaluation Tutorials

- **Evidently — LLM Evaluation Tutorials**  
  Provides end-to-end tutorials covering LLM evaluation, LLM-as-a-judge, RAG evaluation, LLM-as-a-jury, and different LLM evaluation methods.  
  [Evidently Tutorials and Guides](https://docs.evidentlyai.com/examples/introduction) DDocumentation


- **Hugging Face Evaluate — Using the Evaluator**  
  Shows how to evaluate a model using a model, dataset, and metric, with support for tasks including text generation, question answering, summarization, and classification.  
  [Using the Evaluator](https://huggingface.co/docs/evaluate/en/base_evaluator) HHugging Face


- **Hugging Face Evaluate — Evaluation Suites**  
  Demonstrates how to combine multiple evaluation tasks into a single evaluation suite. This is particularly useful for longitudinal testing where several performance dimensions need to be tracked simultaneously.  
  [Creating an EvaluationSuite](https://huggingface.co/docs/evaluate/main/en/evaluation_suite) HHugging Face

## License

This repository is licensed under the [MIT License](LICENSE).

You are free to use, modify, and distribute the original content of this repository, subject to the terms of the MIT License.

Third-party papers, datasets, tools, and other resources referenced in this repository remain subject to their respective licenses and terms of use.


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
