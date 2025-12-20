# ai-resources

This repo is intended to consolidate work that i do with Generative AI tools. It could be high-order work, like figuring out how to assess the impact of AI coding assistants on developer workflows. It could be app-specific prompts and PRDs re vibe coding.

## Developer of the Future (`dev-of-future/`)

Resources and research related to AI-augmented software development, developer skills evolution, and organizational transformation.

### Root Files
- [first_principles.md](dev-of-future/first_principles.md) — Notes on foundational concepts: prompt vs spec engineering, when to use each approach, and leveraging context engineering for better AI responses.

### AI Mentoring (`ai-mentoring/`)
- [ai_code_mentoring.md](dev-of-future/ai-mentoring/ai_code_mentoring.md) — Comprehensive research-based framework for scaling AI coding skills through team coaching, including session structures, the 10-5-10 pattern, creating "Aha!" moments, and fighting the forgetting curve.
- [ai_fluency.md](dev-of-future/ai-mentoring/ai_fluency.md) — Deep dive into AI fluency for developers with three sections: a quick take on what AI fluency means, an extensive research report on the topic (with adoption statistics, competency frameworks, and implementation strategies), and extracted data tables/matrices.

### AI Tool Selection (`ai-tool-selection/`)
- [README.md](dev-of-future/ai-tool-selection/README.md) — Index describing the tool selection files and their evolution.
- [ai-tool-selection.md](dev-of-future/ai-tool-selection/ai-tool-selection.md) — Original criteria for selecting AI coding assistants covering technical capabilities, code quality, integration, enterprise readiness, and adoption factors.
- [ai-coding-assistant-selection-criteria-2025.md](dev-of-future/ai-tool-selection/ai-coding-assistant-selection-criteria-2025.md) — Updated 2025 criteria from GPT-5, adding agentic features, repo-aware context, stricter governance needs, and improved measurement approaches.
- [ai-coding-assistant-selection-criteria-unified-2025.md](dev-of-future/ai-tool-selection/ai-coding-assistant-selection-criteria-unified-2025.md) — Merged and de-duplicated checklist combining the original criteria with 2025 updates, including a quick-use checklist.

### AI Workflows (`ai-workflows/`)
- [ai_tools_and_sdlc.md](dev-of-future/ai-workflows/ai_tools_and_sdlc.md) — Extensive analysis of how AI tools are transforming the software development lifecycle, covering all SDLC phases, measured impacts, implementation reality, future trajectories, and organizational implications.

#### Workflow Impact (`ai-workflows/workflow-impact/`)
- [ai-workflow-impact.md](dev-of-future/ai-workflows/workflow-impact/ai-workflow-impact.md) — Action plan request document for managing AI coding tool integration, covering data gathering, pattern analysis, change assessment, and implementation planning for a ~400 developer organization.

##### AI Responses (`ai-workflows/workflow-impact/ai_responses/`)
- [ai_mvm_plan.md](dev-of-future/ai-workflows/workflow-impact/ai_responses/ai_mvm_plan.md) — "80/20 Minimum Viable Measurement Plan" (GPT-5 generated) for tracking AI coding assistant impact without standing up a full analytics platform.
- [ai_workflow_patterns.md](dev-of-future/ai-workflows/workflow-impact/ai_responses/ai_workflow_patterns.md) — Guide (GPT-5 generated) for observing, interviewing, and analyzing how AI coding assistants are changing developer workflows through structured observation and lightweight instrumentation.

###### Templates (`ai-workflows/workflow-impact/ai_responses/templates/`)
- [developer_diary_template.md](dev-of-future/ai-workflows/workflow-impact/ai_responses/templates/developer_diary_template.md) — Template for developers to log how AI coding assistants affect their daily/weekly work, covering usage, workflow impact, benefits, challenges, and collaboration changes.

### Design Skills (`design-skills/`)
- [context-design-v2.md](dev-of-future/design-skills/context-design-v2.md) — Problem context document describing a department's need to improve software design and architectural skills among ~35 developers.
- [design-skills-plan-chatgpt.md](dev-of-future/design-skills/design-skills-plan-chatgpt.md) — ChatGPT-generated three-phase plan (Assessment/Training, Practice/Application, Embedding/Scaling) for improving developer design skills.
- [design-skills-plan-claude-1.md](dev-of-future/design-skills/design-skills-plan-claude-1.md) — Claude-generated multi-faceted approach including design review culture, architecture office hours, learning through pairing, case study workshops, and design pattern library.
- [design-skills-plan-claude-2.md](dev-of-future/design-skills/design-skills-plan-claude-2.md) — Refined Claude-generated plan with three phases over 12 months: Foundation Building, Skill Development, and Practice/Application, with measurement and feedback mechanisms.

