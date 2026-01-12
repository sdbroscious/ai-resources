# AI Coding Assistant Selection Criteria — 2025 Update (Bulleted)

- **Overall relevance**
  - Your existing framework is still solid and maps well to today’s tools; keep it as the backbone.
  - The biggest 2025 shifts: stronger agentic features, deeper repo-aware context, stricter governance needs, and better measurement of impact beyond LOC or raw acceptance rates.

---

- **Technical capabilities**
  - **Repo-aware context**: first-class understanding across monorepos, multi-service architectures, and cross-language code; supports embeddings/“code graph” style retrieval.
  - **Agentic actions with guardrails**: can plan multi-step changes (e.g., refactors, test creation, migrations) with “dry-run,” PR-only mode, and explicit approval gates.
  - **Prompt & policy controls**: org/project/system prompts; per-repo rules; redaction/PII filters; configurable stop-lists for secrets and domains.
  - **Model strategy**: multi-model routing (reasoning/long-context/speed), transparent update cadence, fallbacks, and on-prem/BYOM options where needed.
  - **Latency & reliability**: sub-200ms inline suggestions, graceful offline/air-gapped modes, clear SLOs.

- **Code quality & safety**
  - **Correctness beyond “looks right”**: testable outputs, tool-assisted execution of unit tests, and easy regeneration when tests fail.
  - **Security by default**: secret-leak prevention, secure-pattern hints (e.g., OWASP, framework-specific vulns), license/OSS policy awareness.
  - **Maintainability checks**: cyclomatic complexity, dependency hygiene, style/convention adherence; preference for minimal diffs.
  - **Provenance & attribution**: flags AI-generated diffs; traceability to prompts/models for audits.

- **Integration & workflow**
  - **IDE coverage**: high-quality support for IntelliJ/JetBrains, VS Code, and common alternates; parity for Java, C#, Python.
  - **PR & CI integration**: review bots, auto-tests, SonarQube hooks, quality gates; “suggest changes” vs “auto-commit” modes.
  - **CLI & API**: scriptable operations for batch refactors, codemods, and repo-wide tasks; event/webhook support.
  - **Observability**: per-team/tenant dashboards, A/B flags, experiment toggles; export to your analytics stack.

- **Measurement & value**
  - **Outcome metrics**: defect escape rate, MTTR, time-to-change, PR cycle time, incident volume—paired with coverage and review depth.
  - **Adoption metrics**: active seats, suggestion acceptance by language/repo, “assisted tests per PR,” agentic tasks completed.
  - **Quality metrics**: post-merge rework %, flaky-test delta, security finding trendlines.
  - **Experiment design**: built-in group assignments, feature flags, and control vs. treatment comparisons.

- **Enterprise readiness & governance**
  - **Data boundaries**: no training on your code by default, regional data residency, retention windows, VPC/private networking.
  - **Admin & policy**: SSO/SCIM/RBAC, policy bundles per business unit, audit logs (prompts/outputs/actions), legal/IP indemnification terms.
  - **Compliance**: SOC 2/ISO 27001, artifact retention for audits, configurable redaction and content logging.

- **Cost & capacity planning**
  - **Transparent pricing**: clear seat + usage components, rate-limit tiers, forecasting tools.
  - **Controls**: per-team caps, burst protection, budget alerts, auto-throttle for non-critical jobs.
  - **TCO**: include security review, enablement, support SLAs, and expected productivity deltas.

- **Adoption & change management**
  - **Enablement**: role-based training (backend, QA, SRE), quick-start prompts/playbooks, “golden paths” for tests and safe refactors.
  - **Change risk controls**: rollout by repo/branch; approval workflows for agentic changes; revert & kill-switch procedures.
  - **Developer experience**: low friction onboarding, high-quality docs, quick feedback loops; accessibility considerations.

- **Recommended evaluation process (refresh)**
  - **Fit check (1–2 weeks)**: verify IDE coverage, latency, model fit, and governance constraints using a small sandbox.
  - **Pilot (3–6 weeks)**: production-adjacent repos; measure outcome/adoption/quality metrics with A/B design.
  - **Scale-up (4–8 weeks)**: expand to critical paths; enforce policies, optimize costs, formalize enablement and SLOs.

---

- **Keep from your original list (with minor tweaks)**
  - Modality support (inline/chat/agents), model support, prompt customization, context awareness, accuracy/relevance, security practices, codebase augmentation, cross-IDE support, workflow impact, metrics, data security, admin tools, licensing/limits, learning curve, adoption factors, vendor support—all remain essential; emphasize agent guardrails, provenance, and observability within each.

> These updates preserve your structure while adding 2025-specific requirements for agent safety, governance, repo-scale context, and rigorous measurement.

---
>NOTE: Response from GPT-5 to this prompt: "The attached file (ai-tool-selection.md) contains criteria for selecting AI coding assistant tools. Are the criteria still relevant? Can they be enhanced at all? Please respond with a similarly bulleted list that is also in the form of a markdown file."
