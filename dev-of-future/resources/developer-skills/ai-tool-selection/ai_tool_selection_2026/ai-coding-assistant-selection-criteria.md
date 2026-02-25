# AI Coding Assistant Selection Criteria (Canonical)

This document is the canonical specification for evaluating end-to-end AI developer tooling in 2026.

## Technical Capabilities

### C01 Modality support
- Why it matters: Teams need inline completion, chat, and agent workflows without context switching overhead.
- How to test: Run representative tasks in all three modes and measure handoff friction.
- Evidence to collect: Completion acceptance rate, task completion time, developer feedback.

### C02 Model support
- Why it matters: Different tasks require different model speed, reasoning depth, and context limits.
- How to test: Compare short-turn, long-context, and complex-reasoning tasks with model routing.
- Evidence to collect: Model options matrix, fallback behavior, latency and quality by model.

### C03 Prompt / instruction customization
- Why it matters: Org and repo policies must be enforceable in AI behavior.
- How to test: Configure org/repo prompts, redaction rules, and blocked topics; run policy-sensitive prompts.
- Evidence to collect: Prompt hierarchy behavior, policy adherence rate, exception logs.

### C04 Context awareness & intelligence
- Why it matters: Large codebases require reliable cross-file and architectural reasoning.
- How to test: Execute monorepo changes spanning multiple services and languages.
- Evidence to collect: Retrieval accuracy, cross-file edit quality, architectural consistency findings.

### C05 Agentic actions with guardrails
- Why it matters: Multi-step automation must remain bounded, reviewable, and safe.
- How to test: Run refactor and migration tasks with dry-run and PR-only constraints.
- Evidence to collect: Approval checkpoints, scope boundary adherence, rollback success rate.

### C06 Latency & reliability
- Why it matters: Developer trust drops quickly with slow or unstable interactions.
- How to test: Measure p50/p95 response times and session stability during peak usage.
- Evidence to collect: Inline/chat latency, error rates, uptime/SLO reports.

## Code Quality & Safety

### C07 Accuracy & relevance
- Why it matters: Correctness and stack fit determine real productivity gains.
- How to test: Benchmark outputs on representative coding tasks and edge cases.
- Evidence to collect: Pass rate on task suite, review defect rate, rework time.

### C08 Security practices
- Why it matters: Suggestions must reduce, not increase, security and licensing risk.
- How to test: Prompt for security-sensitive patterns and vulnerable code remediations.
- Evidence to collect: Vulnerability guidance quality, secret handling behavior, OSS/license checks.

### C09 Code augmentation with your codebase
- Why it matters: Tools should produce idiomatic changes aligned with internal conventions.
- How to test: Request edits in projects with strong style and architecture patterns.
- Evidence to collect: Convention adherence, reviewer acceptance, style/lint failure rate.

### C10 Testability & correctness
- Why it matters: Fast test-aware iteration improves trust in generated changes.
- How to test: Generate code and tests, run tests, and ask tool to repair failures.
- Evidence to collect: Test pass rate, regeneration quality, flaky-test impact.

### C11 Maintainability checks
- Why it matters: Short-term speed should not increase long-term maintenance costs.
- How to test: Compare complexity, dependencies, and diff size before/after AI changes.
- Evidence to collect: Complexity deltas, dependency changes, reviewability metrics.

### C12 Provenance & attribution
- Why it matters: Regulated environments require traceability of AI-assisted changes.
- How to test: Track prompts/models/actions across generated commits and PRs.
- Evidence to collect: Audit trail completeness, attribution metadata, retention behavior.

## Integration & Workflow

### C13 Cross-IDE support
- Why it matters: Mixed-language teams require consistent capabilities across toolchains.
- How to test: Validate feature parity across JetBrains and VS Code in target languages.
- Evidence to collect: IDE compatibility matrix, feature parity gaps, plugin stability issues.

### C14 Workflow impact
- Why it matters: Tooling must fit branch policies, review practices, and SDLC controls.
- How to test: Use standard team workflows including branching, reviews, and pair sessions.
- Evidence to collect: Process friction points, policy exceptions, lead-time changes.

### C15 PR & CI integration
- Why it matters: Quality gates and code review are critical enforcement points.
- How to test: Integrate with PR checks, CI pipelines, and quality gates.
- Evidence to collect: Integration coverage, automation success rates, reviewer load changes.

### C16 CLI & API
- Why it matters: Teams need programmable interfaces for bulk and repeatable workflows.
- How to test: Automate codemod and repo-wide tasks via CLI/API and webhooks.
- Evidence to collect: Automation reliability, API limits, scriptability gaps.

### C17 Observability
- Why it matters: Program leaders need measurable insight into usage and outcomes.
- How to test: Enable dashboards and exports for usage, quality, and cost telemetry.
- Evidence to collect: Available metrics, export fidelity, privacy controls.

## Measurement & Value

### C18 Outcome metrics
- Why it matters: Business value must map to delivery and reliability outcomes.
- How to test: Track baseline versus pilot metrics for cycle time, defects, and MTTR.
- Evidence to collect: Before/after metric snapshots, statistical significance notes.

### C19 Adoption metrics
- Why it matters: Broad and sustained usage is required for portfolio-level impact.
- How to test: Measure active users and acceptance rates by repo/language over time.
- Evidence to collect: Seat utilization, acceptance trendlines, task completion volume.

### C20 Quality metrics
- Why it matters: Quality regressions can offset productivity gains.
- How to test: Monitor post-merge defects, rework, and flaky test trends.
- Evidence to collect: Rework percentage, escaped defect counts, security trendlines.

