This document resulted from a prompt to my Spec-Driven Development & Prompt Engineering (NotebookLM) notebook on 2026-01-19: Here's the prompt:

>Can you rough out a general set of SDD phases based on the different frameworks mentioned in sources

Based on the frameworks discussed in the sources—specifically GitHub Spec Kit, Augment Code, AWS Kiro, and Zencoder—a general Spec-Driven Development (SDD) workflow can be synthesized into four to five core phases. While terminology varies slightly by tool, the underlying architecture of the process remains consistent.  
Here is a rough outline of the general SDD phases:

### Phase 0: The Constitution (Context Establishment)

Before specific feature work begins, a foundational phase establishes the "immutable" rules and governing principles for the project.

* **Purpose:** To define non-negotiable standards regarding code quality, testing methodologies, user experience, and performance requirements 1, 2\.  
* **Action:** This involves creating a "Constitution" or rule set (e.g., constitution.md in GitHub Spec Kit or .cursorrules in Cursor) that acts as a prompt wrapper or "memory bank" to guide the AI agent's decisions across all subsequent phases 3, 4\.  
* **Key Frameworks:** GitHub Spec Kit explicitly uses the /constitution command for this phase 5, 6\.

### Phase 1: Specification (The "What" and "Why")

This phase captures the business intent and user needs without focusing on technical implementation details.

* **Purpose:** To define the user journey, success criteria, and functional requirements in natural language 7\. This serves as the "source of truth" regarding what is being built 8\.  
* **Action:** Developers provide a high-level description, and the AI agent generates a detailed specification document (often spec.md). This document is refined until it accurately reflects the user's goals 9, 10\.  
* **Key Frameworks:**  
* **GitHub Spec Kit:** Uses /specify to generate user stories and requirements 11, 10\.  
* **Augment Code:** Uses auggie /specify for system analysis and requirement documentation 12, 13\.  
* **Kiro:** Starts with a "Requirements" document focused on user stories and acceptance criteria 14\.

### Phase 2: Technical Planning (The "How")

Once the intent is frozen, this phase translates functional requirements into architectural decisions and a technical roadmap.

* **Purpose:** To select the technology stack, define data models, design APIs, and identify integration points with legacy systems 15, 7\. This phase ensures architectural integrity before code is written 16\.  
* **Action:** The AI agent analyzes the specification and generates a comprehensive technical plan (often plan.md or design.md). This allows developers to review architectural trade-offs and enforce constraints 17, 18\.  
* **Key Frameworks:**  
* **GitHub Spec Kit:** Uses /plan to outline frameworks, libraries, and infrastructure decisions 11, 10\.  
* **Augment Code:** Uses auggie /plan to generate migration or implementation strategies 19\.  
* **Kiro:** Generates a "Design" document covering technical details 14\.

### Phase 3: Task Decomposition (The "Steps")

The technical plan is broken down into atomic, manageable units of work that can be executed and tested in isolation.

* **Purpose:** To convert the high-level plan into a checklist of implementable items. This prevents the AI from attempting to generate massive, untestable code dumps 7\.  
* **Action:** The agent generates a task list (often tasks.md or tasks.json), usually prioritized by dependency (e.g., building database schemas before API endpoints) 20, 21\.  
* **Key Frameworks:**  
* **GitHub Spec Kit:** Uses /tasks to break the plan into "small, reviewable chunks" 7\.  
* **Augment Code:** Uses auggie /tasks to prepare for autonomous execution 22\.  
* **Zencoder:** Emphasizes breaking implementations into atomic, testable tasks like "Core Business Logic" or "Security Tasks" 23\.

### Phase 4: Implementation (The "Execution")

The AI agent executes the tasks defined in the previous phase to produce the actual codebase.

* **Purpose:** To generate code, tests, and documentation that adhere strictly to the specification and plan 24\.  
* **Action:** The agent works through the task list, often generating code in parallel or sequentially. The human developer's role shifts from writing code to reviewing focused changes and verifying them against the spec 25, 24\.  
* **Key Frameworks:**  
* **GitHub Spec Kit:** Uses /implement to execute the task list 5\.  
* **Augment Code:** Agents execute the plan across multiple repositories to complete entire features 22\.  
* **Kiro:** Moves methodically through the task breakdown to implement features one by one 26\.

### Phase 5: Continuous Validation (The "Loop")

While not always listed as a distinct "command" in every CLI, this phase is described as critical for maintenance and evolution.

* **Purpose:** To ensure the specification remains the "living" source of truth. If code changes are required during implementation, the specification must be updated first to prevent "spec drift" 27, 28\.  
* **Action:** Developers continuously validate the output against the spec and update the spec documents if reality necessitates a change in requirements 29\.  
* **Key Frameworks:** Zencoder and Isoform highlight this as the management of "living documentation" to ensure auditability and compliance 30, 31\.

