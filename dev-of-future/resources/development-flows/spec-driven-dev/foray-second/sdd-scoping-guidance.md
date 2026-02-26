This document resulted from a prompt to my Spec-Driven Development & Prompt Engineering (NotebookLM) notebook on 2026-01-19: Here's the prompt:

>how can spec-driven development be applied to different levels, scopes of work (e.g., greenfield or brownfield app, epic, feature or story?

Spec-Driven Development (SDD) scales by adjusting the "altitude" of the specification—from high-level architectural constitutions down to atomic unit tests. While the core workflow (Specify → Plan → Task → Implement) remains consistent, the application varies significantly depending on the scope of work.

### 1\. Greenfield Projects (Zero-to-One)

For new applications, SDD focuses on defining the product vision and technical foundation before a single line of code is written. This prevents "vibe coding," where ad-hoc prompting leads to disjointed prototypes 1, 2\.

* **Specification Phase:** You define the product vision, user personas, and core value propositions (the "what" and "why") without technical jargon 3, 4\. This acts as the anchor for the entire project 5\.  
* **Planning Phase:** The AI agent recommends a technology stack and architecture based on the spec. For example, it might suggest a Next.js frontend with a Postgres database based on the requirements 6\. This is where you establish a "Constitution"—a governing document containing immutable rules regarding code style, security, and testing standards 7, 8\.  
* **Execution:** SDD allows for the rapid generation of an MVP (Minimum Viable Product). Teams report launching MVPs 30-50% faster by using specs to generate the initial boilerplate, database schemas, and API contracts in one coordinated effort 9, 10\.

### 2\. Brownfield Projects (Legacy & Modernization)

Applying SDD to existing codebases is more complex but high-value. It shifts the focus from "creation" to "archaeology" and "refactoring" 10\.

* **Reverse-Engineering Specs:** Before making changes, you use AI to analyze the current system and generate a baseline specification of existing behaviors, data flows, and dependencies 11, 12\. This captures "tribal knowledge" that may otherwise be lost 13\.  
* **Incremental Refactoring:** You define a "Target Specification" for the desired end-state (e.g., migrating a monolith to microservices) 14\. The implementation plan typically uses the "Strangler Fig" pattern, creating new specs for isolated modules and migrating them one by one while keeping the old system running 15, 16\.  
* **Context Management:** Tools like GitHub Spec Kit allow you to inject the project's "Constitution" into the context, ensuring new code matches the legacy system's style or enforces new modern standards on old code 17, 18\.

### 3\. Epics (Large-Scale Initiatives)

For Epics, which often span multiple services or repositories, SDD serves as a coordination layer to prevent integration hell.

* **Architecture Decision Records (ADRs):** The spec for an Epic often includes ADRs that document high-level structural decisions (e.g., "Migrate Auth to OAuth 2.0") 19\.  
* **API-First Design:** The spec defines the interface contracts (e.g., OpenAPI specs) between services before implementation begins. This allows frontend and backend teams to work in parallel using mock servers generated from the spec 20, 21, 22\.  
* **Compliance & Security:** For regulated industries like finance, the Epic spec explicitly details non-functional requirements like GDPR compliance or audit logging. This ensures these constraints are baked into the plan rather than added as an afterthought 23, 24\.

### 4\. Features (Medium Complexity)

At the feature level, SDD prevents "scope creep" and ensures the AI understands the feature's boundaries within the existing application.

* **Structured Requirements:** The spec defines user stories, inputs, outputs, and specifically handles edge cases (e.g., "What happens if the user has no favorites?") 25\.  
* **Integration Planning:** The "Plan" phase explicitly maps how the new feature hooks into existing databases and APIs. For example, a "User Authentication" feature spec would detail the specific library (e.g., bcrypt) and the exact validation logic (e.g., "password must be 12+ chars") 26\.  
* **Iterative Refinement:** If requirements change (e.g., adding a new field), you update the spec first, then regenerate the plan. This keeps the documentation and code in sync, reducing technical debt 27, 10\.

### 5\. Stories and Tasks (Atomic Units)

At the lowest level, SDD breaks down plans into small, testable units. This is the "execution" layer where AI agents are most effective because the context window is highly focused.

* **Task Decomposition:** The AI breaks a feature plan into a checklist of tasks (e.g., "Create database migration," "Add API endpoint," "Update UI component") 28, 29\.  
* **Test-Driven Development (TDD):** SDD aligns well with TDD at this level. The spec for a task can be converted directly into a unit test. The AI is then instructed to write code that passes this specific test 30, 31\.  
* **Reviewability:** Instead of reviewing a massive PR, developers review code generated for specific tasks against the task's specific acceptance criteria 32, 4\.

**Note on Limitations:** SDD is generally considered "overkill" for very small tasks, such as minor bug fixes or one-line UI tweaks, where the overhead of writing a spec outweighs the implementation time 33, 34\.  
