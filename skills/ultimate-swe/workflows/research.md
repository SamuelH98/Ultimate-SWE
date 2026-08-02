# 2. Research

## Objective

Understand technologies, tools, and domain context before making decisions.

---

## Key Activities

- Search the web to learn tools, APIs, and find reference examples (e.g. curl examples)
- Review official documentation
- Study APIs and frameworks
- Compare libraries and tools
- Analyze existing systems
- Review examples and best practices
- Identify risks and unknowns

---

## Web Search Is Mandatory, Not Optional, When:

- Working with any library, framework, or API not already verified in this session
- A library's or platform's version, defaults, or behavior could have changed since training data — check current docs rather than assuming
- An error or stack trace doesn't have an obvious cause from the code alone
- Making a claim ("this API works like X", "this library supports Y") that could be checked instead of assumed
- Comparing tools/libraries — pull current adoption, maintenance status, and known issues rather than relying on reputation from memory

If a web search tool is available, use it rather than answering from memory whenever any of the above applies. Memory is a starting hypothesis, not a source.

---

## Re-Entering Research Mid-Project

Research isn't a one-time phase. Return to it immediately — not just when starting a new feature — whenever implementation surfaces a genuine unknown: an undocumented behavior, an error whose cause isn't clear within one attempt, or a claim that can't be verified from memory. If the same problem has already failed twice, that's a `troubleshooting.md` situation, not a plain research one.

---

## Output

- Research summary, with sources noted for any non-trivial claim
- Technology recommendations
- Known constraints and risks

---

## Rule

Do not design, implement, or debug from memory alone when current, verifiable information is one search away.