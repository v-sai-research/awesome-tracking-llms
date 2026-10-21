# LLM Performance Drift - Research Decisions & Evidence Log

## Project Metadata

* **Topic:** Tracking Performance Drift in Large Language Models Across Successive Version Updates `[VERIFIED: Provided in attached survey]`
* **Author:** Vedartha Sai Y (IIITA) `[VERIFIED: Document header]`
* **Status:** Stage 1 Complete $\rightarrow$ Transitioning to Stage 2 (Literature-to-Experiment Mapping) `[VERIFIED]`
* **Current Evidence Base:** `AI_Assisted_Research_Paper.pdf` (11-page survey paper) `[VERIFIED]`

---

## Decision Log

| ID | Stage | Decision | Reason / Justification | Source / Evidence | Status / Next Action |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **D-001** | 0. Setup | Created initial `research_decisions.md` tracking log | Maintain strict provenance, decision tracking, and auditability throughout the project lifecycle | User prompt specification | **Completed** |
| **D-002** | 1. Gap Analysis | Ingested and summarized primary literature review | Ground empirical research in verified survey findings without inventing papers or metrics | `AI_Assisted_Research_Paper.pdf` | **Completed** |
| **D-003** | 1. Gap Analysis | Extracted 6 candidate research frontiers from Section 6 | Select a concrete, feasible scope for implementation-based research paper | Survey Section 6 (pp. 9–10) | **Active:** User to select target research gap |
| **D-004** | 2. Mapping | Proposed experimental candidate setups based on survey equations and taxonomy | Connect survey math ($D_{i,j}$, $D_{total}$, $Z$-score) directly to executable Python benchmarks | Survey Section 3.2 & Section 4 | **Pending:** Awaiting resource & target model confirmation |

---

## Stage Tracking & Analysis Summary

### Stage 1: Scope Summary & Evidence-Based Gap Identification `[VERIFIED]`

#### A. Scope Summary of Source Literature Review
* **Core Subject:** Defines LLM performance drift as gradual or sudden behavioral shifts across model versions under constant evaluation conditions `[VERIFIED: Section 1]`.
* **Empirical Grounding:** Highlights longitudinal observations such as Chen et al. [2] where GPT-4's prime classification accuracy dropped from $84\%$ to $51\%$ between March and June 2023 `[VERIFIED: Section 1, Section 3.1]`.
* **Benchmarking Scope:** Synthesizes standard single-turn frameworks: MMLU [5], HumanEval [3], HELM [6], TruthfulQA [7], and MT-Bench [13] `[VERIFIED: Section 2]`.
* **Mathematical Formalization:** Defines relative drift ($D_{i,j}$), weighted multi-dimensional drift ($D_{total}$), and difference test statistic ($Z$) `[VERIFIED: Section 3.2]`:
  $$D_{i,j} = \frac{P_j - P_i}{P_i} \times 100$$
  $$D_{total} = \sum_{k=1}^{n} w_k \left( \frac{P_{k,j} - P_{k,i}}{P_{k,i}} \right), \quad \text{where } \sum w_k = 1$$
  $$Z = \frac{\bar{X}_j - \bar{X}_i}{\sqrt{\frac{s_i^2}{n_i} + \frac{s_j^2}{n_j}}}$$
* **Taxonomy:** Categorizes drift into 8 operational dimensions: Capability, Reasoning, Semantic, Formatting, Instruction-Following, Safety, Truthfulness, and Multi-Turn Interaction `[VERIFIED: Section 6.2]`.

#### B. Explicitly Identified Research Gaps (Source: Survey Section 6)
1. **Gap 1: Longitudinal Multi-Turn Evaluation:** Single-turn benchmarks fail to capture cumulative context degradation and state drift in multi-turn interactions `[VERIFIED: Section 6.1, Dongre et al. [4]]`.
2. **Gap 2: Standardized Drift Taxonomy Benchmark:** Lack of a benchmark explicitly evaluating all 8 proposed taxonomy dimensions under unified statistical testing `[VERIFIED: Section 6.2]`.
3. **Gap 3: Predictive Evaluation & Pre-Deployment Probing:** Lack of automated staging pipelines using statistical significance thresholding ($Z$-score) prior to routing live API traffic `[VERIFIED: Section 6.3]`.
4. **Gap 4: Time-Aware Immutable Benchmarking Infrastructure:** Difficulty separating true model drift from unannounced benchmark script/prompt template shifts `[VERIFIED: Section 6.4]`.
5. **Gap 5: Application-Level Regression Testing:** Academic benchmarks do not capture software contract compliance (e.g., schema validation, JSON/XML parsing failures) `[VERIFIED: Section 6.5, Tian et al. [12]]`.
6. **Gap 6: Drift in Agentic & Tool-Augmented Systems:** Non-linear cascading failures when function-calling or API interfaces drift in compound AI systems `[VERIFIED: Section 6.6]`.

---

### Stage 2: Literature-to-Experiment Mapping `[INFERRED / PENDING]`

To select the ideal gap for your paper, we must evaluate technical feasibility against your available compute and API budget.

#### Feasibility & Resource Assessment Matrix
* **Target Models under test:** `[UNKNOWN: User to specify (e.g., Open-source local models like Llama-3/Qwen-2.5 vs. Proprietary APIs like OpenAI/Claude/Gemini)]`
* **Execution Environment:** `[UNKNOWN: User to specify local GPU resources (e.g., VRAM) or API budget]`
* **Primary Metric Baseline:** Python execution pass-rate (Pass@k), JSON schema parsing error rate, or statistical $Z$-score thresholds `[INFERRED from survey Sections 3.2 & 4.3]`.

---

## Action Items & Next Immediate Steps

1. **Select Research Gap:** Choose 1 primary gap (or a hybrid combination of 2) from the list of 6 above. *(Recommendation for an implementation paper: **Gap 1 + Gap 5**—Multi-turn context degradation combined with JSON/schema formatting drift—or **Gap 3**—Building an automated CI/CD statistical drift probing engine).*
2. **Confirm Resources:** State your target models (open-weights vs. API) and available compute/API budget.