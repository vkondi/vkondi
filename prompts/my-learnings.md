You are an experienced software engineer and technical reviewer.

Assume the reader is a senior engineer or technical recruiter.

Your task is to analyze this repository and either CREATE or UPDATE the file:
docs/MY_LEARNINGS.md

DOCUMENT INTENT (VERY IMPORTANT)
- This is a SUMMARY document, not a biography or project walkthrough
- The goal is to capture learnings that go *above and beyond common knowledge*
- If a learning would be obvious to an experienced developer, DO NOT include it
- Prefer “why this mattered” over “what was done”

EVERGREEN REQUIREMENT
- The document must remain evergreen
- Add a “Last Updated” field at the very top
- Update the date whenever the document changes
- Content must reflect the current state of the codebase, not its evolution

WHAT TO INCLUDE
- Non-obvious insights discovered during implementation
- Decisions that required trade-offs or course correction
- Patterns, constraints, or edge cases learned the hard way
- Lessons that would meaningfully transfer to another project

WHAT TO EXCLUDE
- Basic setup steps (e.g., project initialization, standard configs)
- Common best practices unless applied in a novel or non-trivial way
- Tool or library descriptions without a specific learning attached
- Historical changes, refactors, or timelines
- Personal storytelling or narrative explanations

QUALITY BAR (STRICT)
Before adding a point, ask:
- Would this teach something new to a senior engineer?
- Would I mention this in a technical interview?
- Is this insight clearly supported by the codebase?

CATEGORIES TO ANALYZE AND DOCUMENT
Include ONLY categories that have high-signal learnings:

1. Technical Learnings
   - Subtle framework behaviors or limitations
   - Advanced configurations or edge cases
   - Architectural implications discovered during development

2. Code Quality & Maintainability
   - Abstractions or patterns that reduced long-term complexity
   - Trade-offs made for readability vs flexibility
   - Decisions that improved or constrained future changes

3. Architecture & Design Decisions
   - Key design choices and the reasoning behind them
   - Alternatives considered and why they were rejected

4. Authentication / Authorization (if applicable)
   - Non-trivial security or session management considerations
   - Real-world constraints or failure modes handled

5. Performance, Scalability & Reliability (if applicable)
   - Bottlenecks encountered and how they were mitigated
   - Optimizations with measurable or practical impact

6. Business / Product Learnings (if applicable)
   - Payment, billing, or integration nuances
   - Edge cases driven by real usage or constraints

7. Tooling & Developer Experience
   - Workflow or automation improvements that saved time or reduced errors

8. What I’d Do Differently Next Time
   - High-impact improvements only
   - No generic “add more tests” or “refactor more”

OUTPUT FORMAT (STRICT)
- Clear section headings (##)
- Bullet points only (no paragraphs)
- One idea per bullet
- Short, precise language
- First-person voice (“I learned…”, “I realized…”)
- No filler, no marketing language

FINAL VALIDATION STEP
Before writing:
- Remove any point that could apply to most projects
- Remove anything not directly evident from the repository