### Spec-Driven Development (`spec-driven-dev/`)
- [sdd-gai-overview.md](dev-of-future/spec-driven-dev/sdd-gai-overview.md) — Overview of Spec-Driven Development, addressing the "crisis of abundance" and the need for determinism in AI-augmented development.
- [sdd-frameworks-steps.md](dev-of-future/spec-driven-dev/sdd-frameworks-steps.md) — Outline of SDD frameworks and stages, including references to GitHub Spec-Kit.
- [sdd-pros-cons.md](dev-of-future/spec-driven-dev/sdd-pros-cons.md) — Analysis of the benefits (shared context, determinism) and trade-offs of the SDD approach.
- [sdd-adoption-guidance.md](dev-of-future/spec-driven-dev/sdd-adoption-guidance.md) — Decision framework for when to adopt formal SDD versus lightweight Agile processes.
- [sdd-ghc-suggestions.md](dev-of-future/spec-driven-dev/sdd-ghc-suggestions.md) — Planning considerations for SDD implementation, focusing on success metrics and measurement.

#### Frontier Model Takes (`spec-driven-dev/frontier-model-takes/`)
- [SpecDrivenDevelopment Plan (ChatGPT).md](dev-of-future/spec-driven-dev/frontier-model-takes/SpecDrivenDevelopment%20Plan%20%28ChatGPT%29.md) — ChatGPT-generated framework for spec-driven development covering methodology overview, Agile integration, machine/human-readable spec formats, AI code validation, and challenge mitigation.
- [SpecDrivenDevelopment Plan (Claude).md](dev-of-future/spec-driven-dev/frontier-model-takes/SpecDrivenDevelopment%20Plan%20%28Claude%29.md) — Comprehensive Claude-generated guide for implementing SDD in a 350-developer organization, covering spec architecture, multi-tool AI consumption, repository governance, phased pilot rollout, and measuring effectiveness.
- [SpecDrivenDevelopment Plan (Gemini).md](dev-of-future/spec-driven-dev/frontier-model-takes/SpecDrivenDevelopment%20Plan%20%28Gemini%29.md) — Extensive Gemini-generated strategic blueprint positioning SDD as "the operating system for enterprise AI engineering," covering theoretical/operational imperatives, workflow phases, technical platform, legacy modernization, and organizational change.

#### Original Foray (`spec-driven-dev/original-foray/`)
- [sdd_research.md](dev-of-future/spec-driven-dev/original-foray/sdd_research.md) — Comprehensive research framework on spec-driven development with AI coding tools, covering the landscape, taxonomy of specification artifacts, required/optional elements, cross-platform compatibility, implementation recommendations, and best practices.
- [sdd_implementation.md](dev-of-future/spec-driven-dev/original-foray/sdd_implementation.md) — Detailed six-month implementation plan for enterprise AI-augmented development with 350 developers, including SDD foundation, centrally managed components, AI code review integration, cross-functional planning, phased pilot implementation, and ROI measurement.

---

## Apps Created with AI Assistants
- **whiskey-log**: This is an app I've 'vibe-coded' using **Claude Code**, mainly. I've also used other tools, like GH Copilot and Gemini Code Assist, but relatively sparingly. This also has a PRD that I created iteratively, adding requirements as building, testing and using the app revealed them. In theory, I should be able to take the PRD, create a new repo, and have an AI assistant recreate the app to its current state. Here's the [github repo](https://github.com/sdbroscious/whiskey-log).

- **taskflow**: This ia an app that I created with **Windsurf** in 2025-05. It's modeled on Todoist. Apparently, I was able to create a working app in a single day, with 2 basic commits: one for the code and a second for tests. Here's the [github repo](https://github.com/sdbroscious/taskflow).

- **todoist-clone**: This is an app that I created with **Claude Code** in 2025/05-06. It was an experiment in recreating Todoist as a VueJS and Spring Boot app. Here's the [github repo](https://github.com/sdbroscious/todoist-clone).

- **connectfour**: This is an app that I created with **GitHub Copilot (Agent mode)** in less than 30 minutes. It's the game you know and love. Here's the [github repo](https://github.com/sdbroscious/connectfour).

- **todoist-vsc-demo**: This is an app that I created with **GitHub Copilot (Agent mode)**. It created a functional app on an extremely parsimonious prompt. For some reason, the README file in the backend directory is the one to review. Here's the [github repo](https://github.com/sdbroscious/todoist-vsc-demo).

- **app-from-image-claude**: This is an app that I ask **Claude** (not Code) to build based solely on a screen shot I took of the Todoist web interface. It produced a functioning CRUD app...crazy. Here's the [githup repo](https://github.com/sdbroscious/app-from-image-claude).

- **whiskey-log-ghc-cli**: This is based on whiskey-log. The experiment here is to take the prd.md file created by **Claude Code** for v1 of the app and see whether Copilot CLI can recreate the app. So far I have the PRD converted to an action plan and **Copilot CLI** and I are working the steps. Here's the [githup repo](https://github.com/sdbroscious/whiskey-log-ghc-cli).

- **antigravity-todoist**: This is an app that I created with **Gemini Antigravity** in 2025-11. It's modeled on Todoist. Here's the [github repo](https://github.com/sdbroscious/antigravity-todoist).

- **task-manager**: This is an app created with **GitHub Spark** in 2025-12. It's based on Google Tasks. Here's the [github repo](https://github.com/sdbroscious/task-manager).

- **subscription-tracker**: This is a simple app (inside gemini-cli-demo) created with **Gemini CLI**. Here's the [github repo](https://github.com/sdbroscious/gemini-cli-demo). Gemini CLI is very similar to Claude Code and Copilot CLI.
