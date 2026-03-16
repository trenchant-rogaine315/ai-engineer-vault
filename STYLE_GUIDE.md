# AI Engineering STYLE_GUIDE

This guide defines the voice, tone, and structural standards for the `ai-engineer-vault`. All contributions must adhere to these rules to maintain the repository's status as a high-authority engineering reference.

## Voice and Tone
- **Senior Technical Authority**: Write like a senior open-source maintainer documenting hard-won production experience.
- **Crisp and Technical**: Avoid fluff, marketing language, or excessive punctuation.
- **Field Manual, Not Tutorial**: Focus on "what to do in production" and "why it fails" rather than step-by-step "Hello World" basics.
- **Banned Words**: NEVER use "amazing", "powerful", "leverage", "utilize", or "best practices" (use "proven patterns" instead).
- **Direct Address**: Use second person ("you") to speak directly to the engineer.

## Heading Hierarchy
- **Level 1**: Reserved for the Chapter or File Title.
- **Level 2**: Reserved for the primary sections (TL;DR, Core Concepts, Failure Modes, etc.).
- **Level 3**: Used for individual concepts, tools, or papers.
- **Level 4**: Only used within complex subsections to avoid deep nesting.

## Section Guidelines

### "When to use this" sections
Must be formatted as a bulleted list answering:
- **Use this when**: Specific production scenario where the pattern is optimal.
- **Do NOT use this when**: Scenarios where the pattern is over-engineered or detrimental.

### "Failure modes" sections
Every failure mode must follow this exact 3-part structure:
1. **Symptom**: The specific technical observation (e.g., error code, latency spike, user complaint).
2. **Root Cause**: The underlying engineering reason for the failure.
3. **Fix**: The specific, actionable steps to resolve the issue.

### Resource Annotations
Every resource (paper, tool, blog) requires a mandatory 2-sentence annotation:
1. **Sentence 1**: What the resource is and what it covers.
2. **Sentence 2**: Why a senior AI engineer needs this specific knowledge for production success.

## Markdown Conventions
- **Alerts**: Use GitHub-flavored Markdown alerts (`> [!NOTE]`, `> [!TIP]`, `> [!IMPORTANT]`, `> [!WARNING]`, `> [!CAUTION]`) strategically to highlight critical information.
- **Links**: Prefer absolute links within the repository (e.g., `chapters/01-prompt-engineering.md`) to ensure portability.
- **Code Blocks**: Always specify the language for syntax highlighting (e.g., `bash`, `python`, `json`).
- **Formatting**: Use **bold** for emphasis and `backticks` for technical terms (functions, files, variables).

## Maintenance Standards
- **Stale Links**: Any resource link that returns a 404 or points to a non-maintained repository for more than 6 months will be removed.
- **Technical Accuracy**: If a pattern is superseded by a newer, more efficient production standard, the entry must be updated or moved to an "Archives" section.
