# Spec-Driven Development Overview

## why
- crisis of abundance
- getting to determinism
- paved path
    - path of least resistance
 
## key elements
- define the components
    - define constitution elements
    - define sdd steps
- devise test plan
- devise roll out plan
- devise operational plan

## Components

- spec-driven process
- constitution ('governance as code')
    - custom instructions
    - custom agents
    - custom prompts
 
## Operationalization
- how do we field test
    - constitution?
    - sdd steps?
- delivery/governance mechanism
    - github action style
    - surveyor chore
    - federated central repo
        - balance central standards with team autonomy

## spec-driven process
- what steps?
    - constitution
    - specify
    - clarify (from Spec Kit)
    - plan
    - tasks
    - analyze (from Spec Kit)
    - implement
- how formal or loose of a process?
- do we create our own or adopt existing?
    - [speckit.org](https://speckit.org/) 
    - [amazon kiro](https://kiro.dev/)
    - [fission-ai openspec](https://github.com/Fission-AI/OpenSpec)
    - [tessl](https://tessl.io/)
    - [nano-spec](https://github.com/tao-hpu/nano-spec)
      - [Medium articile by creator](https://generativeai.pub/nano-spec-the-sweet-spot-between-chaos-and-over-engineering-in-ai-assisted-development-0d0ccec202c0)
    - [awesome-copilot sdd workflow](https://github.com/github/awesome-copilot/blob/main/instructions/spec-driven-workflow-v1.instructions.md)
- if we create our own, do we do more than outline?
- how many variations should we consider?
- what type of process
    - spec-first
    - spec-anchored
    - spec-as-source
- what artifacts
    - do we recommend?
    - do we recommend preserving?
- what type of work?
    - green/brown
    - story/feature/epic

## custom instructions
- what types of instructions?
    - by language
    - by coding approach (e.g., TDD)
    - by framework
    - by quality
    - by security
- how do we ensure usage?
    - by teams and by copilot
 
## custom prompts
- what types of prompts?
    - reviews
        - architecture
        - security
        - language
      
## custom agents
- too soon?
