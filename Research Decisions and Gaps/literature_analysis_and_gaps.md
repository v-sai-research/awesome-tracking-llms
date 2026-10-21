# Baseline Literature Analysis & Gap Identification

**Source Paper:** *Tracking Performance Drift in Large Language Models Across Successive Version Updates: A Survey* (Vedartha Sai Y, 2026)  
**Constraint Profile:** Low-Compute / Minimal VRAM / Open-Weight Models / Zero API Cost  

---

## 1. Literature Baseline Synthesis

### Central Methods
* **Longitudinal API Tracking:** Evaluating closed-source model endpoints at fixed chronological intervals under controlled prompt conditions (e.g., Chen et al. [2]).
* **Behavioral Fingerprinting:** Maintaining fixed prompt suites across domains (math, code, formatting, safety) to track behavioral shifts over time.
* **Executable Unit-Test Verification:** Using execution sandboxes to verify code functional correctness (e.g., HumanEval pass rates) rather than text similarity.
* **Multi-Metric Evaluation:** Profiling multidimensional performance trade-offs (accuracy, toxicity, calibration) simultaneously using frameworks like HELM.
* **LLM-as-a-Judge Scoring:** Automating multi-turn conversational quality assessment using standard judge models (e.g., MT-Bench).
* **Statistical Drift Profiling:** Quantifying relative performance drift $D_{i,j}$, weighted multidimensional drift $D_{\text{total}}$, and sample variance significance $Z$-statistics.

### Datasets
* **Prime Number Identification Dataset:** Used for testing step-by-step arithmetic reasoning stability.
* **HumanEval:** 164 hand-written Python coding problems for functional correctness evaluation.
* **MMLU:** 57 academic subjects for broad domain knowledge tracking.
* **TruthfulQA:** 817 questions probing human false beliefs and misconceptions.
* **MT-Bench:** 80 multi-turn conversational scenarios for dialogue quality judging.
* **Context Equilibrium Streams:** Extended interaction series evaluating context window retention.

### Measured Findings
* **Significant Capability Regression:** GPT-4 prime classification accuracy dropped from $84\%$ to $51\%$ between March and June 2023 updates.
* **Multidimensional Capability Trade-offs:** Model updates frequently improve specific dimensions (e.g., Safety from $85\%$ to $94\%$, Coding from $72\%$ to $75\%$) while inducing simultaneous regressions in others (e.g., Reasoning from $84\%$ to $51\%$, Formatting from $95\%$ to $78\%$).
* **Aggregate Score Blindness:** Composite benchmark scores (e.g., global MMLU averages) mask severe task-specific capability losses.

### Author-Reported Limitations
* **Proprietary Model Opacity:** Black-box API endpoints prevent weight-level or post-training causal tracing.
* **Sampling Stochasticity:** Generative output variance makes single-run comparisons statistically unreliable.
* **Benchmark Contamination:** Public benchmark suites leak into continuous training pipelines over time.
* **LLM-Judge Biases:** Automated judges suffer from verbosity, position, and self-enhancement biases.
* **High Compute Overhead:** Continuous full-suite multidimensional evaluation (e.g., HELM) incurs prohibitive computational costs.
* **Restricted Conversational Scope:** Context equilibrium studies operate on limited conversation structures.

### Unresolved Questions
* How does performance drift propagate across extended multi-turn dialogue horizons?
* Can model version regressions be proactively predicted prior to deployment using pre-flight probing?
* How does model drift affect schema compliance, contract validity, and structured outputs in downstream software?
* How does drift propagate through agentic function-calling tool chains?

---

## 2. Five Computationally Testable Research Gaps

