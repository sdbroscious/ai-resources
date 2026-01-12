# ai-resources

This repo consolidates work with Generative AI tools—from high-order work like assessing AI coding assistant impact on developer workflows, to app-specific prompts and PRDs for vibe coding.

---

## Developer of the Future (`dev-of-future/`)

Resources and research related to AI-augmented software development, developer skills evolution, and organizational transformation.

### Root Files

- [first-principles.md](dev-of-future/first-principles.md) — Guiding metaphors (Yegge/Kim's "head chef" concept from *Vibe Coding*) and eras of AI coding assistance (code completion → chat → agentic).
- [lessons.md](dev-of-future/lessons.md) — Key lessons learned: rapid tooling/thought pattern change, persistence of SDD, variable developer adoption, and enduring concerns around value/quality/speed.

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

- [README.md](dev-of-future/resources/developer-skills/ai-tool-selection/README.md) — Index describing the tool selection files and their evolution.
- [tools_six_dimenations.md](dev-of-future/resources/developer-skills/ai-tool-selection/tools_six_dimenations.md) — Evaluation Criteria Matrix scoring potential solutions across six dimensions (Technical Capabilities, Security, Usability, Cost, Vendor Reliability, IT Infrastructure).

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

- [sdd-gai-overview.md](dev-of-future/resources/development-flows/spec-driven-dev/sdd-gai-overview.md) — Overview of Spec-Driven Development, addressing the "crisis of abundance" and the need for determinism in AI-augmented development.
- [sdd-frameworks-steps.md](dev-of-future/resources/development-flows/spec-driven-dev/sdd-frameworks-steps.md) — Outline of SDD frameworks and stages, including references to GitHub Spec-Kit.
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

#### Miscellaneous (`resources/miscellaneous/`)

- [mcp-security.md](dev-of-future/resources/miscellaneous/mcp-security.md) — Security analysis of MCP (Model Context Protocol) servers for LLMs, covering injection attacks, data exfiltration risks, and mitigation best practices.

---

## Archive (`archive/`)

Archived content from previous iterations of the repository.

### Whiskey Log Prompts (`archive/whiskey-log/`)

Prompts and PRDs related to the [whiskey-log app](https://github.com/sdbroscious/whiskey-log), a vibe-coded whiskey tasting log application.

- [prompt.md](archive/whiskey-log/prompt.md) — Original PRD/prompt for the whiskey log app (now superseded by prd.md in the main app repo).
- [architecture_assessment_prompt.md](archive/whiskey-log/architecture_assessment_prompt.md) — Template for assessing application architecture: system overview, technical architecture, quality attributes, data architecture, development practices, and operational excellence.
- [claude_output_unit_tests.md](archive/whiskey-log/claude_output_unit_tests.md) — Claude-generated unit test outputs.

---

## Apps Created with AI Assistants

- **whiskey-log**: Vibe-coded using **Claude Code** (mainly), with GH Copilot and Gemini Code Assist used sparingly. Has an iteratively-built PRD. [GitHub repo](https://github.com/sdbroscious/whiskey-log).

- **taskflow**: Created with **Windsurf** in 2025-05. Modeled on Todoist; working app in a single day with 2 commits (code + tests). [GitHub repo](https://github.com/sdbroscious/taskflow).

- **todoist-clone**: Created with **Claude Code** in 2025-05/06. Experiment recreating Todoist as VueJS + Spring Boot. [GitHub repo](https://github.com/sdbroscious/todoist-clone).

- **connectfour**: Created with **GitHub Copilot (Agent mode)** in <30 minutes. Classic Connect Four game. [GitHub repo](https://github.com/sdbroscious/connectfour).

- **todoist-vsc-demo**: Created with **GitHub Copilot (Agent mode)** from an extremely parsimonious prompt. [GitHub repo](https://github.com/sdbroscious/todoist-vsc-demo).

- **app-from-image-claude**: Built by **Claude** (not Code) from a Todoist screenshot—produced a functioning CRUD app. [GitHub repo](https://github.com/sdbroscious/app-from-image-claude).

- **whiskey-log-ghc-cli**: Experiment using the whiskey-log prd.md with **Copilot CLI** to recreate the app. [GitHub repo](https://github.com/sdbroscious/whiskey-log-ghc-cli).

- **antigravity-todoist**: Created with **Gemini Antigravity** in 2025-11. Modeled on Todoist. [GitHub repo](https://github.com/sdbroscious/antigravity-todoist).

- **task-manager**: Created with **GitHub Spark** in 2025-12. Based on Google Tasks. [GitHub repo](https://github.com/sdbroscious/task-manager).

- **subscription-tracker**: Simple app (inside gemini-cli-demo) created with **Gemini CLI**. [GitHub repo](https://github.com/sdbroscious/gemini-cli-demo).
