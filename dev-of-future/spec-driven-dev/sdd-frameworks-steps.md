# spec-driven development frameworks - stages

### GitHub Spec-Kit
- [site](https://github.com/github/spec-kit)
- good for new
- stages
	- **constitution**: governing principles, dev guidelines
	- **specify**: what and why to build
	- **plan**: tech stack and architecture choices
	- **tasks**: actionable task list
	- **implement**: task execution
---
### Spec Kit
- [site](https://speckit.org/)
- stages
	- foundation
		- **constitution**: governing principles and dev guidelines
		- **specify**: what you want to build
		- **clarify**: structured questioning
		- **plan**: technical implementation plan
	- implementation
		- **tasks**: implementation task list
		- **analyze**: cross-artifact consistency and coverage analysis
		- **implement**: task execution
---
### nano-spec
- [site](https://github.com/tao-hpu/nano-spec)
- stages
	- **README**: background, goals, scope
	- **todo**: checklist and acceptance criteria
	- **doc**: decisions, schemas, diagrams
	- **log**: daily notes, blockers, discovery
---
### awesome-copilot spec-driven workflow v1
- [site](https://github.com/github/awesome-copilot/blob/main/instructions/spec-driven-workflow-v1.instructions.md)
- stages
	- requirements
	- design
	- tasks
---
### Amazon Kiro
- [site](https://kiro.dev/)
- stages
    - Requirements: Define functional requirements and user stories, often using EARS notation (e.g., "WHEN [something happens] THE SYSTEM SHALL [do this specific thing]").
    - Design: Define the technical architecture and component interactions.
    - Implementation (Tasks): Generate a list of specific, actionable tasks to build the feature, which also serves to track progress.
---
### Tessl

Tessl emphasizes that the specification itself becomes the primary maintained artifact, with the code often being generated from it: spec-centric development.

- Spec-Assisted Development: Agents are provided with structured knowledge (coding standards, API docs).
- Spec-Driven Development: Critical definitions are captured as specifications; code changes require modifying the spec first, then applying the change.
- Spec-Centric Development: Comprehensive specs and tests make the code disposable and regeneratable, as the spec is the source.
---