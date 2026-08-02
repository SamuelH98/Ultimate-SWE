# 8. Deployment / Release

## Objective

Ship validated work safely and reversibly, closing the loop from "code works" to "code is running where it needs to run."

---

## Key Activities

- Verify the build/production configuration (env vars, secrets, config files) is complete and doesn't rely on local-only defaults
- Run the full test suite in a clean environment, not just locally
- Confirm dependency versions are pinned/locked, not floating
- Write or update release notes (what changed, why, any migration steps)
- Define a rollback plan before releasing, not after something breaks
- Tag the release in Git with a meaningful version/tag

---

## Output

- Deployment checklist (completed)
- Release notes
- Rollback plan
- Git tag/release marker

---

## Rule

Do not deploy without a passing full test suite and a documented rollback plan. If there is no deployment target (e.g., a library, script, or internal tool with no release pipeline), state that explicitly and skip to Handoff rather than silently omitting this step.
