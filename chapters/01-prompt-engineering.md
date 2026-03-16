# Chapter 01: Prompt Engineering Patterns

> [!TIP]
> **TL;DR**
> - Prompts are code, not just magic text; they require version control and testing.
> - Deterministic output is achieved through structured schemas, not "asking nicely."
> - Multi-path reasoning (Chain-of-Thought) significantly reduces logical errors.
> - Defensive meta-prompting is the primary defense against semantic drift and injection.

## What this chapter covers
In this chapter, we move beyond the trial-and-error approach to interacting with Large Language Models. We treat the prompt as a programmatic interface—a "software contract" between your application and the model. 

You will learn battle-tested patterns for enforcing structured outputs (like JSON or YAML), implementing multi-step reasoning frameworks like "Tree of Thoughts," and hardening your instructions against adversarial inputs. We focus on techniques that ensure your system instructions remain effective even as underlying model weights are updated by providers.

## When you need this
- **Use this when**: Your application requires reliable, machine-readable data from a model or needs to perform complex logical tasks.
- **Do NOT use this when**: You are performing simple creative writing tasks or one-off chat interactions where consistency is not required.

## Core Concepts

### Prompting as Software Engineering
To build reliable AI systems, you must stop viewing prompts as a "black box" of natural language and start viewing them as executable code. This means applying the same rigor as traditional development: modularity, versioning, and regression testing. A production-ready system prompt should have an explicit version number and be stored in your codebase, not inside a database or a hardcoded string. This allows for clear rollbacks and auditing when a model update causes unexpected "prompt drift."

### Structured Output Enforcement
One of the most persistent failure modes in AI engineering is the model returning prose when your backend expects a specific data structure. While "Shot" prompting (Zero-shot, Few-shot) is common, production systems should rely on "Grammar-based" or "Constrained Decoding" interfaces provided by APIs (like OpenAI's JSON Mode or Anthropic's Tool Use). When these are unavailable, you must implement "Retry-with-Correction" patterns, where the model is fed its own invalid output along with a schema error to self-correct.

### Chain-of-Thought (CoT) and Reasoning Loops
Models are notoriously bad at "mental math" and logical deduction when asked to provide an answer immediately. The "Chain-of-Thought" pattern forces the model to articulate its reasoning step-by-step before arriving at a conclusion. In 2026, this has evolved into "Tree of Thoughts" and "Graph-constrained Reasoning," where the system generates multiple reasoning paths, evaluates the validity of each, and selects the most optimal branch. This pattern is essential for tasks requiring high precision, such as code generation or financial analysis.

### Meta-Prompting for Context Optimization
As systems scale, providing the entire context for every turn becomes prohibitively expensive. "Meta-prompting" involves using a secondary, highly efficient model to summarize or prune the context before it is sent to the primary model. Alternatively, you can use "Prompt Compression" techniques to remove tokens that carry little semantic weight. This reduces latency and cost while keeping the most critical "reasoning anchors" within the context window.

## Common Failure Modes

### 1. The JSON Truncation Nightmare
- **Symptom**: Model returns valid JSON but terminates prematurely, leaving a trailing bracket or missing essential fields.
- **Root Cause**: Failing to reserve enough tokens for the "Answer" portion of the response or using a model that struggles with long structured outputs.
- **Fix**: Explicitly define the maximum token length for the response and implement a middleware parser that can handle (or flag) truncated JSON blocks.

### 2. Semantic Drift after Model Updates
- **Symptom**: A prompt that worked perfectly for months suddenly starts producing low-quality or hallucinated results.
- **Root Cause**: The foundational model weights were updated ("model drift"), changing the way it interprets specific linguistic nuances.
- **Fix**: Maintain a robust Evaluation Suite that runs your prompts against a "Golden Dataset" on every deployment to catch drift before it hits production.

### 3. Prompt Injection (Leaking System Instructions)
- **Symptom**: A user is able to bypass safety filters or see your secret "System Prompt" through clever phrasing.
- **Root Cause**: Mixing user data and system instructions without clear delimiters.
- **Fix**: Use specific "Defensive Delimiters" (e.g., `### USER DATA START ###`) and system-level instructions that explicitly forbid the model from repeating its preamble.

## Annotated Resources

- [Tree of Thoughts: Deliberate Problem Solving](https://arxiv.org/abs/2305.10601)
  > Introduces a framework where models explore multiple reasoning paths. Senior engineers need this for implementing complex logical tasks where a single "shot" is likely to fail.
- [A Survey of Hallucinations in Large Language Models](https://arxiv.org/abs/2311.05232)
  > Provides a taxonomy of why models hallucinate and how to suppress them. Essential for building "Defensive Prompting" strategies that prioritize factual grounding.
- [Brex Prompt Engineering Guide](https://github.com/brexhq/prompt-engineering)
  > Details model-specific guidance for executing deterministic schema enforcement. This is a must-read for anyone building high-volume, machine-to-machine integrations.
- [OpenAI Prompt Engineering Guide](https://platform.openai.com/docs/guides/prompt-engineering)
  > Compiles battle-tested patterns for meta-prompting and context optimization. Useful for reducing token spend while maintaining high-quality reasoning.
- [SWE-agent: Agentic Software Engineering](https://swe-agent.com/)
  > Evaluates agentic prompting strategies against real-world engineering benchmarks. A critical resource for understanding the performance limits of current prompting techniques.

## What to read next
- [Chapter 02: RAG & Retrieval Systems](02-rag-and-retrieval.md)
- [Chapter 03: Agents, Tools & MCP](03-agents-and-mcp.md)
