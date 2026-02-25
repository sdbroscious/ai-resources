# AI Tool Selection Guide for Developer Teams (2026)

Use this concise guide with the workbook template. It mirrors the canonical criteria exactly.

## Criteria Map (C01-C40)

### Technical Capabilities
- C01 Modality support
- C02 Model support
- C03 Prompt / instruction customization
- C04 Context awareness & intelligence
- C05 Agentic actions with guardrails
- C06 Latency & reliability

### Code Quality & Safety
- C07 Accuracy & relevance
- C08 Security practices
- C09 Code augmentation with your codebase
- C10 Testability & correctness
- C11 Maintainability checks
- C12 Provenance & attribution

### Integration & Workflow
- C13 Cross-IDE support
- C14 Workflow impact
- C15 PR & CI integration
- C16 CLI & API
- C17 Observability

### Measurement & Value
- C18 Outcome metrics
- C19 Adoption metrics
- C20 Quality metrics
- C21 Experiment design

### Enterprise Readiness & Governance
- C22 Data security & privacy
- C23 Admin & policy controls
- C24 Compliance

### Cost & Capacity Planning
- C25 Licensing & limits
- C26 Controls & governance of spend
- C27 Total cost of ownership

### Adoption & Change Management
- C28 Learning curve
- C29 Developer adoption factors
- C30 Enablement
- C31 Change risk controls
- C32 Vendor support

### Innovation Readiness (2026)
- C33 Tool protocol interoperability
- C34 Autonomous issue-to-PR execution
- C35 Eval harness & benchmarking
- C36 Memory/context lifecycle controls
- C37 Multimodal engineering support
- C38 Policy-as-code guardrails
- C39 Private/local model deployment flexibility
- C40 Continuous adaptation & feedback loops

## How to run an evaluation in 2-4 weeks

1. Week 1: Setup and gating
- Fill `Checklist` columns A-I for all C01-C40 rows.
- Mark must-haves in column E.
- Set `Category Weight` and `Criterion Weight`.
- Confirm threshold in `Rubric!B10`.

2. Weeks 2-3: Evidence and scoring
- For each vendor, populate `Score` columns N-P using rubric 0-5.
- Capture proof in `Evidence/Notes`, `Data Source`, `Reviewer`, and `Date`.
- Use identical task sets per vendor for fairness.

3. Week 4: Rollup and decision
- Review normalized results and must-have pass/fail in `Rollup`.
- Compare category subtotals to identify risk concentration.
- Make go/no-go recommendation with rollout constraints.

## Workbook tab mapping
- `Checklist`: criteria, weights, evidence, per-vendor scoring.
- `Rubric`: score definitions and must-have threshold.
- `Rollup`: weighted totals, normalized scores, must-have gate, category breakdown.
- `Instructions`: quick operation notes and version marker.

## Decision Rules
- Any vendor with must-have FAIL is not selectable.
- Among PASS vendors, prefer highest normalized weighted score.
- If scores are within 3 percentage points, choose the lower-risk option from governance and support evidence.

## Consistency Guard
Last synchronized with workbook schema version: `v2026.1`.