### Gap 1: Schema Compliance & Formatting Drift Across Quantized Open-Weight Updates
* **Passage / Reference:** Section 6.2, "(4) Formatting Drift: Regressions in strict schema compliance, tag generation, or structured output parsing (e.g., JSON/XML)" and Section 6.5.
* **Limitation Distinction:**
  * *Author-Reported Limitation:* Academic benchmarks evaluate free-form text or multiple-choice questions, failing to measure strict schema compliance required by downstream software.
  * *AI Inference:* In compact open-weight models (e.g., Qwen-2.5-0.5B to 3B or Llama-3.2-1B to 3B), minor checkpoint updates or post-training quantization ($\text{FP16} \rightarrow \text{INT4}$) induce significantly higher relative formatting drift ($D_{\text{formatting}}$) than general capability drift ($D_{\text{general}}$).
* **Experimental Question:** How severely does strict JSON schema parsing pass rate ($D_{\text{formatting}}$) drift across model quantization levels ($\text{FP16}$ vs. $\text{INT8}$ vs. $\text{INT4}$) compared to standard accuracy metrics?
* **Evidence Needed:** Zero-shot pass/fail validation rates across 500 structured JSON extraction prompts, parsed deterministically using `pydantic` or `jsonschema`.
* **Verification Flag:** `[VERIFY REQUIRED]` Verify whether Tian et al. (2023) evaluated version-over-version or quantization-induced drift specifically, or only static single-point failure rates.

### Gap 2: Context Window Instability & Multi-Turn Goal Erosion in Compact Models
* **Passage / Reference:** Section 6.1, "models exhibit cumulative drift over continuous interactions, leading to context degradation and goal erosion" citing Dongre et al.
* **Limitation Distinction:**
  * *Author-Reported Limitation:* Dongre et al. evaluated context equilibrium on restricted, non-standardized conversational patterns.
  * *AI Inference:* Compact open LLMs ($< 3\text{B}$ parameters) exhibit non-linear state decay where initial turn accuracy remains stable, but goal retention drops sharply beyond 5 dialogue turns under system prompt variation.
* **Experimental Question:** To what extent does multi-turn goal preservation degrade across 5-turn vs. 10-turn dialogue chains in small open-weight models under system-prompt perturbations?
* **Evidence Needed:** Turn-by-turn state tracking accuracy (slot filling and negative constraint adherence) verified via deterministic programmatic verifiers across 100 multi-turn session transcripts.
* **Verification Flag:** `[VERIFY REQUIRED]` Verify if Dongre et al. (2025) evaluated open-weight local models or strictly proprietary commercial APIs.

### Gap 3: Causal Dissection of Reasoning Drift: Alignment vs. Quantization Compression
* **Passage / Reference:** Section 3.1, "An update can subtly modify how a model interprets instructions or produces intermediate reasoning... destroying performance on specific logical tasks" and Section 6.2.
* **Limitation Distinction:**
  * *Author-Reported Limitation:* Chen et al. [2] evaluated proprietary closed APIs (ChatGPT), creating a black-box limitation that prevented weight-level or post-training causal tracing.
  * *AI Inference:* Using open-weight model lineages (e.g., Llama-3.2 Base vs. Instruct, or FP16 vs. INT4 GGUF), step-by-step reasoning drift ($D_{\text{reasoning}}$) on deterministic arithmetic can be causally isolated between post-training instruction alignment shifts and weight quantization compression.
* **Experimental Question:** Does post-training instruction alignment induce greater step-by-step reasoning drift ($D_{\text{reasoning}}$) on deterministic symbolic tasks than low-bit quantization compression?
* **Evidence Needed:** Exact-match accuracy and step-by-step chain-of-thought verification rates on deterministic arithmetic datasets (e.g., prime classification / GSM8k subset) across Base, Instruct, and Quantized local model checkpoints.
* **Verification Flag:** `[VERIFY REQUIRED]` Verify whether the prime classification drop reported by Chen et al. has been replicated on open-weight Llama or Qwen model releases.

