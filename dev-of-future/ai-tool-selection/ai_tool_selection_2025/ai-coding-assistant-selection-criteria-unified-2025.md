# AI Coding Assistant Selection Criteria — Unified 2025

> A merged, de-duplicated checklist that keeps the strongest elements of your original list and adds 2025-specific upgrades (agentic safety, repo-scale context, governance, and rigorous measurement).

---

## Technical Capabilities
- **Modality support (keep)** — High-quality inline completions, chat, and *agent* modes; seamless switching among them.
- **Model support (keep + enhance)** — Multiple models with routing for speed/reasoning/long-context; clear update cadence and fallbacks; BYOM/on‑prem options where needed.
- **Prompt / instruction customization (keep + enhance)** — Org/repo/system prompts; policy prompts; allow redaction rules and stop-lists (e.g., secrets, domains).
- **Context awareness & intelligence (keep → enhance)** — Robust repo-aware context across monorepos, multi-service, and multi-language codebases; embeddings/“code graph” retrieval; cross-file & architectural pattern awareness.
- **Agentic actions with guardrails (new)** — Plan & execute multi-step tasks (refactors, test generation, migrations) with dry-run/PR-only modes, explicit approvals, and fine-grained scopes.
- **Latency & reliability (enhance)** — Sub-200ms inline suggestions; stable chat; graceful degradation offline/air‑gapped; published SLOs.

## Code Quality & Safety
- **Accuracy & relevance (keep)** — Measured correctness on representative tasks and stacks.
- **Security practices (keep → enhance)** — Built-in secret-leak prevention; framework-specific vulnerability hints; OWASP-aligned guidance; license & OSS policy awareness.
- **Code augmentation with your codebase (keep)** — Learns patterns and produces idiomatic diffs; respects conventions.
- **Testability & correctness (new)** — One-click run of unit tests on proposed changes; easy regeneration on failures; support for snapshot/approval tests when useful.
- **Maintainability checks (new)** — Complexity deltas, dependency hygiene, style compliance; prefer minimal, reviewable diffs.
- **Provenance & attribution (new)** — Mark AI-generated diffs; trace prompts/models for auditability.

## Integration & Workflow
- **Cross-IDE support (keep)** — First-class IntelliJ/JetBrains and VS Code; credible support for Java, C#, Python.
- **Workflow impact (keep → enhance)** — Fit with existing SDLC; respects branch policies; works with pair programming/reviews.
- **PR & CI integration (new)** — Review bots, unit-test execution, SonarQube/quality gate hooks, “suggest” vs “auto-commit” modes.
- **CLI & API (new)** — Scriptable codemods, bulk refactors, repo-wide tasks; webhooks/events for automation.
- **Observability (new)** — Per-team dashboards, A/B flags, export to your analytics stack; privacy-aware logging.

## Measurement & Value
- **Outcome metrics (new/expanded)** — PR cycle time, time-to-change, defect escape rate, MTTR, incident volume.
- **Adoption metrics (keep → enhance)** — Active seats, acceptance rate by repo/language, *assisted tests per PR*, agentic tasks completed.
- **Quality metrics (new)** — Post-merge rework %, flaky-test delta, security finding trendlines.
- **Experiment design (new)** — Built-in cohorting, control vs. treatment, feature flags for clean comparisons.

## Enterprise Readiness & Governance
- **Data security & privacy (keep → enhance)** — No training on your code by default; data residency; configurable retention; VPC/private networking.
- **Admin & policy controls (keep → enhance)** — SSO/SCIM/RBAC; per-BU policy bundles; audit logs for prompts/outputs/actions; IP indemnification terms.
- **Compliance (new)** — SOC 2/ISO 27001 evidence; artifact retention for audits; configurable redaction/content logging.

## Cost & Capacity Planning
- **Licensing & limits (keep)** — Clear seat/usage components; transparent rate limits.
- **Controls & governance of spend (enhance)** — Per-team budgets, caps, and alerts; burst protection; auto-throttle for non-critical jobs.
- **Total cost of ownership (new)** — Include enablement, security review, support SLAs, infra; weigh against observed productivity deltas.

## Adoption & Change Management
- **Learning curve (keep)** — Time-to-effectiveness; documentation quality; targeted guidance by role.
- **Developer adoption factors (keep)** — Team dynamics, resistance points, fit with current practices.
- **Enablement (new)** — Quick-start playbooks, “golden paths” for tests/refactors, office hours, exemplar repos.
- **Change risk controls (new)** — Rollout by repo/branch; guardrails for agentic changes; revert & kill-switch procedures.
- **Vendor support (keep)** — Community, roadmap transparency, responsiveness.

## Recommended Evaluation Process (Refreshed)
1. **Fit check (1–2 weeks)** — Verify IDE coverage, latency, model fit, and governance constraints in a sandbox.
2. **Pilot (3–6 weeks)** — Production-adjacent repos; measure outcome/adoption/quality metrics with A/B design.
3. **Scale-up (4–8 weeks)** — Expand to critical paths; enforce policies, optimize costs, formalize enablement & SLOs.

---

### Quick Use Checklist (copy/paste)
- Capabilities: modalities ▢  repo-aware context ▢  agent guardrails ▢  latency/SLOs ▢
- Quality: accuracy ▢  security ▢  maintainability ▢  provenance ▢  testability ▢
- Workflow: IDEs ▢  PR/CI hooks ▢  CLI/API ▢  observability ▢
- Measurement: outcomes ▢  adoption ▢  quality ▢  experiment design ▢
- Enterprise: data boundaries ▢  admin/policy ▢  compliance ▢
- Cost: pricing clarity ▢  controls ▢  TCO ▢
- Adoption: enablement ▢  rollout controls ▢  vendor support ▢  developer experience ▢

---
>NOTE: Response from GPT-5 to this prompt: "please combine what's worth keeping from the original with your additions into a single set of selection criteria."

>NOTE: the A__Coding_Assistant_Selection_Template_2025.xlsx was created from this prompt: "please create a spreadsheet template from the unified selection criteria"