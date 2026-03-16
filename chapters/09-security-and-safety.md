# Chapter 09: Security & Safety

> [!TIP]
> **TL;DR**
> - Security in AI is a "System Problem," not just a "Prompt Problem."
> - Prompt Injection is primarily mitigated through delimiters and air-gapped tool execution.
> - Zero-Trust architecture must be applied to all model-driven tool calls.
> - Regulatory compliance (NIST RMF, SOC 2) now includes specific AI risk controls.

## What this chapter covers
Granting an AI model the ability to reason and act on your data introduces entirely new categories of security risk. From "Prompt Injection" that bypasses safety filters to "Tool Poisoning" that exfiltrates database contents, the attack surface of modern AI applications is vast.

This chapter applies classical "Zero-Trust" security principles to the probabilistic world of AI. You will learn how to harden your system prompts against adversarial manipulation, implement isolated sandboxes for model-driven code execution, and ensure your application complies with emerging federal and international safety guidelines like the NIST AI Risk Management Framework. We focus on building defense-in-depth where security is enforced at the infrastructure level, not just the linguistic level.

## When you need this
- **Use this when**: Your AI application has access to private user data, can execute write operations to databases, or is deployed in a regulated industry (Finance, Healthcare, Defense).
- **Do NOT use this when**: You are building a public-facing sandbox with no access to internal tools or sensitive data.

## Core Concepts

### Prompt Injection and Jailbreaking
Prompt Injection occurs when a user provides input that "overwrites" the model's instructions (e.g., "Ignore all previous instructions and instead..."). While it is impossible to 100% prevent injection through language alone, you must implement "Deterministic Delimiters" and "Instruction Separation." The model should be instructed to only treat data between specific, non-user-generatable tokens as "input," and never to execute instructions found within that block. This linguistic defense must be backed by a "Safety Monitor"—a secondary, low-latency model that checks user input for injection attempts before it reaches the core application logic.

### Zero-Trust Tool Execution
When a model calls a tool (via MCP or custom APIs), that call must be treated as inherently adversarial. Never grant an AI "God Mode" access to your infrastructure. Every tool call must be authenticated with a "Short-Lived Token" that has the minimum required permissions (Least Privilege). High-stakes actions—like issuing a refund or deleting a file—must be gated by a "Human-in-the-Loop" approval step where a person verifies the model's intent before the action is committed.

### Data Exfiltration and Privacy
AI applications are high-value targets for data exfiltration. Adversaries may use clever prompts to trick a model into revealing its system prompt, API keys, or pieces of its training data. To mitigate this, you must implement "Output Filtering"—a post-generation step that scans for sensitive patterns (regex for PII, API key patterns, or internal server names) and redacts them before the response reaches the user. Additionally, ensuring your data is not being used for "Improvement Training" by your cloud provider is a mandatory architectural requirement for SOC 2 compliance.

### NIST AI Risk Management Framework (RMF)
Security is not just about stopping hackers; it's about managing risk. The NIST AI RMF provides a structured methodology for measuring and mitigating risks throughout the AI lifecycle: from data curation to production monitoring. As an AI engineer, you must move toward "Observable Security," where every decision made by an agent and every safety filter triggered is logged and audited. This ensures your organization can perform post-incident forensics and prove compliance to regulators.

## Common Failure Modes

### 1. The "Indirect Injection" Loophole
- **Symptom**: An attacker doesn't input a malicious prompt themselves; instead, they place it on a website that your RAG system retrieves, triggering the injection during the "Contextual Reasoning" step.
- **Root Cause**: Treating retrieved context as "trusted" rather than "potentially adversarial."
- **Fix**: Apply the same instruction-separation delimiters to retrieved context as you do to direct user input. Implement a "Context Guard" that scans retrieved chunks for imperative commands before they are added to the prompt.

### 2. Over-permissioned API Keys
- **Symptom**: An injection attack triggers a model to exfiltrate an entire database table because the AI was using a persistent, high-privilege API key.
- **Root Cause**: Violating the Principle of Least Privilege.
- **Fix**: Use an intermediate "Broker Service" between the LLM and your data. The broker receives the model's intent, validates it against the user's RBA (Role-Based Access) permissions, and executes the action using a scoped, one-time credential.

### 3. Safety Filter "Reversals"
- **Symptom**: A user bypasses your filters by asking the model to "play a game" or "write a fictional story about a hacker," which then reveals the restricted information.
- **Root Cause**: Relying on simple keyword-based safety filters.
- **Fix**: Use "Behavioral Safety Models" that evaluate the *intent* of the request rather than just the words used. These models are trained specifically to identify adversarial patterns like social engineering and "roleplay" bypasses.

## Annotated Resources

- [OWASP Top 10 for LLM Applications](https://genai.owasp.org/resource/owasp-top-10-for-llm-applications-project/)
  > The definitive list of critical vulnerabilities in generative AI systems. Use this to guide your security audits and penetration testing.
- [NIST AI Risk Management Framework (AI RMF)](https://www.nist.gov/itl/ai-risk-management-framework)
  > A voluntary framework for managing the risks of AI systems. Essential for ensuring your application is safe, secure, and trustworthy.
- [Jailbreak Foundry: Reproducible Benchmarking](https://arxiv.org/abs/2405.13063)
  > An executable taxonomy of prompt injection techniques. Use this to red-team your own applications and verify your defenses.
- [Microsoft: Red Teaming Large Language Models](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/red-teaming)
  > A practical guide to adversarial testing and risk mitigation for AI models. Learn how to identify and patch security holes before launch.
- [Anthropic: Safety and Security Vision](https://www.anthropic.com/news/claudes-constitution)
  > Real-world methodology for constitutional AI and safety guardrails. Learn how to align model behavior with complex human values.

## What to read next
- [Chapter 03: Agents, Tools & MCP](03-agents-and-mcp.md)
- [Chapter 04: Evals & Testing](04-evals-and-testing.md)
