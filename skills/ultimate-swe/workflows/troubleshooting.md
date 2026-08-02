# Troubleshooting & Escalation

## Objective

Break out of repeated-failure loops on hard problems instead of retrying near-identical fixes indefinitely.

---

## When to Use This

Enter this workflow the moment either is true:

- The **same problem** (test failure, bug, build error, design deadlock) has now failed **twice in a row**, even with different attempted fixes.
- A single problem has consumed noticeably more effort than its scope justified, with no forward progress.

Do not wait for a third attempt to trigger this — the second failure is the signal.

---

## Key Activities

1. **Stop and restate the problem.** Write down, in one or two sentences, exactly what is failing and what has already been tried. If this can't be stated precisely, that's usually why the last two fixes didn't land.
2. **Search the web before trying anything else.** Look up the exact error message, stack trace, or symptom. Check:
   - Official documentation for the library/API/language version in use
   - The project's issue tracker (GitHub issues, changelogs) for known bugs or breaking changes
   - Recent discussion (last-known-good version, migration notes) if the tech has changed since training data
   Do not rely on memorized/potentially stale knowledge once the same issue has survived one fix attempt.
3. **Question the layer above the code.** Two failed fixes at the implementation level often mean the bug isn't in the implementation:
   - Does this contradict something decided in Architecture? → revisit `architecture.md`
   - Is a requirement or acceptance criterion actually ambiguous or wrong? → revisit `requirements.md`
   - Is there a simpler design that avoids the failure mode entirely, rather than patching around it?
4. **Try one well-reasoned fix informed by the above** — not a blind variation of the first two attempts.
5. **If that also fails**, do not continue iterating. Stop and escalate (see below).

---

## Escalation (When Still Stuck)

- Log the blocker in `PROJECT_STATE.md` under **Troubleshooting Log**: what was tried, what was learned, what sources were checked, and current best hypothesis.
- Present the user with a short set of concrete options (e.g., "workaround X with tradeoff Y", "downgrade dependency", "change the requirement") rather than a vague "I'm stuck."
- Do not mark the related task complete or silently move on to unrelated work — an unresolved blocker stays visible until the user decides how to proceed.

---

## Output

- A precise problem statement
- Evidence gathered from current web sources (links/citations, not guesses)
- Either a resolution informed by that evidence, or a documented, escalated blocker with options

---

## Rule

Never attempt the same fix a third time. Two failures means the approach — not the effort — needs to change.
