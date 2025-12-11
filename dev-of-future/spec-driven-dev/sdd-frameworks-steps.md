# Spec-Driven Development Steps by Framework

## 💻 GitHub Spec Kit (and speckit.org)
This process is a four-phase workflow where the developer uses the AI assistant for generation and guides it through explicit checkpoints.

1.  **Specify**: Provide a high-level description of what needs to be built and why (goals, user stories). The AI generates a detailed specification document.
2.  **Plan**: Specify technical constraints (tech stack, architecture). The AI generates a comprehensive technical plan.
3.  **Tasks**: The AI breaks the finalized spec and plan into concrete, small, reviewable tasks.
4.  **Implement**: The AI implements each task, and the developer reviews the code against the spec and plan.

---

## ☁️ Amazon Kiro
Kiro uses three distinct phases to generate planning documents before coding begins.

1.  **Requirements**: Define functional requirements and user stories, often using EARS notation (e.g., "WHEN [something happens] THE SYSTEM SHALL [do this specific thing]").
2.  **Design**: Define the technical architecture and component interactions.
3.  **Implementation (Tasks)**: Generate a list of specific, actionable tasks to build the feature, which also serves to track progress.

---

## ⚛️ Fission-AI OpenSpec
OpenSpec uses a proposal-based system centered around modifying the specs as a source of truth.

1.  **Draft the Proposal**: Ask the AI to create a change proposal. This scaffolds the necessary files (`proposal.md`, `tasks.md`, `spec deltas`).
2.  **Verify & Review**: Validate the spec formatting and review the proposal, tasks, and spec deltas.
3.  **Refine the Specs**: Iterate and update the specifications until they accurately reflect the desired change.
4.  **Implement the Change**: The AI uses the tasks and refined specs to implement the code.
5.  **Archive the Completed Change**: Archive the change, which merges the new requirements into the project's permanent specs.

---

## 🧵 Tessl Framework (Focus on Spec-Centric Approach)
Tessl emphasizes that the specification itself becomes the primary maintained artifact, with the code often being generated from it.

* **Spec-Assisted Development**: Agents are provided with structured knowledge (coding standards, API docs).
* **Spec-Driven Development**: Critical definitions are captured as specifications; code changes require modifying the spec first, then applying the change.
* **Spec-Centric Development**: Comprehensive specs and tests make the code disposable and regeneratable, as the spec is the source.

---

## 🧠 nano-spec (Referencing Zencoder Docs)
This follows a four-step process for developing features against a specific codebase.

1.  **Specify**: Define the feature from the user's perspective, including constraints and success criteria.
2.  **Plan**: Create a technical implementation plan, including architecture and integration points, considering the existing codebase.
3.  **Tasks**: Break down the implementation into discrete, testable tasks.
4.  **Implement**: Execute the tasks with continuous validation against the specifications and plan.