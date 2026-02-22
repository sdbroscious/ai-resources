---
name: test-quality-evaluator
description: Evaluate a project's test-suite quality using two-model comparative review and produce a single report in `docs/tests-eval.md`. Use when the user asks for test-quality assessment, test audit, coverage confidence analysis, or model-based review of tests. Allows the user to select model pairs valid for the active agent.
user-invocable: true
---

# Test Quality Evaluator

Evaluate the quality of a repository's tests by running two independent model assessments and then synthesizing a final judgment.

## Workflow

1. Inspect the test surface before scoring.
2. Read `references/rubric.md` and score against each rubric dimension.
3. Run two independent evaluations using a model pair.
4. The user will select the model pair from a complete list of the coding agent's valid models.
5. Keep the two model passes independent until synthesis.
6. Synthesize agreements and disagreements into one final report.
7. Write the report to a markdown file in `docs`, with a filename of 'tests-eval' + date-time suffix.

## Required Output File

The report file must include the following:

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
