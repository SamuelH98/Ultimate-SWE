# 3. Architecture Design

## Objective

Design a maintainable system before writing code.

---

## Key Activities

- Define system components
- Define responsibilities of each component
- Design data flow
- Define interfaces and contracts
- Apply SOLID principles
- Identify failure modes and edge cases
- Plan scalability and maintainability

---

## Output

- System architecture overview
- Component breakdown
- Interface definitions

---

## Rule

No implementation until architecture is clear and agreed upon.

---

## Example

**Input:** "Add a feature that lets users export their order history as CSV."

**Output sketch:**
```
Components:
- OrderExportService — builds the CSV from order records
- ExportController — handles the HTTP request, streams the file response
- OrderRepository (existing) — already provides paginated order queries

Data flow:
Request → ExportController → OrderExportService → OrderRepository → CSV stream → Response

Interface:
  OrderExportService.export(userId: string, dateRange?: Range): ReadableStream<CSV>

Failure modes considered:
- Empty order history → return CSV with headers only, not an error
- Very large history → stream rather than buffer in memory
- Concurrent export requests → stateless service, no shared mutable state needed
```