### C21 Experiment design
- Why it matters: Controlled experiments avoid misleading conclusions.
- How to test: Run treatment/control cohorts with feature flags during pilots.
- Evidence to collect: Cohort definitions, experiment reports, confidence intervals.

## Enterprise Readiness & Governance

### C22 Data security & privacy
- Why it matters: Source code and prompts often contain sensitive IP and regulated data.
- How to test: Validate retention controls, residency options, and private networking.
- Evidence to collect: Data handling policy docs, tenancy architecture, retention settings.

### C23 Admin & policy controls
- Why it matters: Enterprise rollout requires centralized identity and policy governance.
- How to test: Configure SSO/SCIM/RBAC and enforce per-team policy bundles.
- Evidence to collect: Admin control coverage, audit logs, policy enforcement results.

### C24 Compliance
- Why it matters: Security reviews and audits require formal attestations and artifacts.
- How to test: Validate SOC 2/ISO controls and audit-evidence export workflows.
- Evidence to collect: Attestation docs, control mappings, audit artifact samples.

## Cost & Capacity Planning

### C25 Licensing & limits
- Why it matters: Pricing and limits shape scalability and long-term feasibility.
- How to test: Model expected usage patterns against seat and consumption pricing.
- Evidence to collect: Pricing model sheet, rate-limit behavior, overage terms.

### C26 Controls & governance of spend
- Why it matters: Cost guardrails are needed for multi-team adoption.
- How to test: Configure budgets, caps, and alerts for high-usage scenarios.
- Evidence to collect: Budget controls, alerting behavior, spend anomaly handling.

### C27 Total cost of ownership
- Why it matters: Real cost includes enablement, support, and governance overhead.
- How to test: Estimate full TCO over 12 months with staffing and infrastructure inputs.
- Evidence to collect: TCO model, assumptions log, sensitivity analysis.

## Adoption & Change Management

### C28 Learning curve
- Why it matters: Faster onboarding increases realized value.
- How to test: Time new users to productive usage across representative tasks.
- Evidence to collect: Time-to-first-value, training hours, onboarding completion rate.

### C29 Developer adoption factors
- Why it matters: Team culture and trust influence sustained adoption.
- How to test: Run pilot surveys and interviews across role levels.
- Evidence to collect: Sentiment scores, resistance themes, adoption blockers.

### C30 Enablement
- Why it matters: Repeatable guidance is required to scale usage quality.
- How to test: Provide playbooks/golden paths and measure usage consistency.
- Evidence to collect: Playbook usage metrics, office hours attendance, quality uplift.

### C31 Change risk controls
- Why it matters: Controlled rollout limits blast radius of failures.
- How to test: Roll out by repo/branch with kill-switch and rollback drills.
- Evidence to collect: Rollout plan, incident logs, rollback time.

### C32 Vendor support
- Why it matters: Responsiveness and roadmap transparency affect operational risk.
- How to test: Track support SLAs, escalation outcomes, and roadmap delivery consistency.
- Evidence to collect: Support metrics, escalation timeline, roadmap variance.

## Innovation Readiness (2026)

### C33 Tool protocol interoperability
- Why it matters: Tool ecosystems increasingly depend on interoperable agent/tool protocols.
- How to test: Connect external tools through MCP/tool-calling workflows end to end.
- Evidence to collect: Protocol compatibility matrix, integration failures, latency impact.

### C34 Autonomous issue-to-PR execution
- Why it matters: High-leverage automation requires bounded autonomous delivery.
- How to test: Execute issue-to-PR workflows with explicit scope and approvals.
- Evidence to collect: Completion rate, human intervention points, policy violations.

### C35 Eval harness & benchmarking
- Why it matters: Continuous evaluation is needed as models and tools evolve.
- How to test: Run repeatable benchmark suites on each release or model change.
- Evidence to collect: Eval harness definition, benchmark trend reports, regression alerts.

### C36 Memory/context lifecycle controls
- Why it matters: Persistent memory improves relevance but introduces governance risk.
- How to test: Validate memory retention, expiration, deletion, and access controls.
- Evidence to collect: Memory policy config, lifecycle logs, governance exceptions.

### C37 Multimodal engineering support
- Why it matters: Debugging increasingly uses screenshots, traces, and diagrams.
- How to test: Submit multimodal inputs and validate resulting code/test changes.
- Evidence to collect: Input modality coverage, success rate, quality comparison.

### C38 Policy-as-code guardrails
- Why it matters: Runtime policy enforcement must be deterministic and auditable.
- How to test: Enforce policy rules on tool actions across risky workflows.
- Evidence to collect: Policy config, block/allow logs, false positive/negative rates.

### C39 Private/local model deployment flexibility
- Why it matters: Some workloads require self-hosted or hybrid model deployment.
- How to test: Run identical tasks across hosted and private/local model options.
- Evidence to collect: Deployment architecture options, performance tradeoff data.

### C40 Continuous adaptation & feedback loops
- Why it matters: Quality improves when tools incorporate acceptance/rejection feedback.
- How to test: Track feedback signals and verify measurable output improvements.
- Evidence to collect: Feedback capture pipeline, adaptation cadence, quality trend deltas.

## Recommended Evaluation Process
1. Fit check (week 1): Validate technical compatibility, baseline governance, and pilot scope.
2. Pilot execution (weeks 2-3): Run controlled tasks with measurement instrumentation enabled.
3. Decision week (week 4): Finalize weighted scoring, must-have gates, and rollout recommendation.

## Consistency Guard
Last synchronized with workbook schema version: `v2026.1`.