### Gap 4: Statistical Power of Compact Micro-Fingerprints for Continuous Drift Monitoring
* **Passage / Reference:** Section 4.1 "Behavioral Fingerprinting", Section 5.5 "Limitations of Aggregate Metrics", and Section 3.2 equations (5)–(6).
* **Limitation Distinction:**
  * *Author-Reported Limitation:* Comprehensive multidimensional evaluation frameworks (e.g., HELM) incur high computational costs that prevent continuous deployment execution, while macro-aggregate metrics hide task-specific regressions.
  * *AI Inference:* A lightweight, 50-prompt edge-case micro-fingerprint can detect statistically significant model drift ($|Z| > 1.96$) with $>90\%$ lower token consumption than full evaluation suites.
* **Experimental Question:** Can a 50-prompt edge-case micro-fingerprint detect model version drift with statistical equivalence ($p < 0.05$) to complete benchmark suites?
* **Evidence Needed:** Rank correlation (Spearman's $\rho$) between $Z$-statistic significance scores calculated on the micro-fingerprint versus full benchmark suites across 3 local model versions/quantizations.
* **Verification Flag:** `[VERIFY REQUIRED]` Verify whether existing behavioral fingerprinting literature formally evaluates statistical power ($Z$-score sensitivity) for micro-suite drift detection.

### Gap 5: Deterministic Programmatic Verifiers vs. LLM-as-a-Judge Under Output Drift
* **Passage / Reference:** Section 5.4, "While automated LLM-as-a-judge approaches offer scalable evaluation, they introduce distinct measurement biases, including verbosity and positional bias [13]".
* **Limitation Distinction:**
  * *Author-Reported Limitation:* Automated judges introduce systematic measurement errors, including verbosity bias and self-enhancement bias.
  * *AI Inference:* When model updates alter output verbosity or formatting without changing underlying correctness, LLM-as-a-judge scoring distorts relative drift metrics ($D_{\text{total}}$), whereas AST-based and schema-based deterministic verifiers maintain zero variance.
* **Experimental Question:** How much measurement variance and score distortion does output verbosity drift introduce into automated LLM-judge evaluations compared to deterministic programmatic verifiers?
* **Evidence Needed:** Inter-evaluator variance and rank-order stability of LLM-judge scores vs. Python AST/Regex verifiers when evaluating model outputs subjected to synthetic verbosity expansion.
* **Verification Flag:** `[VERIFY REQUIRED]` Verify whether Zheng et al. (MT-Bench) evaluated drift tracking across model updates specifically or only static model rankings.

---

## 3. Feasibility Ranking (Minimal Scope & Low Compute Profile)

| Rank | Research Gap | Research Significance | Resource Footprint | Implementation Feasibility |
| :--- | :--- | :--- | :--- | :--- |
| **1** | **Gap 1: Schema Compliance & Formatting Drift** | **High:** Addresses critical operational failure mode where downstream apps break due to JSON/schema parsing failures. | **Minimal:** Runs locally using 0.5B–3B parameter models (e.g., Qwen-2.5-0.5B-Instruct GGUF) via Ollama/llama.cpp. Zero API cost. | **High:** Uses deterministic Python parsers (`pydantic` / `jsonschema`) with binary pass/fail ground truth. |
| **2** | **Gap 4: Statistical Power of Micro-Fingerprints** | **High:** Solves the core bottleneck of high computational cost in continuous drift monitoring. | **Minimal:** Requires executing only 50 edge-case prompts across 2–3 quantized checkpoints. | **High:** Directly implements formulas (3)–(6) from Section 3.2 in pure Python. |
| **3** | **Gap 3: Causal Dissection (Alignment vs. Quantization)** | **Medium-High:** Overcomes proprietary opacity by isolating root causes on open weights. | **Low:** Runnable locally on small base vs. instruct open checkpoints (e.g., Llama-3.2-1B vs 1B-Instruct). | **Medium-High:** Evaluates exact-match arithmetic/logic answers using standard Python scripts. |