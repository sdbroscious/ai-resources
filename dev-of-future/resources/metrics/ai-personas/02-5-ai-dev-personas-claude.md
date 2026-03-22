# Five developer personas for AI capability maturity

**The developer who tabs through Copilot suggestions and the one who writes markdown specs while agents build entire features are not on the same journey—they are doing fundamentally different jobs.** This framework defines five named personas, each mapped to a maturity level in your AI Capability Maturity Model, with behavioral descriptions grounded in GitHub Copilot telemetry, enterprise DevEx research, and the emerging spec-driven and agentic paradigms your organization is already piloting. The personas serve a dual purpose: coaches can use them to identify where a developer sits today and design targeted interventions, while CIO-level stakeholders can use them to measure organizational distribution across the maturity curve and track the shift over time.

The framework draws on Anthropic's 4D AI Fluency model, GitHub's four-stage developer fluency research (Dr. Eirini Kalliamvakou, December 2025), Dan Shapiro's five levels of AI coding autonomy, the 2025 DORA State of AI-Assisted Software Development report, DX's AI Measurement Framework, and your organization's own internal analysis of Copilot LOC metrics and SDD governance. Each persona includes instrumentable metrics available through GitHub Copilot telemetry and Faros AI, paired with qualitative indicators drawn from coaching observations and developer surveys—because no single metric captures the behavioral shift that separates an Accelerator from a Specifier.

---

## Level 1 — "The Accelerator"

### Maturity level: Autocomplete (Table stakes)

**The Accelerator treats AI as a faster keyboard.** This developer has GitHub Copilot installed and accepts inline suggestions when they appear, but their fundamental workflow—how they plan, write, test, review, and ship code—is identical to how they worked before AI tools existed. AI enters the picture only at the point of typing. The Accelerator's mental model is "I know what I want to write; sometimes the tool guesses it before I finish." They are productive and may genuinely appreciate the speed boost, but they have not changed *what* they do—only *how fast* they type it. In Anthropic's 4D fluency framework, their strongest competency is Description (translating intent into text the model can complete) but their Delegation is minimal: they never consider handing a larger unit of work to the AI. GitHub's research calls this the **AI Explorer** stage—using AI for "quick wins" without developing consistent habits or deeper integration.

For a ~350-developer insurance IT organization, this is likely **30–40% of the developer population** today. Many of these developers are highly experienced and may view themselves as too productive to need AI for more than autocomplete. The METR randomized controlled trial (July 2025) found that experienced developers working on familiar codebases actually took **19% longer** with AI tools while believing they were 20% faster—a perception-reality gap that is characteristic of Accelerators who haven't calibrated their mental model of AI's actual contribution.

### Observable behaviors

A manager or coach will notice the Accelerator using Copilot's ghost text completions but rarely opening Copilot Chat. Their code reviews look identical to pre-AI reviews—line-by-line reasoning about implementation with no reference to AI-generated outputs, specifications, or validation patterns. In standups, they describe work in terms of what *they* built, not what they delegated or directed. Their IDE configuration is default; no `.github/copilot-instructions.md`, no custom prompt files, no rules-based context shaping. When they encounter a complex problem, they reach for documentation, Stack Overflow, or a colleague before reaching for AI. If they use ChatGPT or another external tool, it is for one-shot questions ("How do I do X in Java?"), and they retype or adapt the answer manually rather than iterating in the conversation.

### Metrics to identify this persona

**Instrumentable (GitHub Copilot telemetry / Faros AI):**

| Metric | Expected Range | What It Signals |
|--------|---------------|----------------|
| Copilot acceptance rate | 15–28% (below the 27–30% industry average) | Selective but passive usage; accepts only obvious completions |
| Feature usage breadth | Inline completions only; zero or near-zero Chat sessions; no Agent mode | Single-surface engagement is the strongest differentiator |
| Active days per month | 8–15 days (Low engagement: <50% of workdays) | Inconsistent usage; AI not embedded in daily habit |
| Daily completions accepted | 30–120 | Low volume relative to coding activity |
| Copilot `loc_added_sum` as % of total lines added | <15% | AI generates a small fraction of committed code |
| Chat-to-completion ratio | Near zero (effectively no Chat usage) | All AI interaction is passive, inline suggestion acceptance |
| Agent mode sessions | Zero | No agentic tool usage |
| PR cycle time delta (vs. pre-AI baseline) | <10% improvement | Minimal delivery acceleration attributable to AI |

