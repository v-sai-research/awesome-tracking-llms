## 1. Survey and Review Papers

### 1. Liu, M., Liu, R., Zhu, Y., et al. (2024).
*A Survey on the Real Power of ChatGPT.*  
*arXiv.*  
This survey reviews the capabilities and limitations of ChatGPT across different application areas and evaluation settings. It provides broader context for understanding how LLM performance should be measured and compared across tasks and models.  
[DOI](https://doi.org/10.48550/arXiv.2405.00704)

### 2. Shalev-Shwartz, S., & Shashua, A. (2025).
*From Reasoning to Super-Intelligence: A Search-Theoretic Perspective.*  
*arXiv.*  
Provides a theoretical perspective on reasoning in large language models and discusses the relationship between reasoning, search, and distributional changes.  
[DOI](https://doi.org/10.48550/arXiv.2507.15865)


## 2. Foundational Papers

### 3. Chen, L., Zaharia, M., & Zou, J. (2024).
*How Is ChatGPT’s Behavior Changing Over Time?*  
*Harvard Data Science Review, 6.*  
This study directly investigates changes in ChatGPT's behavior over time by evaluating the model on multiple tasks and comparing performance across different periods. It provides important evidence that LLM behavior can change even without users explicitly changing their prompts or evaluation procedures.  
[DOI](https://doi.org/10.1162/99608f92.5317da47)

### 4. Zhou, L., Schellaer, W., Ferri, C., et al. (2024).
*Larger and More Instructable Language Models Become Less Reliable.*  
*Nature, 634, 61–68.*  
This study examines how model scaling and instruction tuning can affect reliability. It highlights that increased capability does not always correspond to increased reliability and provides important evidence for studying behavioral changes in LLMs.  
[DOI](https://doi.org/10.1038/s41586-024-07930-y)

### 5. Pelrine, K., Imouza, A., Thibault, C., et al. (2023).
*Towards Reliable Misinformation Mitigation: Generalization, Uncertainty, and GPT-4.*  
*arXiv.*  
This research examines GPT-4's reliability in misinformation-related tasks, focusing on generalization and uncertainty. It is relevant to understanding how reliability and uncertainty can change across datasets and deployment conditions.  
[DOI](https://doi.org/10.48550/arXiv.2305.14928)


## 3. Recent Research Papers

### 6. Dongre, V., Rossi, R. A., Lai, V. D., et al. (2025).
*Drift No More? Context Equilibria in Multi-Turn LLM Interactions.*  
*arXiv.*  
This work examines changes in LLM behavior during multi-turn interactions and introduces the idea of context equilibria. It is particularly relevant to understanding how accumulated conversational context can influence model behavior and potentially contribute to observed performance drift.  
[DOI](https://doi.org/10.48550/arXiv.2510.07777)

### 7. Wu, Y., He, Y., Hu, Z., et al. (2026).
*CritICL: Inference-Time Weak-to-Strong Generalization from Small Language Model Failure Modes.*  
*arXiv.*  
This work examines how failure modes of weaker language models can be used to guide stronger LLMs during inference. It contributes to understanding how inference-time strategies can alter reasoning behavior and improve model performance.  
[DOI](https://doi.org/10.48550/arXiv.2608.27455)

### 8. Shen, X., Zhang, H., Li, P., et al. (2026).
*Boosting LLM Exploration via Weak-Model Guidance in RLVR.*  
*arXiv.*  
This study investigates how reinforcement learning with verifiable rewards can influence reasoning diversity and exploration in LLMs. It provides insights into how training procedures can affect model reasoning behavior.  
[DOI](https://doi.org/10.48550/arXiv.2608.27420)

### 9. Ba, Y., Zheng, Z., Xie, Y., et al. (2026).
*Understanding Evolution Strategies for LLM Reasoning: Broader Reasoning Coverage than GRPO.*  
*arXiv.*  
This paper studies how different training strategies influence reasoning behavior and parameter changes in LLMs. It is relevant to understanding how reasoning capabilities evolve as models undergo additional optimization.  
[DOI](https://doi.org/10.48550/arXiv.2608.27351)

### 10. Hoy, W., & Celik, N. (2025).
*STABLE: Gated Continual Learning for Large Language Models.*  
*arXiv.*  
This research investigates continual learning approaches for LLMs and examines the resulting effects on performance and forgetting. It is relevant to model drift because continuous model updates can introduce behavioral changes over time.  
[DOI](https://doi.org/10.48550/arXiv.2510.16089)

### 11. Wu, Y. Y., Pillai, A., Chen, Y., et al. (2026).
*BALMS: Benchmarking Agentic LLMs for Longitudinal Mental Health Sensing.*  
*arXiv.*  
This study evaluates LLM agents on reasoning over information collected across time. It contributes to research on longitudinal LLM behavior and the challenges associated with maintaining consistent reasoning across temporally distributed information.  
[DOI](https://doi.org/10.48550/arXiv.2608.27219)


## 4. Methods / Algorithms

### 12. Abdelnabi, S., Fay, A., Cherubin, G., et al. (2024).
*Get my drift? Catching LLM Task Drift with Activation Deltas.*  
*arXiv.*  
This work proposes activation-based methods for detecting changes in LLM task behavior. It is particularly relevant for identifying task drift without relying solely on changes in output-level performance.  
[DOI](https://doi.org/10.48550/arXiv.2406.00799)

### 13. Polo, F. M., Xu, R., Weber, L., et al. (2024).
*Efficient Multi-Prompt Evaluation of LLMs.*  
*Advances in Neural Information Processing Systems (NeurIPS 2024).*  
This paper proposes evaluating LLMs across multiple prompt variations rather than relying on a single prompt. The approach provides a more reliable measurement of performance variability and helps distinguish genuine model changes from prompt sensitivity.  
[DOI](https://doi.org/10.48550/arXiv.2405.17202)

### 14. Bravo-Rocca, G., Guitart, J., Dholakia, A., et al. (2026).
*KC-Agent: A Dual-Process Cognitive Architecture for Efficient ML Model Improvement.*  
*arXiv.*  
This research addresses data drift and continuous adaptation in machine-learning systems. It provides methodological insights into detecting and responding to changes in data and model behavior over time.  
[DOI](https://doi.org/10.48550/arXiv.2608.02351)

### 15. Che, T., Liu, J., Zhou, Y., et al. (2023).
*Federated Learning of Large Language Models with Parameter-Efficient Prompt Tuning and Adaptive Optimization.*  
*arXiv.*  
This study investigates client drift caused by heterogeneous data during federated LLM training. It is relevant to model drift because differences in client data distributions can lead to changes in model parameters and performance.  
[DOI](https://doi.org/10.48550/arXiv.2310.15080)


## 5. Applications

### 16. Tian, H., Lu, W., Li, T. O., et al. (2023).
*Is ChatGPT the Ultimate Programming Assistant – How Far Is It?*  
*arXiv.*  
This study evaluates ChatGPT's effectiveness as a programming assistant across different programming tasks. It demonstrates the importance of task-specific evaluation when assessing LLM performance and provides a useful reference for tracking changes in coding-related capabilities.  
[DOI](https://doi.org/10.48550/arXiv.2304.11938)

### 17. Liu, S., You, F., Chen, X., & Su, N. (2026).
*When Replanning Becomes the Bottleneck: Budgeted Replanning for Embodied Agents.*  
*arXiv.*  
This work examines how increasing context affects LLM-agent efficiency and replanning. It provides an application-oriented perspective on how context growth can influence the behavior and computational efficiency of language-model-based agents.  
[DOI](https://doi.org/10.48550/arXiv.2608.01428)


## 6. Evaluation Methods / Benchmarks

### 18. Zhuo, J., Zhang, S., Fang, X., et al. (2024).
*ProSA: Assessing and Understanding the Prompt Sensitivity of LLMs.*  
*Findings of the Association for Computational Linguistics: EMNLP 2024.*  
This paper examines how small changes in prompts can significantly affect LLM performance across tasks. It is useful for distinguishing genuine model drift from prompt-induced variability during evaluation.  
[DOI](https://doi.org/10.18653/v1/2024.findings-emnlp.108)

### 19. Wang, X., et al. (2024).
*MT-Eval: A Multi-Turn Capabilities Evaluation Benchmark for Large Language Models.*  
*Proceedings of EMNLP 2024.*  
This study evaluates LLMs in multi-turn conversations and examines performance degradation compared with single-turn settings. It is relevant to understanding how accumulated conversational context affects model behavior and evaluation outcomes.  
[DOI](https://doi.org/10.18653/v1/2024.emnlp-main.1124)

### 20. Siska, C., Marazopoulou, K., Ailem, M., & Bono, J. (2024).
*Examining the Robustness of LLM Evaluation to the Distributional Assumptions of Benchmarks.*  
*Proceedings of the 62nd Annual Meeting of the Association for Computational Linguistics (ACL 2024).*  
This paper investigates how benchmark assumptions can influence measured LLM performance and model rankings. It is particularly relevant when comparing model performance across datasets, benchmarks, or evaluation periods.  
[DOI](https://doi.org/10.18653/v1/2024.acl-long.560)
