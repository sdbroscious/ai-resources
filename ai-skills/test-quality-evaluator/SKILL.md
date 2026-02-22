---
name: test-quality-evaluator
description: Evaluate a project's test-suite quality using two-model comparative review and produce a single report in `docs/tests-eval.md`. Use when the user asks for test-quality assessment, test audit, coverage confidence analysis, or model-based review of tests. Select model pairs by active agent - Codex uses `gpt-5.3-codex` + `gpt-5.2-codex` (both medium), Claude uses `opus` + `sonnet`, and Copilot uses `Claude Opus 4.6` + `GPT-5.2-Codex`.
---

# Test Quality Evaluator

Evaluate the quality of a repository's tests by running two independent model assessments and then synthesizing a final judgment.

## Workflow

1. Inspect the test surface before scoring.
2. Read `references/rubric.md` and score against each rubric dimension.
3. Run two independent evaluations using the model pair for the active agent:
   - Codex:
     - `gpt-5.3-codex` (`medium`)
     - `gpt-5.2-codex` (`medium`)
   - Claude:
     - `opus`
     - `sonnet`
   - Copilot:
     - `Claude Opus 4.6`
     - `GPT-5.2-Codex`
4. Keep the two model passes independent until synthesis.
5. Synthesize agreements and disagreements into one final report.
6. Write the report to a markdown file in `docs`, with a filename of 'tests-eval' + date-time suffix.

## Required Output File

Always overwrite `docs/tests-eval.md` with:

1. Metadata section:
   - date (ISO format)
   - repository path
   - active agent
   - model pair
2. Per-model evaluation sections:
   - summary judgment
   - rubric scores
   - key findings
   - critical risks
3. Synthesis section:
   - consensus findings
   - disagreement analysis
   - confidence level
4. Action plan:
   - prioritized fixes
   - missing tests to add
   - suggested command checks

## Constraints

1. Base findings on repository evidence; call out unknowns.
2. Prefer concrete file and test references over generic advice.
3. Keep recommendations executable and ordered by impact.
