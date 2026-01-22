# ai-resources

This repo consolidates work with Generative AI tools—from high-order work like assessing AI coding assistant impact on developer workflows, to app-specific prompts and PRDs for vibe coding.

---

## Root Files

Foundational documents and high-level resources at the repository root.

- [ai-principles.md](ai-principles.md) — Guiding metaphors (Yegge/Kim's "head chef" concept from *Vibe Coding*) and eras of AI coding assistancen (code completion → chat → agentic).
- [ai-lessons.md](ai-lessons.md) — Key lessons learned: rapid tooling/thought pattern change, persistence of SDD, variable developer adoption, and enduring concerns around value/quality/speed.
- [ai-experiments-tools.md](ai-experiments-tools.md) — Catalog of AI coding tools experimented with (Claude Code, Windsurf, GitHub Copilot, Gemini tools, etc.) and GenAI apps used for various projects.
- [ai-experiments-apps.md](ai-experiments-apps.md) — Detailed list of applications built with various AI coding tools, including whiskey-log, taskflow, todoist clones, Connect Four, and work-related apps.
- [ai-sdd-pitch.md](ai-sdd-pitch.md) — Overview pitch for Spec-Driven Development (SDD) in the context of "vibe coding," including advantages, disadvantages, and the "vibe then verify" approach.
- [ai-coding-tools-recommendations.md](ai-coding-tools-recommendations.md) — Claude Code-generated recommendations for AI coding tools to explore next, organized by category (agentic tools, specialized workflow tools, quality/testing specialists, experimental tools) with prioritized suggestions.

---

## GAI Lab Planning (`ai-gai/`)

Resources and planning documents specific to GAI (Generative AI) Lab initiatives and SDD implementation work.

- [gai-ai-lab-plans.md](ai-gai/gai-ai-lab-plans.md) — Strategic framework for AI adoption organized into two prongs: "Developer of the Future" (Lab focus on dev skills, design, critical thinking) and "Development of the Future" (IT focus on AI fluency, SDD workflow, and process inputs).
- [gai-ai-players.md](ai-gai/gai-ai-players.md) — List of people and teams for POCs and initiatives across GAS Lab, SDLC COE, API COE, EISG, Data Science, and Emerging Tech.
- [gai-sdd-overview.md](ai-gai/gai-sdd-overview.md) — GAI-focused overview of Spec-Driven Development covering crisis of abundance, determinism, paved path approach, key components (process, constitution, operationalization), and various framework options to consider.
- [gai-sdd-notes.md](ai-gai/gai-sdd-notes.md) — Meeting notes from GAI Lab discussions on SDD workflow/kit, including Rally integration, constitution elements (skills, instructions, agents, prompts), and scope considerations.
- [gai-ai-feed-beast.md](ai-gai/gai-ai-feed-beast.md) — Analysis of the "yawning void" problem: AI-enabled developers delivering faster than stories arrive, with options for spinning plates, TPM leverage, faster feature cycling, A/B testing, and collaborative story/spec cycles.
- [gai-ai-user-metrics.md](ai-gai/gai-ai-user-metrics.md) — Framework for measuring individual developer AI tool usage and effectiveness through metrics like total interactions, days active, model usage breakdown, agent vs. ask patterns, and CLI usage.

---

## Developer of the Future (`dev-of-future/`)

Resources and research related to AI-augmented software development, developer skills evolution, and organizational transformation.

### Problem Domains (`problem-domains/`)

Framing documents that define the problem spaces addressed by the resources.

- [developer-skills.md](dev-of-future/problem-domains/developer-skills.md) — Problem domain for developer skills: orchestration vs coding, AI literacy, system design, non-technical skills, and key challenges.
- [development-flows.md](dev-of-future/problem-domains/development-flows.md) — Problem domain for development workflows: AI output volume/speed, natural throttles, and ensuring quality at increased delivery speed.
- [measuring-impact.md](dev-of-future/problem-domains/measuring-impact.md) — Problem domain for measuring AI's impact: product quality (bugs, rejected stories) and developer experience (productivity, happiness).

### Resources (`resources/`)

Detailed research, frameworks, and templates organized by problem domain.

#### Developer Skills (`resources/developer-skills/`)

Resources addressing developer skills evolution in the AI era.

##### AI Mentoring (`resources/developer-skills/ai-mentoring/`)

- [ai_code_mentoring.md](dev-of-future/resources/developer-skills/ai-mentoring/ai_code_mentoring.md) — Comprehensive research-based framework for scaling AI coding skills through team coaching, including session structures, the 10-5-10 pattern, creating "Aha!" moments, and fighting the forgetting curve.
- [ai_fluency.md](dev-of-future/resources/developer-skills/ai-mentoring/ai_fluency.md) — Deep dive into AI fluency for developers: quick take, extensive research report (adoption statistics, competency frameworks, implementation strategies), and extracted data tables/matrices.

##### AI Tool Selection (`resources/developer-skills/ai-tool-selection/`)

- [tools_six_dimenations.md](dev-of-future/resources/developer-skills/ai-tool-selection/tools_six_dimenations.md) — Evaluation Criteria Matrix scoring potential solutions across six dimensions (Technical Capabilities, Security, Usability, Cost, Vendor Reliability, IT Infrastructure).
- [ai-code-review-tools-comparison.md](dev-of-future/resources/developer-skills/ai-tool-selection/ai-code-review-tools-comparison.md) — ChatGPT-generated comparative analysis of automated code review tools (Zencoder, Codacy, SonarQube, CodeRabbit, Snyk Code, DeepSource, Qodo, Codiga) for a 350-developer organization using GitHub Enterprise.

###### 2025 Selection Criteria (`resources/developer-skills/ai-tool-selection/ai_tool_selection_2025/`)

- [ai-tool-selection.md](dev-of-future/resources/developer-skills/ai-tool-selection/ai_tool_selection_2025/ai-tool-selection.md) — Original criteria for selecting AI coding assistants covering technical capabilities, code quality, integration, enterprise readiness, and adoption factors.
- [ai-coding-assistant-selection-criteria-2025.md](dev-of-future/resources/developer-skills/ai-tool-selection/ai_tool_selection_2025/ai-coding-assistant-selection-criteria-2025.md) — Updated 2025 criteria from GPT-5, adding agentic features, repo-aware context, stricter governance needs, and improved measurement approaches.
- [ai-coding-assistant-selection-criteria-unified-2025.md](dev-of-future/resources/developer-skills/ai-tool-selection/ai_tool_selection_2025/ai-coding-assistant-selection-criteria-unified-2025.md) — Merged and de-duplicated checklist combining original criteria with 2025 updates, including a quick-use checklist.
- [AI_Coding_Assistant_Selection_Template_2025.xlsx](dev-of-future/resources/developer-skills/ai-tool-selection/ai_tool_selection_2025/AI_Coding_Assistant_Selection_Template_2025.xlsx) — Excel template for scoring and evaluating AI coding assistants.

##### Design Skills (`resources/developer-skills/design-skills/`)

- [context-design-v2.md](dev-of-future/resources/developer-skills/design-skills/context-design-v2.md) — Problem context describing a department's need to improve software design and architectural skills among ~35 developers.
- [design-skills-plan-chatgpt.md](dev-of-future/resources/developer-skills/design-skills/design-skills-plan-chatgpt.md) — ChatGPT-generated three-phase plan (Assessment/Training, Practice/Application, Embedding/Scaling) for improving developer design skills.
- [design-skills-plan-claude-1.md](dev-of-future/resources/developer-skills/design-skills/design-skills-plan-claude-1.md) — Claude-generated multi-faceted approach including design review culture, architecture office hours, pairing, case study workshops, and design pattern library.
- [design-skills-plan-claude-2.md](dev-of-future/resources/developer-skills/design-skills/design-skills-plan-claude-2.md) — Refined Claude-generated plan with three phases over 12 months, including measurement and feedback mechanisms.

#### Development Flows (`resources/development-flows/`)

Resources addressing development workflows and processes in the AI era.

##### AI Workflows (`resources/development-flows/ai-workflows/`)

- [ai_tools_and_sdlc.md](dev-of-future/resources/development-flows/ai-workflows/ai_tools_and_sdlc.md) — Extensive analysis of how AI tools are transforming the SDLC, covering all phases, measured impacts, implementation reality, future trajectories, and organizational implications.
- [ai_sdlc_maturity.md](dev-of-future/resources/development-flows/ai-workflows/ai_sdlc_maturity.md) — Five-stage maturity model from manual development (Level 0) to fully AI-orchestrated environments (Level 4).

###### Workflow Impact (`resources/development-flows/ai-workflows/workflow-impact/`)

- [ai-workflow-impact.md](dev-of-future/resources/development-flows/ai-workflows/workflow-impact/ai-workflow-impact.md) — Action plan request for managing AI coding tool integration, covering data gathering, pattern analysis, change assessment, and implementation planning for a ~400 developer organization.

**AI Responses** (`resources/development-flows/ai-workflows/workflow-impact/ai_responses/`)

- [ai_mvm_plan.md](dev-of-future/resources/development-flows/ai-workflows/workflow-impact/ai_responses/ai_mvm_plan.md) — "80/20 Minimum Viable Measurement Plan" (GPT-5 generated) for tracking AI coding assistant impact without a full analytics platform.
- [ai_workflow_patterns.md](dev-of-future/resources/development-flows/ai-workflows/workflow-impact/ai_responses/ai_workflow_patterns.md) — Guide (GPT-5 generated) for observing, interviewing, and analyzing how AI coding assistants change developer workflows through structured observation and lightweight instrumentation.

**Templates** (`resources/development-flows/ai-workflows/workflow-impact/ai_responses/templates/`)

- [developer_diary_template.md](dev-of-future/resources/development-flows/ai-workflows/workflow-impact/ai_responses/templates/developer_diary_template.md) — Template for developers to log AI coding assistant effects on daily/weekly work.
- [developer_diary_template.xlsx](dev-of-future/resources/development-flows/ai-workflows/workflow-impact/ai_responses/templates/developer_diary_template.xlsx) — Excel version of the developer diary template.
- [ai_workflow_observation_template.xlsx](dev-of-future/resources/development-flows/ai-workflows/workflow-impact/ai_responses/templates/ai_workflow_observation_template.xlsx) — Excel template for observing and recording AI workflow patterns.

##### Spec-Driven Development (`resources/development-flows/spec-driven-dev/`)

- [sdd-blueprint.md](dev-of-future/resources/development-flows/spec-driven-dev/sdd-blueprint.md) — General SDD phases synthesized from multiple frameworks (GitHub Spec Kit, Augment Code, AWS Kiro, Zencoder): Constitution, Specification, Technical Planning, Task Decomposition, Implementation, and Continuous Validation.
- [sdd-frameworks-steps.md](dev-of-future/resources/development-flows/spec-driven-dev/sdd-frameworks-steps.md) — Outline of SDD frameworks and stages, including references to GitHub Spec-Kit.
- [sdd-scoping-guidance.md](dev-of-future/resources/development-flows/spec-driven-dev/sdd-scoping-guidance.md) — How to apply SDD at different levels and scopes: greenfield/brownfield projects, epics, features, stories, and tasks—adjusting the "altitude" of specifications accordingly.
- [sdd-pros-cons.md](dev-of-future/resources/development-flows/spec-driven-dev/sdd-pros-cons.md) — Analysis of the benefits (shared context, determinism) and trade-offs of the SDD approach.
- [sdd-adoption-guidance.md](dev-of-future/resources/development-flows/spec-driven-dev/sdd-adoption-guidance.md) — Decision framework for when to adopt formal SDD versus lightweight Agile processes.
- [sdd-ghc-suggestions.md](dev-of-future/resources/development-flows/spec-driven-dev/sdd-ghc-suggestions.md) — Planning considerations for SDD implementation, focusing on success metrics and measurement.
- `images/` — Supporting diagrams (sdd-maturity.png, sdd-pros-cons.png, sdd-steps-1.png, sdd-steps-2.png).

###### Frontier Model Takes (`resources/development-flows/spec-driven-dev/frontier-model-takes/`)

- [SpecDrivenDevelopment Plan (ChatGPT).md](dev-of-future/resources/development-flows/spec-driven-dev/frontier-model-takes/SpecDrivenDevelopment%20Plan%20%28ChatGPT%29.md) — ChatGPT-generated framework for spec-driven development: methodology overview, Agile integration, machine/human-readable spec formats, AI code validation, and challenge mitigation.
- [SpecDrivenDevelopment Plan (Claude).md](dev-of-future/resources/development-flows/spec-driven-dev/frontier-model-takes/SpecDrivenDevelopment%20Plan%20%28Claude%29.md) — Comprehensive Claude-generated guide for implementing SDD in a 350-developer organization: spec architecture, multi-tool AI consumption, repository governance, phased pilot rollout, and measuring effectiveness.
- [SpecDrivenDevelopment Plan (Gemini).md](dev-of-future/resources/development-flows/spec-driven-dev/frontier-model-takes/SpecDrivenDevelopment%20Plan%20%28Gemini%29.md) — Extensive Gemini-generated strategic blueprint positioning SDD as "the operating system for enterprise AI engineering."

###### Original Foray (`resources/development-flows/spec-driven-dev/original-foray/`)

- [sdd_research.md](dev-of-future/resources/development-flows/spec-driven-dev/original-foray/sdd_research.md) — Comprehensive research framework on spec-driven development with AI coding tools: landscape, taxonomy of specification artifacts, required/optional elements, cross-platform compatibility, implementation recommendations, and best practices.
- [sdd_implementation.md](dev-of-future/resources/development-flows/spec-driven-dev/original-foray/sdd_implementation.md) — Detailed six-month implementation plan for enterprise AI-augmented development with 350 developers, including SDD foundation, centrally managed components, AI code review integration, cross-functional planning, phased pilot implementation, and ROI measurement.

###### Claude Cowork (`resources/development-flows/spec-driven-dev/claude-cowork/`)

- [sdd-plan.md](dev-of-future/resources/development-flows/spec-driven-dev/claude-cowork/sdd-plan.md) — Unified Spec-Driven Development workflow synthesizing insights from multiple frameworks: five-layer architecture (Specification, Generation, Artifact, Validation, Runtime), three-artifact workflow (Requirements, Technical Spec, Implementation Plan), phased execution model with RED/GREEN/VERIFY loops, human-AI collaboration patterns, and drift detection mechanisms.

#### Miscellaneous (`resources/miscellaneous/`)

- [mcp-security.md](dev-of-future/resources/miscellaneous/mcp-security.md) — Security analysis of MCP (Model Context Protocol) servers for LLMs, covering injection attacks, data exfiltration risks, and mitigation best practices.

---

## Reports (`reports/`)

Deep-dive explanatory documents and analysis reports.

- [explanation-ai-resources-repo-20260112.md](reports/explanation-ai-resources-repo-20260112.md) — Comprehensive explanation of the ai-resources repository: what it is, why it exists, the guiding philosophy (head chef metaphor), three core problem domains (developer skills, development workflows, measuring impact), repository structure, key content highlights, practical applications for different roles, and how to get the most value from the repository.

---

## Configuration (`/.github/`)

Repository configuration, tool-specific instructions, and automation assets.

- [copilot-instructions.md](.github/copilot-instructions.md) — GitHub Copilot instructions describing the repository structure, content patterns (frontier model comparisons, AI-generated content, README as index), key concepts (SDD, AI mentoring framework), writing style, and guidelines for adding new content.

### Agents (`.github/agents/`)

Custom agent definitions for repository maintenance and automation tasks.

- [update-readme.md](.github/agents/update-readme.md) — Agent definition for synchronizing the README with repository structure: ensures README accurately reflects all files, directories, and content changes in the repository.

### Prompts (`.github/prompts/`)

Custom prompt instructions for automated workflows.

- [update-readme.prompt.md](.github/prompts/update-readme.prompt.md) — Prompt instruction to invoke the README update agent.

---

## Skills (`skills/`)

Custom Claude Code skills for specialized tasks in this repository.

- [m3-expressive.md](skills/m3-expressive.md) — Claude Code skill for applying Google Material 3 Expressive design system to web pages: design tokens, typography, motion, components, responsive layouts, and accessibility requirements.
- [report-unit-tests.md](skills/report-unit-tests.md) — Claude Code skill for ensuring comprehensive unit test coverage (80%+) for report generation code: test structure, coverage requirements, data fixtures, assertions, mock guidelines, and CI/CD integration.

---

## Archive (`archive/`)

Archived content from previous iterations of the repository.

### Whiskey Log Prompts (`archive/whiskey-log/`)

Prompts and PRDs related to the [whiskey-log app](https://github.com/sdbroscious/whiskey-log), a vibe-coded whiskey tasting log application.

- [prompt.md](archive/whiskey-log/prompt.md) — Original PRD/prompt for the whiskey log app (now superseded by prd.md in the main app repo).
- [architecture_assessment_prompt.md](archive/whiskey-log/architecture_assessment_prompt.md) — Template for assessing application architecture: system overview, technical architecture, quality attributes, data architecture, development practices, and operational excellence.
- [claude_output_unit_tests.md](archive/whiskey-log/claude_output_unit_tests.md) — Claude-generated unit test outputs.

