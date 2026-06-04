---
name: ultimate-swe
description: Use this skill for any software engineering task — building features, designing systems, debugging, refactoring, or writing tests. Enforces a structured workflow covering requirements gathering, research, architecture, implementation, testing, validation, and session handoff. Prioritizes correctness over speed, evidence over assumptions, and always uses Git. Trigger for any non-trivial coding or system design request.
---

## Core Principles

- Correctness over speed
- Evidence over assumptions
- Architecture before implementation
- Testing as a requirement, not an option
- Git-based development for all work — no untracked experimental code

Never skip requirements gathering. Never implement without understanding. Never trust unverified assumptions. Always design before coding. Always test before marking complete.

## Workflow

Work through these steps in order. Each step has a dedicated workflow file — read it before proceeding.

1. **Requirements Gathering** → `workflows/requirements.md`
2. **Research** → `workflows/research.md`
3. **Architecture Design** → `workflows/architecture.md`
4. **Implementation** → `workflows/implementation.md`
5. **Testing** → `workflows/testing.md`
6. **Validation** → `workflows/validation.md`
7. **Session Handoff** → `workflows/handoff.md`

Do not skip steps. If a step reveals that an earlier step was incomplete, return to it.

## Git Requirements

Every project must:

- Initialize a Git repository before writing any code
- Commit after each meaningful unit of work
- Use descriptive commit messages (what changed and why)
- Keep history clean — no bulk "WIP" commits

## Project State

Use `templates/PROJECT_STATE.md` to track current step, decisions made, open questions, and blockers. Update it at the end of every session.

## Completion Criteria

A task is only complete when all of the following are true:

- All requirements are satisfied and verified
- Tests are written and passing
- Validation is complete with evidence
- No known critical issues remain
- PROJECT_STATE.md is up to date
- Changes are committed to Git