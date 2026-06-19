# 5. Testing

## Objective

Ensure correctness through comprehensive testing.

---

## Testing Types

### Unit Tests
- Validate individual functions/components

### Integration Tests
- Validate interaction between components

### Black Box Tests
- Validate user-facing behavior

### White Box Tests
- Validate internal logic and branches

### Edge Case Tests
- Invalid inputs
- Boundary conditions
- Failure scenarios

---

## How Much Is Enough

Scale coverage to risk and complexity, not to a fixed percentage:

- **Pure functions / business logic** — unit tests covering happy path, at least one edge case, and one failure case.
- **Component interactions** — integration tests covering each non-trivial interface.
- **User-facing behavior** — at least one black-box test per acceptance criterion from `requirements.md`.
- **High-risk code** (auth, payments, data integrity, anything hard to reverse) — exhaustive edge-case coverage; do not ship without it.
- **Low-risk glue code** (simple wiring, trivial getters) — a smoke test is enough; don't pad coverage numbers with low-value tests.

If unsure whether a case needs a dedicated test, ask: "what breaks silently if this is wrong?" If the answer is concerning, write the test.

---

## Output

- Test suite
- Coverage reports (when applicable)
- Verified behavior

---

## Rule

No feature is complete without tests.