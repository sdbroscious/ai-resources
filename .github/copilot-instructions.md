# AI Resources - Copilot Instructions

This repository consolidates research, frameworks, and resources for AI-augmented software development. It is a **documentation-only repository** with no code to build or test.

## Token Usage

- for every response, append the total token usage to docs/metrics/token-usage.md and docs/metrics/token-usage.csv; for each response, capture date, task, model, tokens in, and tokens out; create the files, if they doesn't exist

## Repository Structure

### `docs/` - Foundational Documentation
Foundational documents and high-level resources:
- `ai-principles.md` - Guiding metaphors and AI coding assistance eras
- `ai-lessons.md` - Key lessons learned
- `sdd-pitch.md` - Spec-Driven Development overview pitch
- `coding-tools-recommendations.md` - AI coding tool recommendations

### `experiments/` - AI Tool Experiments
Catalog of AI coding tools and applications experimented with:
- `tools.md` - AI coding tools tested (Claude Code, Windsurf, GitHub Copilot, etc.)
- `apps.md` - Applications built with AI tools

### `organization/` - Organization-Specific Resources
Resources specific to organizational AI adoption initiatives:
- `gaig/` - GAI (Generative AI) Lab planning documents and implementation strategies

### `dev-of-future/` - Developer of the Future Research
Research and frameworks for AI-augmented development, organized by topic:
- `resources/developer-skills/ai-mentoring/` - Team coaching frameworks (10-5-10 pattern, scaling AI skills)
- `resources/developer-skills/ai-tool-selection/` - Criteria for evaluating AI coding assistants
- `resources/development-flows/ai-workflows/` - SDLC impact analysis and measurement plans
- `resources/developer-skills/design-skills/` - Developer skills improvement plans
- `resources/development-flows/spec-driven-dev/` - Spec-Driven Development (SDD) frameworks and implementation guides

### `archive/` - Archived Content
- `whiskey-log/` - PRDs and prompts for "vibe-coded" applications. The main app lives in a [separate repo](https://github.com/sdbroscious/whiskey-log).

## Content Patterns

### Frontier Model Comparisons
Several topics include outputs from multiple AI models (ChatGPT, Claude, Gemini) on the same prompt. When adding new research:
- Store model outputs in a `frontier-model-takes/` or similar subdirectory
- Use consistent naming: `Topic (ModelName).md`
- Reference the original prompt in YAML frontmatter or document header

### AI-Generated Content
Many files are AI-generated research. Mark AI outputs with:
```yaml
---
tags:
  - ai-output
---
```

### README as Index
Each major directory should have a README.md explaining file purposes and evolution. See [ai-tool-selection/README.md](dev-of-future/ai-tool-selection/README.md) as an example.

## Key Concepts

### Spec-Driven Development (SDD)
A core theme: using structured specifications as context for AI coding tools. Key files:
- [organization/gaig/gai-sdd-overview.md](organization/gaig/gai-sdd-overview.md) - Overview and open questions
- [dev-of-future/resources/development-flows/spec-driven-dev/frontier-model-takes/SpecDrivenDevelopment Plan (Claude).md](dev-of-future/resources/development-flows/spec-driven-dev/frontier-model-takes/SpecDrivenDevelopment%20Plan%20(Claude).md) - Comprehensive implementation guide

### AI Mentoring Framework
The 10-5-10 coaching pattern for scaling AI coding skills:
- 10 min demo → 5 min guided practice → 10 min independent challenge
- Emphasizes "Aha! moments" through guided discovery, not feature lectures
- See [dev-of-future/resources/developer-skills/ai-mentoring/ai_code_mentoring.md](dev-of-future/resources/developer-skills/ai-mentoring/ai_code_mentoring.md)

## Writing Style

- Use Markdown with clear heading hierarchy
- Prefer bullet points over prose for actionable items
- Include context about prompt/source when documenting AI outputs
- Link to external repos for actual code (this repo is documentation only)

## When Adding Content

1. Place files in appropriate topic subdirectories
2. Update the root [README.md](README.md) with file descriptions
3. Add directory-level README.md if creating new topic areas
4. Use relative links between documents
