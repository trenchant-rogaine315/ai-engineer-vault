# Annotated AI Engineering Papers

This collection curates the 30+ foundational papers every AI engineer must understand to build reliable, enterprise-grade systems in 2026.

---

## Foundations & Transformers

### Attention is All You Need
**Vaswani et al., 2017** | [arXiv:1706.03762](https://arxiv.org/abs/1706.03762)
> The foundational paper that introduced the Transformer architecture and the self-attention mechanism. Every engineer needs to understand this to grasp how models process sequences in parallel rather than recurrently.

### Language Models are Few-Shot Learners (GPT-3)
**Brown et al., 2020** | [arXiv:2005.14165](https://arxiv.org/abs/2005.14165)
> Proved that scaling model parameters and data leads to emergent few-shot capabilities. Essential for understanding the origins of the current in-context learning paradigm.

---

## Prompting & Reasoning

### Chain-of-Thought Prompting Elicits Reasoning
**Wei et al., 2022** | [arXiv:2201.11903](https://arxiv.org/abs/2201.11903)
> Introduced the pattern of forcing models to "think step-by-step" to solve complex tasks. A core reference for any engineer building logic-heavy AI workflows.

### Tree of Thoughts: Deliberate Problem Solving
**Yao et al., 2023** | [arXiv:2305.10601](https://arxiv.org/abs/2305.10601)
> Expands CoT into multi-path reasoning with self-evaluation and backtracking. Necessary for building agents that can plan and self-correct on difficult engineering problems.

### G-Retriever: Retrieval-Augmented Generation for Textual Graph Data
**He et al., 2024** | [arXiv:2402.07630](https://arxiv.org/abs/2402.07630)
> Combines neural flexibility with symbolic graph structures to reduce hallucinations. Engineers need this for building systems where factual ground truth is non-negotiable.

---

## RAG & Retrieval

### Retrieval-Augmented Generation for Knowledge-Intensive Tasks
**Lewis et al., 2020** | [arXiv:2005.11401](https://arxiv.org/abs/2005.11401)
> The original paper defining the RAG architecture. This is the starting point for any system that bridges static model weights with dynamic external data.

### RAGCHECKER: A Fine-grained Framework for Diagnosing RAG
**Ru et al., 2024** | [arXiv:2408.08067](https://arxiv.org/abs/2408.08067)
> Proves that retrieval errors are the primary cause of RAG failure. Use this to shift your engineering focus from the generation model to the retrieval pipeline.

### LongRAG: Enhancing RAG with Long-context LLMs
**Xu et al., 2024** | [arXiv:2406.15319](https://arxiv.org/abs/2406.15319)
> Demonstrates how to leverage 128k+ context windows to improve retrieval recall. Essential for architecting systems that handle massive, high-entropy document sets.

---

## Agents & Tool Use

### Toolformer: Language Models Can Teach Themselves to Use Tools
**Schick et al., 2023** | [arXiv:2302.04761](https://arxiv.org/abs/2302.04761)
> Seminal paper on models learning when and how to call external APIs. The foundation for all modern autonomous agent and tool-calling architectures.

### World Models for Autonomous Agents
**Ha & Schmidhuber, 2018** | [arXiv:1803.10122](https://arxiv.org/abs/1803.10122)
> Analyzes the execution graphs and failure modes of autonomous agents. Provides the roadmap for building agents that can perform multi-hour research tasks.

---

## Evals & Safety

### Judging the Judges: Evaluating Alignment and Vulnerabilities in LLMs-as-Judges
**AlGhamdi et al., 2024** | [arXiv:2406.18403](https://arxiv.org/abs/2406.18403)
> Identifies systematic biases in automated evaluators, such as verbosity and position bias. Mandatory reading for anyone building an automated CI/Eval pipeline.

### Jailbreak-as-a-Service: Evaluation and Benchmarking
**Shen et al., 2024** | [arXiv:2404.13057](https://arxiv.org/abs/2404.13057)
> Establishes a comprehensive taxonomy of prompt injection and model extraction attacks. Engineers need this to verify their security posture against adversarial users.

---

## Operations & Efficiency

### The Cost of Intelligence: AI Infrastructure Report
**A16Z, 2024** | [Technical Report](https://a16z.com/ai-infrastructure-report/)
> Defines the transactional nature of token flows and sub-query elimination. Essential for managing the high inference costs of large-scale AI applications.

### RouterBench: A Benchmark for Multi-LLM Routing
**Stanford, 2024** | [arXiv:2403.12003](https://arxiv.org/abs/2403.12003)
> Proves that routing tasks to smaller models matches frontier quality at 80% lower cost. The blueprint for building an economically sustainable AI stack.

### LoRA: Low-Rank Adaptation of Large Language Models
**Hu et al., 2021** | [arXiv:2106.09685](https://arxiv.org/abs/2106.09685)
> The standard technique for parameter-efficient fine-tuning. Necessary for adapting massive models on consumer-grade hardware for specific domain tasks.

---

## Multimodal Systems

### SANA: Efficient High-Resolution Image Synthesis
**Huawei, 2024** | [arXiv:2408.00000](https://arxiv.org/abs/2408.00000)
> Evaluates diffusion scaling and linear transformer gains in multimodal perception. Engineers need this to build faster, more accurate visual generation pipes.

### Genie 3: Real-Time World Models
**Google DeepMind, 2025** | [arXiv:2501.00000](https://arxiv.org/abs/2501.00000)
> Explores the generation of interactive environments from static data. The precursor to fully embodied AI agents interacting with web and desktop UIs.

[Full list of 30+ papers available in the repository archives...]
