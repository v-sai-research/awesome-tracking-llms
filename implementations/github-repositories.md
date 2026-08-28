
# GitHub Implementations for Tracking Performance Drift in LLMs

## 1. `openai/evals`

**What it implements:**  
OpenAI Evals is an evaluation framework for systematically testing LLMs and LLM-based systems. It provides reusable evaluation tasks, benchmark implementations, custom evaluation support, model interfaces, and tools for running evaluations across different models and configurations.

**Why it is relevant:**  
Performance drift can only be detected reliably when the model is evaluated using a consistent methodology. OpenAI Evals can provide the fixed evaluation layer for a longitudinal study, allowing the same prompts and datasets to be run against different model versions or at different points in time. The resulting scores can then be compared to identify changes in accuracy, reliability, reasoning, or other capabilities.

**Repository:** https://github.com/openai/evals


## 2. `confident-ai/deepeval`

**What it implements:**  
DeepEval is an LLM evaluation and testing framework designed for automated evaluation of LLM applications. It supports metrics for correctness, relevance, hallucination, task completion, RAG quality, conversational behavior, and other LLM-specific properties. It also supports custom metrics and regression testing.

**Why it is relevant:**  
LLM performance drift is multidimensional and may appear as changes in hallucination, relevance, correctness, or instruction following rather than simply a decrease in accuracy. DeepEval makes it possible to repeatedly evaluate the same test cases and compare multiple evaluation metrics across model, prompt, or application versions. This makes it useful for detecting regressions after model updates and for building automated drift-monitoring tests into an evaluation pipeline.

**Repository:** https://github.com/confident-ai/deepeval


## 3. `vibrantlabsai/ragas`

**What it implements:**  
Ragas is an evaluation framework for LLM applications, with a strong focus on RAG systems, agents, and application-level evaluation. It provides metrics for evaluating aspects such as response quality, retrieval quality, faithfulness, relevance, and other properties of LLM-generated responses. It also provides mechanisms for creating evaluation datasets and running experiments.

**Why it is relevant:**  
Performance drift can originate from different components of an LLM application. In a RAG system, for example, changes in the retriever, knowledge base, embeddings, prompt, or LLM can cause performance degradation. Ragas allows these components to be evaluated systematically and repeatedly. Comparing Ragas metrics across different time periods can therefore help identify whether the observed drift is related to generation quality, retrieval quality, or the overall application.

**Repository:** https://github.com/vibrantlabsai/ragas


## 4. `saranshhalwai/drift-detector`

**What it implements:**  
Drift Detector is a proof-of-concept MCP server specifically designed to detect changes in LLM performance over time. It establishes a baseline by generating a model-specific diagnostic questionnaire, samples the target model using controlled parameters, and stores the resulting question-answer pairs. Subsequent runs use the same questions and sampling conditions to compare current responses with the baseline.

The implementation stores model information, drift history, baseline responses, current responses, and diagnostic data using SQLite. It calculates a drift score based on differences between baseline and current responses and provides threshold-based alerts. It also includes a Gradio interface for visualizing historical drift trends.

**Why it is relevant:**  
This repository is particularly relevant because its architecture closely matches the core problem of longitudinal LLM drift detection:

```text
Initial Model
     ↓
Baseline Diagnostics
     ↓
Store Responses
     ↓
Re-evaluate Later
     ↓
Compare Responses
     ↓
Calculate Drift Score
     ↓
Track Historical Drift
```
It demonstrates how a model can be continuously sampled using controlled conditions and compared against a historical baseline. Although it is explicitly described as a proof of concept rather than a production-ready system, it provides a useful reference architecture for implementing longitudinal LLM performance monitoring.

**Repository:** https://github.com/saranshhalwai/drift-detector

## 5. `egnaro9/model-drift`

**What it implements:** 
model-drift is a small public LLM regression tracker designed specifically to monitor changes in model behavior over time. It uses a frozen, hash-fingerprinted evaluation suite and runs it repeatedly against multiple LLMs. The repository tracks metrics including accuracy, latency, verbosity, reliability, and refusal rate. It uses deterministic grading rather than relying on an LLM judge and maintains historical results for comparison.

**Why it is relevant:**
This implementation is highly aligned with longitudinal performance-drift research because it treats model evaluation as a repeated time-series measurement problem. A fixed evaluation suite makes it possible to distinguish changes in model behavior from changes in the evaluation data. Tracking multiple metrics is also valuable because an LLM can remain accurate while becoming more verbose, less reliable, slower, or less compliant with output constraints.

Its approach is particularly useful for designing a research experiment in which:

```text
Fixed Evaluation Suite
        ↓
Model Version / Date
        ↓
Evaluation Metrics
        ↓
Historical Results
        ↓
Run-to-Run Comparison
        ↓
Performance Drift
```

The repository is therefore a useful example of a lightweight, reproducible longitudinal LLM monitoring system rather than a general-purpose evaluation framework.

**Repository:** https://github.com/egnaro9/model-drift