**Qualitative / survey-based indicators:**

- Self-reports saving **<1 hour per week** from AI tools, or cannot quantify time savings
- In developer experience surveys, rates AI tools as "somewhat helpful" or "not reliable enough"
- Describes AI's role as "autocomplete" or "saving keystrokes" when asked in coaching sessions
- Does not mention AI in retrospectives, architecture discussions, or design reviews
- Peer feedback identifies them as someone who "doesn't really use AI" despite having the license active
- When observed in pairing sessions, does not naturally turn to AI when stuck; defaults to manual problem-solving
- May express skepticism about AI code quality, citing trust concerns (consistent with the **46% of developers** who distrust AI output accuracy per Stack Overflow 2025)

---

## Level 2 — "The Amplifier"

### Maturity level: Conversation as Workflow

**The Amplifier has made AI a constant companion across every task, but the task list itself hasn't changed.** This developer uses Copilot Chat to draft PR descriptions, explain unfamiliar code, generate unit tests for existing functions, summarize long documents, and scaffold boilerplate. They may also use ChatGPT, Claude, or other tools alongside Copilot—**59% of developers** now use three or more AI tools simultaneously. The critical distinction from the Accelerator: the Amplifier *converses* with AI rather than merely accepting suggestions. They have developed prompting instincts—they know to provide context, specify format, and iterate when the first response misses the mark. In Anthropic's 4D model, they demonstrate meaningful Delegation and Description but are still developing Discernment (the ability to evaluate AI output critically for correctness and completeness).

The Amplifier's relationship with AI is **horizontal**: they apply it broadly across many tasks but do not fundamentally change the structure of any single task. They still own every decision, write every spec by hand, review every line of AI-generated code personally, and manage their own task decomposition. This is the level that **most executives find impressive** because it is visible—Amplifiers talk about AI in meetings, share prompts with colleagues, and visibly produce work faster. GitHub's research labels this the **AI Collaborator** stage, characterized by "co-creating with AI, iterating frequently, and expecting back-and-forth with agents." DX's data shows these developers typically report saving **2–4 hours per week** and merge **60% more PRs** than non-AI-users.

For a ~350-developer org, this is likely **25–35%** of the population and the fastest-growing segment.

### Observable behaviors

The Amplifier's IDE shows a mix of inline completions and Chat interactions—they switch between surfaces fluidly. In code reviews, their PRs may include AI-generated test suites or documentation that is suspiciously thorough for the time allocated. They reference AI output in standups ("I had Copilot generate the test scaffolding, then I refined it"). They experiment with different prompting approaches and may maintain a personal prompt library or bookmarked chat conversations. When debugging, they paste stack traces into Chat and iterate on solutions. They use Copilot's PR summary feature and may have experimented with Copilot code review. Their configuration shows moderate customization—perhaps a `copilot-instructions.md` file with basic project context, but not the detailed rules files of more advanced personas. They are natural candidates for **AI Champion programs** (organizations with champion programs see **38% higher adoption**, per GitHub).

### Metrics to identify this persona

**Instrumentable (GitHub Copilot telemetry / Faros AI):**

| Metric | Expected Range | What It Signals |
|--------|---------------|----------------|
| Copilot acceptance rate | 28–35% (at or above industry average, trending upward) | Growing trust and effective prompting; the 6-month benchmark of ~34% is typical for this persona |
| Feature usage breadth | Inline completions **and** Chat (5–15 Chat sessions/week); occasional PR summaries | Multi-surface engagement distinguishes Amplifier from Accelerator |
| Active days per month | 15–20 days (Medium-to-High engagement: 50–80%+ of workdays) | Consistent daily usage; AI embedded in habit |
| Daily completions accepted | 150–350 | Steady, above-average utilization |
| Copilot `loc_added_sum` as % of total lines added | 20–40% | Meaningful AI contribution to code volume |
| Chat-to-completion ratio | 0.1–0.3 (1 Chat session for every 3–10 completion sessions) | Active conversational usage beyond passive acceptance |
| Agent mode sessions | 0–5 per month (exploring) | Beginning to experiment with agentic features |
| PR throughput delta | 15–30% increase vs. baseline | Measurable delivery acceleration |
| PR cycle time delta | 15–25% improvement | Faster time from PR open to merge |
| Multi-tool usage | Uses 2–3 AI tools (detectable via DX file-system observability or developer survey) | Indicates active exploration beyond default toolchain |

