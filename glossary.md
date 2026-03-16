# Glossary of AI Engineering Terms

This glossary provides precise, unambiguous definitions for terms used throughout the AI Engineer Vault. Use these terms to ensure clear communication across engineering teams.

---

### A
- **Agentic Workflow**: A multi-step reasoning process where an LLM is given autonomy to plan, execute, and refine tasks through repeated iterations rather than a single turn.
- **Attention Mechanism**: The mathematical component of a Transformer that allows the model to weigh the importance of different parts of the input sequence relative to each other.
- **Auto-Evaluation (LLM-as-a-Judge)**: The practice of using a high-capability model to grade the outputs of another system based on predefined rubrics or reference data.

### B
- **BM25 (Best Matching 25)**: A sparse retrieval algorithm used to rank documents based on the frequency of query terms, serving as a critical component in hybrid search pipelines.

### C
- **Chunking**: The process of segmenting long documents into smaller, manageable pieces to fit within model context windows and improve retrieval granularity.
- **Context Window**: The maximum number of tokens a model can process in a single request, including both input and generated output.
- **Continuous Batching**: An inference optimization technique that allows new requests to be scheduled mid-generation, maximizing GPU throughput.

### D
- **Dense Embedding**: A high-dimensional vector representation of text where semantic meaning is captured in the values of continuous numbers rather than discrete keywords.
- **Deterministic Output**: LLM responses that are forced into a specific schema or format (e.g., valid JSON) using techniques like constrained decoding.
- **Distillation**: The process of training a smaller, more efficient model to replicate the performance of a larger, more expensive "teacher" model for a specific task.

### E
- **Embedding Model**: A specialized neural network designed to convert text or other modalities into numerical vectors for similarity searching.

### F
- **Fine-tuning**: The process of further training a pre-trained model on a specific, smaller dataset to adapt its behavior or domain knowledge.

### G
- **Greedy Decoding**: A text generation strategy where the model always selects the most probable next token, often resulting in less creative but more deterministic responses.

### H
- **Hallucination**: A phenomenon where a model generates factually incorrect or nonsensical information with high confidence.
- **Hybrid Search**: A retrieval strategy that combines semantic (dense) search with keyword (sparse) search to maximize precision and recall.

### K
- **KV Cache (Key-Value Cache)**: A mechanism that stores intermediate model states during inference to avoid redundant computations, significantly reducing latency for long sequences.

### L
- **LoRA (Low-Rank Adaptation)**: A parameter-efficient fine-tuning technique that only updates a small fraction of a model's weights by introducing low-rank matrices.

### M
- **MCP (Model Context Protocol)**: An open standard designed to unify the way AI applications connect to external data sources and tools, reducing the need for custom integrations.
- **Multimodal**: The capability of a model to process and generate multiple types of data, such as text, images, audio, and video, within a single architecture.

### N
- **Non-determinism**: The inherent unpredictability in LLM outputs where identical inputs may result in different responses due to sampling parameters.

### O
- **Quantization**: The process of reducing the precision of model weights (e.g., from 16-bit to 4-bit) to decrease memory usage and increase inference speed with minimal accuracy loss.

### P
- **Prompt Injection**: A security vulnerability where adversarial user input overrides a model's system instructions to perform unauthorized actions.

### R
- **RAG (Retrieval-Augmented Generation)**: An architectural pattern that retrieves relevant external data to provide context for an LLM's generation, reducing hallucinations and enabling access to private data.
- **Reranking**: An additional layer in a retrieval pipeline that uses a more expensive model to re-order the top results from a faster first-stage retrieval step.

### S
- **Semantic Caching**: The process of storing and retrieving previous model responses based on the semantic similarity of the query, rather than exact text matches.
- **Structured Output**: Forcing a model to return data in a machine-readable format like JSON or XML, typically enforced through system prompts or constrained decoding.
- **System Prompt**: The foundational instructions provided to a model that define its persona, constraints, and operational boundaries.

### T
- **Token**: The basic unit of text processed by an LLM; usually represents approximately 0.75 words.
- **Token Physics**: The study of how tokenization, context length, and generation speed impact system performance and cost.

### V
- **Vector Database**: A specialized database designed to store, index, and search high-dimensional embeddings with high efficiency.
- **Vertical Slice Architecture**: A design pattern that organizes code around specific features or "slices" of functionality, maximizing context isolation for AI coding assistants.

### Z
- **Zero-Shot Prompting**: A technique where a model is asked to perform a task without any prior examples or specific training for that task.
