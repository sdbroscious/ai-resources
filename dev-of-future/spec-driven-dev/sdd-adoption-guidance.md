# Guidance: When to Adopt Spec-Driven Development (SDD)

This document summarizes a conversation I had with Google Gemini and provides a decision framework for when to incur the overhead of formal Spec-Driven Development (creating requirements, specs, plans, and tasks docs) versus when to stick to lightweight Agile processes.

**The Golden Rule:** SDD is an investment. Use it only when the cost of planning is lower than the cost of getting it wrong.

### 1. The Primary Filter: Scope & Complexity
The most immediate indicator is the size of the unit of work.

| Attribute | **Use SDD (The "Large" Story)** | **Skip SDD (The "Small" Story)** |
| :--- | :--- | :--- |
| **Duration** | Estimated > 3-5 days of dev work. | Estimated < 1-2 days. |
| **Ambiguity** | "I know *what* we need, but not *how* to build it yet." | "I know exactly what to type." |
| **Components** | Touches multiple services, modules, or databases. | Isolated to a single function, component, or file. |
| **Testing** | Requires a complex test plan or integration tests. | Can be verified with a simple unit test or visual check. |

### 2. Contextual Facets
Size isn't the only factor. Use these modifiers to adjust your decision.

#### A. Greenfield vs. Brownfield
* **Greenfield (New Features/Apps):**
    * **Guidance:** Lean heavily toward **SDD**.
    * **Reasoning:** You are defining the data structures and architecture for the first time. Mistakes here serve as "foundational technical debt" that cripples future velocity. A spec validates the architecture before code is written.
* **Brownfield (Maintenance/Legacy):**
    * **Guidance:** Use SDD **only for refactors or behavior changes.** Skip for patches.
    * **Reasoning:** If you are fixing a bug or patching a known issue, the "Spec" is effectively the existing code. However, if you are refactoring a messy legacy class, a Spec is crucial to document *expected behavior* to ensure you don't introduce regressions.

#### B. Risk & Criticality
* **High Risk (Security, Billing, Auth, PII):**
    * **Guidance:** **Always use SDD**, regardless of size.
    * **Reasoning:** You need an audit trail. The "Plan" document serves as a "Checklist of Doom" to ensure no edge case (e.g., race conditions in payment processing) is missed.
* **Low Risk (UI Polish, Internal Tools, Copy):**
    * **Guidance:** **Skip SDD.**
    * **Reasoning:** If it breaks, nobody dies. The overhead of writing a spec for a button color change is waste.

#### C. Dependencies
* **Cross-Team/Public API:**
    * **Guidance:** **Use SDD.**
    * **Reasoning:** Your spec acts as a contract. Other people are building against your interface. You cannot "figure it out as you go" if another team is waiting on your API definition.
* **Solo/Internal:**
    * **Guidance:** **Developer Discretion.**

### 3. Examples for Calibration

**Scenario A: The API Integration**
* *Task:* Integrate a new third-party payment provider.
* *Facet Analysis:* Large Scope + Greenfield + High Risk.
* *Verdict:* **Spec Required.** Define the state machine for payments, error handling, and webhooks before coding.

**Scenario B: The Legacy Refactor**
* *Task:* Update the user profile page to use React instead of jQuery.
* *Facet Analysis:* Large Scope + Brownfield.
* *Verdict:* **Spec Required.** You need to map out exactly which data endpoints are needed and how the new component hierarchy maps to the old one.

**Scenario C: The UI Tweak**
* *Task:* Change the "Submit" button to be disabled until the form is valid.
* *Facet Analysis:* Small Scope + Low Risk.
* *Verdict:* **No Spec.** Just write the code and the test.

**Scenario D: The Database Migration**
* *Task:* Add a `last_login` column to the Users table.
* *Facet Analysis:* Small Scope + Brownfield.
* *Verdict:* **No Spec.** Standard migration scripts are sufficient documentation.