**Qualitative / survey-based indicators:**

- Self-reports saving **2–4 hours per week** from AI tools, aligned with the DX industry benchmark
- Describes AI as "a really good pair programmer" or "my research assistant" in coaching sessions
- Actively shares prompts or AI tips with teammates; identified as an emerging AI champion by peers
- In surveys, rates high on satisfaction with AI tools but may flag frustrations with "almost-right solutions" (the **#1 complaint** per Stack Overflow 2025, cited by 66% of developers)
- Uses AI for at least four distinct task types: code generation, test writing, documentation, debugging/explanation
- Still describes their work process in terms of tasks *they* perform ("I wrote the API, then used AI to generate tests") rather than work they *delegated*
- In coaching sessions, demonstrates the ability to iterate on AI output (Anthropic's research shows iterative conversations exhibit **2.67x more fluency behaviors** than non-iterative ones)
- May express concern about over-reliance or code quality of AI output—a healthy sign of developing Discernment

---

## Level 3 — "The Specifier"

### Maturity level: Specification-Driven Development (SDD)

**The Specifier has fundamentally inverted the development workflow: they write the blueprint first, and AI produces the implementation.** This is the critical inflection point in the maturity model—the moment where AI shifts from supporting existing work to reshaping *how work is structured*. The Specifier begins with a structured specification document—context, acceptance criteria, interface definitions, scenarios, security constraints—and uses this spec as the "prompt on steroids" that constrains and directs AI code generation. They iterate through verify-and-refine loops: the AI generates code, the Specifier runs tests, reviews output against the spec, provides corrective feedback, and repeats until the implementation satisfies the specification. The human remains accountable for architecture, intent, and acceptance—but the human is no longer the primary author of syntax.

This persona represents what your organization's SDD Governance Plan describes as the target state: specs as the source of truth for behavior, tests as the executable form of specs, and code referencing spec IDs in commits and PRs. The Specifier's internal document, "Spec-Driven Development for Large Organizations," captures the role precisely: *"The job description of the Senior/Staff Engineer changes. Old Role: writing the hardest code. New Role: writing the Constitution, reviewing the Plans, designing the Spec Architecture."* A Specifier writing a good spec can effectively "program" five junior engineers or AI agents to implement correctly. They practice what Annie Vella's research at Westpac calls **Supervisory Engineering Work**: directing AI (specifying intent, crafting prompts, managing context), evaluating output (deciding what to accept, modify, or reject), and correcting errors (fixing mistakes, maintaining consistency).

In Anthropic's 4D framework, the Specifier demonstrates all four competencies at high levels: strong Delegation (knowing what to hand off and how), excellent Description (specs are structured, unambiguous instructions), developing Discernment (rigorous verification against acceptance criteria), and high Diligence (maintaining traceability and governance). GitHub's research calls this the **AI Strategist** stage: "Plans, orchestrates, and verifies work; describes role as 'creative director of code.'"

For a ~350-developer org piloting SDD, this is currently **10–15%** of the population, concentrated among senior and staff engineers on pilot teams. This is the segment your enablement investment should grow most aggressively.

### Observable behaviors

The Specifier's primary artifacts are markdown files, not code files. Their commits reference spec IDs. Their PRs include or link to structured specifications with acceptance criteria, and the PR description maps implementation to spec requirements. In code reviews, they evaluate whether the code satisfies the specification rather than debating implementation style—a fundamentally different review posture. In standups, they describe progress in terms of "spec coverage" and "scenarios passing" rather than "features coded." They maintain project-level configuration files: `.github/copilot-instructions.md` with detailed project context, `CLAUDE.md` or `.cursorrules` encoding team standards, testing requirements, and architectural constraints. They use **plan mode** in agentic tools—reviewing the AI's proposed approach before authorizing implementation.

In pairing sessions, the Specifier's screen shows a split between a specification document and the IDE, with the spec receiving more editing attention than the code. They use agentic tools (Copilot Agent mode, Claude Code, Cursor Composer) for multi-file changes directed by specs. They ask AI agents to *interview them* for requirements—"What questions do you have about this spec before implementing?"—demonstrating the "clarify loop" that catches ambiguity early. Their test-to-code ratio is high because specifications naturally produce testable acceptance criteria.

### Metrics to identify this persona

**Instrumentable (GitHub Copilot telemetry / Faros AI):**

| Metric | Expected Range | What It Signals |
|--------|---------------|----------------|
| Copilot acceptance rate | 30–40%+ (sustained high acceptance with high volume) | Intentional, effective AI-directed generation |
| Feature usage breadth | Inline + Chat + **Agent mode** (10–20+ Agent sessions/month) | Agent adoption is the binary signal separating Level 3 from Level 2 |
| Copilot `loc_added_sum` as % of total lines added | 40–60% | Majority of code volume originates from AI |
| Active days per month | 18–22 (>80% of workdays = High engagement) | AI is integral to daily workflow |
| Chat sessions per week | 15–30+ (architecture discussion, refactoring, debugging) | Heavy conversational usage for complex tasks |
| Agent mode to completion ratio | >0.3 (Agent sessions constitute significant share of interactions) | Work is being delegated as multi-file tasks, not accepted line-by-line |
| Spec-to-merge cycle time | Tracked per spec ID; trending downward over time | Primary SDD velocity metric from governance plan |
| Defect escape rate (SDD repos vs. non-SDD) | Lower than non-SDD repos | Spec validation catches defects pre-merge |
| PR metadata | Commits/PRs reference spec IDs; PRs link to specification docs | Traceability chain intact per SDD governance |
| Repo configuration files | `.github/copilot-instructions.md`, `CLAUDE.md`, `.cursorrules`, or equivalent | Rules-based AI context shaping in place |
| Test-to-code ratio | Higher than team average (specs generate test scaffolding) | Spec-first approach produces more comprehensive test suites |
| Code churn rate (14-day) | Equal to or lower than team average despite higher AI code volume | Spec-directed code is more stable than "vibe-coded" AI output |

**Qualitative / survey-based indicators:**

- Self-reports saving **4+ hours per week** (DX data shows Staff+ engineers report **4.4 hours/week** on average—Specifiers should exceed this)
- Describes their primary activity as "writing specs" or "defining acceptance criteria" rather than "writing code"
- In coaching sessions, demonstrates the Specify → Plan → Task → Implement workflow and can articulate why each phase matters
- Uses language like "I directed the agent to implement this against the spec" or "the spec tests all pass, so I'm confident in the implementation"
- Peer feedback identifies them as the person who "thinks about the problem before touching the keyboard"
- Maintains or contributes to team-level rules files and project constitutions; peers reference their configuration as a starting point
- In retrospectives, raises issues framed as "spec quality" problems rather than "code quality" problems—recognizing that specification debt is the new bottleneck
- Actively mentors Amplifiers toward spec-first practices; runs informal workshops or demos
- When reviewing AI-generated PRs, evaluates against the spec's acceptance criteria rather than reviewing every line of implementation detail—a critical shift from Level 2

---

## Level 4 — "The Orchestrator"

### Maturity level: Agentic Orchestration (EA / Innovation Lab)

**The Orchestrator designs the system; AI executes the steps.** Where the Specifier writes a spec and iterates with one agent, the Orchestrator configures and coordinates multiple AI agents working in parallel, reading rules files, selecting tools, making multi-step decisions, and routing work across a pipeline. Their primary artifact is not a specification for a single feature—it is the **architecture of the agentic system itself**: the `AGENTS.md` that defines agent behavior, the rules files that constrain each agent's scope, the test harnesses that validate outputs, and the orchestration logic that sequences agent tasks. In Dan Shapiro's five-level framework, this is **Level 4 (Robotaxi)**: "You're a PM. You write specs, argue about specs, craft skills for Claude Code, plan schedules, review plans. Then leave for 12 hours and check if tests pass."

The Orchestrator's mental model treats **markdown as source code**. Their `CLAUDE.md`, `.cursorrules`, and `AGENTS.md` files are version-controlled, reviewed in PRs, and iterated on with the same rigor as application code—because these files *are* the instructions that produce application code. The Orchestrator thinks in terms of agent capabilities, context boundaries, and validation layers. They configure multi-agent architectures where specialized agents handle different aspects of a task (one agent for backend implementation, another for test generation, a third for documentation, a fourth for security review), with the Orchestrator defining the interfaces between agents.

This persona is rare in most organizations today. Anthropic's 2026 Agentic Coding Trends report found that while engineers use AI in ~60% of their work, they can "fully delegate" only **0–20% of tasks**. The Orchestrator is the developer who pushes that delegation percentage to its upper bound. In your organization, this persona likely represents **3–7%** of developers, concentrated among innovation lab participants, platform engineers, and senior architects who have invested significant time experimenting with Claude Code, Cursor's Composer, and multi-agent workflows.

### Observable behaviors

The Orchestrator's screen looks fundamentally different from other developers'. They run **parallel agent sessions**—multiple terminals or Cursor Composer windows working on different aspects of the same feature simultaneously. Their Git log shows commits attributed to AI agents alongside their own, with clear annotation of what was agent-generated versus human-directed. They maintain detailed, version-controlled rules files that encode not just coding standards but decision logic: "If you encounter a policy calculation, always use the actuarial service; never inline the math." Their PRs are large in scope but arrive with comprehensive test coverage because agents generate tests as part of the implementation pipeline.

In standups, the Orchestrator describes work in terms of **systems** rather than tasks: "I configured two agents to parallelize the migration—one handling the data layer, one handling the API surface—and spent the afternoon reviewing their outputs against the contract tests." In architecture discussions, they propose solutions that include "where the AI agents fit"—not as an afterthought, but as a first-class architectural decision. They are the developers who experiment with new agentic tools before the organization officially adopts them, evaluate MCP (Model Context Protocol) integrations, and build custom agent workflows for domain-specific patterns (claims processing workflows, underwriting rule engines).

Their time allocation has shifted dramatically: roughly **20% designing specifications and agent configurations, 50% reviewing and validating agent output, 20% architectural design, and only 10% writing code by hand**. This matches GitHub's finding that AI Strategists "spend more time verifying than generating."

### Metrics to identify this persona

**Instrumentable (GitHub Copilot telemetry / Faros AI):**

| Metric | Expected Range | What It Signals |
|--------|---------------|----------------|
| Agent mode usage | Heavy: 20+ sessions/month; uses Copilot coding agent to open issues and generate PRs | Agent delegation is the defining behavior |
| Copilot Agent PRs | Regularly creates PRs via `@copilot` assignments; reviews and merges agent-generated PRs | Work is delegated to agents as autonomous units |
| Feature usage across surfaces | All surfaces: IDE completions + Chat + Agent + CLI + PR summaries + Code Review + custom prompt files | Maximum feature breadth indicates deep platform mastery |
| Copilot `loc_added_sum` as % of total lines added | 55–75% | Majority of code volume is AI-generated |
| CLI activity | Active Copilot CLI or Claude Code terminal usage | Working in agentic tools beyond the IDE |
| Rules file commits | Version-controlled `AGENTS.md`, `CLAUDE.md`, `.cursorrules`, or equivalent files with active commit history | Markdown-as-source-code is a definitive Level 4 indicator |
| Multi-model usage | Switches between models strategically (per GitHub telemetry's model-usage-per-chat-mode data) | Uses different models for different task types—reasoning vs. implementation vs. review |
| PR volume + size pattern | Higher PR volume, often with agent-attributed commits; larger scope but well-tested | Agent-generated PRs follow a distinct pattern: broad scope with automated test coverage |
| DORA deployment frequency | At or above team average; may show improvement | Agentic workflows should accelerate delivery if governance is in place |
| Change failure rate | Requires close monitoring; should remain stable or improve | The critical guardrail: high agent autonomy must not degrade stability |

**Qualitative / survey-based indicators:**

- Describes their role as "designing systems" or "orchestrating agents," not "writing code"
- In coaching sessions, can demonstrate configuring and running a multi-agent workflow end-to-end
- Peer feedback identifies them as the team's "AI architect" or "agent expert"
- Self-reports saving **6+ hours per week**; may describe entire categories of work that "I no longer do manually"
- In surveys, rates highest on "AI has changed how I approach problems" and "I think about work differently because of AI tools"
- Contributes to or maintains team/org-level agent configurations and rules files that other developers inherit
- Actively evaluates new agentic tools and provides recommendations to platform engineering or architecture review boards
- In retrospectives, raises issues about **agent governance**: audit trails, approval gates for agent-generated changes to security-critical code, agent identity and access management
- Measures their own productivity in terms of **outcomes delivered** rather than code written—tokens consumed and test pass rates are more relevant metrics than lines of code
- May express frustration with organizational constraints that limit agent autonomy (approval workflows, mandatory human review for all PRs)—a healthy tension indicating they've hit the governance boundary

---

## Level 5 — "The Architect"

### Maturity level: Autonomous Feedback Loops (Future State / Dark Factory)

**The Architect sets objectives and constraints; AI systems monitor outcomes, adjust their own rules, and escalate only true exceptions.** This is the most aspirational persona in the model—one that very few developers in any organization have fully achieved, and one that may only be appropriate for specific, well-bounded subsystems within a commercial insurance carrier. The Architect does not write code, does not review code line-by-line, and may not even read individual PRs. Instead, they design the **validation architecture**: the acceptance scenario suites, the monitoring dashboards, the escalation rules, and the quality gates that allow AI systems to operate autonomously while maintaining the organization's risk tolerance. Their primary artifact is an **autonomous feedback loop**—a system where AI monitors its own outputs against predefined constraints, adjusts its approach based on test results, and surfaces only genuine exceptions for human judgment.

StrongDM's "software factory" provides the most vivid implementation: a three-person team operating under two non-negotiable rules—"code must not be written by humans; code must not be reviewed by humans." Their spec repository contains **no code at all**, just markdown files describing specifications and behavioral scenarios. Agents write code, test harnesses validate, and software ships. Spotify's Honk platform similarly enables engineers to trigger autonomous code changes via Slack, with roughly **50% of updates** flowing through the system. Anthropic reports that **90% of Claude Code's own codebase** was written by Claude Code itself.

For a ~350-developer insurance IT organization, this persona is **future state** for most systems, but potentially achievable today for well-bounded, low-risk subsystems with excellent test coverage: internal tooling, documentation generation pipelines, standardized CRUD services, or monitoring/alerting configuration. The ACG maturity framework (Autonomy + Controls + Governance, each scored 0–5) provides the critical guardrail: **dark factory requires Level 5 on all three axes**. High autonomy with weak controls is the "danger zone"—especially in a regulated industry where code correctness has financial and compliance consequences.

This persona represents **<2%** of your developer population today, and likely exists only in pilot or experimental capacity.

### Observable behaviors

The Architect's daily work looks nothing like traditional software development. Their screen shows **monitoring dashboards, test harness results, and specification documents**—rarely an IDE. They spend their time defining acceptance scenarios (including "holdout scenarios" not visible to the coding agent, preventing agents from gaming their own tests), designing validation frameworks, and setting the constraints within which autonomous systems operate. When they engage with code at all, it is to investigate escalated exceptions—situations where the autonomous system encountered something outside its decision boundaries.

In organizational settings, the Architect functions as a **bridge between engineering and business**: they translate business objectives into measurable constraints that autonomous systems can enforce. In standups, they report on system health metrics and exception rates rather than feature progress. In architecture reviews, they propose autonomous subsystems with explicit scope boundaries: "This claims intake validation service is a strong candidate for autonomous operation because it has 400+ behavioral scenarios, 99.7% test coverage, and a clear escalation path for edge cases."

They measure engineering efficiency in terms of **token economics** (cost per feature delivered via agents), **exception rates** (percentage of outputs requiring human intervention), and **specification drift** (how often the system's autonomous adjustments diverge from the intended spec). They are thinking about **specification debt** as the new technical debt: "Bad specs at scale could be worse than bad code at scale, because the feedback loop is different."

### Metrics to identify this persona

**Instrumentable (GitHub Copilot telemetry / Faros AI / CI/CD systems):**

| Metric | Expected Range | What It Signals |
|--------|---------------|----------------|
| Personal code authorship | Near zero; commits are agent-generated or system-generated | The defining metric: humans don't write code at this level |
| Agent-generated PR volume | High; PRs opened by `@copilot` or CI/CD agent accounts | Work flows through automated pipelines |
| Test coverage on autonomous subsystems | >95% (with holdout scenarios) | Validation architecture is the primary human contribution |
| Exception/escalation rate | Tracked and trending downward over time | The "dark factory" gets better as scenarios accumulate |
| Token consumption per engineer | High ($500–1,000+/month per human engineer, per StrongDM's benchmark) | Token spend replaces LOC as the primary engineering input metric |
| Spec-to-deploy cycle time | Fully automated for autonomous subsystems; minutes to hours | Zero human intervention from spec approval to production deployment |
| Change failure rate on autonomous subsystems | At or below organizational average | The critical safety metric: autonomy must not degrade stability |
| DORA metrics on autonomous pipelines | Elite-level deployment frequency (on-demand); sub-hour lead time | Autonomous systems should achieve the best DORA metrics in the org |
| Specification churn | Low; specs stabilize as scenarios accumulate | Indicates specification maturity and system convergence |

**Qualitative / survey-based indicators:**

- Describes their role as "designing the factory" or "setting constraints for autonomous systems"—never as "writing code"
- In coaching sessions, can demonstrate an end-to-end autonomous pipeline: spec → agent implementation → automated validation → deployment → monitoring → feedback loop
- Peer feedback identifies them as the person who "thinks about software as a system that builds itself"
- In surveys, rates highest on "AI has fundamentally changed my understanding of what software development is"
- Actively participates in governance design: defining which subsystems are candidates for autonomy, what risk thresholds trigger human escalation, and how autonomous adjustments are audited
- Evaluates success in terms of **business outcomes delivered** (cycle time from business request to production, exception rate, cost per feature) rather than engineering metrics
- In retrospectives, raises issues about specification quality, validation coverage gaps, and governance maturity—the three factors that constrain how far autonomy can safely extend
- May advocate for organizational changes that most colleagues find uncomfortable: "We should stop reviewing this service's PRs and trust the test harness"
- Thinks about the **feedback loop quality**: how quickly the system learns from exceptions, whether autonomous adjustments drift from intent, and whether the escalation patterns are efficient

---

## How the five personas map to organizational measurement

The five personas create a distribution curve that your organization can track over time. Today, a ~350-developer insurance IT organization with GitHub Copilot deployed and SDD being piloted likely looks approximately like this:

| Persona | Maturity Level | Estimated Current Distribution | 12-Month Target |
|---------|---------------|-------------------------------|----------------|
| **The Accelerator** | L1: Autocomplete | 30–40% | 15–20% |
| **The Amplifier** | L2: Conversation as Workflow | 25–35% | 30–35% |
| **The Specifier** | L3: Specification-Driven Development | 10–15% | 25–30% |
| **The Orchestrator** | L4: Agentic Orchestration | 3–7% | 10–15% |
| **The Architect** | L5: Autonomous Feedback Loops | <2% | 3–5% |

The **strategic objective is not to push everyone to Level 5**. It is to shift the center of gravity from Level 1–2 toward Level 3, while building a small cadre of Level 4–5 practitioners who can design the agentic and autonomous systems that the organization will increasingly rely on. The SDD pilot is the primary vehicle for this shift: it provides the structured pathway from Amplifier to Specifier that transforms how developers relate to AI.

### Measurement principles that protect these personas from misuse

Three principles from your internal research and the broader evidence base are non-negotiable when deploying this framework:

**Measure at team level, never tie to individual evaluation.** Your internal analysis is unequivocal: "Individual developer productivity metrics consistently backfire." DORA, DX, SPACE, and every major researcher agrees. Use persona distribution as a **team-level diagnostic** that informs enablement investment—not as an individual performance label. A team that is 80% Accelerators needs different coaching than one that is 60% Amplifiers.

**Always pair velocity metrics with quality counterweights.** The 2025 DORA report's central finding—that AI adoption correlates with **higher throughput but also higher delivery instability**—means that persona progression without quality gates is organizational risk. Every persona's metrics include quality indicators (defect escape rate, change failure rate, code churn) alongside velocity indicators. For a commercial insurance carrier, where code correctness has regulatory and financial consequences, this is especially critical.

**Combine telemetry with self-report and coaching observation.** No single metric captures the behavioral shift between personas. An Accelerator and a Specifier might have similar acceptance rates on a given day; what distinguishes them is *what they're accepting and why*. The qualitative indicators—how developers describe their relationship with AI, what artifacts they produce, what questions they ask in design reviews—are as diagnostic as any dashboard metric. DX's experience sampling methodology (asking targeted questions at the point of work) is the most effective approach: prompt developers after PR submission with "Did AI generate the initial implementation for this PR?" and after code review with "Did you evaluate this PR against a specification?"

### The progression is not automatic—it requires deliberate enablement

GitHub's research found that "none of these AI strategists started out that way. Most of them started as AI skeptics or timid explorers." The path involves "relentless trial-and-error" and "pushing themselves to use AI tools every day for everything." Each transition between personas requires a specific enablement intervention:

**Accelerator → Amplifier** requires exposure to Chat-based workflows and peer modeling. Pair Accelerators with Amplifiers in coding sessions. Set team challenges: "Complete this sprint's test generation entirely through Copilot Chat." The goal is habit formation—moving from sporadic to daily multi-surface usage.

**Amplifier → Specifier** requires structured training in specification engineering. Your SDD pilot is this intervention. Teach developers to write structured markdown specs with acceptance criteria, scenarios, and interface definitions *before* touching the IDE. The internal "Spec-Driven Development for Large Organizations" document provides the curriculum: technical writing, systems thinking, decomposition, and contract definition. This is the hardest transition because it requires changing *how developers think about their job*, not just which tools they use.

**Specifier → Orchestrator** requires access to agentic tools and permission to experiment. Provide sandbox environments where developers can run Claude Code in plan mode, configure multi-agent workflows, and iterate on rules files without production risk. Create an "agent lab" where aspiring Orchestrators can try Copilot's coding agent, experiment with MCP integrations, and learn to design autonomous pipelines.

**Orchestrator → Architect** requires organizational trust and governance infrastructure. This transition depends less on individual skill and more on the organization's maturity in testing, CI/CD, monitoring, and audit. The ACG framework applies: you cannot safely operate at Level 5 autonomy without Level 5 controls and Level 5 governance. Start with low-risk, well-bounded subsystems and prove the model before expanding scope.

---

## Conclusion: the real metric is the shape of the curve

The five personas—Accelerator, Amplifier, Specifier, Orchestrator, Architect—provide a shared vocabulary for a conversation that is otherwise dangerously vague. When a CIO asks "How AI-mature is our engineering organization?", the answer is not a single number but a **distribution**: what percentage of our 350 developers operate at each level, and how is that distribution shifting quarter over quarter? When a coach sits with a developer who "uses Copilot," the persona framework reveals whether that developer is tab-completing their way through boilerplate (Accelerator) or writing executable specifications that agents implement against test harnesses (Specifier)—two fundamentally different activities that happen to involve the same tool.

The most important insight from the research is that **the bottleneck is never the AI tools—it is how developers relate to them**. An organization at the same Copilot license count can be 80% Accelerators or 40% Specifiers; the difference is not technology budget but enablement investment, workflow design, and the organizational courage to let specifications replace syntax as the primary artifact of software development. For a commercial insurance carrier navigating the shift from hand-written to AI-generated code, the safest and highest-leverage move is clear: invest in growing the Specifier population, because that is the persona where AI contribution increases *and* code quality improves simultaneously—the only level where more AI means better software, not just faster software.