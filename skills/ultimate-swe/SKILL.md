---
name: ultimate-swe
description: "Use this skill whenever the user asks to build a feature, design or architect a system, implement a non-trivial piece of software, debug a multi-component issue, refactor more than a single file, or write production-quality code with tests. Make sure to trigger this for requests like \"build me an X\", \"add a Y feature\", \"design a system for Z\", \"refactor this module\", or \"write tests for this\" — even if the user doesn't explicitly ask for a \"workflow\" or \"process\". Enforces a structured, disciplined workflow covering requirements gathering, research, architecture, implementation, testing, validation, and session handoff. Prioritizes correctness over speed, evidence over assumptions, and Git-based development. Do NOT use for single-line fixes, isolated typo/bug patches, config tweaks, or simple one-step refactors confined to one file — see \"Scope Check\" below for the gray zone."
compatibility: Requires shell/file-system access and Git for version control. Not suited to read-only or chat-only contexts where code cannot actually be written or committed.
---

## Scope Check (read this first)

Before starting the full workflow, classify the task:

- **Trivial** (single-line fix, typo, config value, isolated one-file patch): skip this skill entirely — just make the change.
- **Small but multi-file** (e.g., a bug fix touching 2-4 files, a small refactor with no new architecture): run a *lightweight* pass — confirm the fix with the user if ambiguous, write/update tests for the change, commit with a clear message. Skip Architecture and Handoff unless the change reveals a design problem.
- **Non-trivial** (new feature, new system, multi-step design decision, anything where "how should this work" isn't obvious): run the full workflow below, in order.

When in doubt, ask the user, or default to the lightweight pass — the goal is rigor proportional to risk, not ceremony for its own sake.

## Core Principles

- Correctness over speed
- Evidence over assumptions
- Architecture before implementation
- Testing as a requirement, not an option
- Git-based development for all work — no untracked experimental code
- Search before guessing — verify against current, live sources rather than memory alone
- Two failed attempts at the same problem is a signal to stop and change approach, not a reason to try a third guess

Never skip requirements gathering. Never implement without understanding. Never trust unverified assumptions. Always design before coding. Always test before marking complete. Never repeat the same failing approach a third time — see the Escalation Protocol below.

## Workflow

Work through these steps in order. Each step has a dedicated workflow file — read it before proceeding.

1. **Requirements Gathering** → `workflows/requirements.md`
2. **Research** → `workflows/research.md`
3. **Architecture Design** → `workflows/architecture.md`
4. **Implementation** → for each new feature:
   - 🔄 **Re-run Research** → `workflows/research.md` *(skip only if the feature uses solely already-researched tech; any new library, API, or unfamiliar error goes back through Research first)*
   - Then proceed → `workflows/implementation.md`
   - 🚧 **Stuck on the same problem twice?** → stop implementing and follow `workflows/troubleshooting.md` before attempting a third fix
5. **Testing** → `workflows/testing.md`
6. **Code Review** → review for readability, SOLID adherence, and edge cases before merging
7. **Validation** → `workflows/validation.md`
8. **Deployment / Release** → `workflows/deployment.md`
9. **Session Handoff** → `workflows/handoff.md`

Do not skip steps. If a step reveals that an earlier step was incomplete, return to it.
If research invalidates the architecture, return to step 3. If requirements change mid-implementation, return to step 1.
If implementation gets stuck in a repeated failure loop, do not keep iterating silently — return to step 2 (Research) or step 3 (Architecture) via `workflows/troubleshooting.md`, or escalate to the user.

## Escalation Protocol (Avoiding Loops)

Complex problems can trigger repeated, near-identical fix attempts that burn effort without progress. Treat this as a hard circuit breaker, not a suggestion:

- **1st failure** on a given problem: fix it directly if the cause is clear.
- **2nd consecutive failure on the same problem**: stop. Do not try a third variation from memory. Switch to `workflows/troubleshooting.md` — search the web for the exact error/symptom, re-check assumptions, and consider that the design (not the code) may be wrong.
- **Still unresolved after following troubleshooting.md**: do not keep looping. Document the blocker in `PROJECT_STATE.md` (Troubleshooting Log) with what was tried and why it failed, then present the user with concrete options rather than continuing to iterate silently.

This applies at every phase — a stuck architecture decision, a flaky test, or a recurring bug all qualify.

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