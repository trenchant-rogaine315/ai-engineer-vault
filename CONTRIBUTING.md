# Contributing to AI Engineer Vault

We value high-authority, production-focused contributions. This repository is not a collection of "awesome" lists; it is a rigorous field manual for engineers.

## What Belongs Here
- **Proven Architectural Patterns**: Design patterns that have been tested in production environments with high traffic.
- **Failure Mode Analyses**: Deep dives into why systems fail and specific, technical fixes.
- **Rigorous Annotations**: Every resource must be accompanied by a 2-sentence explanation of what it is and why it matters to an AI Engineer.
- **Vendor-Agnostic Knowledge**: Information that teaches fundamental concepts (e.g., the mathematics of chunking) rather than just library-specific syntax.

## What Does NOT Belong
- **Entry-level Tutorials**: Content aimed at absolute beginners or non-technical audiences.
- **Unannotated Links**: PRs that just add a list of URLs without engineering context.
- **Sponsored Content**: We do not accept paid placements or promotional material.
- **Transient Tools**: Beta libraries that lack stability or established community trust.

## Resource Annotation Format (Mandatory)
Every link or paper must follow this exact structure:
`[Resource Title](URL)`
`> [2-sentence annotation: First sentence explains what the resource is. Second sentence explains why a senior AI engineer needs this specific knowledge for production.]`

## How to Contribute

### Adding a Resource
1. Identify the relevant chapter or resource file.
2. Locate the appropriate section (e.g., "Annotated Resources").
3. Add the resource using the mandatory annotation format.
4. Open a PR with a description of why this resource meets our quality bar.

### Proposing a New Section or Chapter
1. Open an Issue with the prefix `[PROPOSAL]`.
2. Outline the technical gap the new section addresses.
3. Provide a brief syllabus of core concepts to be covered.
4. Once approved by a maintainer, you may proceed with the PR.

## Quality Bar for PRs
A PR will only be merged if it:
1. Adheres strictly to the [STYLE_GUIDE.md](STYLE_GUIDE.md).
2. Contains zero fluff or marketing language (e.g., no "amazing", "powerful", "best practices").
3. Is technically accurate and addresses a specific engineering pain point.
4. Includes internal links to related chapters or the [glossary.md](glossary.md) where appropriate.

## Code of Conduct
We maintain a professional, senior-level technical environment. All interactions must be respectful, objective, and focused on engineering excellence. Disagreements must be settled with technical evidence and production telemetry.
