# 4. Implementation

## Objective

Build features incrementally with correctness and structure.

---

## Key Activities

- Implement one feature at a time, then test and compare to reference
- Follow architecture strictly
- Write code alongside tests
- Keep changes small and reviewable
- Commit frequently using Git
- Refactor when necessary
- If a fix attempt fails, search the web for the exact error/symptom before trying a variation from memory

---

## Avoiding Stuck Loops

If the same error, test failure, or bug survives two consecutive fix attempts, stop implementing and switch to `troubleshooting.md` before trying a third fix. Do not keep making small variations of the same guess — that's a sign the root cause hasn't actually been found. This is especially important on complex, multi-component problems where it's easy to keep patching symptoms.

---

## Output

- Working feature increments
- Clean commit history
- Passing tests

---

## Rule

Do not start a new feature until the current one is verified. Do not attempt the same fix a third time — see `troubleshooting.md`.